---
title: BizTalk Server 2016 的新增功能 |Microsoft 文档
description: 更改和改进，包括功能包、 适配器、 安全、 跟踪、 性能和 BizTalk Server 2016 中的详细信息
ms.custom: ''
ms.prod: biztalk-server
ms.date: 11/15/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fce1fe8-f515-462d-bf6d-19408d515479
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8e28b3c54afd130176e9bb19b2e0b1a59415d0
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497758"
---
# <a name="whats-new-in-biztalk-server-2016"></a>BizTalk Server 2016 的新增功能
了解 [!INCLUDE[bts2016](../includes/bts2016-md.md)] 中的新增功能。 
  
## <a name="new-in-biztalk-server-2016"></a>BizTalk Server 2016 中的新增功能  
  
|功能|说明|  
|-------------|-----------------|  
|对较新平台的支持|[!INCLUDE[bts2016](../includes/bts2016-md.md)] 添加了对以下 Microsoft 平台的支持：<br /><br /> -   Visual Studio 2015<br />-   Windows Server 2016<br />-   [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]<br />-   Office 2016<br/><br/>[BizTalk Server 2016 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)|  
| 功能包 2 | 改进包括使用 API 管理的集成更紧密，Azure 事件中心适配器、 备份到 Azure blob 存储帐户、 对服务总线分区的支持和的详细信息。 <br/><br/>[安装功能包](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[请参阅什么包含的并配置它的功能](../core/configure-the-feature-pack.md) |
| 功能包 1 | 包括支持使用 VSTS 自动部署、将跟踪数据发送到 Azure Application Insights 和 Power BI 以及有关接收位置的高级计划选项等等。<br/><br/>[安装功能包](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[请参阅什么包含的并配置它的功能](../core/configure-the-feature-pack.md) |
|[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn 可用性组|支持包括：<br /><br /> -   在本地和 [!INCLUDE[winazure](../includes/winazure-md.md)] IaaS 虚拟机内使用<br />-   用于生产工作负荷<br />-   在 [!INCLUDE[winazure](../includes/winazure-md.md)] 中提供高度可用 (HA) 的解决方案 <br/><br/>[使用 SQL Server AlwaysOn 实现高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)<br/><br/> 请参阅[分布式事务用于始终在 AG](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)任何特定于 SQL 的要求和功能。|  
|生产中的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Azure VM|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Azure 虚拟机现在完全支持用于生产环境。 使用 [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn，高度可用的解决方案现已成为可能。<br/><br/>[使用 SQL Server AlwaysOn 实现高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)|  
|逻辑应用适配器|连接到 Azure 中托管的逻辑应用，获取对所有连接器的访问权限，其中包括：Salesforce、SharePoint、CRM Online 等。 例如，可以在 BizTalk Server 中接收指令，连接到逻辑应用，然后更新 Salesforce。<br/><br/>[逻辑应用适配器](../core/logic-app-adapter.md)|  
| 文件适配器 | 连接到 Azure 存储文件共享。 可以接收来自 Azure 文件共享的文件，并将消息发送到 Azure 文件共享。 <br/><br/>[配置文件适配器](../core/configure-the-file-adapter.md)|
| FTP 适配器 | 不再需要 SYST 命令。 在接收位置或发送端口处配置 FTP 适配器时，有一个名为“FTP 服务器类型”的属性。 使用此属性，可以选择所需的 FTP 服务器；该服务器可确定是否需要 SYST。 <br/><br/>此更改的结果是，有了更多“受支持的”FTP 服务器。 <br/><br/> [配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)|
|SFTP 适配器| SFTP 适配器已重新进行设计，可使用 WinSCP 连接到 SFTP；从而可支持更多 SFTP 服务器。 客户端日志记录和其他加密密码也是新增内容。 <br/><br/>[SFTP 适配器](../core/sftp-adapter.md)|  
| 允许导入跟踪设置 | 导入绑定文件时，可以选择导入（或不导入）在业务流程、发送端口等中启用的跟踪属性。 这属于全局设置（组级别设置），因此可以在不同环境中设置此功能。 例如，可以导入开发环境的现有跟踪属性，以及不导入生产环境的跟踪属性。<br/><br/>请参阅**BizTalk 设置仪表板，组页** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|
| 共享访问签名 (SAS) | 可将 SAS 身份验证用于服务总线与 BasicHttpRelay、NetTcpRelay、BasicHttp 和 WebHttp 适配器的连接。<br/><br/>[WCF-BasicHttpRelay 适配器](../core/wcf-basichttprelay-adapter.md)<br/>[WCF-NetTcpRelay 适配器](../core/wcf-nettcprelay-adapter.md)<br/>[WCF-BasicHttp 适配器](../core/wcf-basichttp-adapter.md)<br/>[WCF-WebHTTP 适配器](../core/wcf-webhttp-adapter.md)<br/><br/> [SB-Messaging 适配器](../core/sb-messaging-adapter.md)现包括使用 PowerShell 获取访问控制 (ACS) 值的步骤。|
|动态端口按序送达|适用于支持静态发送端口按序送达的适配器。 可以在“BizTalk 管理员控制台”中启用“按序送达”选项。<br /><br />[如何为发送端口配置传输高级选项](../core/how-to-configure-backup-transport-options-for-a-send-port.md)<br />[消息按序送达](../core/ordered-delivery-of-messages.md)|  
|SHA-2 哈希函数|完全支持 SHA-2，其中包括：<br /><br /> <ul><li>BizTalk 可跨其所有组件使用 SHA2 签名的证书，包括 HTTPS、FTPS、POP3 和 WCF 适配器中的 SSL 消息传递 </li><li>支持以下用于 AS2、RosettaNet 和 MIME/SMIME 编码器中签名密钥的高级加密标准 (AES) 交换系统：<ul><li>AES128（默认）</li><li>AES192</li><li>AES256</li><br /></ul></li><li>针对 AS2 支持以下基于 SHA2 的 MIC 计算：<ul><li>SHA256（默认）</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>支持 RosettaNet 中以下基于 SHA2 的摘要式方法：<ul><li>SHA256（默认）</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>SHA1 证书继续用于后向兼容性</li></ul><br />[配置验证（AS2）](../core/configuring-validation-as2.md)<br />[配置确认 (MDN) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)<br />[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)|  
|编译映射|选择使用 XslTransform 或 XslCompiledTransform 编译映射<br/><br/>[设置映射编译和输出设置](../core/how-to-specify-xslt-output-settings.md)|  
|架构窗口|在 BizTalk 映射器中，添加/替换源架构和目标架构。 现在，执行此操作时，“类型选取器”窗口可调整大小。 通过此更改，可展开窗口并查看架构的完整名称。<br/><br/>[如何调整架构选取器大小，并展开和折叠架构树](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)|  
|适配器和加速器|改进和更改包括：<ul><li>SAP 适配器支持经典 RFC SDK，以及 SAP 绑定属性中的 .NET 连接器。 <br/><br/>安装 **SAP Connector for.NET**，它现已提供在 SAP 服务市场 (service.sap.com/connectors)。 安装期间，请务必选择“将程序集安装到 GAC”。<br/><br/>有关其他详细信息，请参阅[WCF-SAP 适配器支持 SAP .NET 连接器](https://support.microsoft.com/kb/3100811)。  </li><br /><li>BizTalk Accelerator for HL7：接收位置处的 MLLP 适配器现支持启动到远程 LOB 侦听器的出站连接。</li></ul>|  
|导入/导出参与方|更改包括：<br /><br /> -   导入和导出选项与应用程序是分离的。 例如，可在不导出应用程序的情况下导出参与方。 可在不导入应用程序的情况下导入参与方。<br />-   可选择要导入或导出的参与方、业务配置文件和协议<br />-   可以继续导入/导出企业到企业项目，操作方法和 [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 中一样。<br/><br/>[使用绑定文件进行导入或导出](../core/use-binding-files-to-import-or-export.md)|  
|BizTalk 管理|除了更现代的外观和使用体验外，一些其他更改包括：<br /><br /> -   可同时配置多个主机/主机实例的设置。 例如，可以同时设置多个主机实例的 .NET CLR 设置。<br />-   使用新的“搜索”功能在应用程序中筛选和查找项目，如架构、资源等。<br />-   当对挂起的消息进行故障排除时，可同时将挂起的消息保存到一个文件中。<br /><br />[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)|  
|其他更新|<ul><li>[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../includes/hl7-currentversion-firstref-md.md)] 启动到业务线服务器 (LOB) 的连接，并通过该连接推送消息。 LOB 等待连接，然后发送消息。 <br/><br/>在之前的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本中，HL7 MLLP 接收适配器等待 LOB 服务器连接到 HL7，然后再发送消息。 LOB 连接到 HL7，然后发送消息。 </li><br/><li>现可在安装中选择 Office Web 组件 (OWC)，它在“程序”中单独列出</li><br/><li>业务流程实例 ID 被添加到 XLANG FireEvent 跟踪输出</li></ul>|   
  
## <a name="deprecated--removed-list"></a>已弃用和已删除的列表  
  
|Program|状态|替代功能|  
|-------------|------------|-----------------|  
|RFID Mobile|已删除|无|  
|RFID Server|已删除|无|  
|SharePoint SSOM/Web Service 适配器|已删除|使用 CSOM（客户端对象模型）选项。<br /><br /> [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)<br /><br /> [附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)|  
|SOAP 适配器|不推荐使用|[WCF-BasicHttp 适配器](../core/wcf-basichttp-adapter.md)|  
|旧 SQL 适配器|不推荐使用|[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的基于 WCF 的 SQL 适配器|  
|UDDI|已删除|无|  
  
> [!IMPORTANT]
>  较新版本的 BizTalk 中可能包含其中一些已弃用的功能。 在这些情况下，请考虑以下方面：  
>   
> -   此功能可能 BizTalk，在内部使用，并不是由客户解决方案。 它在客户解决方案中不受支持。  
> -   接口可能已由 Microsoft、 修改和可能不能公开。

## <a name="next-steps"></a>后续步骤
[硬件和软件要求](hardware-and-software-requirements-for-biztalk-server-2016.md)  
[安装程序和安装必备组件](set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
[安装 BizTalk](install-biztalk-server-2016.md)