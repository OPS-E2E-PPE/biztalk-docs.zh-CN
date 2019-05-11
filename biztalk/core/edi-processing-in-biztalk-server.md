---
title: BizTalk Server 中的 EDI 处理 |Microsoft Docs
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
ms.openlocfilehash: 5867707fccda26f0c8938226886d879bdd19d57a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350325"
---
# <a name="edi-processing-in-biztalk-server"></a>BizTalk Server 中的 EDI 处理
本主题概述的 EDI 消息，以及贸易合作伙伴协议如何帮助实现 EDI 消息的接收端和发送端处理。  
  
## <a name="trading-partner-agreements-for-edi-processing"></a>用于 EDI 处理的贸易合作伙伴协议  
 贸易合作伙伴协议在 BizTalk Server 中的 EDI 支持中起重要作用。 大多数配置和管理功能与中的 EDI 处理相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过配置业务配置文件之间的贸易合作伙伴协议来执行。 协议将来自两个合作伙伴的特定业务配置文件的组合在一起的常见双向消息处理属性。 协议基于为每个业务配置文件定义的协议设置。 实现通过定义每个业务配置文件，将交换消息的属性的两个业务配置文件之间的贸易合作伙伴协议。 作为交换接收方和作为交换发送方设置每个业务配置文件的属性。 若要处理的传入消息或生成传出消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要知道可解析为的协议和适用于消息的架构。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议，它将使用 TPM 界面为后备贸易合作伙伴协议中定义的属性。  
  
 有两组主要的编码协议设置在 TPM 中： 一个用于 EDIFACT 属性，一个用于 X12 属性。 近两种属性集。 有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。 贸易合作伙伴管理 (TPM) 用户界面中设置的协议设置和贸易合作伙伴协议。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 无需成为开发人员若要配置中的 EDI 处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 有关贸易合作伙伴协议如何帮助在 EDI 处理中的详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)。  
  
## <a name="edi-receive-side-processing"></a>EDI 接收端处理  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息时，处理该消息在 EDI 接收管道。 接收管道将执行以下基本处理：  
  
- 贸易合作伙伴协议查找和架构确定。  
  
  > [!NOTE]
  >  在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。 因此，当接收管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 使用 BizTalk Server，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，接收管道查找贸易合作伙伴协议专门。  
  > 
  > [!NOTE]
  >  如果某个消息解析到的所有协议将被都禁用，则将挂起消息。 此外在事件日志中记录警告。  
  
- 如果一条 EDI 消息包含多个交换，拆分交换并处理每个交换，单独 （如果启用）。 有关详细信息，请参阅[启用接收的多个交换中一条消息](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)。  
  
- 分析每个 EDI 交换，将转换 X12-或 EDIFACT-编码为 XML 文档的数据。  
  
- 验证信封及其消息根据 EDI 标准、 合作伙伴协议和消息架构。  
  
- 如果批处理交换，则将拆分该批处理的交换，创建所需的批处理、 设置和升级属性的 XML 文件，以便每个事务，或保留该交换。  
  
- 生成确认。  
  
- EDI 信封转换为上下文属性，并将升级用于 EDI 处理其他属性。  
  
- 升级属性用于控制批处理的。 这可能包括将解除批处理后的事务集发送到多个参与方。  
  
  以下是使用 EDI 接收端处理时必须考虑一些注意事项：  
  
- 接收位置可以使用任何类型的传输类型。  
  
- 有关 EDI 接收端处理的详细信息，请参阅[如何 BizTalk Server 接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)。  
  
- 有关由接收管道中的 EDI 拆装器执行的特定处理的详细信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
## <a name="edi-batch-processing"></a>EDI 批处理  
 如果传入消息为批处理，EDI 接收管道将拆分为其组成事务集，该批处理的交换或保留该批处理的交换，具体取决于配置。 EDIReceive 管道使用 BatchMarker 管道组件将对其进行批处理对批处理业务流程或路由业务流程的任何交换路由。  
  
 在接收端处理后要进行批处理以备发送的事务集将由批处理业务流程处理。 批处理业务流程将创建一批基于筛选条件、 激活范围和发布条件。  
  
 如果未批处理的 EDI 事务集需要发送到批次，路由业务流程将处理的事务集。 将创建每个匹配的批处理的事务集的副本。  
  
 在批处理中执行的特定处理的详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)或[批处理传出 EDI 消息](../core/batching-outgoing-edi-messages.md)。  
  
## <a name="edi-send-side-processing"></a>EDI 发送端处理  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成并发送传出 EDI 消息时，它可以处理 EDI 发送管道中的消息。 发送管道执行以下处理：  
  
- 贸易合作伙伴协议查找和架构确定。  
  
  > [!NOTE]
  >  在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。 因此，当发送管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 使用 BizTalk Server，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，发送管道查找贸易合作伙伴协议专门。  
  > 
  > [!NOTE]
  >  如果某个消息解析到的所有协议将被都禁用，则将挂起消息。  此外在事件日志中记录警告。  
  
- 序列化 EDI 消息，将 XML 文档转换成 X12-或 EDIFACT-编码的数据。  
  
- 如果消息数据包含还用作为 X12 的字符分隔符，发送管道可以配置为负载中的字符替换为另一个字符。  
  
- 如果 EDI 消息的批处理的交换，发送管道提取交换从 BizTalk MessageBox 后批处理业务流程生成批。  
  
- 验证传出消息。  
  
- 创建 EDI 信封根据参与方属性或在运行时指定的 EDI 信封属性。  
  
- 处理接收的确认。  
  
  以下是使用 EDI 发送端处理时必须考虑一些注意事项：  
  
- 发送端口可以使用任何类型的传输。  
  
- 有关 EDI 发送端处理的详细信息，请参阅[如何 BizTalk Server 将发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)。  
  
- 在发送管道中执行的特定处理的详细信息，请参阅[EDI 组装器的工作原理](../core/how-the-edi-assembler-works.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 中的 EDI 支持](../core/edi-support-in-biztalk-server1.md)   
 [EDI 支持问题](../core/edi-support-issues.md)   
 [协议在 EDI 处理的角色](../core/the-role-of-agreements-in-edi-processing.md)   
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)   
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)