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
ms.openlocfilehash: 3ab3522254ea7cd965ed1b9172de2c382d214fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014454"
---
# <a name="known-issues-with-biztalk-server"></a>BizTalk Server 的已知问题
本主题列出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一些已知问题。  
  
## <a name="dtc-firewall-rules"></a>DTC 防火墙规则  
 在单独的计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 时，分布式事务协调器 (MS DTC) 处理计算机之间的事务。 因此，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的防火墙规则中启用 DTC 端口。  
  
 配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，如果未在防火墙中启用 DTC 端口，可能会发生以下错误：  
  
 **创建数据库; 时发生 WMI 错误尝试回滚并删除部分创建的 database 'SQLServerName\BizTalkMsgBoxDb'**  
  
 **生成 WMI 错误说明： 引发 'system.enterpriseservices.transactionproxyexception ' 类型的异常。**  
  
 以下链接提供了详细信息：  
  
 [用于管理服务器的端口](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [BizTalk Server 2013 和 2013 R2 的安装后步骤](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a> 业务活动监视  
 本部分列出了业务活动监视 (BAM) 模块的已知问题。  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a>由于 SQL 登录错误而导致 BAM 定义部署失败  
 部署 BAM 定义时，该操作可能会由于登录错误（错误代码为 42000）而失败。  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 若要解决此问题，请确保 SQL Analysis Service 登录帐户在与 BAM 相关的所有数据库上都有权限。  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a>BAM 配置可能会导致与 BAM Analysis 登录帐户相关的警告  
 BAM 配置将与要能够对其进行访问的 BAM 相关的所有数据库中添加 BAM Analysis 登录帐户的权限。 但是，如果未满足以下任一先决条件，该配置可能无法访问这些数据库，并且会显示一条警告：  
  
- 运行该 BAM 配置的用户应是安装了 Analysis Service 的计算机上的管理员。  
  
- 在该计算机上必须允许通过防火墙进行远程管理。  
  
- 如果 BAM Analysis 登录帐户是安装了 BAM 相关数据库的 SQL Server 的管理员，那么同样可能会向你显示警告。 你可以忽略该警告并继续操作。  
  
  **解决方法**– 必须与 BAM 相关的所有数据库上手动添加为 BAM Analysis 登录帐户的权限。  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a>与 Internet Explorer 10 的 BAM 门户兼容性  
 若要将 BAM 门户与 Internet Explorer 10 结合使用，必须始终在兼容模式下使用浏览器。  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a>即使在警报主机服务停止后仍接收通知电子邮件  
 如果您使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，如果你想要使用 BAM 警报，则必须在 SQL Server 配置数据库邮件功能。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用警报主机服务与数据库邮件功能结合使用来发送通知警报。 警报主机服务在处理通知后，会将通知工作量继续传递给 SQL Server 中的数据库邮件组件。 因此，即使停止警报主机服务，也仍可能会收到一些针对警报主机服务已处理但数据库邮件组件未处理的事件通知。  
  
### <a name="configuring-tracing-for-bam-alerts"></a>为 BAM 警报配置跟踪  
 如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 结合使用，并且要为 BAM 警报启用诊断跟踪，则必须通过为 BAM 警报主机创建配置文件来执行此操作。 必须为文件命名**BAMAlerts.exe.config**并将其复制到与 EXE 相同的位置 (**BAMAlerts.exe**)，即 \Program Files\Microsoft BizTalk Server\Tracking\\。  
  
 示例配置文件如下所示。 此文件记录了**信息**级别事件查看器的详细信息。  
  
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
 使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]可以设置**远程登录超时值**SQL Server 中为 20 秒的值。 否则，在任务繁忙时可能会出错。 有关如何设置远程登录超时值的说明[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，请参阅 [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)  
  
##  <a name="BKMK_Adapters"></a> 适配器的问题  
 本部分列出了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器的已知问题。  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a>在使用 Windows SharePoint Services (WSS) 适配器时，动态端口可能发生故障  
 使用 WSS 适配器的动态端口可能发生故障，并出现以下错误：  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 **解决方法**:  
  
-   在端口配置中，站点 URL 同时包括端口号。 例如， `http://server:80/site`。  
  
-   启用**Windows Identity Foundation 3.5**功能。  
  
-   确认运行 BizTalk 主机的帐户有权访问 SharePoint。  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a>在只安装了 BizTalk Server 管理组件的计算机上，无法管理 BizTalk 适配器包中提供的适配器  
 如果在只安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的计算机上安装 BizTalk 适配器包，则随 BizTalk 适配器包安装的适配器在你创建发送端口或接收位置时将不可用。 原因是，这些适配器依赖于在同一计算机上安装的 BizTalk 运行时。  
  
 解决方法 – 在已安装适配器包和 BizTalk Server 管理组件的计算机上安装 BizTalk Server 运行时。 无需在该计算机上配置 BizTalk Server。  
  
## <a name="other-issues"></a>其他问题  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a>用于 BizTalk Server 示例的 Setup.bat 通过 32 位命令提示符来运行  
 对于此版本随附的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例，必须只从 32 位命令提示符中运行附带的 setup.bat 文件。 从 64 位命令提示符中运行批处理文件可能导致失败。  
  
### <a name="run-setup-as-administrator"></a>以管理员身份运行安装程序  
 安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，使用**以管理员身份运行**选项。 否则，可能会出现以下错误：  
  
 内部错误 2761年。 返回代码： 1  
  
 MSI 安装返回了 1603-安装时发生严重错误。  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a>将证书用于 1024 密钥进行编码和签名会导致 MIME-SMIME 解码失败  
 在 Windows 8 中，如果使用包含 1024 密钥的证书对消息进行加密和签名操作，MIME-SMIME 解码在验证消息时会失败。 为避免此问题，可使用包含 2048 密钥的证书。  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a>UDDI 解析程序在与 ESB 工具包结合使用时发出序列化错误  
 如果将 UDDI 与 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]结合使用，在查找绑定详细信息时可能会遇到 XML 序列化错误。 如果未指定绑定密钥，则会出现此错误。  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a>ESB 工具包的路线设计器  
 现在，[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]的路线设计器属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装介质的一部分。 在介质的根文件夹中可以找到路线设计器，其名称为 `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`。 以前，此文件位于安装 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] 的位置，该位置通常为 \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
### <a name="edi"></a>EDI  
 正在使用 EDI 批处理。 在使用阿拉伯语日历或阿拉伯语本地设置时，业务流程挂起，并出现以下错误：  
  
 **错误代码： 0xC0C01B52 （业务流程引擎错误） 错误描述： 持久性失败由于冻结期间挂起。** 阿拉伯语格里支持从*04/30/1900 00.00.00*到*05/13/2029年 23:59:59*。  
  
 要解决此行为的问题，请输入有效的阿拉伯语结束日期。  
  
### <a name="enterprise-single-sign-on"></a>企业单一登录  
 安装 Enterprise Single Sign-On (ESSO) 或重新启动 ESSO 服务时，你可能会看到事件查看器中记录的以下错误。  
  
 **未能加载 \Program Files\Common Files\Enterprise 单一 sign-on\ssopsserver.dll 错误代码： 0x8007007E，找不到指定的模块。** 可以安全地忽略此错误。