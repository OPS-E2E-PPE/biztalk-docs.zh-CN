---
title: "自定义 BAM 门户配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd99c0746c09f88d71e3a44e625ae5c52458f2f3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="customizing-the-bam-portal-configuration"></a>自定义 BAM 门户配置
BAM 门户有多个可配置选项。 下面的过程演示如何修改 BAM 门户，以获取最佳用户体验。  
  
> [!NOTE]
>  以非管理员模拟用户身份配置门户时，你很有必要注销然后再登录，以便能够访问 BAM 门户功能而无需输入凭据。 例如，请考虑以下情况：  
>   
>  你可以配置 Web 服务或 BAM 门户与非管理员模拟用户。 然后设置对门户的权限，例如 Everyone 组没有门户的访问权限。 然后创建名为 PortalUsersGroup 的本地组，并将该组指定为 Portal Users 组。 这意味着只有该组中的用户可以访问门户。 对 BAM 门户进行配置后，将当前用户添加到 Portal Users 组。 打开 BAM 门户时，将要求您提供凭据。 如果您注销然后再登录，则可以在不要求提供凭据的情况下打开 BAM 门户。  
>   
>  BizTalk Server 只有在单计算机配置中才支持本地组和本地用户帐户。 BizTalk Server 在单计算机配置和多计算机配置中都支持域组和域用户帐户。  
  
## <a name="running-the-bam-portal-in-a-64-bit-environment"></a>在 64 位环境下运行 BAM 门户  
 如果在 64 位环境中使用 Internet 信息服务 (IIS)，你必须设置为 32 位模式下运行 BAM 门户的 IIS。 
  
> [!IMPORTANT]
>  不必将 IIS7 设置为 32 位模式。  
  
#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a>将安装的 64 位模式 IIS 设置为 32 位模式  
  
1.  打开命令提示符并运行**adsutil**命令。 若要执行此操作，请单击**启动**，单击**运行**，然后键入**cmd**。  
  
2.  在命令提示符下键入以下内容： `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`。  
  
3.  关闭命令提示符。  
  
## <a name="configuring-the-bam-portal-banner"></a>配置 BAM 门户横幅  
 可以修改 BAM 门户页以显示类似如下的、有关您业务的文本和图形：  
  
-   Windows Server System 徽标，它位于 BAM 门户页的右上角。  
  
 在以下过程中，您将编辑级联样式表文件（.css 文件）来自定义 BAM 门户的外观。 只支持对指定类的修改。 系统已尽可能孤立对类所做修改的影响，这样如果修改过程中出现错误，则 BAM 门户仍处于工作状态。  
  
> [!CAUTION]
>  在 styles.css 文件中修改其他类将隐藏数据和门户功能，并可能使门户无法使用。  
  
#### <a name="to-configure-the-banner"></a>配置横幅  
  
1.  编辑 BAM 门户 web.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2.  主页快速入门内容是可替换的通过修改以下行：\<添加键 ="MainPageContentUrl"value="~/MainPageContent.htm"/\>。 更改**MainPageContent.htm**值字段，使其指向你自己的 HTML 文件中。 该 HTML 文件必须位于 web.config 文件所在的目录中。  
  
3.  更改标识通过将以下行添加到 web.config 文件的文本页：\<添加键 ="PortalTitle"value ="新标识 text"/\>。 将值字段更改为包含标识门户的文本。  
  
4.  编辑 BAM 门户 styles.css 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css，，然后单击**确定**。  
  
5.  通过查找.headerLogo div 类并更改以下行来更改右上角的徽标： 背景图像： url("../ images/WSS_Logo.gif");使其指向已创建的映像文件。 建议您使用 .gif 格式的图像。  
  
6.  通过查找.headerPageIcon div 类并更改以下行来更改显示 SharePoint 图标： 背景图像： url("../ images/btsSuiteProduction.gif");使其指向已创建的映像文件。  
  
7.  保存该文件。  
  
8.  打开 BAM 门户查看您所做的更改。  
  
## <a name="modifying-the-bam-portal-webconfig-file"></a>修改 BAM 门户 web.config 文件  
 如果 BAM 门户驻留在将企业单一登录 (SSO) 证书用于安全套接字层 (SSL) 的服务器上，则必须将该门户配置为接受证书的正确 URL。  
  
#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a>将 BAM 门户修改为支持 SSL 站点  
  
1.  使用记事本打开 web.config 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2.  将文件中的以下两行修改为指向启用了 SSL 的门户的位置：  
  
    ```  
    <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
    <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
    ```  
  
3.  保存该文件。  
  
 BAM 门户显示并接受符合已为数据配置的区域性的数据格式。 该配置在 web.config 文件中指定。 Web 门户将忽略 Internet Explorer 发送的“接受语言”信息。 例如，假设您正在运行 Internet Explorer 这设置为日语区域性设置并已配置 BAM 门户以使用美国英语区域性设置。 在这种情况下数据项，如将显示日期和整数，，接受，并使用适用于美国规则排序英语区域性设置而不是适用于日语区域性设置的规则。 输入使用日语格式设置的任何特定于区域性的信息将被视为无效 BAM 门户因为应适用于美国格式数据美国英语的默认值。  
  
 若要基于区域性设置对数据的可变显示和格式设置进行一致性处理，请选择适用于所有 BAM 门户客户端的语言。 为此区域性 BAM 门户进行配置。 必须安装多语言用户界面包以确保将每个客户端设置为所选区域性。  
  
 适用于非美国BAM 的英语安装它可能有必要在 web.config 文件中设置的区域性参数。 需要设置区域性参数的情况包括：  
  
-   要本地化日期和时间的显示格式。  
  
-   要本地化货币的显示格式。  
  
#### <a name="to-modify-the-culture-setting-of-the-portal"></a>修改门户的区域性设置  
  
1.  使用记事本打开 web.config 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2.  修改文件以反映相应的全球化设置中的以下行中的区域性属性：  
  
    ```  
    <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
    ```  
  
3.  保存该文件。  
  
 在因等待大量 SQL 查询而超时的情况下，需要增大查询服务超时值。  
  
#### <a name="to-increase-the-query-service-time-out-value"></a>若要增加查询服务超时值  
  
1.  使用记事本打开 web.config 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，，然后单击**确定**。  
  
2.  QueryServiceTimeout 的默认值为 45 秒。 修改以下行中的值以增大或减小超时时间间隔：  
  
    ```  
    <add key="QueryServiceTimeout" value="45" />  
    ```  
  
3.  保存该文件。  
  
 在多服务器环境下，有时候某一服务器会脱机。 发生这种情况时，门户用户可能会因 BAM 门户停止响应而受到延迟。 若要改善用户的延迟体验，可以修改服务器重试时间间隔。 这将设置一段最短时间，在这段时间内如果连接失败，则 BAM 查询 Web Services 假定服务器为脱机。  
  
 如果本地数据库超时尝试联系远程数据库时，数据将被标记为不完整和本地计算机将不会尝试连接到远程数据库，直到经过了指定的时间之后，将指示的值。  
  
#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a>增大多服务器环境下发布式活动的重试时间间隔  
  
1.  使用记事本打开 web.config 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，，然后单击**确定**。  
  
2.  ServerRetryInterval 的默认值为五分钟。 修改以下行中的值以增大或减小服务器重试时间间隔：  
  
    ```  
    <add key="ServerRetryInterval" value="5"/>  
    ```  
  
3.  保存该文件。  
  
#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a>配置如何在 BAM 门户中显示警报通知选项  
  
1.  使用记事本打开 web.config 文件。 单击**启动**，单击**运行**，类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2.  修改中的值字段\<添加键 ="AlertNotificationOptions"value =""/\>行包含指定有效的通知选项具有下列值之一以逗号分隔列表的 web.config 文件。 空值将以服务器返回的顺序显示服务器上可用的所有通知选项。 任何不可识别的值等效于空值。  
  
    |值|Description|  
    |-----------|-----------------|  
    |File, Email|显示文件选项和电子邮件选项。 在下拉列表中，先显示文件再显示电子邮件。|  
    |Email, File|显示文件选项和电子邮件选项。 在下拉列表中，先显示电子邮件再显示文件。|  
    |文件|在门户中仅显示文件通知。|  
    |电子邮件|在门户中仅显示电子邮件通知。|  
  
3.  保存该文件。  
  
## <a name="distributed-server-environments"></a>分布式服务器环境  
 如果你安装 BAM 门户放在不同服务器上警报和 BAM 门户，你将看到事件日志中的以下错误:"System.Reflection.TargetInvocationException： 目标的调用引发异常。 ---> 找不到项通知服务的指定实例的注册表。"  
  
#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a>配置位于不同服务器上的门户和警报  
  
1.  打开命令提示符。  
  
2.  运行**C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register-name bamalerts-服务器***\<服务器名称\>*替换*\<服务器名称\>*与服务器的名称。  
  
3.  按下 F5 键来刷新浏览器。  
  
## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a>将 IIS 配置为允许 BAM 门户使用 Kerberos 网络协议  
 如果要在 BAM 门户中使用 Kerberos 网络协议，必须修改 Web 门户站点的 ACL 安全性。 如果 IIS 配置不正确，用户将收到以下错误：  
  
 HTTP 错误 401.1-未授权： 由于凭据无效而被拒绝访问。  
  
 有关 IIS 安全设置修改的其他信息，请参阅知识库文章， [http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)。  
  
## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a>在 SQL Server 2008 部署 BAM 门户查看聚合 BAM 数据  
 若要在从客户端计算机连接到 BAM 门户，在部署环境使用 SQL Server 2008 时 BAM 门户中查看聚合数据，必须在客户端计算机上安装 Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB 提供程序。 如果未安装分析服务，用户将会收到以下错误消息：  
  
 服务器 *\<servername\>* 无法连接或太忙。  
  

  
## <a name="see-also"></a>另请参阅  
 [规划 BAM 门户](../core/planning-for-the-bam-portal.md)