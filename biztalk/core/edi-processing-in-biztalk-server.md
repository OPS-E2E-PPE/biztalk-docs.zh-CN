---
title: BizTalk Server 中的 EDI 处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc60423-24b6-4920-a870-520f575085ed
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b68781707211922d7d29958f896608c87358c7c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008678"
---
# <a name="edi-processing-in-biztalk-server"></a>BizTalk Server 中 EDI 处理
本主题概述了 EDI 消息的接收端和发送端处理过程，以及贸易合作伙伴协议如何帮助实现 EDI 消息。  
  
## <a name="trading-partner-agreements-for-edi-processing"></a>用于 EDI 处理的贸易合作伙伴协议  
 贸易合作伙伴协议在 BizTalk Server 中的 EDI 支持中扮演着关键作用。 大多数与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中 EDI 处理相关的配置和管理功能可通过配置业务配置文件之间的贸易合作伙伴协议来执行。 协议集中了处理各种属性（来自合作伙伴双方的特定业务配置文件）的常见双向消息。 协议基于为每个业务配置文件定义的协议设置构建。 可通过为将交换消息的每个业务配置文件定义属性来实现两个业务配置文件之间的贸易合作伙伴协议。 可为每个作为交换接收方的业务配置文件以及作为交换发送方的业务配置文件设置属性。 若要处理传入消息或生成传出消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要了解解析该消息的协议，以及适用于该消息的架构。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，它将使用 TPM 界面中为后备贸易合作伙伴协议定义的属性。  
  
 TPM 中有两组主要的编码协议设置：一组用于 EDIFACT 属性，另一组用于 X12 属性。 属性的两个集是密切并行的。 有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。 可在贸易合作伙伴管理 (TPM) 用户界面中设置协议设置和贸易合作伙伴协议。 TPM 屏幕处于**方**节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 您无须是开发人员即可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置 EDI 处理。  
  
 有关如何贸易合作伙伴协议 EDI 处理帮助的详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)。  
  
## <a name="edi-receive-side-processing"></a>EDI 接收端处理  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收一个 EDI 消息后，它将在 EDI 接收管道中处理该消息。 接收管道执行以下基本处理：  
  
-   贸易合作伙伴协议查找和架构确定。  
  
    > [!NOTE]
    >  在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。 因此，当接收管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 与 BizTalk Server 中，因为方 （或贸易合作伙伴） 不同于贸易合作伙伴协议，接收管道中寻找贸易合作伙伴协议专门。  
  
    > [!NOTE]
    >  如果禁用某个消息解析到的所有协议，则该消息将被挂起。 还会在“事件”日志中记录警告。  
  
-   当单个 EDI 消息中包含多个交换，拆分的交换，并处理每次交换单独 （如果启用）。 有关详细信息，请参阅[启用接收的多个交换单一消息](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)。  
  
-   解析每个 EDI 交换，同时将 X12 编码数据或 EDIFACT 编码数据转换为 XML 文档。  
  
-   根据 EDI 标准、合作伙伴协议和消息架构验证信封及其消息。  
  
-   如果交换为批处理交换，则可以拆分该批处理交换，同时为每个事务集创建 XML 文件并升级批处理所需的属性；或者保留该交换。  
  
-   生成确认。  
  
-   将 EDI 信封转换为上下文属性，并升级用于 EDI 处理的其他属性。  
  
-   升级用于控制批处理的属性。 执行此操作可能会将解除批处理后的事务集发送给多个参与方。  
  
 以下是您在使用 EDI 接收端处理时必须考虑的一些注意事项：  
  
-   接收位置可以使用任何类型的传输类型。  
  
-   有关 EDI 接收方处理的详细信息，请参阅[如何 BizTalk Server 接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)。  
  
-   有关特定的处理由 EDI 拆装器接收管道中执行的详细信息，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
## <a name="edi-batch-processing"></a>EDI 批处理  
 如果传入消息为一批消息，则 EDI 接收管道会将该批处理交换拆分为其组成事务集，或保留该批处理交换，具体取决于配置。 EDIReceive 管道会使用 BatchMarker 管道组件将任何要进行批处理的交换路由至批处理业务流程或路由业务流程。  
  
 在接收端处理之后，要进行批处理以备发送的事务集将由批处理业务流程进行处理。 批处理业务流程将基于筛选条件、激活范围和发布条件创建批。  
  
 如果未经过批处理的 EDI 事务集需要发送给多个批，则路由业务流程将处理该事务集。 将为每个匹配的批处理创建该事务集的副本。  
  
 有关执行批处理中的特定处理的详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)或[批处理传出的 EDI 消息](../core/batching-outgoing-edi-messages.md)。  
  
## <a name="edi-send-side-processing"></a>EDI 发送端处理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成并发送传出 EDI 消息时，将在 EDI 发送管道中处理该消息。 发送管道执行以下处理：  
  
-   贸易合作伙伴协议查找和架构确定。  
  
    > [!NOTE]
    >  在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。 因此，当发送管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 与 BizTalk Server 中，因为不同于贸易合作伙伴协议，方 （或贸易合作伙伴） 发送管道查找贸易合作伙伴协议专门。  
  
    > [!NOTE]
    >  如果禁用某个消息解析到的所有协议，则该消息将被挂起。  还会在“事件”日志中记录警告。  
  
-   序列化 EDI 消息，同时将 XML 文档转换为 X12 编码数据或 EDIFACT 编码数据。  
  
-   如果消息数据包含还用作为 X12 分隔符的字符，则可以将发送管道配置为使用其他字符替换负载中的字符。  
  
-   如果 EDI 消息为批处理交换，则发送管道会在批处理业务流程生成批之后从 BizTalk MessageBox 提取该交换。  
  
-   验证传出消息。  
  
-   根据参与方属性或运行时指定的 EDI 信封属性创建 EDI 信封。  
  
-   处理收到的确认。  
  
 以下是在使用 EDI 发送端处理期间必须考虑的一些注意事项：  
  
-   发送端口可以使用任何传输类型。  
  
-   有关 EDI 发送方处理的详细信息，请参阅[如何 BizTalk Server 发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)。  
  
-   有关在发送管道中执行的特定处理的详细信息，请参阅[EDI 汇编程序的工作原理](../core/how-the-edi-assembler-works.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk Server EDI 支持](../core/edi-support-in-biztalk-server1.md)   
 [EDI 支持问题](../core/edi-support-issues.md)   
 [协议在 EDI 处理过程中的角色](../core/the-role-of-agreements-in-edi-processing.md)   
 [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server 将 EDI 消息的发送](../core/how-biztalk-server-sends-edi-messages.md)   
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)