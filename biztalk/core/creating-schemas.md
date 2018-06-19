---
title: 创建架构 |Microsoft 文档
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
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238533"
---
# <a name="creating-schemas"></a><span data-ttu-id="3f43d-102">创建架构</span><span class="sxs-lookup"><span data-stu-id="3f43d-102">Creating Schemas</span></span>
<span data-ttu-id="3f43d-103">你可以使用 BizTalk 编辑器创建两种类型的架构： 消息架构和属性的架构。</span><span class="sxs-lookup"><span data-stu-id="3f43d-103">You can use BizTalk Editor to create two types of schemas: message schemas and property schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f43d-104">消息架构包括以下几种类型：XML 消息架构、平面文件消息架构和信封架构。</span><span class="sxs-lookup"><span data-stu-id="3f43d-104">There are several types of message schemas, including XML message schemas, flat file message schemas, and envelope schemas.</span></span>  
  
 <span data-ttu-id="3f43d-105">消息架构可定义要向贸易合作伙伴或应用程序发送或从其接收的消息的结构，并约束这些消息的内容。</span><span class="sxs-lookup"><span data-stu-id="3f43d-105">Message schemas define the structure and constrain the content of messages that you expect to send to, and receive from, your trading partners or applications.</span></span> <span data-ttu-id="3f43d-106">消息架构是架构将与 Microsoft 使用的最常见类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f43d-106">Message schemas are the most common types of schemas that you will use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3f43d-107">可以创建业务文档和用于包含，包络线的 XML 消息架构，并通过使用平面文件扩展到 BizTalk 编辑器，它可以创建平面文件消息架构，包括有关标头、 正文和拖车的架构。</span><span class="sxs-lookup"><span data-stu-id="3f43d-107"> can create XML message schemas for both business documents and the envelopes used to contain them, and through the use of the Flat File Extension to BizTalk Editor, it can create flat file message schemas, including schemas for headers, bodies and trailers.</span></span>  
  
 <span data-ttu-id="3f43d-108">属性架构是特殊类型的架构。</span><span class="sxs-lookup"><span data-stu-id="3f43d-108">Property schemas are a special type of schema.</span></span> <span data-ttu-id="3f43d-109">对于从实例消息中升级为消息上下文的字段和/或记录数据，属性架构为其提供了验证模板。</span><span class="sxs-lookup"><span data-stu-id="3f43d-109">Property schemas provide a validation template for field and/or record data that is promoted from within an instance message into what is known as the message context.</span></span> <span data-ttu-id="3f43d-110">属性架构的用途是要在运行时升级的数据提供正式的强类型定义。</span><span class="sxs-lookup"><span data-stu-id="3f43d-110">The purpose of property schemas is to provide a formal, strongly typed definition of the data to be promoted at run time.</span></span>  
  
 <span data-ttu-id="3f43d-111">属性提升提供用于提取关键信息的集中式的机制、 由你定义、 从内实例消息并使其更轻松地访问 BizTalk Server 组件，正在处理该消息通过 BizTalk 传递服务器。</span><span class="sxs-lookup"><span data-stu-id="3f43d-111">Property promotion provides a centralized mechanism for pulling key pieces of information, defined by you, from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span> <span data-ttu-id="3f43d-112">升级属性常用于将消息实例与订阅相匹配，从而允许正确地路由消息以进行处理。</span><span class="sxs-lookup"><span data-stu-id="3f43d-112">One common use of promoted properties is in matching a message instance to a subscription, allowing the message to be properly routed for processing.</span></span>  
  
 <span data-ttu-id="3f43d-113">本部分介绍了在 BizTalk Server 中创建不同类型架构的几种方式，并且提供了与多种架构类型有关的相关主题。</span><span class="sxs-lookup"><span data-stu-id="3f43d-113">This section describes the ways in which you can create different types of schemas within BizTalk Server, and presents related subjects that pertain to multiple types of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f43d-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="3f43d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="3f43d-115">管理架构在项目中</span><span class="sxs-lookup"><span data-stu-id="3f43d-115">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)  
  
-   [<span data-ttu-id="3f43d-116">管理在架构中的节点</span><span class="sxs-lookup"><span data-stu-id="3f43d-116">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)  
  
-   [<span data-ttu-id="3f43d-117">提升属性</span><span class="sxs-lookup"><span data-stu-id="3f43d-117">Promoting Properties</span></span>](../core/promoting-properties.md)