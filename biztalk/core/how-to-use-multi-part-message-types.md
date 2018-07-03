---
title: 如何使用多部分消息类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083746c38a175db840f4554297e86d26b5fcb366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013942"
---
# <a name="how-to-use-multi-part-message-types"></a><span data-ttu-id="ef2ee-102">如何使用多部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ef2ee-102">How to Use Multi-part Message Types</span></span>
<span data-ttu-id="ef2ee-103">每条消息都具有多部分消息类型，该消息类型描述由零个或多个消息部分构成的消息结构。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-103">Each message has a multi-part message type, a description of the message structure that consists of zero or more message parts.</span></span> <span data-ttu-id="ef2ee-104">这些部分由 XML 架构定义 (XSD) 语言架构或 .NET 类定义。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-104">The parts are defined by XML Schema Definition (XSD) language schemas or .NET classes.</span></span> <span data-ttu-id="ef2ee-105">您可以定义自己的多部分消息类型，或使用现有的 .NET 类和架构。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-105">You can define your own multi-part message types, or you can use existing .NET classes and schemas.</span></span>  

 <span data-ttu-id="ef2ee-106">您可以在业务流程中直接访问或分配消息部分，或使用消息部分中已公开为可分辨字段或属性字段的单个元素。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-106">You can access or assign message parts directly within your orchestration, or you can use individual elements of message parts that are exposed as distinguished fields or property fields.</span></span> <span data-ttu-id="ef2ee-107">有关详细信息，请参阅[使用可分辨字段和消息属性](../core/using-distinguished-fields-and-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-107">For more information, see [Using Distinguished Fields and Message Properties](../core/using-distinguished-fields-and-property-fields.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="ef2ee-108">多部分消息类型不一定包含多个部分。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-108">A multi-part message type does not necessarily contain multiple parts.</span></span>  

> [!NOTE]
>  <span data-ttu-id="ef2ee-109">可通过.NET 类型定义消息部分**XmlDocument**，这可以用于包含任意 XML 文档、 XML 序列化，任何.NET 类型或任何.NET 类型支持的自定义序列化。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-109">A message part can be defined by the .NET type **XmlDocument**, which can be used to contain an arbitrary XML document, by any .NET type that is XML-serializable, or by any .NET type supporting custom serialization.</span></span>  

## <a name="add-a-multi-part-message-type"></a><span data-ttu-id="ef2ee-110">添加多部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ef2ee-110">Add a multi-part message type</span></span>  

1.  <span data-ttu-id="ef2ee-111">在中**业务流程视图**窗口中，展开**类型**节点。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-111">In the **Orchestration View** window, expand the **Types** node.</span></span>  

2.  <span data-ttu-id="ef2ee-112">右键单击**多部分消息类型**，然后单击**新建多部分消息类型**。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-112">Right-click **Multi-part Message Types** and then click **New Multi-part Message Type**.</span></span>  

     <span data-ttu-id="ef2ee-113">**多部分消息类型**文件夹扩展，如果处于折叠状态，并与一个默认消息部分添加一个新的多部分消息类型。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-113">The **Multi-part Message Types** folder expands, if collapsed, and a new multi-part message type is added with one default message part.</span></span>  

3.  <span data-ttu-id="ef2ee-114">命名多部分消息类型和所提供的消息部分。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-114">Name the multi-part message type and the provided message part.</span></span>  

     <span data-ttu-id="ef2ee-115">如果您的多部分消息类型需要多个消息部分，可以通过将分配到的名称添加其他部分\<新建\>消息部分。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-115">If your multi-part message type requires more than one message part, you can add additional parts by assigning a name to the \<New\> message part.</span></span>  

4.  <span data-ttu-id="ef2ee-116">将每个消息部分与一个类型相关联，如 .NET 类或架构。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-116">Associate each message part with a type, such as a .NET class or schema.</span></span>  

## <a name="remove-a-multi-part-message-type"></a><span data-ttu-id="ef2ee-117">删除多部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ef2ee-117">Remove a multi-part message type</span></span>  

-   <span data-ttu-id="ef2ee-118">在中**业务流程视图**窗口中，右键单击多部分消息的类型要删除，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-118">In the **Orchestration View** window, right-click the multi-part message type you want to remove and then click **Delete**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ef2ee-119">从业务流程中删除多部分消息类型还会从使用它的消息中删除类型信息。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-119">Removing a multi-part message type from your orchestration will also remove the type information from messages that use it.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ef2ee-120">显示为只读的项目将在其他业务流程中定义。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-120">Items that appear as read-only are defined in another orchestration.</span></span>  

## <a name="remove-a-part-from-a-multi-part-message-type"></a><span data-ttu-id="ef2ee-121">从多部分消息类型中删除部件</span><span class="sxs-lookup"><span data-stu-id="ef2ee-121">Remove a part from a multi-part message type</span></span>  

-   <span data-ttu-id="ef2ee-122">在中**业务流程视图**窗口中，右键单击你想要删除，然后单击的部件**删除**。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-122">In the **Orchestration View** window, right-click the part you want to remove and click **Delete**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ef2ee-123">如果不能删除消息类型的消息部分**消息正文部分**属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-123">You cannot delete a message type's message part if the **Message Body Part** property is set to true.</span></span> <span data-ttu-id="ef2ee-124">必须先设置**消息正文部分**属性设置为 True 的另一个消息类型的部件。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-124">You must first set the **Message Body Part** property to True for another of the message type's parts.</span></span>  

## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a><span data-ttu-id="ef2ee-125">设置多部分消息类型的类型修饰符</span><span class="sxs-lookup"><span data-stu-id="ef2ee-125">Set the type modifier for a multi-part message type</span></span>  

- <span data-ttu-id="ef2ee-126">在中**属性**窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="ef2ee-126">In the **Properties** window, set the following property:</span></span>  


  |     <span data-ttu-id="ef2ee-127">“属性”</span><span class="sxs-lookup"><span data-stu-id="ef2ee-127">Property</span></span>      |                                                                                                                                                                                        <span data-ttu-id="ef2ee-128">Description</span><span class="sxs-lookup"><span data-stu-id="ef2ee-128">Description</span></span>                                                                                                                                                                                         |
  |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <span data-ttu-id="ef2ee-129">**类型修饰符**</span><span class="sxs-lookup"><span data-stu-id="ef2ee-129">**Type Modifier**</span></span> | <span data-ttu-id="ef2ee-130">确定多部分消息类型的作用域：</span><span class="sxs-lookup"><span data-stu-id="ef2ee-130">Determines the scope of the multi-part message type:</span></span><br /><br /> <span data-ttu-id="ef2ee-131">-   <strong>私有 —</strong>此多部分消息类型的访问权限仅限于包含模块。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-131">-   <strong>Private—</strong>Access to this multi-part message type is limited to the containing module.</span></span><br /><span data-ttu-id="ef2ee-132">-   <strong>公共 —</strong>访问此多部分消息类型不受限制。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-132">-   <strong>Public—</strong>Access to this multi-part message type is not limited.</span></span><br /><span data-ttu-id="ef2ee-133">-   <strong>内部 —</strong>此多部分消息类型的访问权限仅限于同一项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-133">-   <strong>Internal—</strong>Access to this multi-part message type is limited to modules within the same project.</span></span> |

## <a name="add-parts-to-an-existing-multi-part-message"></a><span data-ttu-id="ef2ee-134">将部件添加到现有的多部分消息</span><span class="sxs-lookup"><span data-stu-id="ef2ee-134">Add parts to an existing multi-part message</span></span>  

- <span data-ttu-id="ef2ee-135">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以向多部分 XLANG 消息中添加部分，还可以使用大于最初声明的部分号的索引来引用消息部分（如果该部分存在）。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-135">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the ability to add parts to a multi part XLANG message and also to refer to a message part by an index greater than the originally declared number of parts if the part exists.</span></span> <span data-ttu-id="ef2ee-136">在发送或接收附件数量不确定的 SMTP 邮件时，此功能可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-136">This functionality may be useful for sending or receiving SMTP messages with a variable number of attachments.</span></span> <span data-ttu-id="ef2ee-137">按照以下所述进行操作，即可实现此功能：</span><span class="sxs-lookup"><span data-stu-id="ef2ee-137">This functionality is implemented as follows:</span></span>  

- <span data-ttu-id="ef2ee-138">从你的项目，添加对的引用**Microsoft.XLANGs.BaseTypes**。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-138">From your project, add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  

- <span data-ttu-id="ef2ee-139">创建一个变量 (例如*xlangPart*) 的类型**Microsoft.XLANGs.BaseTypes.XLANGMessage**。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-139">Create a variable (for example *xlangPart*) of type **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span></span>  

- <span data-ttu-id="ef2ee-140">调用<em>xlangPart</em>**。AddPart(...)** 使用适当的参数从表达式形状。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-140">Call <em>xlangPart</em>**.AddPart(…)** using the appropriate arguments from an Expression shape.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="ef2ee-141">已增加的部件属于类型**XmlDocument**因此不能添加自定义格式的消息部分使用**addpart （)** 方法。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-141">The added parts are of type **XmlDocument** so you cannot add a custom formatted message part using the **AddPart()** method.</span></span>  

> [!NOTE]
>  <span data-ttu-id="ef2ee-142">如果收到包含多于声明部分数量更多部分消息，则业务流程引擎读取有多少个部分是在消息中，然后构造正确的部分类型的部件的匹配部分中声明的消息数类型，然后构造**XmlDocument**部件的剩余部分。</span><span class="sxs-lookup"><span data-stu-id="ef2ee-142">If a multi part message that contains greater than the number of declared parts is received, the orchestration engine reads how many parts there are in the message, then constructs the proper part types for the parts that match the number of parts in the declared message type and then constructs **XmlDocument** parts for the remaining parts.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ef2ee-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef2ee-143">See Also</span></span>  
 <span data-ttu-id="ef2ee-144">**IBaseMessage.AddPart 方法 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ef2ee-144">**IBaseMessage.AddPart Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
 <span data-ttu-id="ef2ee-145">[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="ef2ee-145">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 <span data-ttu-id="ef2ee-146">[使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="ef2ee-146">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="ef2ee-147">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="ef2ee-147">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)