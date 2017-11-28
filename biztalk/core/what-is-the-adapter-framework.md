---
title: "适配器框架概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648c22a52e543b24458daa73146836e1e3a5463e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-adapter-framework"></a><span data-ttu-id="024b6-103">适配器框架概述</span><span class="sxs-lookup"><span data-stu-id="024b6-103">What Is the Adapter Framework?</span></span>
<span data-ttu-id="024b6-104">BizTalk 适配器框架提供了一个稳定、 打开机制，以实现或访问工作中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。</span><span class="sxs-lookup"><span data-stu-id="024b6-104">The BizTalk Adapter Framework offers a stable, open mechanism for all adapters to implement or access work from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messaging Engine.</span></span> <span data-ttu-id="024b6-105">接口中所述**Microsoft.BizTalk.Adapter.Framework**命名空间启用适配器，以提供一种方式来修改配置属性页。</span><span class="sxs-lookup"><span data-stu-id="024b6-105">The interfaces described in the **Microsoft.BizTalk.Adapter.Framework** namespace enable adapters to provide a means to modify configuration property pages.</span></span> <span data-ttu-id="024b6-106">它还可用于将服务和架构导入到 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="024b6-106">It also is a means to import services and schemas into the BizTalk project.</span></span>  
  
 <span data-ttu-id="024b6-107">下图显示了适配器和适配器框架如何协同工作来应用程序连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="024b6-107">The following figure shows how an adapter and the Adapter Framework work together to connect your application to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="024b6-108">![适配器 framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="024b6-108">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
 <span data-ttu-id="024b6-109">下面的步骤描述上图中的一系列步骤：</span><span class="sxs-lookup"><span data-stu-id="024b6-109">The following steps describe the sequence of steps shown in this figure:</span></span>  
  
1.  <span data-ttu-id="024b6-110">通过接收位置接收数据，接收位置会侦听指定地址的特定协议的消息。</span><span class="sxs-lookup"><span data-stu-id="024b6-110">Data is received from a receive location that is listening for messages with a certain protocol at a specified address.</span></span> <span data-ttu-id="024b6-111">接收位置与适配器和接收管道相关联。</span><span class="sxs-lookup"><span data-stu-id="024b6-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="024b6-112">你可以配置适配器和管道组件来执行某些逻辑上预先确定的协议的消息。</span><span class="sxs-lookup"><span data-stu-id="024b6-112">You can configure both the adapter and the pipeline components to perform certain logic on messages of a predetermined protocol.</span></span>  
  
2.  <span data-ttu-id="024b6-113">接收位置接收到消息后，消息将发送给适配器，适配器会创建新的 BizTalk 消息、将数据流附加到该消息（通常在消息的正文部分）中、添加接收数据的终结点的所有相关元数据，然后将消息提交到消息引擎中。</span><span class="sxs-lookup"><span data-stu-id="024b6-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="024b6-114">消息引擎将消息发送到接收管道，在这里会将数据转换成 XML，验证消息发件人的身份，对消息进行解密，然后验证 XML。</span><span class="sxs-lookup"><span data-stu-id="024b6-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4.  <span data-ttu-id="024b6-115">消息引擎将消息发布到 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="024b6-115">The Messaging Engine publishes the message to the MessageBox database.</span></span> <span data-ttu-id="024b6-116">MessageBox 是 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]表包含要处理的消息。</span><span class="sxs-lookup"><span data-stu-id="024b6-116">The MessageBox is a Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] table containing messages to be processed.</span></span> <span data-ttu-id="024b6-117">两种业务流程和发送端口都可以订阅 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="024b6-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5.  <span data-ttu-id="024b6-118">消息引擎根据与订户筛选器所设置规范匹配的消息上下文属性，将消息发送给业务流程或发送端口订户。</span><span class="sxs-lookup"><span data-stu-id="024b6-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6.  <span data-ttu-id="024b6-119">如果某个业务流程是订户，它会处理消息并通过发送端口将消息发送出去。</span><span class="sxs-lookup"><span data-stu-id="024b6-119">If an orchestration is the subscriber, it processes the message and sends it out through a send port.</span></span> <span data-ttu-id="024b6-120">如果该订户是发送订户，则该消息会经过发送管道传递到发送适配器中，然后进行传输。</span><span class="sxs-lookup"><span data-stu-id="024b6-120">If the subscriber is a send the message passes through the send pipeline into a send adapter before being transmitted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="024b6-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="024b6-121">In This Section</span></span>  
  
-   [<span data-ttu-id="024b6-122">使用适配器 Framework 工具</span><span class="sxs-lookup"><span data-stu-id="024b6-122">Using the Adapter Framework Tools</span></span>](../core/using-the-adapter-framework-tools.md)  
  
-   [<span data-ttu-id="024b6-123">适配器消息交换模式</span><span class="sxs-lookup"><span data-stu-id="024b6-123">Adapter Message Exchange Patterns</span></span>](../core/adapter-message-exchange-patterns.md)  
  
-   [<span data-ttu-id="024b6-124">适配器 Framework 组件</span><span class="sxs-lookup"><span data-stu-id="024b6-124">Adapter Framework Components</span></span>](../core/adapter-framework-components.md)  
  
-   [<span data-ttu-id="024b6-125">承载模型的适配器</span><span class="sxs-lookup"><span data-stu-id="024b6-125">Adapter Hosting Model</span></span>](../core/adapter-hosting-model.md)  
  
-   [<span data-ttu-id="024b6-126">适配器组件</span><span class="sxs-lookup"><span data-stu-id="024b6-126">Adapter Components</span></span>](../core/adapter-components.md)