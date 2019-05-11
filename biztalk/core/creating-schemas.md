---
title: 创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e3197dee20a222be35aa2e72dc4ac5e04208da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389876"
---
# <a name="creating-schemas"></a><span data-ttu-id="c3f7f-102">创建架构</span><span class="sxs-lookup"><span data-stu-id="c3f7f-102">Creating Schemas</span></span>
<span data-ttu-id="c3f7f-103">您可以使用 BizTalk 编辑器创建两种类型的架构： 消息架构和属性架构。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-103">You can use BizTalk Editor to create two types of schemas: message schemas and property schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3f7f-104">有几种类型的消息架构，包括 XML 消息架构、 平面文件消息架构和信封架构。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-104">There are several types of message schemas, including XML message schemas, flat file message schemas, and envelope schemas.</span></span>  
  
 <span data-ttu-id="c3f7f-105">消息架构定义的结构和约束应发送到计算机并从贸易合作伙伴或应用程序接收的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-105">Message schemas define the structure and constrain the content of messages that you expect to send to, and receive from, your trading partners or applications.</span></span> <span data-ttu-id="c3f7f-106">消息架构是最常见的与 Microsoft 将使用的架构类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-106">Message schemas are the most common types of schemas that you will use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c3f7f-107">可以创建的业务文档和用来包含它们的信封的 XML 消息架构，并通过使用平面文件扩展向 BizTalk 编辑器，它可以创建平面文件消息架构，包括头部、 正文和尾部的架构。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-107">can create XML message schemas for both business documents and the envelopes used to contain them, and through the use of the Flat File Extension to BizTalk Editor, it can create flat file message schemas, including schemas for headers, bodies and trailers.</span></span>  
  
 <span data-ttu-id="c3f7f-108">属性架构是架构的一种特殊类型。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-108">Property schemas are a special type of schema.</span></span> <span data-ttu-id="c3f7f-109">属性架构字段和/或从提升实例消息中到称为消息上下文的记录数据提供了验证模板。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-109">Property schemas provide a validation template for field and/or record data that is promoted from within an instance message into what is known as the message context.</span></span> <span data-ttu-id="c3f7f-110">属性架构的用途是提供要在运行时升级的数据的正式、 强类型定义。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-110">The purpose of property schemas is to provide a formal, strongly typed definition of the data to be promoted at run time.</span></span>  
  
 <span data-ttu-id="c3f7f-111">属性升级提供了一种用于提取关键信息的集中式的机制、 由你定义，从在实例消息并使其更轻松地访问 BizTalk Server 组件，处理消息通过 BizTalk 传递服务器。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-111">Property promotion provides a centralized mechanism for pulling key pieces of information, defined by you, from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span> <span data-ttu-id="c3f7f-112">升级的属性的一个常见用途是在匹配到订阅，从而允许消息正确路由进行处理的消息实例中。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-112">One common use of promoted properties is in matching a message instance to a subscription, allowing the message to be properly routed for processing.</span></span>  
  
 <span data-ttu-id="c3f7f-113">本部分介绍了可以在其中创建不同类型的 BizTalk Server 中的架构的方式，并提供了有关对多个类型的架构的相关的主题。</span><span class="sxs-lookup"><span data-stu-id="c3f7f-113">This section describes the ways in which you can create different types of schemas within BizTalk Server, and presents related subjects that pertain to multiple types of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3f7f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="c3f7f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c3f7f-115">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="c3f7f-115">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)  
  
-   [<span data-ttu-id="c3f7f-116">管理架构中的节点</span><span class="sxs-lookup"><span data-stu-id="c3f7f-116">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)  
  
-   [<span data-ttu-id="c3f7f-117">升级属性</span><span class="sxs-lookup"><span data-stu-id="c3f7f-117">Promoting Properties</span></span>](../core/promoting-properties.md)