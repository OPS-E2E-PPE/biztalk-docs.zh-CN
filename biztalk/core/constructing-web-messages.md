---
title: "构造 Web 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-web-messages"></a><span data-ttu-id="3e534-102">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="3e534-102">Constructing Web Messages</span></span>
<span data-ttu-id="3e534-103">可从 Web 消息类型构造 Web 消息。</span><span class="sxs-lookup"><span data-stu-id="3e534-103">You construct a Web message from a Web message type.</span></span> <span data-ttu-id="3e534-104">添加 Web 引用时，BizTalk 会基于已添加的 Web Services 的 Web 方法自动创建 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-104">When you add a Web reference, BizTalk automatically creates Web message types, which BizTalk creates based on the Web methods from the added Web service.</span></span> <span data-ttu-id="3e534-105">你可以向业务流程添加 Web 消息，并将消息类型设置为 Web 消息类型之一。</span><span class="sxs-lookup"><span data-stu-id="3e534-105">You add a Web message to your orchestration, setting the message type to one of the Web message types.</span></span> <span data-ttu-id="3e534-106">你可以基于基元 .NET 或架构类型创建各消息部分。</span><span class="sxs-lookup"><span data-stu-id="3e534-106">You create individual message parts based on primitive .NET or schema types.</span></span> <span data-ttu-id="3e534-107">构造的 Web 消息可以不包含任何消息部分。</span><span class="sxs-lookup"><span data-stu-id="3e534-107">You can construct a Web message that contains no message parts.</span></span>  
  
 <span data-ttu-id="3e534-108">**Web 消息类型**</span><span class="sxs-lookup"><span data-stu-id="3e534-108">**Web message types**</span></span>  
  
 <span data-ttu-id="3e534-109">Reference.odx 中定义的 Web 消息类型与一般消息类型相同，不同之处在于你不能对 Web 消息类型进行修改，重命名或删除。</span><span class="sxs-lookup"><span data-stu-id="3e534-109">Web message types, defined in the Reference.odx, are identical to a normal message type, except you cannot modify, rename or delete them.</span></span> <span data-ttu-id="3e534-110">若要删除 Web 消息类型，你必须从 BizTalk 项目删除 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="3e534-110">To delete a Web message type, you must remove the Web reference from your BizTalk project.</span></span>  
  
 <span data-ttu-id="3e534-111">BizTalk 项目为已添加的 Web Services 中的每个 Web 方法创建一个请求和一个响应 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-111">BizTalk project creates one request and one response Web message type for each Web method in the added Web service.</span></span> <span data-ttu-id="3e534-112">如果 Web 方法是单向操作，BizTalk 仅创建请求 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-112">If the Web method is a one-way operation, BizTalk only creates a request Web message type.</span></span> <span data-ttu-id="3e534-113">请求 Web 消息类型针对 Web 方法的每个输入参数各包含一个消息部分。</span><span class="sxs-lookup"><span data-stu-id="3e534-113">A request Web message type contains one message part for each input parameter of the Web method.</span></span> <span data-ttu-id="3e534-114">响应 Web 消息类型针对返回值包含一个消息部分，并针对 Web 方法的每个输出参数各包含一个消息部分。</span><span class="sxs-lookup"><span data-stu-id="3e534-114">A response Web message type contains one message part for the return value and one message part for each output parameter of the Web method.</span></span>  
  
 <span data-ttu-id="3e534-115">根据 Web 方法参数（输入或输出），BizTalk 从基元 .NET 类型或架构类型创建 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-115">Depending on the Web method parameter (input or output), BizTalk creates a Web message type from a primitive .NET type or a schema type.</span></span> <span data-ttu-id="3e534-116">如果 Web 方法参数是基元 .NET 类型，消息部分则使用基元 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-116">If the Web method parameter is a primitive .NET type, the message part uses a primitive .NET type.</span></span> <span data-ttu-id="3e534-117">如果 Web 方法参数是架构类型，BizTalk 将此架构类型作为 Reference.xsd 中的架构添加到 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="3e534-117">If the Web method parameter is a schema type, BizTalk adds the schema type to the BizTalk project as a schema in Reference.xsd.</span></span> <span data-ttu-id="3e534-118">架构是消息部分的基础。</span><span class="sxs-lookup"><span data-stu-id="3e534-118">The schema is the basis for the message part.</span></span> <span data-ttu-id="3e534-119">你可以在 Web 引用文件夹中查找 Reference.xsd。</span><span class="sxs-lookup"><span data-stu-id="3e534-119">You can find Reference.xsd in the Web references folder.</span></span>  
  
 <span data-ttu-id="3e534-120">另外，你还可以通过调用 .NET 类来创建基元和架构 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="3e534-120">Alternatively, you can create both primitive and schema .NET types by calling a .NET class.</span></span> <span data-ttu-id="3e534-121">通过使用一个.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="3e534-121">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
 <span data-ttu-id="3e534-122">**Web 消息**</span><span class="sxs-lookup"><span data-stu-id="3e534-122">**Web messages**</span></span>  
  
 <span data-ttu-id="3e534-123">Web 消息是使用（调用）Web Services 时所使用的消息。</span><span class="sxs-lookup"><span data-stu-id="3e534-123">Web messages are the messages you use when you consume (call) a Web service.</span></span> <span data-ttu-id="3e534-124">你可以以添加常规消息的方式将 Web 消息添加到业务流程，不同之处在于将消息类型设置为添加 Web 引用时 BizTalk 创建的 Web 消息类型之一。</span><span class="sxs-lookup"><span data-stu-id="3e534-124">You add a Web message to an orchestration the same way that you add a regular message, except that you set the message type to one of the Web message types that BizTalk created when you added a Web reference.</span></span>  
  
 <span data-ttu-id="3e534-125">**消息部分**</span><span class="sxs-lookup"><span data-stu-id="3e534-125">**Message parts**</span></span>  
  
 <span data-ttu-id="3e534-126">在创建 Web 消息之后，请构造各个消息部分。</span><span class="sxs-lookup"><span data-stu-id="3e534-126">After you create the Web message, you construct the individual message parts.</span></span> <span data-ttu-id="3e534-127">如果消息部分使用基元的.NET 类型，则使用**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="3e534-127">If your message part uses a primitive .NET type, you use a **Message Assignment** shape.</span></span> <span data-ttu-id="3e534-128">如果消息部分使用的架构类型，则使用**转换**形状或**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="3e534-128">If your message part uses a schema type, you use a **Transform** shape or **Message Assignment** shape.</span></span> <span data-ttu-id="3e534-129">有关详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="3e534-129">For more information, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e534-130">本节内容</span><span class="sxs-lookup"><span data-stu-id="3e534-130">In This Section</span></span>  
  
-   [<span data-ttu-id="3e534-131">如何添加 Web 消息</span><span class="sxs-lookup"><span data-stu-id="3e534-131">How to Add Web Messages</span></span>](../core/how-to-add-web-messages.md)  
  
-   [<span data-ttu-id="3e534-132">如何确定 Web 消息部分类型</span><span class="sxs-lookup"><span data-stu-id="3e534-132">How to Determine a Web Message Part Type</span></span>](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [<span data-ttu-id="3e534-133">如何构造从基元.NET 类型的 Web 消息部分</span><span class="sxs-lookup"><span data-stu-id="3e534-133">How to Construct a Web Message Part from a Primitive .NET Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [<span data-ttu-id="3e534-134">如何构造中的架构类型的 Web 消息部件</span><span class="sxs-lookup"><span data-stu-id="3e534-134">How to Construct a Web Message Part from a Schema Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [<span data-ttu-id="3e534-135">如何构造具有任何消息部分的 Web 消息</span><span class="sxs-lookup"><span data-stu-id="3e534-135">How to Construct a Web Message with No Message Parts</span></span>](../core/how-to-construct-a-web-message-with-no-message-parts.md)