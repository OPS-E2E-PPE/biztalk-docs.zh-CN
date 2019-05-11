---
title: 适配器框架是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd96ab8287a3c8d02bb612d4595c9f418e566eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243220"
---
# <a name="what-is-the-adapter-framework"></a><span data-ttu-id="d02cf-103">适配器框架是什么？</span><span class="sxs-lookup"><span data-stu-id="d02cf-103">What Is the Adapter Framework?</span></span>
<span data-ttu-id="d02cf-104">BizTalk 适配器框架提供了稳定、 开放的机制，用于所有适配器来实现或访问来自工作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。</span><span class="sxs-lookup"><span data-stu-id="d02cf-104">The BizTalk Adapter Framework offers a stable, open mechanism for all adapters to implement or access work from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messaging Engine.</span></span> <span data-ttu-id="d02cf-105">接口中所述**Microsoft.BizTalk.Adapter.Framework**命名空间启用适配器，以提供用于修改配置属性页。</span><span class="sxs-lookup"><span data-stu-id="d02cf-105">The interfaces described in the **Microsoft.BizTalk.Adapter.Framework** namespace enable adapters to provide a means to modify configuration property pages.</span></span> <span data-ttu-id="d02cf-106">它也是一种服务和架构导入到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d02cf-106">It also is a means to import services and schemas into the BizTalk project.</span></span>  
  
 <span data-ttu-id="d02cf-107">下图显示了适配器和适配器框架如何协同工作以应用程序连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d02cf-107">The following figure shows how an adapter and the Adapter Framework work together to connect your application to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d02cf-108">![适配器框架](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="d02cf-108">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
 <span data-ttu-id="d02cf-109">以下步骤介绍在此图中所示的步骤序列：</span><span class="sxs-lookup"><span data-stu-id="d02cf-109">The following steps describe the sequence of steps shown in this figure:</span></span>  
  
1. <span data-ttu-id="d02cf-110">从侦听指定地址处的特定协议的消息的接收位置接收数据。</span><span class="sxs-lookup"><span data-stu-id="d02cf-110">Data is received from a receive location that is listening for messages with a certain protocol at a specified address.</span></span> <span data-ttu-id="d02cf-111">接收位置是与适配器和接收管道相关联。</span><span class="sxs-lookup"><span data-stu-id="d02cf-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="d02cf-112">您可以配置适配器和管道组件执行某个逻辑上预先确定的协议的消息。</span><span class="sxs-lookup"><span data-stu-id="d02cf-112">You can configure both the adapter and the pipeline components to perform certain logic on messages of a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="d02cf-113">接收位置接收此消息后，将消息发送到适配器，会创建新的 BizTalk 消息、 将数据流附加到消息 （通常在消息的正文部分）、 添加到终结点相关的任何元数据数据已收到，，然后将该消息提交到消息引擎。</span><span class="sxs-lookup"><span data-stu-id="d02cf-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="d02cf-114">消息引擎将消息发送到接收管道，其中数据转换为 XML、 邮件发件人进行身份验证、 对消息进行解密，并验证 XML。</span><span class="sxs-lookup"><span data-stu-id="d02cf-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="d02cf-115">消息引擎将消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="d02cf-115">The Messaging Engine publishes the message to the MessageBox database.</span></span> <span data-ttu-id="d02cf-116">MessageBox 是一个 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]表，它包含要处理的消息。</span><span class="sxs-lookup"><span data-stu-id="d02cf-116">The MessageBox is a Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] table containing messages to be processed.</span></span> <span data-ttu-id="d02cf-117">业务流程和发送端口可以订阅 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="d02cf-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="d02cf-118">消息引擎将消息发送到业务流程或发送端口订阅服务器根据订阅服务器上的筛选器中所设置规范匹配的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d02cf-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="d02cf-119">如果业务流程是订户，它处理消息，并通过发送端口将其发送出去。</span><span class="sxs-lookup"><span data-stu-id="d02cf-119">If an orchestration is the subscriber, it processes the message and sends it out through a send port.</span></span> <span data-ttu-id="d02cf-120">如果订户是发送该消息会传递经过发送管道到发送适配器传输之前。</span><span class="sxs-lookup"><span data-stu-id="d02cf-120">If the subscriber is a send the message passes through the send pipeline into a send adapter before being transmitted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d02cf-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="d02cf-121">In This Section</span></span>  
  
-   [<span data-ttu-id="d02cf-122">使用适配器框架工具</span><span class="sxs-lookup"><span data-stu-id="d02cf-122">Using the Adapter Framework Tools</span></span>](../core/using-the-adapter-framework-tools.md)  
  
-   [<span data-ttu-id="d02cf-123">适配器消息交换模式</span><span class="sxs-lookup"><span data-stu-id="d02cf-123">Adapter Message Exchange Patterns</span></span>](../core/adapter-message-exchange-patterns.md)  
  
-   [<span data-ttu-id="d02cf-124">适配器框架组件</span><span class="sxs-lookup"><span data-stu-id="d02cf-124">Adapter Framework Components</span></span>](../core/adapter-framework-components.md)  
  
-   [<span data-ttu-id="d02cf-125">适配器宿主模型</span><span class="sxs-lookup"><span data-stu-id="d02cf-125">Adapter Hosting Model</span></span>](../core/adapter-hosting-model.md)  
  
-   [<span data-ttu-id="d02cf-126">适配器组件</span><span class="sxs-lookup"><span data-stu-id="d02cf-126">Adapter Components</span></span>](../core/adapter-components.md)