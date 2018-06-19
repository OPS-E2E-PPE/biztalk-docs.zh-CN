---
title: 运行时体系结构 |Microsoft 文档
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
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268989"
---
# <a name="runtime-architecture"></a><span data-ttu-id="f4427-102">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="f4427-102">Runtime Architecture</span></span>
<span data-ttu-id="f4427-103">然后再进行查看更多详细信息中的各种组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，具有组件到产品的总体体系结构的适合程度的了解是很重要。</span><span class="sxs-lookup"><span data-stu-id="f4427-103">Before reviewing more detailed information about the various components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is important that you have an understanding of how the components fit into the overall architecture of the product.</span></span> <span data-ttu-id="f4427-104">BizTalk Server 运行时是基于发布/订阅结构建立的，在该结构中消息发布到系统，然后由一个或多个活动订户接收。</span><span class="sxs-lookup"><span data-stu-id="f4427-104">The BizTalk Server runtime is built on a publish/subscribe architecture in which a message is published into the system, and then received by one or more active subscribers.</span></span> <span data-ttu-id="f4427-105">此体系结构的不同方式存在，但在 BizTalk Server 中实现此模型通常称为*基于内容的发布/订阅*。</span><span class="sxs-lookup"><span data-stu-id="f4427-105">Different flavors of this architecture exist, but the model implemented in BizTalk Server is often called *content-based publish/subscribe*.</span></span>  
  
 <span data-ttu-id="f4427-106">在基于内容的发布/订阅模型中，订户使用有关消息的一组条件来指定要接收的消息。</span><span class="sxs-lookup"><span data-stu-id="f4427-106">In a content-based publish/subscribe model, subscribers specify the messages they want to receive using a set of criteria about the message.</span></span> <span data-ttu-id="f4427-107">在发布消息时对消息进行评估，具有匹配订阅（由筛选器表达式指明）的所有活动订户将接收该消息。</span><span class="sxs-lookup"><span data-stu-id="f4427-107">The message is evaluated at the time it is published, and all of the active subscribers with matching subscriptions (indicated by filter expressions), receive the message.</span></span> <span data-ttu-id="f4427-108">但是，在应用于 BizTalk Server 时，基于内容有点名不副实，因为用于生成订阅的条件不一定必须来自消息内容，还可以包括有关消息的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="f4427-108">As it applies to BizTalk Server, content-based is a bit of a misnomer, however, because the criteria used to build subscriptions do not have to come from the message content, and may include contextual information about the message as well.</span></span> <span data-ttu-id="f4427-109">有关订阅机制的详细信息，请参阅[发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="f4427-109">For details of the subscription mechanism, see [Publish and Subscribe Architecture](../core/publish-and-subscribe-architecture.md).</span></span>  
  
 <span data-ttu-id="f4427-110">后面的部分将介绍 BizTalk Server 运行时结构的各种组件。</span><span class="sxs-lookup"><span data-stu-id="f4427-110">The sections that follow describe the various components of the BizTalk Server runtime architecture.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4427-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f4427-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f4427-112">BizTalk Server 消息</span><span class="sxs-lookup"><span data-stu-id="f4427-112">The BizTalk Server Message</span></span>](../core/the-biztalk-server-message.md)  
  
-   [<span data-ttu-id="f4427-113">消息的生命周期</span><span class="sxs-lookup"><span data-stu-id="f4427-113">Lifecycle of a Message</span></span>](../core/lifecycle-of-a-message.md)  
  
-   [<span data-ttu-id="f4427-114">处理消息</span><span class="sxs-lookup"><span data-stu-id="f4427-114">Processing the Message</span></span>](../core/processing-the-message.md)  
  
-   [<span data-ttu-id="f4427-115">请求-响应消息传送</span><span class="sxs-lookup"><span data-stu-id="f4427-115">Request-Response Messaging</span></span>](../core/request-response-messaging.md)  
  
-   [<span data-ttu-id="f4427-116">消息传送的引擎</span><span class="sxs-lookup"><span data-stu-id="f4427-116">The Messaging Engine</span></span>](../core/the-messaging-engine.md)  
  
-   [<span data-ttu-id="f4427-117">实体</span><span class="sxs-lookup"><span data-stu-id="f4427-117">Entities</span></span>](../core/entities.md)  
  
-   [<span data-ttu-id="f4427-118">项目</span><span class="sxs-lookup"><span data-stu-id="f4427-118">Artifacts</span></span>](../core/artifacts.md)  
  
-   [<span data-ttu-id="f4427-119">企业单一登录 (SSO)</span><span class="sxs-lookup"><span data-stu-id="f4427-119">Enterprise Single Sign-On (SSO)</span></span>](../core/enterprise-single-sign-on-sso.md)  
  
-   [<span data-ttu-id="f4427-120">业务规则引擎</span><span class="sxs-lookup"><span data-stu-id="f4427-120">Business Rules Engine</span></span>](../core/business-rules-engine.md)  
  
-   [<span data-ttu-id="f4427-121">BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="f4427-121">BizTalk Assemblies</span></span>](../core/biztalk-assemblies.md)