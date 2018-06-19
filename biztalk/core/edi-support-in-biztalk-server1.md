---
title: 在 BizTalk Server1 的 EDI 支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cddab7a-99ef-4dbb-bb74-9e3d03df3996
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8351420ed8d7815944c3ae619420137a8a61df
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006966"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server 中的 EDI 支持
本主题提供 EDI 和 BizTalk Server 如何支持 EDI 常规简要概述。  
  
## <a name="introduction-to-edi"></a>EDI 介绍  
 电子数据交换 (EDI) 是商业贸易伙伴以电子方式交换数据所最常用的一种手段。 EDI 很大程度上是面向消息的。 文档被实现为可包含批事务集的平面文件。 批交换可以包含多个组，每个组又可以包含多个事务集或消息。  
  
 EDI 由标准团体协商制订的特定数据交换方法组成。 主要的 EDI 标准包括 X12（由 ANSI 进行标准化，主要在北美地区使用）和 EDIFACT（由联合国进行标准化，主要在美国以外地区使用）。 其他标准都是从这两个标准派生出来的，例如：从 X12 派生的 HIPAA 和从 EDIFACT 派生的韩国的 KEDIFACT 标准。 这些标准在消息结构和确认架构上都基本类似，但是也具有一些明显的差异。  
  
 EDI 标准规定了以下内容：  
  
-   文档交换使用的格式、字符集和数据元素  
  
-   EDI 事务中使用的信封  
  
-   验证是否送达所需的确认  
  
-   如何提供有保障且只需一次的传递，以及对损坏数据或不正确数据的自动检测和报告。  
  
 尽管 EDI 标准确定了文档结构的规则，但是贸易伙伴必须对要传输的特定信息和如何使用该特定信息达成一致。 连接两个贸易伙伴的 EDI 系统的设计是由标准所要求的内容和贸易伙伴所达成一致的内容共同决定的。 有关 EDI 消息传送的详细信息，请参阅[EDI 消息传递](../core/edi-messaging.md)。  
  
> [!NOTE]
>  EDI 消息的传输方式多种多样。 EDI 标准没有对消息传输加以规定，因此可以通过各种不同的手段发送 EDI 消息。  
  
## <a name="how-edi-is-implemented-in-biztalk-server"></a>BizTalk Server 中 EDI 的实现方式  
 BizTalk Server 包括提供对 EDI 的支持的本机功能。 EDI 内置于产品中。它不是外接程序，例如适配器或快捷键。  
  
 **交换处理**  
  
 此 EDI 功能在强制实施 EDI 标准所规定的规则的管道中执行以下接收端和发送端处理。  
  
-   处理传入的 EDI 消息，包括验证交换和生成确认。  
  
-   生成并将传出 EDI 消息，包括验证的交换和处理收到的具体取决于配置的确认。  
  
 **批处理**  
  
 批处理由接收管道和业务流程进行处理：  
  
-   如果收到的批交换将被拆分，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会拆分为其构成事务集，同时为每个事务集生成一个 XML 文件并且升级执行发送端批生成操作所需的属性。  
  
-   如果收到的批交换将被保留，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会对批进行处理，使批保留收到它时所包含的事务集和组。  
  
-   如果收到的批交换将进行配置，则批会将 EDI 事务集和组接收到传出交换中。  
  
-   如果有多个参与方订阅了某个批交换，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会向每个参与方发送该批的一个副本。  
  
 **贸易合作伙伴协议**  
  
 贸易合作伙伴相互定义贸易合作伙伴协议这是一组在 BizTalk Server 管理控制台中定义的属性。 这些参与方属性、发送和接收端口/位置属性决定了接收端和发送端的 EDI 处理过程。 有关贸易合作伙伴协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
 **交换状态**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可提供特定于 EDI 的状态报告。 这些状态报告提供了 EDI 文档交换事务的全面状态，包括与交换有关的确认状态。  
  
## <a name="edi-components-in-biztalk-server"></a>BizTalk Server 中的 EDI 组件  
 Microsoft BizTalk Server 用于 EDI 处理的组件包括：  
  
-   BizTalk EDI 应用程序，包含处理 EDI 文档所需的项目（包括管道、业务流程和架构）。  
  
    > [!NOTE]
    >  当你在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置的 EDI 功能时，配置程序会创建此应用程序。 只要你创建了将处理 EDI 交换的应用程序，就必须从该应用程序中添加对 BizTalk EDI 应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
-   BizTalk EDI 接收管道（EdiReceive 管道），用于分析 EDI 编码的文档，拆分 EDI 批，将 EDI 编码的文档转换为 XML 编码，执行 EDI 和 XSD 验证，以及执行 HIPAA X12 子文档拆分。 有关详细信息，请参阅[EDI 接收组件](../core/edi-receive-components.md)。  
  
-   BizTalk EDI 发送管道（EdiSend 管道），用于将 XML 文档转换为 X12 或 EDIFACT 编码，序列化 EDI 编码的文档以及执行 EDI 和 XSD 验证。 有关详细信息，请参阅[EDI 发送组件](../core/edi-send-components.md)。  
  
-   使用贸易合作伙伴管理 (TPM) 用户接口，你可以为参与 EDI 文档交换和 AS2 文档传输的贸易合作伙伴设置处理属性。 有关详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)和**EDI 和 AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
-   批处理业务流程，用于对 EDI 交换进行批处理，以及设置用于发送批交换的上下文属性。 路由业务流程处理其中消息匹配多个批处理的实例，创建需要的多个消息副本。 有关详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)和[批处理传出的 EDI 消息](../core/batching-outgoing-edi-messages.md)。  
  
-   状态报告用户界面，提供了 EDI 交换和相关确认的全面状态信息。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
-   Visual Studio 中的设计时工具，通过这些工具，可以生成实例、验证实例，验证架构，测试映射以及验证映射。 有关详细信息，请参阅[使用设计时 XML 工具](../core/using-design-time-xml-tools.md)。  
  
-   架构存储库，包括 X12、EDIFACT、HIPAA X12N 4010A XSD、EANCOM 以及控制架构。 有关详细信息，请参阅[EDI 文档架构支持](../core/edi-document-schema-support.md)。  
  
-   迁移工具 （方迁移工具） 允许你将从 BizTalk Server 2006 R2 或 BizTalk Server 2009 EDI 方数据迁移到 BizTalk Server。 有关详细信息，请参阅[迁移 BizTalk Server 以前版本中的 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 中的 EDI 处理](../core/edi-processing-in-biztalk-server.md)   
 [BizTalk Server 中的 HIPAA 支持](../core/hipaa-support-in-biztalk-server.md)   
 [EDI 支持问题](../core/edi-support-issues.md)   
 [EDI 解决方案体系结构](../core/edi-solution-architecture.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)