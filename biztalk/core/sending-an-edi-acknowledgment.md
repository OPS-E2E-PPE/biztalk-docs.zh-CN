---
title: 发送 EDI 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a036d08-8a65-43ad-b72c-2a246d302792
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 323913bcd4104304f3971ac3eb0c0e37ee8d6354
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011430"
---
# <a name="sending-an-edi-acknowledgment"></a>发送 EDI 确认
确认指示 EDI 消息传输的状态。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到 EDI 交换后，会根据已启用的确认将一个或多个确认返回给 EDI 交换的发送方。  
  
 基于验证的级别，EDI 消息确认会分为两种类型：  
  
- 一个**技术确认**作为标头验证的结果生成。 技术确认报告地址接收方对交换标头和尾部的处理的状态。  
  
- 一个**功能确认**作为正文验证的结果生成。 功能确认报告在处理所接收文档时遇到的每个错误。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以返回技术和功能确认以响应单个交换。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 返回单个技术确认为每个交换。 对于 x12 交换，它将为收到的每个组返回功能确认。 对于 EDIFACT 交换，它将为每个交换返回功能确认，而无论该交换包含多少个组。  
  
## <a name="x12-acknowledgments"></a>X12 确认  
 **X12 技术确认**  
  
 如果 X12 消息的 ISA 标头和 IEA 尾部都有效（不考虑其他内容），则会发出肯定的 TA1 确认。 有关内容 TA1 确认的详细信息，请参阅[X12 TA1 确认](../core/x12-ta1-acknowledgment.md)。  
  
 **X12 功能确认**  
  
 997 确认用于确认对交换或功能组的接受，接受或拒绝一个或多个功能组或者一项或多项事务，以及确认并报告与标准的符合情况。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到具有多个组的交换，将为每个组返回确认。 如果某个组包含多个事务集，该组的确认将根据是否为接受的事务集生成 AK2 循环而包含多个 AK2 循环（每个事务集一个循环）。 内容将 997 确认的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。  
  
> [!NOTE]
>  当 EDI 接收管道为 X12 功能确认构建功能组标头 (GS) 段时，会从正被确认的功能组摘取应用程序发送方代码 (GS02) 和应用程序接收方代码 (GS03)。 但是，传入消息上的 GS02 会映射到确认上的 GS03，GS03 映射到确认上的 GS02。  
  
## <a name="edifact-acknowledgments"></a>EDIFACT 确认  
 **EDIFACT 技术确认**  
  
 对于 EDIFACT，不会使用单独的技术确认，但技术确认或 CONTRL 确认部分（参见下面的内容）却可重复用于确认回执。 这是模拟的技术确认。  
  
 有关技术 CONTRL 确认的详细信息，请参阅[作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)。  
  
 **EDIFACT 功能确认**  
  
 对于 EDIFACT，功能 CONTRL 确认用于确认收到的交换、组和消息，接受或拒绝收到的交换、组和消息，并列出其中包含的所有语法错误以及不受支持的功能。 CONTRL 确认报告对已完全收到的交换所进行的语法检查的结果。  
  
 有关功能 CONTRL 确认的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。  
  
## <a name="when-an-acknowledgment-is-generated"></a>何时生成确认  
 如果满足以下条件之一，EDI 接收管道就会生成一个确认：  
  
- 收到的交换中的数据元素提示确认。 对于 X12 编码的消息，接收管道会生成技术 TA1 确认，如果 ISA14 数据元素设置为 1。 对于 EDIFACT 编码的消息，接收管道会生成技术 CONTRL 确认，如果 UNB9 数据元素设置为 2，并且如果 UNB9 数据元素设置为 1，它将生成功能 CONTRL 确认。  
  
- 协议属性提示确认。 对于 X12 交换，这些属性是**预期的 TA1**并**预期的 997**中的属性**确认**的双向协议选项卡的页面**协议属性**对话框。 对于 EDIFACT 交换，这些属性是**预期接收消息 (CONTRL)** 并**确认 (CONTRL) 预期**中**确认**页双向协议选项卡的**协议属性**对话框。 当启用一种确认类型后，还可以指明是否批处理该类型的确认。  
  
- 如果没有为交换确定协议，全局属性会提示确认。 这些属性是  
  
  -   **预期的 TA1**并**预期的 997**中的属性**确认**页上的协议选项卡**X12 后备设置**对话框。  
  
  -   **预期接收消息 (CONTRL)** 并**确认 (CONTRL) 预期**中**确认**的协议选项卡页**EDIFACT 后备设置**对话框。  
  
  对于 EDIFACT，如果技术确认和功能确认同时被提示，EDI 接收管道会返回两个独立的 CONTRL 确认。 技术 CONTRL 确认只包括确认回执信息。 功能 CONTRL 确认则包含回执信息和功能确认信息。 有关详细信息，请参阅[EDIFACT CONTRL 确认](../core/edifact-contrl-acknowledgment.md)。  
  
## <a name="identifying-an-acknowledgment-with-a-control-number"></a>使用控制编号标识确认  
 每个确认都要用用于 X12 的事务集控制编号（ST2 数据元素）或用于 EDIFACT 的事务集参考编号（UNH1 数据元素）来标识。 如果为传出确认配置协议，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将事务集控制编号或参考编号设置为根据以下各项为协议设置的值：  
  
- **对于 X12 确认**– (**确认控制编号 (ST02)** 中的属性**本地主机设置**页 (**接收方设置**部分) 的协议选项卡在中**协议属性**对话框  
  
- **对于 EDIFACT 确认**– (**Edifact 确认控制编号**中的属性**本地主机设置**页 (**接收方设置**部分) 的在协议选项卡**协议属性**对话框  
  
  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能确定协议对于确认，它将使用与上述中的协议选项卡上提供相同的属性**X12 后备设置**ad **EDIFACT 回退设置**对话框。 此设置适用于技术确认和功能确认（如果二者都已配置）。 每生成一个确认或交换，该整数都将递增 1。  
  
  确认的信封根据确认控制架构利用接收到的消息中的数据生成。  
  
## <a name="preparing-the-acknowledgment"></a>准备确认  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为确认生成信封的方法，就像为消息生成信封一样，通过查看交换控制标头和功能组标头的定义来完成。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
 为启用生成确认（TA1、997 或 CONTRL）的无缝路由，EDI 拆装器会在确认上填充 `DestinationPartyReceiverQualifier`、`DestinationPartyReceiverIdentifier`、`DestinationPartySenderQualifier` 和 `DestinationPartySenderIdentifier` 属性。  
  
## <a name="synchronous-and-asynchronous-acknowledgments"></a>同步和异步确认  
 您可以选择以同步还是异步的方式来发送 EDI 确认。 如果选择同步发送，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会直接将确认路由到双向请求-响应接收端口的发送管道。 如果选择异步发送，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将确认路由到 MessageBox，同时会有一个发送端口订阅该消息。  
  
 若要指定的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送确认以同步方式，选择**确认路由到发送管道请求-响应接收端口**中**本地主机设置**页 (**接收方设置**一节) 下**交换设置**的双向协议选项卡 （针对 X12 和 EDIFACT 协议） 中。 如果清除该属性，双向接收端口的发送管道则必须设置为返回 EDI 交换。  
  
 如果方案使用的是请求-响应接收端口，并且技术确认和功能确认都已启用，则技术确认就会同步发回，而功能确认则异步发回。  
  
 通过 HTTP/HTTPS 接收 EDIINT/AS2 编码的消息时，如果在对同一套接字上的以 MIME 包装的 EDI 负载的响应中有 MDN 发出，EDI 确认就不会同步发出。 如果在这种情况下**将确认路由到发送管道请求-响应接收端口**属性为选中状态，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会忽略此属性。  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)   
 [EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)   
 [X12 TA1 确认](../core/x12-ta1-acknowledgment.md)   
 [X12 997 确认](../core/x12-997-acknowledgment.md)   
 [EDIFACT CONTRL 确认](../core/edifact-contrl-acknowledgment.md)   
 [作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)   
 [作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)