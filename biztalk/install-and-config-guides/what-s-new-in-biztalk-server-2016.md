---
title: 什么是 BizTalk Server 2016 中的新增功能 |Microsoft Docs
description: 更改和改进，包括功能包、 适配器、 安全、 跟踪、 性能和 BizTalk Server 2016 中的详细信息
ms.custom: ''
ms.prod: biztalk-server
ms.date: 6/22/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fce1fe8-f515-462d-bf6d-19408d515479
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db2edbf6661a2658dba882f102fcc5d355fefc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401431"
---
# <a name="whats-new-in-biztalk-server-2016"></a>什么是 BizTalk Server 2016 中的新增功能
阅读有关新增功能[!INCLUDE[bts2016](../includes/bts2016-md.md)]。 
  
## <a name="new-in-biztalk-server-2016"></a>BizTalk Server 2016 中的新增功能  
  
|功能|Description|  
|-------------|-----------------|  
|对较新平台的支持|[!INCLUDE[bts2016](../includes/bts2016-md.md)] 添加对以下 Microsoft 平台的支持：<br /><br /> -   Visual Studio 2015<br />-   Windows Server 2016<br />-   [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]<br />-   Office 2016<br/><br/>[硬件和软件要求适用于 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)|  
| 功能包 3 | 包括 Office 365 适配器，以使用电子邮件、 日历和联系人。 <br/><br/>[安装功能包](https://aka.ms/bts2016fp3)<br/>[请参阅已包含和配置其功能的内容](../core/configure-the-feature-pack.md) |
| 功能包 2 | 改进包括更紧密集成 API 管理中，使用 Azure 事件中心适配器、 备份到 Azure blob 存储帐户、 对服务总线分区的支持和的详细信息。 <br/><br/>[安装功能包](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[请参阅已包含和配置其功能的内容](../core/configure-the-feature-pack.md) |
| 功能包 1 | 有关使用 VSTS，发送到 Azure Application Insights 和 Power BI 中，跟踪数据的自动部署高级计划包括支持选项上的接收位置，以及更多。<br/><br/>[安装功能包](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[请参阅已包含和配置其功能的内容](../core/configure-the-feature-pack.md) |
|[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn 可用性组|支持包括：<br /><br /> -使用在本地和在[!INCLUDE[winazure](../includes/winazure-md.md)]IaaS 虚拟机<br />-使用适用于生产工作负荷<br />-提供一个高可用 (HA) 解决方案中 [!INCLUDE[winazure](../includes/winazure-md.md)] <br/><br/>[使用 SQL Server AlwaysOn 实现高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)<br/><br/> 请参阅[Always On AG 的分布式事务](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)有关任何特定于 SQL 的要求和功能。|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在生产环境中的 azure Vm|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Azure 虚拟机现在完全支持用于生产环境中。 使用[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]AlwaysOn，高度可用的解决方案现在已成为可能。<br/><br/>[使用 SQL Server AlwaysOn 实现高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)|  
|逻辑应用适配器|连接到逻辑应用托管在 Azure 中，并获取访问权限包括 Salesforce、 SharePoint、 CRM Online 等的所有连接器。 例如，可以在 BizTalk Server 中接收订单、 连接到逻辑应用和更新 Salesforce。<br/><br/>[逻辑应用适配器](../core/logic-app-adapter.md)|  
| 文件适配器 | 连接到 Azure 存储文件共享。 可以接收来自 Azure 文件共享的文件并将消息发送到 Azure 文件共享。 <br/><br/>[配置文件适配器](../core/configure-the-file-adapter.md)|
| FTP 适配器 | 不再需要 SYST 命令。 当配置 FTP 适配器接收位置或发送端口时，没有名为的属性**FTP 服务器类型**。 使用此属性，选择您要; 的 FTP 服务器用于确定是否需要 SYST。 <br/><br/>由于此更改，有更多"支持的"FTP 服务器。 <br/><br/> [配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)|
|SFTP 适配器| SFTP 适配器是重新设计，可使用 WinSCP 连接到 SFTP;从而可支持更多 SFTP 服务器。 客户端日志记录和其他加密密码也是新的。 <br/><br/>[SFTP 适配器](../core/sftp-adapter.md)|  
| 允许导入跟踪设置 | 当导入绑定文件，您可以选择要导入 （或不导入） 启用的跟踪属性在业务流程、 发送端口，等等。 因此，你可以在不同环境中设置此功能，这是一种全局设置 （在组级别设置）。 例如，您可以导入的现有跟踪属性的开发环境，并为生产环境中不导入的跟踪属性。<br/><br/>请参阅**BizTalk 设置仪表板，组页面** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|
| 共享访问签名 (SAS) | 可以使用服务总线连接使用 SAS 身份验证*BasicHttpRelay*， *NetTcpRelay*， *BasicHttp*，和*WebHttp*适配器。<br/><br/>[Wcf-basichttprelay 适配器](../core/wcf-basichttprelay-adapter.md)<br/>[Wcf-nettcprelay 适配器](../core/wcf-nettcprelay-adapter.md)<br/>[Wcf-basichttp 适配器](../core/wcf-basichttp-adapter.md)<br/>[Wcf-webhttp 适配器](../core/wcf-webhttp-adapter.md)<br/><br/> [SB 消息适配器](../core/sb-messaging-adapter.md)现在包括获取使用 PowerShell 的访问控制 (ACS) 值的步骤。|
|动态端口按序送达|适用于静态发送端口支持按序的送达的适配器。 可以启用 BizTalk 管理控制台中的按序的送达选项。<br /><br />[如何配置传输高级选项的发送端口](../core/how-to-configure-backup-transport-options-for-a-send-port.md)<br />[按序送达消息](../core/ordered-delivery-of-messages.md)|  
|Sha-2 哈希函数|完全支持 sha-2，其中包括：<br /><br /> <ul><li>BizTalk 可跨其所有组件，包括 SSL 在 HTTPS、 FTPS、 POP3 和 WCF 消息传送适配器都使用 SHA2 签名的证书 </li><li>用于 AS2、 RosettaNet 和 MIME/SMIME 编码器中签名密钥支持以下高级加密标准 (AES) 交换系统：<ul><li>AES128 （默认值）</li><li>AES192</li><li>AES256</li><br /></ul></li><li>针对 AS2 支持以下基于 SHA2 的 MIC 计算：<ul><li>SHA256 （默认值）</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>支持 RosettaNet 中以下基于 SHA2 的摘要式方法：<ul><li>SHA256 （默认值）</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>SHA1 证书继续用于向后兼容性</li></ul><br />[配置验证 (AS2)](../core/configuring-validation-as2.md)<br />[配置确认 (Mdn) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)<br />[如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)|  
|编译映射|选择您的映射使用 XslTransform 或 XslCompiledTransform 编译<br/><br/>[设置映射编译和输出设置](../core/how-to-specify-xslt-output-settings.md)|  
|架构窗口|在 BizTalk 映射器中，添加/替换源架构和目标架构。 当执行此操作时，现在已可调整大小类型选取器窗口。 此更改，可展开该窗口，并查看您的架构的完整名称。<br/><br/>[如何调整架构选取器，并展开和折叠架构树](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)|  
|适配器和加速器|改进和更改包括：<ul><li>SAP 适配器支持经典 RFC SDK 和.NET 连接器 SAP 绑定属性中。 <br/><br/>安装**适用于.NET 的 SAP 连接器**，位于 SAP 服务市场 (service.sap.com/connectors)。 在安装期间，请务必选择**程序集安装到 GAC**。<br/><br/>[对 SAP.NET 连接器的 WCF-SAP 适配器支持](https://support.microsoft.com/kb/3100811)提供其他详细信息。  </li><br /><li>BizTalk Accelerator for HL7:接收位置处的 MLLP 适配器现支持启动与远程 LOB 侦听器的出站连接的选项。</li></ul>|  
|导入/导出的参与方|更改包括：<br /><br /> -导入和导出选项是与应用程序分离。 例如，您可以不导出应用程序的情况下导出参与方。 不导入应用程序，可以导入参与方。<br />-可以选择哪些参与方、 业务配置文件和你想要导入或导出的协议<br />-可以继续导入/导出企业到企业项目中一样[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013，和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010年。<br/><br/>[使用绑定文件导入或导出](../core/use-binding-files-to-import-or-export.md)|  
|BizTalk 管理|除了更现代的外观和感觉，一些其他更改包括：<br /><br /> -同时配置多个主机/主机实例的设置。 例如，可以同时设置多个主机实例的.NET CLR 设置。<br />-使用新的搜索功能来筛选和应用程序，如架构、 资源和的详细信息中查找项目。<br />-故障排除时挂起的消息，可以对文件同时保存多个挂起的消息。<br /><br />[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)|  
|其他更新|<ul><li>[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../includes/hl7-currentversion-firstref-md.md)]启动到业务线服务器 (LOB) 的连接，并将消息推送通过该连接。 LOB 等待连接，然后发送消息。 <br/><br/>在以前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本中，HL7 MLLP 接收适配器等待 LOB 服务器连接到 HL7，然后再发送消息。 LOB 连接到 HL7，，然后发送消息。 </li><br/><li>Office web 组件 (OWC) 现在是在安装中，可选的在程序中单独列出</li><br/><li>业务流程实例 ID 添加到 XLANG FireEvent 跟踪输出</li></ul>|   
  
## <a name="deprecated--removed-list"></a>不推荐使用和删除列表  
  
|               程序               |   “登录属性”   |                                                                                                                                                替代功能                                                                                                                                                |
|-------------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             RFID Mobile             |  删除   |                                                                                                                                                   None                                                                                                                                                    |
|             RFID 服务器             |  删除   |                                                                                                                                                   None                                                                                                                                                    |
| SharePoint SSOM/Web 服务适配器 |  删除   | 使用 CSOM （客户端对象模型） 选项。<br /><br /> [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)<br /><br /> [附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) |
|            SOAP 适配器             | 不推荐使用 |                                                                                                                         [Wcf-basichttp 适配器](../core/wcf-basichttp-adapter.md)                                                                                                                         |
|           旧 SQL 适配器           | 不推荐使用 |                                                                                                   中基于 WCF 的 SQL 适配器 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]                                                                                                   |
|                UDDI                 |  删除   |                                                                                                                                                   None                                                                                                                                                    |
  
> [!IMPORTANT]
>  这些不推荐使用的功能的一些可能在较新版本的 BizTalk 中找到。 在这些情况下，考虑以下方面：  
>   
> -   该功能可能会在 BizTalk 中，在内部使用，并不表示用于通过客户解决方案。 不支持在客户解决方案中。  
> -   接口可能已由 Microsoft、 修改和可能公开可用。

## <a name="next-steps"></a>后续步骤
[硬件和软件要求](hardware-and-software-requirements-for-biztalk-server-2016.md)  
[安装与安装的必备组件](set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
[安装 BizTalk](install-biztalk-server-2016.md)