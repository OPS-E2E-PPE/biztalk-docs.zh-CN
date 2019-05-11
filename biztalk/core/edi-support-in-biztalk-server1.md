---
title: BizTalk 服务器 1 中的 EDI 支持 |Microsoft Docs
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
ms.openlocfilehash: 5b422f593558881b11936aa98355aa6d0fb3ae03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389159"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server 中的 EDI 支持
本主题提供了 EDI 以及 BizTalk Server 如何支持 EDI 的一般概述。  
  
## <a name="introduction-to-edi"></a>EDI 介绍  
 电子数据交换 (EDI) 是最常使用的单个意味着业务以电子方式贸易合作伙伴交换数据。 EDI 是很大程度上面向消息的。 文档被实现为平面文件，其中可以包括批处理事务集。 批的交换可以包含多个组，其中每个可以包含多个事务集或消息。  
  
 EDI 由特定的数据交换方法协定的标准主体组成。 主要的 EDI 标准包括 X12 （由 ANSI 进行标准化和主要在北美地区使用） 和 EDIFACT （由联合国进行标准化，主要在美国以外）。 从这些数据，例如，从 X12 的 HIPAA 和从 EDIFACT 韩国的 KEDIFACT 派生出其他标准。 标准近在消息结构和确认架构，但具有一些明显的差异。  
  
 EDI 标准规定了以下：  
  
- 格式、 字符集和文档的交换中使用的数据元素  
  
- EDI 事务中使用的信封  
  
- 验证送达所需的确认  
  
- 如何提供有保障且只-一次传递，并自动检测和报告的已损坏或不正确的数据。  
  
  尽管 EDI 标准确定文档的结构的规则，贸易合作伙伴必须要传输的特定信息和达成应如何使用它。 连接两个贸易合作伙伴的 EDI 系统的设计取决于标准的要求，和贸易合作伙伴达成。 有关 EDI 消息传送的详细信息，请参阅[EDI 消息传送](../core/edi-messaging.md)。  
  
> [!NOTE]
>  EDI 消息而有别于其传输。 EDI 标准不规定消息传输和 EDI 消息可以发送的各种不同的方法。  
  
## <a name="how-edi-is-implemented-in-biztalk-server"></a>在 BizTalk Server 中 EDI 的实现方式  
 BizTalk Server 包括为 EDI 提供支持的固有功能。 EDI 内置于产品中。它不是外接程序，例如适配器或加速器。  
  
 **交换处理**  
  
 强制执行规则的发送端处理管道中的 EDI 标准所规定和 EDI 功能执行以下接收端。  
  
- 处理传入的 EDI 消息，包括验证交换和生成确认。  
  
- 生成并发送传出 EDI 消息，包括验证交换和处理接收到 Ack 取决于配置。  
  
  **批处理**  
  
  批处理由接收管道和业务流程处理：  
  
- 如果收到的批的交换将被拆分，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拆分为其组成事务集，生成每个事务集的 XML 文件并且升级发送端批生成所需的属性。  
  
- 如果收到的批的交换将被保留，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]批进行处理，使它保留在事务集和时收到所包含的组。  
  
- 如果收到的批的交换将进行配置，批处理将接收到传出交换的 EDI 事务集和组。  
  
- 如果多个参与方订阅了某个批交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]向每个参与方发送该批的副本。  
  
  **贸易合作伙伴协议**  
  
  贸易合作伙伴相互定义贸易合作伙伴协议中这是一组在 BizTalk Server 管理控制台中定义的属性。 这些参与方属性，发送和接收端口/位置属性，决定了接收端和发送端 EDI 处理过程。 有关贸易合作伙伴协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
  
  **交换状态**  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可提供特定于 EDI 的状态报告。 这些状态报告提供全面的 EDI 文档交换事务，包括与交换的确认状态。  
  
## <a name="edi-components-in-biztalk-server"></a>在 BizTalk Server 中的 EDI 组件  
 用于 EDI 处理的 Microsoft BizTalk Server 组件包括：  
  
- BizTalk EDI 应用程序包含处理 EDI 文档所需的项目 （包括管道、 业务流程和架构）。  
  
  > [!NOTE]
  >  配置中的 EDI 功能时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，配置程序会创建此应用程序。 每当创建的应用程序将处理 EDI 交换时，必须添加对 BizTalk EDI 应用程序从你的应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
- BizTalk EDI 接收管道 （EdiReceive 管道） 分析 EDI 编码的文档中，拆分 EDI 批、 转换为 XML 编码的 EDI 编码的文档、 执行 EDI 和 XSD 验证和执行 HIPAA X12 子文档拆分。 有关详细信息，请参阅[EDI 接收组件](../core/edi-receive-components.md)。  
  
- BizTalk EDI 发送管道 （EdiSend 管道） 转换为 X12 或 EDIFACT 编码的 XML 文档，序列化 EDI 编码的文档，并执行 EDI 和 XSD 验证。 有关详细信息，请参阅[EDI 发送组件](../core/edi-send-components.md)。  
  
- 贸易合作伙伴管理 (TPM) 用户界面，可设置处理属性为参与 EDI 文档交换和 AS2 文档传输的贸易合作伙伴。 有关详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)并**EDI 和 AS2 用户界面** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- 批处理业务流程批处理 EDI 交换并设置用于发送批处理交换的上下文属性。 路由业务流程处理其中消息匹配多个批次，创建任意多个所需的消息副本的实例。 有关详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)并[批处理传出 EDI 消息](../core/batching-outgoing-edi-messages.md)。  
  
- 状态报告用户界面提供了全面的状态的 EDI 交换和相关确认。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
- 在 Visual Studio 中的设计时工具，可生成实例、 验证实例、 验证架构、 测试映射，以及验证映射。 有关详细信息，请参阅[使用的设计时 XML 工具](../core/using-design-time-xml-tools.md)。  
  
- 架构存储库包括 X12、 EDIFACT、 HIPAA X12N 4010A XSD、 EANCOM 以及控制架构。 有关详细信息，请参阅[EDI 文档架构支持](../core/edi-document-schema-support.md)。  
  
- 迁移工具 （参与方迁移工具），可将 EDI 参与方数据从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移到 BizTalk Server。 有关详细信息，请参阅[从以前版本的 BizTalk Server 迁移 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 中的 EDI 处理](../core/edi-processing-in-biztalk-server.md)   
 [BizTalk Server 中的 HIPAA 支持](../core/hipaa-support-in-biztalk-server.md)   
 [EDI 支持问题](../core/edi-support-issues.md)   
 [EDI 解决方案体系结构](../core/edi-solution-architecture.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)