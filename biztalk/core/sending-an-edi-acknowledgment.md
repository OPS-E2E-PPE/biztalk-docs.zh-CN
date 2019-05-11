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
ms.openlocfilehash: 971d999cdaa839fec2bcb835b114abeb8da31c7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399074"
---
# <a name="sending-an-edi-acknowledgment"></a>发送 EDI 确认
确认指示 EDI 消息传输的状态。 之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 交换，它将一个或多个确认返回到发送方的 EDI 交换，取决于已启用的确认。  
  
 基于级别的验证，EDI 消息确认会分为两种类型：  
  
- 一个**技术确认**作为标头验证的结果生成。 技术确认报告的交换标头和尾部地址接收方处理的状态。  
  
- 一个**功能确认**作为正文验证的结果生成。 功能确认报告在处理收到的文档时遇到的每个错误。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以返回技术和功能确认以响应单个交换。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 返回单个技术确认为每个交换。 对于 X12 交换，它将返回接收到的每个组的功能确认。 对于 EDIFACT 交换，它将返回每个交换，无论该交换包含多少个组的功能确认。  
  
## <a name="x12-acknowledgments"></a>X12 确认  
 **X12 技术确认**  
  
 如果 ISA 标头和 IEA 尾部，则会发送肯定的 TA1 确认的 X12 消息是有效 （不考虑其他内容）。 有关内容 TA1 确认的详细信息，请参阅[X12 TA1 确认](../core/x12-ta1-acknowledgment.md)。  
  
 **X12 功能确认**  
  
 997 确认用于确认接收的交换或功能组中，接受或拒绝一个或多个功能组或一个或多个事务，还可以验证和报告与标准符合性。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收交换具有多个组，它将返回每个组的确认。 如果一个组中包含多个事务集，该组的确认将包含多个 AK2 循环，为接受的事务集生成一个用于每个事务集，取决于是否 AK2 循环。 内容将 997 确认的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。  
  
> [!NOTE]
>  当 EDI 接收管道生成的 X12 功能细分功能组标头 (GS) 确认、 应用程序发送方代码 (GS02) 和应用程序接收方代码 (GS03) 取自正在确认的功能组。 但是，传入消息上的 GS02 映射到确认上 GS03 和 GS03 上传入的消息映射到 GS02。  
  
## <a name="edifact-acknowledgments"></a>EDIFACT 确认  
 **EDIFACT 技术确认**  
  
 对于 EDIFACT，未使用单独的技术确认，但部分功能确认或 CONTRL 确认 （见下文） 重新用于回执确认。 这模拟的技术确认。  
  
 有关技术 CONTRL 确认的详细信息，请参阅[作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)。  
  
 **EDIFACT 功能确认**  
  
 对于 EDIFACT，功能 CONTRL 确认用于确认收到的交换、 组和消息;接受或拒绝收到的交换、 组和消息;用于列出任何语法错误或不受支持的功能，其中包含的和。 CONTRL ACK 报告收到的完整交换的语法检查结果。  
  
 有关功能 CONTRL 确认的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。  
  
## <a name="when-an-acknowledgment-is-generated"></a>何时生成确认  
 EDI 接收管道会生成一个确认，如果满足以下条件之一：  
  
- 收到的交换中的数据元素提示确认。 对于 X12 编码的消息，接收管道会生成技术 TA1 确认，如果 ISA14 数据元素设置为 1。 对于 EDIFACT 编码的消息，接收管道会生成技术 CONTRL 确认，如果 UNB9 数据元素设置为 2，并且如果 UNB9 数据元素设置为 1，它将生成功能 CONTRL 确认。  
  
- 协议属性提示确认。 对于 X12 交换，这些属性是**预期的 TA1**并**预期的 997**中的属性**确认**的双向协议选项卡的页面**协议属性**对话框。 对于 EDIFACT 交换，这些属性是**预期接收消息 (CONTRL)** 并**确认 (CONTRL) 预期**中**确认**页双向协议选项卡的**协议属性**对话框。 当启用一种确认类型时，您还可以指示是否批处理该类型的确认。  
  
- 为交换确定没有协议时，全局属性会提示确认。 这些属性是  
  
  -   **预期的 TA1**并**预期的 997**中的属性**确认**页上的协议选项卡**X12 后备设置**对话框。  
  
  -   **预期接收消息 (CONTRL)** 并**确认 (CONTRL) 预期**中**确认**的协议选项卡页**EDIFACT 后备设置**对话框。  
  
  对于 EDIFACT，EDI 接收管道将返回两个独立的 CONTRL 确认，如果一个技术确认和功能确认提示。 技术 CONTRL 确认将包括回执确认信息。 功能 CONTRL 确认将包含回执信息和功能确认信息。 有关详细信息，请参阅[EDIFACT CONTRL 确认](../core/edifact-contrl-acknowledgment.md)。  
  
## <a name="identifying-an-acknowledgment-with-a-control-number"></a>标识确认控制编号与  
 每个确认需要由 X12 （ST2 数据元素） 的事务集控制编号标识，或对于 EDIFACT （UNH1 数据元素） 的事务集参考编号。 如果为传出确认配置协议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将设置为根据以下协议设置的值的事务集控制编号或参考编号：  
  
- **对于 X12 确认**– (**确认控制编号 (ST02)** 中的属性**本地主机设置**页 (**接收方设置**部分) 的协议选项卡在中**协议属性**对话框  
  
- **对于 EDIFACT 确认**– (**Edifact 确认控制编号**中的属性**本地主机设置**页 (**接收方设置**部分) 的在协议选项卡**协议属性**对话框  
  
  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能确定协议对于确认，它将使用与上述中的协议选项卡上提供相同的属性**X12 后备设置**ad **EDIFACT 回退设置**对话框。 如果二者都已配置，此设置适用于技术和功能确认。 将由另一个用于每个确认或生成交换递增此整数。  
  
  确认的信封根据确认控制架构对收到的消息中的数据从生成。  
  
## <a name="preparing-the-acknowledgment"></a>准备确认  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成确认的信封，就像通过查看交换控制标头和功能组标头的定义来生成一条消息的信封一样。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
 以启用无缝路由生成确认 (TA1、 997 或 CONTRL)，EDI 拆装器将填充`DestinationPartyReceiverQualifier`， `DestinationPartyReceiverIdentifier`， `DestinationPartySenderQualifier`，和`DestinationPartySenderIdentifier`在确认上的属性。  
  
## <a name="synchronous-and-asynchronous-acknowledgments"></a>同步和异步确认  
 您可以选择同步或异步发送 EDI 确认。 如果同步的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将路由到双向请求-响应的发送管道直接确认接收端口。 如果异步的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将确认路由到 MessageBox，和一个发送端口订阅该消息。  
  
 若要指定的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送确认以同步方式，选择**确认路由到发送管道请求-响应接收端口**中**本地主机设置**页 (**接收方设置**一节) 下**交换设置**的双向协议选项卡 （针对 X12 和 EDIFACT 协议） 中。 如果清除此属性，发送管道的双向接收端口必须设置为返回 EDI 交换。  
  
 如果方案使用的请求-响应接收端口和两个技术确认和功能确认都已启用、 技术确认将会同步发回，并将返回发送功能确认以异步方式。  
  
 当通过接收 EDIINT/AS2 编码的消息 （同一套接字上），HTTP/HTTPS，如果 MDN 已发送响应以 mime 包装的 EDI 负载，然后 EDI 确认将不会同步发出。 如果在这种情况下**将确认路由到发送管道请求-响应接收端口**属性为选中状态，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会忽略此属性。  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)   
 [EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)   
 [X12 TA1 确认](../core/x12-ta1-acknowledgment.md)   
 [X12 997 确认](../core/x12-997-acknowledgment.md)   
 [EDIFACT CONTRL 确认](../core/edifact-contrl-acknowledgment.md)   
 [作为技术确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-technical-acknowledgment.md)   
 [作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)