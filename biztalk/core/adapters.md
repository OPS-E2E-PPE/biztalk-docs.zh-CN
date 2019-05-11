---
title: 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d3e669f31f1050a0e2c37388cd8106a2386da45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361074"
---
# <a name="adapters"></a><span data-ttu-id="05ef3-102">适配器</span><span class="sxs-lookup"><span data-stu-id="05ef3-102">Adapters</span></span>
<span data-ttu-id="05ef3-103">为了与外部系统、 应用程序和实体交换消息 Microsoft BizTalk Server 使用的适配器的概念。</span><span class="sxs-lookup"><span data-stu-id="05ef3-103">To exchange messages with external systems, applications, and entities Microsoft BizTalk Server uses the concept of an adapter.</span></span> <span data-ttu-id="05ef3-104">*适配器*是 COM 或。传输消息在业务终结点 （如文件系统、 数据库和自定义业务应用程序） 的基于 NET 的组件使用各种通信协议。</span><span class="sxs-lookup"><span data-stu-id="05ef3-104">*Adapters* are COM or .NET-based components that transfer messages to and from business endpoints (such as file systems, databases, and custom business applications) using various communication protocols.</span></span>  
  
 <span data-ttu-id="05ef3-105">适配器使用 BizTalk server 交换消息与外部实体发送和接收操作</span><span class="sxs-lookup"><span data-stu-id="05ef3-105">Adapters are used by BizTalk Server to exchange messages with external entities in send and receive operations</span></span>  
  
-   <span data-ttu-id="05ef3-106">BizTalk Server 在将信息发送到使用该适配器支持的协议的外部实体时，会发生发送 （或发送端） 操作。</span><span class="sxs-lookup"><span data-stu-id="05ef3-106">Send (or send-side) operations occur when information is being sent by BizTalk Server to an external entity using the protocols supported by the adapter.</span></span>  
  
-   <span data-ttu-id="05ef3-107">接收 （或接收方） 时，适配器从外部实体接收信息并将其传递到 BizTalk Server 消息引擎执行的操作。</span><span class="sxs-lookup"><span data-stu-id="05ef3-107">Receive (or receive-side) operations occur when the adapter receives information from an external entity and passes it into the BizTalk Server Messaging Engine.</span></span>  
  
## <a name="the-adapter-framework"></a><span data-ttu-id="05ef3-108">适配器框架</span><span class="sxs-lookup"><span data-stu-id="05ef3-108">The Adapter Framework</span></span>  
 <span data-ttu-id="05ef3-109">下图显示了适配器和适配器框架如何协同工作以连接到 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="05ef3-109">The following figure shows how an adapter and the Adapter Framework work together to connect your application to BizTalk Server.</span></span>  
  
1. <span data-ttu-id="05ef3-110">通过侦听指定地址的特定协议的消息的接收位置接收的数据。</span><span class="sxs-lookup"><span data-stu-id="05ef3-110">Data is received through a receive location that is listening for messages of a certain protocol at a specified address.</span></span> <span data-ttu-id="05ef3-111">接收位置是与适配器和接收管道相关联。</span><span class="sxs-lookup"><span data-stu-id="05ef3-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="05ef3-112">您可以配置适配器和管道组件对具有预设的协议的消息执行特定逻辑。</span><span class="sxs-lookup"><span data-stu-id="05ef3-112">You can configure both the adapter and the pipeline components to perform certain logic on messages having a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="05ef3-113">接收位置接收此消息后，将消息发送到适配器，适配器创建新的 BizTalk Server 消息、 将数据流附加到消息 （通常在消息的正文部分）、 添加所有相关终结点，通过元数据收到数据，然后将该消息提交到消息引擎。</span><span class="sxs-lookup"><span data-stu-id="05ef3-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk Server message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="05ef3-114">消息引擎将消息发送到接收管道，其中数据转换为 XML、 邮件发件人进行身份验证、 对消息进行解密，并验证 XML。</span><span class="sxs-lookup"><span data-stu-id="05ef3-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="05ef3-115">消息引擎将消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="05ef3-115">The Messaging Engine publishes the message to the MessageBox.</span></span> <span data-ttu-id="05ef3-116">MessageBox 是一个包含要处理的消息的 Microsoft SQL Server 表。</span><span class="sxs-lookup"><span data-stu-id="05ef3-116">The MessageBox is a Microsoft SQL Server table containing messages to be processed.</span></span> <span data-ttu-id="05ef3-117">业务流程和发送端口可以订阅 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="05ef3-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="05ef3-118">消息引擎将消息发送到业务流程或发送端口订阅服务器根据订阅服务器上的筛选器中所设置规范匹配的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="05ef3-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="05ef3-119">如果业务流程是订户，它处理消息，并将其发送出使用发送端口。</span><span class="sxs-lookup"><span data-stu-id="05ef3-119">If an orchestration is the subscriber, it processes the message and sends it out using a send port.</span></span> <span data-ttu-id="05ef3-120">发送端口有这个功能，或仅订阅服务器后，该消息会传递经过发送管道到发送适配器然后通过网络进行传输。</span><span class="sxs-lookup"><span data-stu-id="05ef3-120">After the send port has it, or is the only subscriber, the message passes through the send pipeline into a send adapter before being transmitted over the wire.</span></span>  
  
   <span data-ttu-id="05ef3-121">适配器框架</span><span class="sxs-lookup"><span data-stu-id="05ef3-121">The Adapter Framework</span></span>  
  
   <span data-ttu-id="05ef3-122">![适配器框架](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="05ef3-122">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
## <a name="receive-adapters"></a><span data-ttu-id="05ef3-123">接收适配器</span><span class="sxs-lookup"><span data-stu-id="05ef3-123">Receive Adapters</span></span>  
 <span data-ttu-id="05ef3-124">接收适配器负责通过将网络/数据源流附加到消息正文来创建新的 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="05ef3-124">Receive adapters are responsible for creating a new BizTalk Server message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="05ef3-125">它还会添加到终结点的数据接收的则该将消息提交到消息引擎相关的任何元数据。</span><span class="sxs-lookup"><span data-stu-id="05ef3-125">It also adds any metadata pertinent to the endpoint over which the data was received, then submits that message to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="05ef3-126">适配器从接收终结点删除数据，或将相应的确认消息发送到客户端，该值指示数据已被接受到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="05ef3-126">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgement message to the client indicating that the data has been accepted into BizTalk Server.</span></span>  
  
## <a name="send-adapters"></a><span data-ttu-id="05ef3-127">发送适配器</span><span class="sxs-lookup"><span data-stu-id="05ef3-127">Send Adapters</span></span>  
 <span data-ttu-id="05ef3-128">发送适配器负责将 BizTalk 消息发送到指定的终结点使用其特定的传输协议。</span><span class="sxs-lookup"><span data-stu-id="05ef3-128">Send adapters are responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
 <span data-ttu-id="05ef3-129">适配器和编写自定义适配器的结构有关适配器的详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="05ef3-129">For more information about adapters, the structure of an adapter, and writing custom adapters, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ef3-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="05ef3-130">See Also</span></span>  
 [<span data-ttu-id="05ef3-131">项目</span><span class="sxs-lookup"><span data-stu-id="05ef3-131">Artifacts</span></span>](../core/artifacts.md)