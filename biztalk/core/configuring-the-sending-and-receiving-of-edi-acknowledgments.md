---
title: 配置发送和接收的 EDI 确认的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3db1c9f7-bafa-4659-a3c4-0faa56606081
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0443ea2ac3573bc960978075223cf7a2871a473
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000390"
---
# <a name="configuring-the-sending-and-receiving-of-edi-acknowledgments"></a>配置 EDI 确认的发送和接收
若要配置 EDI 确认的发送以响应接收交换，您需要执行以下操作：  
  
-   在接收的交换解析到的协议中启用确认。 通过执行此操作，将声明发送交换的参与方期望得到确认。  
  
-   如果需要在设置特定属性（如启用 CR LF、使用不同分隔符等）后发回确认，请在另一个单向协议选项卡中设置这些属性。通过执行此操作，可以配置参与方发回确认的方式。  
  
    > [!NOTE]
    >  如果交换解析为协议中定义**PartyA-> 参与**选项卡上，应如何生成确认相关的属性中配置**参与-> PartyA**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**PartyA-> 参与**选项卡。例如，如果发送方和接收方标识符在交换消息要向其解析的协议中设置为 THEM 和 US，则发送方和接收方的上下文属性在确认中将设置为 US 和 THEM。 通常，其他单向协议选项卡中的发送方和接收方标识符也应分别设置为 US 和 THEM。 因此，确认消息将解析为该协议，并且将提取属性设置。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**参与-> PartyA**选项卡。  
  
     从概念上讲，将从任何单向协议选项卡上提取具有与确认上下文属性中设置的相同发件人和接收方限定符的确认的属性。 但是，为了便于实际使用，你通常会在你创建的交换将解析为的协议的其他单向协议选项卡中设置此属性。  
  
-   如果您是将 EDI 确认发回到发送原始交换的参与方的参与方，请设置一个单向发送端口以选择该确认并发送，或设置一个双向接收端口以发送确认。 有关详细信息，请参阅[配置为发送 EDI 交换和确认的静态发送端口](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)。  
  
-   如果您是期望得到 EDI 确认的参与方，请设置一个双向发送端口或一个单向接收端口以接收确认。 有关详细信息，请参阅[配置为接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。  
  
-   BizTalk EDI 应用程序包含控制架构。 因此，包含您的 EDI 解决方案的应用程序必须包含指向 BizTalk EDI 应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-request-an-acknowledgment-for-the-party-that-sent-the-original-interchange"></a>为发送原始交换的参与方请求确认  
  
1. > [!NOTE]
   >  通过执行此过程中的步骤，将配置发送交换的参与方期望返回确认。  
  
    在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**页上，单击具有您需要为其启用确认的协议的参与方。 在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。 在中**协议属性**对话框单向协议选项卡 （向其入站的交换将解析） 中，执行以下操作：  
  
   1. 在中**标识符**页上，输入的值在发送方和接收方限定符。  
  
       对于 X12 编码的确认，请输入 ISA5、ISA6、ISA7 和 ISA8 的值。 对于 ISA5 和 ISA6，请输入将发送交换的参与方的值。 对于 ISA7 和 ISA8，请输入将接收交换的参与方的值。  
  
       对于 EDIFACT 编码的确认，UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 输入值。 对于 UNB2.1 和 UNB2.2，输入将发送交换的参与方的值。 对于 UNB3.1 和 UNB3.2，请输入将接收交换的参与方的值。  
  
   2. 在中**确认**页上，选择属性定义的发送方预期确认种类：  
  
       对于 X12 确认，选择**预期的 TA1**和/或**预期的 997**根据确认预期。 对于每个确认类型，选择**进行批处理\<ACK 类型\>** 如果需要确认作为单独的交换发送的每个实例。  
  
       对于 EDIFACT 确认，请选择**预期接收消息 (CONTRL)** 和/或**确认 (CONTRL) 预期**根据确认预期。 对于每个确认类型，选择**进行批处理\<ACK 类型\>** 如果需要确认作为单独的交换发送的每个实例。  
  
   3. 在中**本地主机设置**页**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**返回以异步方式通过单向发送端口的确认。 保持选中此属性可通过双向接收端口同步返回确认。  
  
   4. 在中**发送端口**页上，在**名称**的列**发送端口**网格中，选择已设置为发送确认的发送端口。  
  
      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用该发送端口设置来确定处理消息时所用的参与方。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
      > 
      > [!NOTE]
      >  如果尚未设置发送端口，则可能须在稍后执行此步骤。  
  
### <a name="to-configure-how-the-party-sends-the-acknowledgement-back"></a>配置参与方如何发回确认  
  
1. > [!NOTE]
   >  通过执行此过程中的步骤，可以配置接收交换的参与方如何发回确认。  
  
    在同一**协议属性**对话框中的，其他单向协议选项卡中，执行以下操作：  
  
   1. 在中**标识符**页上，输入的值在发送方和接收方限定符。  
  
      > [!NOTE]
      >  发送确认时，接收原始交换的参与方将变成发送方，发送原始交换的参与方将变成接收方。 因此，您在“标识符”页输入的值现在与上一步骤中在单向协议选项卡中输入的值相反。 这有两种用途：  
      > 
      > - 因为确认的发送方和接收方上下文属性现在将与您在“标识符”页输入的发送方和接收方值匹配，所以发回的确认将解析为您正创建的单向协议。  
      >   -   可以在此协议选项卡上配置您要在确认中包括的任何自定义设置。例如，可以使用其他分隔符，可以选择启用 CR LF 等。  
  
       对于 X12 编码的确认，请输入 ISA5、ISA6、ISA7 和 ISA8 的值。 对于 ISA5 和 ISA6，请输入将发送确认的参与方的值（与接收原始交换的参与方相同）。 对于 ISA7 和 ISA8，请输入将接收确认的参与方的值（与发送原始交换的参与方相同）。  
  
       对于 EDIFACT 编码的确认，UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 输入值。 对于 UNB2.1 和 UNB2.2，请输入将发送确认的参与方的值（与接收原始交换的参与方相同）。 对于 UNB3.1 和 UNB3.2，请输入将接收确认的参与方的值（与发送原始交换的参与方相同）。  
  
   2. 对于 X12 或 EDIFACT 确认，如果需要，在**字符集和分隔符**页上，指定你想要在确认中使用的分隔符。 还可以指定确认是否必须使用 CR LF 后缀。  
  
   3. 对于 EDIFACT 确认，如果需要，在**信封**页**交换设置**部分中，指定是否确认将包含 UNA 或 UNG 段通过选择相应的选项。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)   
 [如何创建接收端口](../core/how-to-create-a-receive-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)