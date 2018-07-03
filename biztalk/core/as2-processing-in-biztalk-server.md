---
title: AS2 在 BizTalk Server 中的处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0027d3db-24a5-459d-9f4e-a75f49d31d82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69c778df5ccafc11a5a3a8aef4326138d54c4596
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013078"
---
# <a name="as2-processing-in-biztalk-server"></a>BizTalk Server 中的 AS2 处理
本主题概述了 AS2 消息的接收端和发送端处理过程以及贸易合作伙伴协议将如何帮助您实现 AS2 消息传送。  
  
## <a name="trading-partner-agreements-for-as2-processing"></a>用于 AS2 处理的贸易合作伙伴协议  
 贸易合作伙伴协议在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 支持中起着重要作用。 与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 处理相关的大多数配置和管理功能是通过配置业务配置文件之间的贸易合作伙伴协议来执行的。 协议集中了处理各种属性（来自合作伙伴双方的特定业务配置文件）的常见双向消息。 协议基于为每个业务配置文件定义的协议设置构建。 可通过为将交换消息的每个业务配置文件定义属性来实现两个业务配置文件之间的贸易合作伙伴协议。 在贸易合作伙伴管理 (PAM) 用户界面中设置作为 AS2 消息接收方和 AS2 消息发送方的每个业务配置文件的属性。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 您无需是开发人员即可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置 AS2 处理。  
  
 您可以作为业务配置文件的“传输协议设置”的一部分指定 AS2 属性，也可以通过在贸易合作伙伴协议中直接指定 AS2 设置来指定 AS2 属性。 有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  您可设置特定于 AS2 的属性来配置下列 AS2 功能：  
  
- 选择不可否认存储选项  
  
- 为传出消息指定签名、压缩或加密属性  
  
- 为传出消息请求 MDN  
  
- 通过替代 AS2 消息标头中的签名、压缩、加密和 MDN 属性可设置传入 MDN 的属性。  
  
  有关贸易合作伙伴协议如何帮助在 AS2 处理中的详细信息，请参阅[协议的角色中的 AS2 处理](../core/the-role-of-agreements-in-as2-processing.md)。  
  
> [!NOTE]
>  AS2 处理没有全局属性，这与 EDI 处理不同。  
  
## <a name="as2-receive-side-processing"></a>AS2 接收方处理  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收一个 AS2 消息后，它将在 AS2 接收管道中处理该消息。 系统中存在一个用于通过 AS2 接收 EDI 消息的管道 (AS2EdiReceive)，此管道执行 AS2 和 EDI 处理。 另一个管道 (AS2Receive) 只对通过 AS2 接收的非 EDI 消息执行 AS2 处理。  
  
 AS2 接收方处理包括下列操作：  
  
- 贸易合作伙伴协议查找  
  
  > [!NOTE]
  >  在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。 因此，当接收管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，由于参与方（或贸易合作伙伴）与贸易合作伙伴协议截然不同，因此接收管道将特别查找贸易合作伙伴协作。  
  > 
  > [!NOTE]
  >  如果禁用某个消息解析到的所有协议，则该消息将被挂起。  还会在“事件”日志中记录警告。  
  
- 在不可否认数据库中保存消息副本  
  
- 检查重复的消息  
  
- 处理包含多个文档的消息  
  
- 从 MIME 信封中检索文档文件名称  
  
- 解密消息  
  
- 解压缩消息  
  
- 验证消息的数字签名。  
  
- 生成 HTTP 响应  
  
- 生成 MDN 响应  
  
  以下是您在使用 AS2 接收端处理时必须考虑的一些注意事项：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以同步或异步模式返回一个 MDN。 如果将以异步方式返回 MDN，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须通过一个单独的发送端口发送它。  
  
- 通过 AS2 接收非 EDI 文件（非 XML），并且需要执行非 EDI 负载的拆装时，您将需要一种具有第二个接收管道的环回机制。 有关详细信息，请参阅[接收方处理通过 AS2 传入的非 EDI 消息的](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md)。  
  
- 接收位置只能使用 HTTP 适配器。  
  
- 有关 AS2 接收方处理的详细信息，请参阅[如何 BizTalk Server 接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)。  
  
- 有关由接收管道中的 AS2 拆装器执行的特定处理的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="as2-send-side-processing"></a>AS2 接收方处理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成并发送传出 AS2 消息时，将在 AS2 发送管道中处理该消息。 系统中存在一个用于通过 AS2 发送 EDI 消息的管道 (AS2EdiSend)，此管道执行 AS2 和 EDI 处理。 另一个管道 (AS2Send) 只对通过 AS2 发送的非 EDI 消息执行 AS2 处理。  
  
 AS2 发送方处理包括下列操作：  
  
- 贸易合作伙伴协议查找  
  
  > [!NOTE]
  >  在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。 因此，当发送管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，由于参与方（或贸易合作伙伴）与贸易合作伙伴协议截然不同，因此发送管道将特别查找贸易合作伙伴协作。  
  > 
  > [!NOTE]
  >  如果禁用某个消息解析到的所有协议，则该消息将被挂起。  还会在“事件”日志中记录警告。  
  
- 在不可否认数据库中保存消息副本  
  
- 应用 AS2 信封  
  
- 发送多个文档  
  
- 作为 MIME 信封的一部分存储每个文档的文件名  
  
- 签名消息  
  
  > [!NOTE]
  >  通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以覆盖默认签名证书，改用在协议中认可的证书。 有关重写默认传出消息进行签名的证书的说明，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
- 压缩消息  
  
- 对消息进行加密  
  
- 为 MDN 计算一个 MIC 值  
  
- 处理传入 MDN（在同步 MDN 情况下）  
  
- 如果未收到 MDN，则重新发送消息  
  
  以下是您在使用 AS2 接收端处理时必须考虑的一些注意事项：  
  
- 发送端口只能使用 HTTP 适配器。  
  
- 有关 AS2 发送方处理的详细信息，请参阅[如何 BizTalk Server 将发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)。  
  
- 在发送管道中执行的特定处理的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [协议在 AS2 处理的角色](../core/the-role-of-agreements-in-as2-processing.md)   
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)