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
ms.openlocfilehash: ea65fea589d0d5bdd69de1e9fcd762c27e6b28c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358881"
---
# <a name="as2-processing-in-biztalk-server"></a>在 BizTalk Server 中的 AS2 处理
本主题概述了 AS2 消息和贸易合作伙伴协议如何帮助实现 AS2 消息传送的接收端和发送端处理。  
  
## <a name="trading-partner-agreements-for-as2-processing"></a>用于 AS2 处理贸易合作伙伴协议  
 贸易合作伙伴协议中的 AS2 支持中扮演着关键角色[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 大多数配置和管理功能与中的 AS2 处理相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过配置业务配置文件之间的贸易合作伙伴协议来执行。 协议将来自两个合作伙伴的特定业务配置文件的组合在一起的常见双向消息处理属性。 协议基于为每个业务配置文件定义的协议设置。 实现通过定义每个业务配置文件，将交换消息的属性的两个业务配置文件之间的贸易合作伙伴协议。 贸易合作伙伴管理 (TPM) 用户界面中为 AS2 消息接收方和 AS2 消息发送方设置为每个业务配置文件的属性。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 无需成为开发人员若要配置中的 AS2 处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 可以指定 AS2 属性的"传输协议设置"为业务配置文件或通过直接在贸易合作伙伴协议中指定 AS2 设置的一部分。 有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。 有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  通过设置特定于 AS2 的属性来配置下列 AS2 功能：  
  
- 选择不可否认存储选项  
  
- 指定传出消息的签名、 压缩或加密的属性  
  
- 传出消息的请求 Mdn  
  
- 通过重写签名、 压缩、 加密和 MDN 的 AS2 消息标头中的属性设置为传入 Mdn 的属性。  
  
  有关贸易合作伙伴协议如何帮助在 AS2 处理中的详细信息，请参阅[协议的角色中的 AS2 处理](../core/the-role-of-agreements-in-as2-processing.md)。  
  
> [!NOTE]
>  与 EDI 处理有 AS2 处理没有全局属性。  
  
## <a name="as2-receive-side-processing"></a>AS2 接收方处理  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 AS2 消息时，处理该消息中 AS2 接收管道。 没有用于通过 AS2 接收 EDI 消息的管道 (AS2EdiReceive)，该文件将执行 AS2 和 EDI 处理。 另一个管道 (AS2Receive) 只对执行 AS2 处理通过 AS2 接收非 EDI 消息。  
  
 AS2 接收方处理包括以下操作：  
  
- 贸易合作伙伴协议查找  
  
  > [!NOTE]
  >  在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。 因此，当接收管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，贸易合作伙伴协议则接收管道看起来特别。  
  > 
  > [!NOTE]
  >  如果某个消息解析到的所有协议将被都禁用，则将挂起消息。  此外在事件日志中记录警告。  
  
- 不可否认数据库中保存消息的副本  
  
- 检查重复消息  
  
- 处理包含多个文档的消息  
  
- 从 MIME 信封中检索文档文件名称  
  
- 解密消息  
  
- 解压缩消息  
  
- 验证消息的数字签名  
  
- 生成 HTTP 响应  
  
- 生成 MDN 响应  
  
  以下是使用 AS2 接收端处理时必须考虑一些注意事项：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以同步或异步模式返回一个 MDN。 如果将以异步方式返回 MDN[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须通过单独的发送端口发送它。  
  
- 当通过 AS2 接收非 EDI 文件 (非 XML) 并且需要执行的非 EDI 负载的拆装时，您将需要使用需要使用第二个接收管道的环回机制。 有关详细信息，请参阅[接收方处理通过 AS2 传入的非 EDI 消息的](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md)。  
  
- 接收位置只能使用 HTTP 适配器。  
  
- 有关 AS2 接收方处理的详细信息，请参阅[如何 BizTalk Server 接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)。  
  
- 有关由接收管道中的 AS2 拆装器执行的特定处理的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  
  
## <a name="as2-send-side-processing"></a>AS2 发送方处理  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成并发送传出 AS2 消息时，处理该消息在 AS2 发送管道中的。 没有用于通过 AS2 发送 EDI 消息的管道 (AS2EdiSend)，该文件将执行 AS2 和 EDI 处理。 另一个管道 (AS2Send) 只对执行 AS2 处理通过 AS2 发送非 EDI 消息。  
  
 AS2 发送方处理包括以下组件：  
  
- 贸易合作伙伴协议查找  
  
  > [!NOTE]
  >  在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。 因此，当发送管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，贸易合作伙伴协议则发送管道看起来特别。  
  > 
  > [!NOTE]
  >  如果某个消息解析到的所有协议将被都禁用，则将挂起消息。  此外在事件日志中记录警告。  
  
- 不可否认数据库中保存消息的副本  
  
- 应用 AS2 信封  
  
- 发送多个文档  
  
- 作为 MIME 信封的一部分存储每个文档的文件名  
  
- 签名消息  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使你能够重写默认签名证书并改为使用证书达成协议中。 有关重写默认传出消息进行签名的证书的说明，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
- 压缩消息  
  
- 对消息进行加密  
  
- 为 MDN 计算一个 MIC 值  
  
- 处理传入 MDN （对于同步 MDN)  
  
- 如果不收到任何 MDN 则重新发送消息  
  
  以下是使用 AS2 接收端处理时必须考虑一些注意事项：  
  
- 发送端口只能使用 HTTP 适配器。  
  
- 有关 AS2 发送方处理的详细信息，请参阅[如何 BizTalk Server 将发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)。  
  
- 在发送管道中执行的特定处理的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [协议在 AS2 处理的角色](../core/the-role-of-agreements-in-as2-processing.md)   
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)   
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)