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
ms.openlocfilehash: 8f8b1ea4b228a4cc69d02184a4e70557d378cc2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390720"
---
# <a name="configuring-the-sending-and-receiving-of-edi-acknowledgments"></a>配置 EDI 确认的发送和接收
若要配置 EDI 确认以响应接收交换的发送，需要执行以下操作：  
  
-   启用确认收到的交换解析为协议中。 通过执行此操作，您可以声明发送交换的参与方期望确认。  
  
-   如果需要使用特定的属性集，如启用 CR LF、 重新发送确认的分隔符是不同的等等，其他单向协议选项卡中设置这些属性。通过执行此操作，可以配置如何，该参与方发回确认。  
  
    > [!NOTE]
    >  如果交换解析为协议中定义**PartyA-> 参与**选项卡上，应如何生成确认相关的属性中配置**参与-> PartyA**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**PartyA-> 参与**选项卡。例如，如果发送方和接收方标识符在交换消息解析成，则发送方和接收方上下文属性将设置为 US 和 THEM 在确认消息的协议被设置为 THEM 和 US。 通常情况下，其他单向协议选项卡还会发送方和接收方的标识符分别设置为 US 和 THEM。 因此，确认消息将解析为该协议并将有选择地设置的属性。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**参与-> PartyA**选项卡。  
  
     从概念上讲，确认属性将有选择地从任何单向协议选项卡中具有相同的发送方和接收方限定符的确认上下文属性中设置。 但是，对于便于实际使用，可以将通常设置这在您创建该交换将解析到协议的其他单向协议选项卡中。  
  
-   如果不将 EDI 确认发送回发送原始交换的参与方的参与方，设置一个单向发送端口以选择该确认并发送或双向接收端口以发送确认。 有关详细信息，请参阅[配置为发送 EDI 交换和确认的静态发送端口](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)。  
  
-   如果你是需要 EDI 确认的参与方，设置一个双向发送端口或一个单向接收端口以接收确认。 有关详细信息，请参阅[配置为接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。  
  
-   BizTalk EDI 应用程序包含控制架构。 因此，包含 EDI 解决方案的应用程序必须包含对 BizTalk EDI 应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-request-an-acknowledgment-for-the-party-that-sent-the-original-interchange"></a>若要为发送原始交换的参与方请求确认  
  
1. > [!NOTE]
   >  通过在此过程中执行的步骤，可以配置发送交换的参与方期望返回确认。  
  
    在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**页上，单击具有您需要为其启用确认的协议的参与方。 在中**协议**部分中的页上，右键单击该协议，然后单击**属性**。 在中**协议属性**对话框单向协议选项卡 （向其入站的交换将解析） 中，执行以下操作：  
  
   1. 在中**标识符**页上，输入的值在发送方和接收方限定符。  
  
       对于 X12 编码的确认，ISA5、 ISA6、 ISA7 和 ISA8 输入值。 对于 ISA5 和 ISA6，输入将发送交换的参与方的值。 对于 ISA7 和 ISA8，输入将接收交换的参与方的值。  
  
       对于 EDIFACT 编码的确认，UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 输入值。 对于 UNB2.1 和 UNB2.2，输入将发送交换的参与方的值。 对于 UNB3.1 和 UNB3.2，输入将接收交换的参与方的值。  
  
   2. 在中**确认**页上，选择属性定义的发送方预期确认种类：  
  
       对于 X12 确认，选择**预期的 TA1**和/或**预期的 997**根据确认预期。 对于每个确认类型，选择**进行批处理\<ACK 类型\>** 如果需要确认作为单独的交换发送的每个实例。  
  
       对于 EDIFACT 确认，请选择**预期接收消息 (CONTRL)** 和/或**确认 (CONTRL) 预期**根据确认预期。 对于每个确认类型，选择**进行批处理\<ACK 类型\>** 如果需要确认作为单独的交换发送的每个实例。  
  
   3. 在中**本地主机设置**页**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**返回以异步方式通过单向发送端口的确认。 保持选中此属性返回确认同步通过双向接收端口。  
  
   4. 在中**发送端口**页上，在**名称**的列**发送端口**网格中，选择已设置为发送确认的发送端口。  
  
      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用此发送端口设置来确定处理消息时要使用的参与方。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
      > 
      > [!NOTE]
      >  如果未设置发送端口，可能需要更高版本执行此步骤。  
  
### <a name="to-configure-how-the-party-sends-the-acknowledgement-back"></a>若要配置参与方如何发回确认  
  
1. > [!NOTE]
   >  通过在此过程中执行的步骤，可以配置接收交换的参与方如何发回确认。  
  
    在同一**协议属性**对话框中的，其他单向协议选项卡中，执行以下操作：  
  
   1. 在中**标识符**页上，输入的值在发送方和接收方限定符。  
  
      > [!NOTE]
      >  尽管发送确认，接收原始交换的参与方将成为发送方和发送原始交换的参与方变为接收端。 因此，您现在输入在标识符页中的值是相反的上一步中的单向协议选项卡中输入的值。 这有两个用途：  
      > 
      > - 要发回的确认将解析为因为确认的发送方和接收方上下文属性将匹配发送方和接收输入的值在标识符页上现在要创建此单向协议。  
      >   -   此协议选项卡上，可以配置想要包括在确认消息进行任何自的定义。例如，可以使用其他分隔符，你可以选择允许启用 CR LF，等等。  
  
       对于 X12 编码的确认，ISA5、 ISA6、 ISA7 和 ISA8 输入值。 对于 ISA5 和 ISA6，输入将发送的确认 （将接收原始交换的参与方相同） 的参与方的值。 对于 ISA7 和 ISA8，输入将接收的确认 （将发送原始交换的参与方相同） 的参与方的值。  
  
       对于 EDIFACT 编码的确认，UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 输入值。 对于 UNB2.1 和 UNB2.2，输入将发送的确认 （将接收原始交换的参与方相同） 的参与方的值。 对于 UNB3.1 和 UNB3.2，输入将接收的确认 （将发送原始交换的参与方相同） 的参与方的值。  
  
   2. 对于 X12 或 EDIFACT 确认，如果需要，在**字符集和分隔符**页上，指定你想要在确认中使用的分隔符。 此外可以指定确认必须使用 CR LF 后缀。  
  
   3. 对于 EDIFACT 确认，如果需要，在**信封**页**交换设置**部分中，指定是否确认将包含 UNA 或 UNG 段通过选择相应的选项。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)   
 [如何创建接收端口](../core/how-to-create-a-receive-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)