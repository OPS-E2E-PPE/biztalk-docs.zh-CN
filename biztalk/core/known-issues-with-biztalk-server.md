---
title: 使用 BizTalk Server 的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1aa5fb60-e8db-4cd2-88be-3c71b7b1d44d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f933555f4643fb293d6fad882950eaf2f15ac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330570"
---
# <a name="known-issues-with-biztalk-server"></a>BizTalk Server 的已知的问题
本主题列出了一些已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="dtc-firewall-rules"></a>DTC 防火墙规则  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]安装在不同计算机，分布式事务处理协调器 (MS DTC) 句柄的计算机之间的事务。 因此，在上启用防火墙规则中的 DTC 端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，未在防火墙中启用 DTC 端口时，可能出现以下错误：  
  
 **创建数据库; 时发生 WMI 错误尝试回滚并删除部分创建的 database 'SQLServerName\BizTalkMsgBoxDb'**  
  
 **生成 WMI 错误说明：引发 'system.enterpriseservices.transactionproxyexception ' 类型的异常。**  
  
 以下链接提供的详细信息：  
  
 [用于管理服务器的端口](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [BizTalk Server 2013 和 2013 R2 的安装后步骤](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a> 业务活动监视  
 本部分列出了业务活动监视 (BAM) 模块的已知的问题。  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a>由于 SQL 登录错误而失败的 BAM 定义部署  
 同时部署 BAM 定义，该操作可能会由于登录错误，错误代码为 42000 失败。  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 若要解决此问题，请确保 SQL Analysis Service 登录帐户与 BAM 相关的所有数据库上具有权限。  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a>BAM 配置可能会导致与 BAM Analysis 登录帐户相关的警告  
 BAM 配置将与要能够对其进行访问的 BAM 相关的所有数据库中添加 BAM Analysis 登录帐户的权限。 但是，配置可能无法执行此操作并提供一条警告，如果不满足任何以下先决条件：  
  
- 用户在其下运行 BAM 配置应是安装分析服务的计算机上的管理员。  
  
- 必须在该计算机上允许通过防火墙的远程管理。  
  
- 如果 BAM Analysis 登录帐户是安装与 BAM 相关数据库的 SQL 服务器的管理员，也会收到一条警告。 可以忽略该警告并继续。  
  
  **解决方法**– 必须与 BAM 相关的所有数据库上手动添加为 BAM Analysis 登录帐户的权限。  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a>BAM 门户兼容性和 Internet Explorer 10  
 若要使用 Internet Explorer 10 的 BAM 门户，必须始终在兼容模式下使用浏览器。  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a>接收通知电子邮件，即使在警报主机服务已停止  
 如果您使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，如果你想要使用 BAM 警报，则必须在 SQL Server 配置数据库邮件功能。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用警报主机服务与数据库邮件功能结合使用来发送通知警报。 警报主机服务，在处理通知之后, 将传递通知工作负荷到 SQL Server 中的数据库邮件组件。 因此，即使停止警报主机服务，你可能仍会通过警报主机服务但不能通过数据库邮件组件已处理的事件的几个通知。  
  
### <a name="configuring-tracing-for-bam-alerts"></a>为 BAM 警报配置跟踪  
 如果使用的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，和你想要为 BAM 警报启用诊断跟踪，必须通过为 BAM 警报主机创建配置文件进行操作。 必须为文件命名**BAMAlerts.exe.config**并将其复制到与 EXE 相同的位置 (**BAMAlerts.exe**)，即 \Program Files\Microsoft BizTalk Server\Tracking\\。  
  
 示例配置文件看起来如下所示。 此文件记录了**信息**级别事件查看器的详细信息。  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a> 与 SQL Server 2012 中使用 BizTalk Server 时的问题  
 使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]可以设置**远程登录超时值**SQL Server 中为 20 秒的值。 如果不这样做，可能会遇到在高负荷环境中的错误。 有关如何设置远程登录超时值的说明[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，请参阅 [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)  
  
##  <a name="BKMK_Adapters"></a> 适配器的问题  
 本部分列出了的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a>动态端口可能发生故障时使用 Windows SharePoint Services (WSS) 适配器  
 使用 WSS 适配器的动态端口可能会失败并出现以下错误：  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 **解决方法**:  
  
-   在端口配置中，对于站点 URL，包括端口号。 例如，`http://server:80/site`。  
  
-   启用**Windows Identity Foundation 3.5**功能。  
  
-   确认运行 BizTalk 主机的帐户有权访问 SharePoint。  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a>不能仅安装 BizTalk Server 管理组件的计算机上管理中提供的 BizTalk 适配器包适配器  
 如果必须仅有的计算机上安装的 BizTalk 适配器包[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装管理控制台中，BizTalk 适配器包的一部分安装的适配器不可用时创建的发送端口或接收位置。 这是因为这些适配器在同一台计算机上安装 BizTalk 运行时具有的依赖项。  
  
 解决方法 – 安装适配器包和安装了 BizTalk Server 管理组件的计算机上的 BizTalk Server 运行时。 不需要在该计算机上配置 BizTalk Server。  
  
## <a name="other-issues"></a>其他问题  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a>Setup.bat 为 BizTalk Server 示例使用 32 位命令提示符下运行  
 有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]附带此版本的示例，你必须只从 32 位命令提示符下运行附带的 setup.bat 文件。 在 64 位命令提示符下运行批处理文件可能会导致失败。  
  
### <a name="run-setup-as-administrator"></a>以管理员身份运行安装程序  
 安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，使用**以管理员身份运行**选项。 否则，可能会出现以下错误：  
  
 内部错误 2761年。 返回代码：1  
  
 MSI 安装返回了 1603-安装时发生严重错误。  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a>将证书用于 1024年密钥进行编码和签名会导致 MIME-SMIME 解码失败  
 在 Windows 8 中，一条消息使用加密和签名证书用于 1024年密钥时 MIME-SMIME 解码在验证消息失败。 若要避免此问题，您可以使用包含 2048年密钥证书。  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a>UDDI 解析程序与 ESB 工具包提供序列化错误  
 使用与 UDDI 时[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]查找绑定详细信息时，可能会遇到 XML 序列化错误。 如果未指定的绑定键，将发生此错误。  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a>ESB 工具包的路线设计器  
 路线设计器[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]是现已成为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装介质。 您可以找到路线设计器中的媒体的根文件夹并具有名称`Microsoft.Practices.Services.Itinerary.DslPackage.vsix`。 更早版本，此文件时可用的安装的位置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]，这通常是 \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
### <a name="edi"></a>EDI  
 正在使用 EDI 批处理。 使用阿拉伯语日历或阿拉伯语本地设置时，业务流程挂起，并出现以下错误：  
  
 **错误代码：0xC0C01B52 （业务流程引擎错误） 错误描述：持久性失败由于冻结期间挂起。** 阿拉伯语格里支持从*04/30/1900 00.00.00*到*05/13/2029年 23:59:59*。  
  
 若要解决此问题，请输入有效的阿拉伯语结束日期。  
  
### <a name="enterprise-single-sign-on"></a>企业单一登录  
 安装企业单一登录 (ESSO) 时或当您重新启动 ESSO 服务时可能会看到以下错误记录在事件查看器。  
  
 **未能加载 \Program Files\Common Files\Enterprise 单一 sign-on\ssopsserver.dll 错误代码：0x8007007E，找不到指定的模块。** 您可以放心地忽略此错误。