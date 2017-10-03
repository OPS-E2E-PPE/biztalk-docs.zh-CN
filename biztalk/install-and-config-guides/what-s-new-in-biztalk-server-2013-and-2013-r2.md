---
title: "什么是 BizTalk Server 2013 和 2013 R2 中的新增功能 |Microsoft 文档"
description: "BizTalk Server 2013 R2 和 2013年中新功能和更改的完整列表"
caps.latest.revision: "67"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 2017-08-10
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdb841f7-4aa9-45c9-a6f1-d527089fcc09
ms.author: mandia
ms.openlocfilehash: 49a4e668f1c5e23169464fdbc4b4f0464a062628
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="whats-new-in-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 和 2013 R2 的新增功能
请查看 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 中的新增功能和已弃用的功能。
  
##  <a name="BKMK_NewR2"></a>BizTalk Server 2013 R2 的新增功能有哪些？  
  
|功能|说明|  
|-------------|-----------------|  
|支持新版本的 Windows OS、SQL Server 和 Visual Studio|请参阅 [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)。|  
|支持 JSON|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 现支持发送和接收 JSON 消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含一个向导，可以从 JSON 实例生成 XSD 架构，还包含用于自定义管道的编码器和解码器组件。 有关详细信息，请参阅[使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)。|  
|对 SB 消息适配器的更新|SB 消息传送适配器得到增强，除 ACS 外，还可支持基于 SAS（共享访问签名）的身份验证。  通过此新改进，BizTalk Server 现在还可与本地版本的服务总线进行交互。 有关详细信息，请参阅 [SB 消息适配器](../core/sb-messaging-adapter.md)。|  
|对 SFTP 适配器的更新|SFTP 适配器现在支持双重身份验证，并提供了一个可以在上载/下载大型文件时指定临时文件夹的选项。 您也可以选择特定于目标服务器的加密密码值。 有关详细信息，请参阅 [SFTP 适配器](../core/sftp-adapter.md)。|  
|对 HL7 Accelerator 的更新|HL7 Accelerator 现在支持以下功能：<br /><br /> - 能够在 HL7 管道可处理的消息中加入任意文本数据。<br /><br /> - 对托管 Hl7 适配器的 64 位支持。<br /><br /> 请参阅 [BizTalk Accelerator for HL7 的新增功能](http://msdn.microsoft.com/library/ee409458\(v=bts.80\).aspx)。|  
|BizTalk 运行状况监视器|BizTalk 运行状况监视器是新的 BizTalk 管理单元，可帮助监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的运行状况。 该管理单元可添加到现有的 BizTalk 管理控制台中，也可以单独运行。 以下是 BizTalk 运行状况监视器的功能：<br /><br /> - 生成和查看运行状况报告<br /><br /> - BizTalk 环境整体运行状况的仪表板视图<br /><br /> - 发送电子邮件通知<br /><br /> - 计划报告收集<br /><br /> - 性能监视器与预加载的基于方案的性能计数器相集成<br /><br /> - 监视多个 BizTalk 环境<br /><br /> - 报告管理<br /><br /> 有关 BizTalk 运行状况监视器的详细信息，请参阅 [Getting Started with BizTalk Health Monitor](http://go.microsoft.com/fwlink/?LinkId=403315)（BizTalk 运行状况监视器入门）和 [Overview of BizTalk Health Monitor](http://go.microsoft.com/fwlink/?LinkId=403316)（BizTalk 运行状况监视器概述）。|  
  
### <a name="deprecated-list"></a>已弃用列表  
  
|Program|状态|替代功能|  
|-------------|------------|-----------------|  
|RFID Mobile|已删除|无|  
|RFID Server|不推荐使用|无|  
|SharePoint SSOM/Web Service 适配器|不推荐使用|使用 CSOM（客户端对象模型）选项。<br /><br /> [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)<br /><br /> [附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)|  
|SOAP 适配器|不推荐使用|[WCF-BasicHttp 适配器](../core/wcf-basichttp-adapter.md)|  
|旧 SQL 适配器|不推荐使用|[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的基于 WCF 的 SQL 适配器|  
|UDDI|不推荐使用|无|  
  
> [!IMPORTANT]
>  较新版本的 BizTalk 中可能包含其中一些已弃用的功能。 在这些情况下，请考虑以下方面：  
>   
>  -   该功能可能会在 BizTalk 中内部使用，但并不表示供客户解决方案使用。 它在客户解决方案中不受支持。  
> -   接口可能已被 Microsoft 修改，并且可能未公开。  
  
##  <a name="BKMK_New"></a>BizTalk Server 2013 的新增功能有哪些？  
 BizTalk Server 2013 中增加了以下功能。  
  
 **Azure IaaS 上的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  
  
|功能|说明|  
|-------------|-----------------|  
|在 [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[vm](../includes/vm-md.md)] 上配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|请参阅[在 Windows Azure 中创建 BizTalk 虚拟机](http://msdn.microsoft.com/library/jj572843.aspx)。|  
|在 [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[vm](../includes/vm-md.md)] 上创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组|请参阅[创建 BizTalk 组必备组件](http://msdn.microsoft.com/library/jj248711.aspx)和[配置 BizTalk 组](http://msdn.microsoft.com/library/jj572845.aspx)。|  
  
 **本地 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  
  
|功能|说明|  
|-------------|-----------------|  
|按内核许可模型|BizTalk Server 2013 是按内核许可的。 SQL Server 2012 也是按内核许可的。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 和以前版本是按处理器许可的。<br /><br /> 在四核或小于四核的处理器上运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，许可证成本与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 保持一致。 核心许可证的价格是处理器许可证成本的四分之一。 在处理能力更高的处理器上运行服务器时，由于硬件功耗增加，许可费用也随之增加。<br /><br /> 为帮助你确定可能需要的许可证数量，在 *C:\Program Files (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\LicenseUsageTracking* 中提供了一个 PowerShell cmdlet。<br /><br /> 实用链接：<br /><br /> [BizTalk Server 2013 定价及版本](http://www.microsoft.com/biztalk/pricing.aspx)<br /><br /> [了解 BizTalk Server 2013 许可](http://blogs.biztalk360.com/understand-biztalk-server-2013-licensing/)|  
|支持新适配器|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了新的适配器，可将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序的连接扩展到 [!INCLUDE[winazure](../includes/winazure-md.md)]。 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 还提供 SharePoint 适配器更新，使用户可选择是使用客户端对象模式还是使用服务器端对象模型连接到 SharePoint 服务器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括一个新的适配器，可从 SFTP 服务器发送和接收邮件。|  
|跟踪项目之间的依存关系|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 更新了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，以提供 UI 驱动的体验，便于查看不同 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目（如业务流程、发送端口、接收位置等）之间的依存关系。 有关详细信息，请参阅[跟踪 BizTalk Server 应用程序中项目之间的依赖关系](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)|  
|集成的 ESB 工具包|ESB 工具包现在已集成到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序中。 而且，ESB 工具包配置体验经过简化，可为用户缩短快速启动时间。 有关详细信息，请参阅[安装和配置 Microsoft BizTalk ESB 工具包](../esb-toolkit/install-and-configure-the-microsoft-biztalk-esb-toolkit.md)|  
|支持新版本的 Windows OS、SQL Server 和 Visual Studio|请参阅 [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)|  
|受支持的 EDI 架构的更新|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引入了对以下 EDI 架构的支持：<br /><br /> -                     **X12** – 5040, 5050, 6020, 6030<br /><br /> - **EDIFACT** – D06A, D06B, D07A, D07B, D08A, D08B, D09A, D09B, D10A, D10B<br /><br /> -                     **HL7** – 增加了 2.51 消息支持<br /><br /> -                     **SWIFT** – 2012 Message Pack<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装包中包括这些架构。 可从 [http://go.microsoft.com/fwlink/p/?LinkId=258228](http://go.microsoft.com/fwlink/p/?LinkId=258228) 下载该安装包。|  
|映射器使用 XSLCompiledTransform|该映射器使用 XSLCompiledTransform 类。 以前的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本使用 XslTransform 类，该类已过时。 XSLCompiledTransform 类提升了性能，其中包括：<br /><br /> - Load 方法成功完成后，可从多个线程同时调用 Transform 方法。<br /><br /> - 新的 XSLT 处理器可将 XSLT 样式表编译成常见的中间格式。 编译完该样式表之后，可以缓存并重用它。<br /><br /> 有关详细信息，请参阅[映射程序更新的意义](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)和 [XslCompiledTransform 类](https://msdn.microsoft.com/library/system.xml.xsl.xslcompiledtransform.aspx)。|  
|可配置动态发送端口处理程序|创建动态发送端口时，可为*每个*安装的适配器配置适配器发送处理程序。 包括单向动态端口和要求响应动态端口。 在以前的 BizTalk 版本中，动态发送端口使用适配器的默认主机。<br /><br /> 有关详细信息，请参阅[动态发送端口处理程序可配置](../core/dynamic-send-port-handler-is-configurable.md)。|  
|按序送达|在以前的 BizTalk 版本中，如果按序送达使用多个终结点，则速度最慢的适配器类型为最大速度。 此行为会直接影响 HL7 解决方案。 使用 MLLP 适配器时，需要确认 (ACK)。 可能会发生延迟，因为必须在收到确认之后才能发送下一条消息。<br /><br /> 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，无需等待前一条消息的确认即可发送下一条消息。 确认到达后，它将在内部与其消息关联/连接。|  
|支持工具|支持工具会自动随 BizTalk 一起安装：*C:\Program Files (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\Support Tools*。<br /><br /> 工具包括：<br /><br /> - BizTalk 程序集检查器<br /><br /> - MsgBox 查看器<br /><br /> - PSSDiagForBizTalk<br /><br /> - BizTalk 终止符下载的 Internet 快捷方式|  
|PowerShell 提供程序|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] PowerShell 提供程序位于 *C:\Program Files (x86)\Microsoft BizTalk Server 2013\SDK\Utilities\PowerShell* 中。<br /><br /> 对于以前的 BizTalk 版本，[http://psbiztalk.codeplex.com/](http://psbiztalk.codeplex.com/) 有一个 CodePlex PowerShell 提供程序。|  
|BAM 警报|如果 BizTalk Server 2013 使用 [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，则使用 BAM 警报需要数据库邮件。 如果 BizTalk Server 使用 SQL Server 2008 R2，则需安装 SQL Server Notification Services 才能使用 BAM 警报。<br /><br /> [BAM 警报](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)提供了详细信息。|  
  
> [!IMPORTANT]
>  在单独的计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 时，分布式事务协调器 (MS DTC) 处理计算机之间的事务。 因此，[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)] 和 2013 不支持 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 功能。 从 [!INCLUDE[bts2016](../includes/bts2016-md.md)] 开始**支持** AlwaysOn 功能。 有关详细信息，请参阅 [BizTalk Server 2016 中的新增功能](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)。  
  
### <a name="known-issues"></a>已知问题  
 [BizTalk Server 2013 中的已知问题](http://support.microsoft.com/kb/2954101)