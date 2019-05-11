---
title: 自定义 BAM 门户配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4749ada0c4e85252403a10dbe88d0f7ea2191a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353168"
---
# <a name="customizing-the-bam-portal-configuration"></a>自定义 BAM 门户配置
有许多在 BAM 门户网站上的可配置选项。 以下过程介绍如何修改 BAM 门户，以获取最佳用户体验。  

> [!NOTE]
>  当以非管理员身份配置门户模拟用户时，它可能有必要，以便先注销，然后再登录后才可以访问 BAM 门户功能而无需输入凭据。 例如，考虑以下方案：  
>   
>  使用非管理员模拟用户配置的 Web 服务或 BAM 门户。 Everyone 组不具有对门户的访问，在门户上然后设置了权限。 然后创建名为 PortalUsersGroup 的本地组并将该组作为 Portal Users 组。 这意味着只有该组中的用户有权访问门户。 配置 BAM 门户后，将当前用户添加到 Portal Users 组。 当您打开 BAM 门户时，你将要求输入凭据。 注销并重新登录，但是，你能够打开 BAM 门户，而不要求提供凭据。  
>   
>  BizTalk Server 支持只在单台计算机配置中的本地组和用户帐户。 BizTalk Server 支持单个和多计算机配置中的域组和用户帐户。  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a>在 64 位环境下运行 BAM 门户  
 如果在 64 位环境中使用 Internet 信息服务 (IIS)，则必须将 IIS 设置为 32 位模式运行 BAM 门户。 

> [!IMPORTANT]
>  您不必将 IIS7 设置为 32 位模式。  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a>若要设置为 32 位模式下的 64 位模式下的 IIS 安装  

1.  打开命令提示符并运行**adsutil**命令。 若要执行此操作，请单击**启动**，单击**运行**，然后键入**cmd**。  

2.  在命令提示符下键入以下内容： `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`。  

3.  关闭命令提示符。  

## <a name="configuring-the-bam-portal-banner"></a>配置 BAM 门户横幅  
 可以修改 BAM 门户页以显示类似文本和有关您业务的图形：  

- Windows Server System 徽标，它位于 BAM 门户页的右上角。  

  在下面的过程中，您将编辑级联样式表文件 （.css 文件） 以自定义 BAM 门户的外观。 对指定类的修改均受支持的唯一修改。 尽可能多地，对类进行修改的影响已被隔离，以便在修改过程中发生的错误则 BAM 门户仍处于工作状态。  

> [!CAUTION]
>  修改 styles.css 文件中的其他类将隐藏数据和门户功能，并且可能会使门户不可用。  

#### <a name="to-configure-the-banner"></a>若要配置横幅  

1. 编辑 BAM 门户 web.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。  

2. 主页快速入门内容是可替换通过修改以下行：\<添加键 ="MainPageContentUrl"value="~/MainPageContent.htm"/\>。 更改**MainPageContent.htm**值字段，使其指向您自己的 HTML 文件中。 HTML 文件必须在 web.config 文件所在的同一目录中。  

3. 可以更改页标识文本通过将以下行添加到 web.config 文件：\<添加键 ="PortalTitle"value ="新标识 text"/\>。 更改值字段，以包含标识门户的文本。  

4. 编辑 BAM 门户 styles.css 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css，并单击**确定**。  

5. 通过找到.headerLogo div 类并将以下行更改中右上角的徽标： 背景图像： url("../ images/WSS_Logo.gif");使其指向已创建的图像文件。 我们建议您使用.gif 格式的图像。  

6. 更改 SharePoint 图标，请找到.headerPageIcon div 类并将以下行： 背景图像： url("../ images/btsSuiteProduction.gif");使其指向已创建的图像文件。  

7. 保存该文件。  

8. 打开 BAM 门户以查看所做的更改。  

## <a name="modifying-the-bam-portal-webconfig-file"></a>修改 BAM 门户 web.config 文件  
 如果 BAM 门户驻留在使用安全套接字层 (SSL) 的企业单一登录 (SSO) 证书的服务器上，你必须配置门户以接受该证书的正确 URL。  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a>若要修改 BAM 门户为支持 SSL 站点  

1. 打开使用记事本的 web.config 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。  

2. 修改文件以指向已启用 SSL 的门户的位置中的以下两行：  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. 保存该文件。  

   BAM 门户显示并接受数据根据其配置为其的区域性设置格式。 在 web.config 文件中指定配置。 Web 门户将忽略发送的 Internet Explorer 的"接受语言"信息。 例如，假设您正在运行 Internet Explorer 设置为日语区域性设置和 BAM 门户配置为使用美国英语区域性设置。 在这种情况下数据的项，如日期和整数，则会显示，接受，并使用适用于美国规则排序英语区域性设置而不是适用于日语区域性设置的规则。 任何使用日语格式输入的特定于区域性的信息将被视为无效的 BAM 门户因为它只接受采用格式美国的数据（美国）。  

   若要获取一致的处理方式的显示和格式设置是根据区域性设置的变量的数据，请选择一种语言，适用于所有 BAM 门户客户端。 配置 BAM 门户为此区域性。 您必须确保每个客户端安装多语言用户界面包设置为所选区域性。  

   非美国的英语安装 BAM 它可能需要在 web.config 文件中设置的区域性参数。 您可能需要执行此操作的情况是：  

-   要本地化的日期和时间显示格式。  

-   要本地化货币的显示格式。  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a>若要修改在门户的区域性设置  

1. 打开使用记事本的 web.config 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。  

2. 修改以下行中的文件以反映相应的全球化设置区域性属性：  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. 保存该文件。  

   在您等待大量 SQL 查询时遇到超时的情况下，可能需要增大查询服务超时值。  

#### <a name="to-increase-the-query-service-time-out-value"></a>若要增大查询服务超时值  

1. 打开使用记事本的 web.config 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。  

2. Queryservicetimeout 的默认值为 45 秒。 修改以下行，以增加或减小超时时间间隔中的值：  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. 保存该文件。  

   多服务器环境中可能有一台服务器处于脱机状态时的时间。 在此情况下，在门户的用户可能会在 BAM 门户停止响应的时间延迟。 若要改善用户体验可以修改服务器重试时间间隔。 这将创建在此期间，将假定服务器处于脱机状态之后连接失败一次, BAM 查询 Web 服务的最小时间。  

   值指示是否本地数据库超时尝试联系远程数据库时，将数据标记为不完整和本地计算机不会尝试连接到远程数据库，直到指定的时间已过。  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a>若要增加多服务器环境中的分布式活动的重试间隔  

1. 打开使用记事本的 web.config 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config，并单击**确定**。  

2. Serverretryinterval 的默认值为 5 分钟。 修改以下行以增大或减小服务器重试时间间隔中的值：  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. 保存该文件。  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a>若要配置如何警报通知选项将显示在 BAM 门户  

1. 打开使用记事本的 web.config 文件。 单击**启动**，单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，然后再单击**确定**。  

2. 修改中的值字段\<添加键 ="AlertNotificationOptions"value =""/\>的 web.config 文件中使用以逗号分隔的列表指定有效的通知选项具有下列值之一的行。 空值由服务器返回的顺序在服务器上显示所有可用的通知选项。 无法识别的任何值等同于空值。  


   |    ReplTest1    |                                              Description                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | 文件中，电子邮件 | 将显示文件和电子邮件选项。 在下拉列表中，文件首先显示，然后发送电子邮件。 |
   | 电子邮件、 文件 | 将显示文件和电子邮件选项。 在下拉列表中，电子邮件首先显示，然后将文件。 |
   |    文件     |                             仅文件通知显示在门户中。                             |
   |    电子邮件    |                            在门户中显示仅电子邮件通知。                            |


3. 保存该文件。  

## <a name="distributed-server-environments"></a>分布式的服务器环境  
 如果您安装的 BAM 门户将警报和 BAM 门户置于不同的服务器上，您将看到事件日志中的以下错误："System.Reflection.TargetInvocationException:调用的目标已引发异常。 ---> 找不到指定的 Notification Services 实例的项的注册表。"  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a>若要配置不同的服务器上的门户和警报  

1. 打开命令提示符。  

2. 运行**C:\Program Files\Microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register-name bamalerts-server**<em>\<服务器名称\></em>替换*\<服务器名称\>* 与服务器的名称。  

3. 按 F5 刷新浏览器。  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a>将 IIS 配置为允许 BAM 门户使用 Kerberos 网络协议  
 如果你想要使用 BAM 门户使用 Kerberos 网络协议必须修改 Web 门户的 ACL 安全性。 如果 IIS 配置不正确，用户将收到以下错误：  

 HTTP 错误 401.1-未经授权：由于凭据无效，访问被拒绝。  

 有关修改 IIS 安全设置的其他信息，请参阅知识库文章，网址[ http://go.microsoft.com/fwlink/?LinkId=57922 ](http://go.microsoft.com/fwlink/?LinkId=57922)。  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a>在 SQL Server 2008 部署 BAM 门户中查看聚合 BAM 数据  
 若要从部署环境中使用 SQL Server 2008 时连接到 BAM 门户的客户端计算机在 BAM 门户中查看聚合数据，必须在客户端计算机上安装 Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB 访问接口。 如果未安装的 analysis services 的用户将收到以下错误消息：  

 在服务器*\<servername\>* 太忙或无法联系。  



## <a name="see-also"></a>请参阅  
 [规划 BAM 门户](../core/planning-for-the-bam-portal.md)