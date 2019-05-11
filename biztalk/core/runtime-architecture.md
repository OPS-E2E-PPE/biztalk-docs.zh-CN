---
title: 运行时体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6b7a01f8919a1c2bee415df3733394462d59f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393976"
---
# <a name="runtime-architecture"></a><span data-ttu-id="dd8e0-102">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="dd8e0-102">Runtime Architecture</span></span>
<span data-ttu-id="dd8e0-103">然后再进行查看更多详细信息中的各种组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，很重要，必须了解如何将这些组件组合到产品的整体体系结构。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-103">Before reviewing more detailed information about the various components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is important that you have an understanding of how the components fit into the overall architecture of the product.</span></span> <span data-ttu-id="dd8e0-104">BizTalk Server 运行时是基于发布/订阅体系结构构建其中一条消息是发布到系统，，然后由一个或多个活动订户接收。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-104">The BizTalk Server runtime is built on a publish/subscribe architecture in which a message is published into the system, and then received by one or more active subscribers.</span></span> <span data-ttu-id="dd8e0-105">此体系结构的不同方式存在，但 BizTalk Server 中实现的模型通常称为*基于内容的发布/订阅*。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-105">Different flavors of this architecture exist, but the model implemented in BizTalk Server is often called *content-based publish/subscribe*.</span></span>  
  
 <span data-ttu-id="dd8e0-106">在基于内容的发布/订阅模型中，订阅服务器指定他们想要接收使用一组消息有关的条件的消息。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-106">In a content-based publish/subscribe model, subscribers specify the messages they want to receive using a set of criteria about the message.</span></span> <span data-ttu-id="dd8e0-107">在发布时计算消息和所有具有匹配订阅 （由筛选器表达式指示），活动订户接收消息。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-107">The message is evaluated at the time it is published, and all of the active subscribers with matching subscriptions (indicated by filter expressions), receive the message.</span></span> <span data-ttu-id="dd8e0-108">适用于 BizTalk Server，基于内容的少量的用词不当，但是，是因为用于生成订阅的条件，而无需来自消息内容，并且可能包括有关消息的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-108">As it applies to BizTalk Server, content-based is a bit of a misnomer, however, because the criteria used to build subscriptions do not have to come from the message content, and may include contextual information about the message as well.</span></span> <span data-ttu-id="dd8e0-109">有关订阅机制的详细信息，请参阅[发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-109">For details of the subscription mechanism, see [Publish and Subscribe Architecture](../core/publish-and-subscribe-architecture.md).</span></span>  
  
 <span data-ttu-id="dd8e0-110">以下各节介绍了 BizTalk Server 运行时体系结构的各种组件。</span><span class="sxs-lookup"><span data-stu-id="dd8e0-110">The sections that follow describe the various components of the BizTalk Server runtime architecture.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd8e0-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="dd8e0-111">In This Section</span></span>  
  
-   [<span data-ttu-id="dd8e0-112">BizTalk Server 消息</span><span class="sxs-lookup"><span data-stu-id="dd8e0-112">The BizTalk Server Message</span></span>](../core/the-biztalk-server-message.md)  
  
-   [<span data-ttu-id="dd8e0-113">消息的生命周期</span><span class="sxs-lookup"><span data-stu-id="dd8e0-113">Lifecycle of a Message</span></span>](../core/lifecycle-of-a-message.md)  
  
-   [<span data-ttu-id="dd8e0-114">处理消息</span><span class="sxs-lookup"><span data-stu-id="dd8e0-114">Processing the Message</span></span>](../core/processing-the-message.md)  
  
-   [<span data-ttu-id="dd8e0-115">请求-响应消息</span><span class="sxs-lookup"><span data-stu-id="dd8e0-115">Request-Response Messaging</span></span>](../core/request-response-messaging.md)  
  
-   [<span data-ttu-id="dd8e0-116">消息引擎</span><span class="sxs-lookup"><span data-stu-id="dd8e0-116">The Messaging Engine</span></span>](../core/the-messaging-engine.md)  
  
-   [<span data-ttu-id="dd8e0-117">实体</span><span class="sxs-lookup"><span data-stu-id="dd8e0-117">Entities</span></span>](../core/entities.md)  
  
-   [<span data-ttu-id="dd8e0-118">项目</span><span class="sxs-lookup"><span data-stu-id="dd8e0-118">Artifacts</span></span>](../core/artifacts.md)  
  
-   [<span data-ttu-id="dd8e0-119">企业单一登录 (SSO)</span><span class="sxs-lookup"><span data-stu-id="dd8e0-119">Enterprise Single Sign-On (SSO)</span></span>](../core/enterprise-single-sign-on-sso.md)  
  
-   [<span data-ttu-id="dd8e0-120">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="dd8e0-120">Business Rules Engine</span></span>](../core/business-rules-engine.md)  
  
-   [<span data-ttu-id="dd8e0-121">BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="dd8e0-121">BizTalk Assemblies</span></span>](../core/biztalk-assemblies.md)