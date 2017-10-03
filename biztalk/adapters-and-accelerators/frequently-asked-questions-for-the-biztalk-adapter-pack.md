---
title: "BizTalk 适配器包常见问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cdaf09a-50fe-4f30-bd9d-60e316351846
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c9d6e28a5839bafb135285b90d8174a3fa18f49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frequently-asked-questions"></a>常见问题
常见问题 (Faq) 有关[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
 

## <a name="general-questions"></a>一般问题

### <a name="what-are-the-supported-biztalk-versions-for-the-biztalk-adapter-pack"></a>BizTalk 适配器包的支持的 BizTalk 版本有哪些？  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]附带 Microsoft [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 安装附带的版本你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本。 安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从另一个[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本不受支持。 
  
### <a name="in-which-user-context-should-the-setup-be-run"></a>应在哪个用户上下文中运行安装程序？  
运行[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序使用的是本地 administrators 组的成员的帐户和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 

相关的链接：[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)

### <a name="how-do-i-get-started-using-the-adapter"></a>如何开始使用适配器？  
如果你熟悉[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，然后安装[BAP 2016](../adapters-and-accelerators/install-the-biztalk-adapter-pack-2016.md)或[BAP 2013 R2 和 2013年](../adapters-and-accelerators/install-biztalk-adapter-pack-2013-r2-and-2013.md)，然后开始使用和[不同适配器](../adapters-and-accelerators/biztalk-adapter-pack.md).

如果你是全新[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，则看 get 启动主题，并单步执行教程： 

[开始使用 BizTalk 适配器用于 Oracle 数据库](../adapters-and-accelerators/adapter-oracle-database/get-started-with-the-oracle-database-adapter.md)  
[开始使用 BizTalk 适配器用于 Oracle E-business Suite](../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)  
[要开始使用用于 mySAP Business Suite 的 BizTalk Adapter](../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)  
[要开始使用用于 Siebel eBusiness Applications 的 BizTalk Adapter](../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[开始使用 BizTalk adapter for SQL](../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)
   
### <a name="does-the-microsoft-biztalk-adapter-pack-support-tracing"></a>Microsoft BizTalk 适配器包是否支持跟踪？  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]允许适配器客户端启用 Windows Communication Foundation (WCF) 跟踪和特定于适配器的跟踪。 当启用跟踪时，你还选择的文件夹路径和文件名称。 因此，跟踪存储您喜欢的位置。 若要查看跟踪，使用 WCF 服务跟踪查看器工具。 请参阅[使用服务跟踪查看器查看相关跟踪和故障排除](https://msdn.microsoft.com/library/aa751795.aspx)。

有关跟踪和其他的疑难解答方法的详细信息，请参阅： 

[对 Oracle 数据库适配器进行故障排除](../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[对 Oracle EBS 适配器进行故障排除](../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)  
[故障排除 SAP 适配器](../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)  
[解决在 Siebel 适配器](../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)  
[解决 SQL 适配器](../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)  
  
### <a name="are-performance-counters-available-for-the-adapters"></a>是否性能计数器可用于适配器？  
是。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供**LOB 时间 （的累积）**性能计数器，以测量的时间，以毫秒为单位，LOB 客户端库所需完成某项操作启动的适配器。  可以通过设置中启用性能计数器`EnablePerformanceCounters`属性绑定到**True**。 若要禁用性能计数器，设置`EnablePerformanceCounters`到**False** （默认值）。   

## <a name="biztalk-server-questions"></a>BizTalk Server 问题

### <a name="which-biztalk-server-tools-are-used-while-working-with-adapters-where-can-i-find-more-information-about-these-tools"></a>使用适配器时可以使用哪些 BizTalk Server 工具？ 在哪里可以找到有关这些工具的详细信息？  
有几个工具，可帮助使用这些适配器的项目： 
 
 |工具|中的主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]核心文档|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]|-   [使用 Visual Studio](../core/using-visual-studio.md) <br />-   [使用 BizTalk 项目](../core/working-with-biztalk-projects.md)<br />-   [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和 Visual Studio 中的项目](https://msdn.microsoft.com/library/b142f8e7.aspx)。|  
|业务流程设计器|[创建使用业务流程设计器的业务流程](../core/creating-orchestrations-using-orchestration-designer.md)|  
|管道设计器| [创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)|  
|BizTalk 映射程序| [创建映射使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)|  
|BizTalk Server 管理控制台|[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)|  
  
### <a name="can-i-reuse-bindings-of-a-biztalk-application-how"></a>可以重复使用的 BizTalk 应用程序的绑定。 如何？  
是。 一个绑定之间创建映射了逻辑的终结点，如业务流程端口或角色链接，以及物理终结点，如发送和接收端口。 这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。 绑定信息存储在 XML 文件，其中包含每个 BizTalk 业务流程的作用域中的 BizTalk 程序集、 应用程序或组的绑定信息。 你可以导出 BizTalk 集、 应用程序，或组中，绑定，然后通过导入到任何其他 BizTalk 应用程序或组重复使用它。 有关详细信息，请参阅 

[重复使用 Oracle 数据库适配器绑定](../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)  
[重复使用 Oracle EBS 适配器绑定](../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
[重复使用 SAP 适配器绑定](../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)  
[重用 Siebel 适配器绑定](../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)  
[重用 SQL 适配器绑定](../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
### <a name="what-is-the-transaction-isolation-level-how-can-i-configure-it"></a>"事务隔离级别"是什么？ 如何配置它？  
 事务隔离级别确定事务与受其他事务所做的数据更改隔离的程度。 它定义到的业务线 (LOB) 系统的连接发出的 TRANSACT-SQL 命令的锁定行为。 
  
这是适配器的某些可配置。 请参阅： 

[Oracle 数据库： 配置事务隔离级别和事务超时](../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)  
[Oracle E-business Suite： 配置事务隔离级别和事务超时](../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)  
[SQL： 配置事务隔离级别和事务超时](../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)

[在 SQL 数据库引擎的隔离级别](https://technet.microsoft.com/library/ms189122.aspx)描述 SQL 中的不同级别。 

## <a name="wcf-based-adapter-faqs"></a>基于 WCF 的适配器常见问题

### <a name="what-is-wcf"></a>WCF 是什么？
 WCF 代表 Windows Communication Foundation。 WCF 是用于构建面向服务的应用程序由 Microsoft 开发的编程框架。 WCF 是.NET framework 的一部分，使开发人员可以构建跨平台集成又能与现有投资交互的安全、 可靠且已经过事务处理解决方案。  
  
相关的链接：[什么是 Windows Communication Foundation](https://msdn.microsoft.com/library/ms731082.aspx)  
  
### <a name="what-is-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 是什么？  
 WCF LOB 适配器 SDK 是一套工具和开发的业务线系统的可重用、 元数据丰富适配器提供一致的 framework 的组件。 使用 WCF LOB 适配器 SDK 编写的适配器作为自定义 WCF 绑定，可由 WCF 支持的客户端使用。 
 
相关的链接： [WCF 行的业务适配器 SDK 文档](../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md) 

### <a name="what-is-the-wcf-service-model"></a>WCF 服务模型是什么？  
 WCF 服务模型是在其中 LOB 系统 （如 Oracle 或 SAP） 公开为 WCF 服务的 WCF 提供的编程模型。 为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 WCF 服务模型生成一个代理类-WCF 客户端类-你的代码可以通过其调用操作和接收数据使用适配器。 
 
 中的所有适配器[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]支持 WCF 服务模型。
 
 ### <a name="what-is-the-wcf-channel-model"></a>WCF 通道模型是什么？  
 WCF 通道模型是客户端和服务之间的 SOAP 消息交换的低级别抽象。 它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。 堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。 每个适配器是公开 LOB 系统作为 WCF 服务的 WCF 自定义传输绑定。 
 
  中的所有适配器[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]支持 WCF 通道模型。
  
### <a name="when-should-i-use-the-wcf-service-model-or-the-wcf-channel-model"></a>何时应使用 WCF 服务模型或 WCF 通道模型？  
 WCF 服务模型中存在的.NET 程序员熟悉并通过通道隐藏 SOAP 消息交换的基础复杂性的模型。 此外，添加适配器服务引用插件与 Visual Studio 设计体验，集成，并且提供一个标准的 Microsoft Windows 界面提供功能强大的浏览和搜索功能公开的适配器操作。 因此，WCF 服务模型通常是最佳的选择为开发适用于任何基于 WCF 的适配器的编程解决方案。  

 你想要使用 WCF 通道模型通过 WCF 服务模型时：  
  
-   WCF 通道模型提供更好地控制细化因为在 WCF 通道模型中，您可以直接控制通过通道发送的消息的内容在 LOB 系统执行的操作。  
  
-   WCF 通道模型提供更全面的端到端流式处理的大型对象 (LOB) 数据类型，而 WCF 服务模型不支持。 这是因为在 WCF 通道模型中，您可以直接控制如何提供传出消息的消息正文，并对传入的消息的消息正文的处理方式。 
  
### <a name="how-do-i-get-started-with-the-wcf-service-model"></a>我如何开始使用 WCF 服务模型？  
 提供通过 WCF 服务模型生成 WCF 客户端类或 WCF 服务协定和关联的帮助程序从服务元数据的代码公开的每个适配器，可以使用以下工具之一：  
  
-   ServiceModel 元数据实用工具 (svcutil.exe)，其中附带了 WCF。  
  
-   添加适配器服务引用 Visual Studio 插件，其中附带[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]。  
  
### <a name="how-do-i-get-started-with-the-wcf-channel-model"></a>我如何开始使用 WCF 通道模型？  
 使用 WCF 通道模型，您可以调用操作，并通过与适配器交换 SOAP 消息，通过 WCF 通道收到轮询查询的结果。 若要开始，你需要创建出站 （客户端） 和入站 （服务） 通道。
  
## <a name="see-also"></a>另请参阅  
[BizTalk 适配器包](../adapters-and-accelerators/biztalk-adapter-pack.md)