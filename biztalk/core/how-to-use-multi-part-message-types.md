---
title: "如何使用多个部分消息类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87f210c4b0d2969edc9ddfa27b1d8494310eb6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-multi-part-message-types"></a><span data-ttu-id="ebec5-102">如何使用多个部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ebec5-102">How to Use Multi-part Message Types</span></span>
<span data-ttu-id="ebec5-103">每条消息都具有多部分消息类型，该消息类型描述由零个或多个消息部分构成的消息结构。</span><span class="sxs-lookup"><span data-stu-id="ebec5-103">Each message has a multi-part message type, a description of the message structure that consists of zero or more message parts.</span></span> <span data-ttu-id="ebec5-104">这些部分由 XML 架构定义 (XSD) 语言架构或 .NET 类定义。</span><span class="sxs-lookup"><span data-stu-id="ebec5-104">The parts are defined by XML Schema Definition (XSD) language schemas or .NET classes.</span></span> <span data-ttu-id="ebec5-105">您可以定义自己的多部分消息类型，或使用现有的 .NET 类和架构。</span><span class="sxs-lookup"><span data-stu-id="ebec5-105">You can define your own multi-part message types, or you can use existing .NET classes and schemas.</span></span>  
  
 <span data-ttu-id="ebec5-106">您可以在业务流程中直接访问或分配消息部分，或使用消息部分中已公开为可分辨字段或属性字段的单个元素。</span><span class="sxs-lookup"><span data-stu-id="ebec5-106">You can access or assign message parts directly within your orchestration, or you can use individual elements of message parts that are exposed as distinguished fields or property fields.</span></span> <span data-ttu-id="ebec5-107">有关详细信息，请参阅[使用可分辨字段和消息属性](../core/using-distinguished-fields-and-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="ebec5-107">For more information, see [Using Distinguished Fields and Message Properties](../core/using-distinguished-fields-and-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebec5-108">多部分消息类型不一定包含多个部分。</span><span class="sxs-lookup"><span data-stu-id="ebec5-108">A multi-part message type does not necessarily contain multiple parts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebec5-109">可以由.NET 类型定义的消息部分**XmlDocument**，这可以用于包含任意 XML 文档由 XML 序列化，任何.NET 类型或任何.NET 类型支持的自定义序列化。</span><span class="sxs-lookup"><span data-stu-id="ebec5-109">A message part can be defined by the .NET type **XmlDocument**, which can be used to contain an arbitrary XML document, by any .NET type that is XML-serializable, or by any .NET type supporting custom serialization.</span></span>  
  
## <a name="add-a-multi-part-message-type"></a><span data-ttu-id="ebec5-110">添加多个部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ebec5-110">Add a multi-part message type</span></span>  
  
1.  <span data-ttu-id="ebec5-111">在**业务流程视图**窗口中，展开**类型**节点。</span><span class="sxs-lookup"><span data-stu-id="ebec5-111">In the **Orchestration View** window, expand the **Types** node.</span></span>  
  
2.  <span data-ttu-id="ebec5-112">右键单击**多部分消息类型**，然后单击**新多部分消息类型**。</span><span class="sxs-lookup"><span data-stu-id="ebec5-112">Right-click **Multi-part Message Types** and then click **New Multi-part Message Type**.</span></span>  
  
     <span data-ttu-id="ebec5-113">**多部分消息类型**文件夹扩展，如果折叠状态，并与一个默认的消息部分添加一个新的多个部分消息类型。</span><span class="sxs-lookup"><span data-stu-id="ebec5-113">The **Multi-part Message Types** folder expands, if collapsed, and a new multi-part message type is added with one default message part.</span></span>  
  
3.  <span data-ttu-id="ebec5-114">命名多部分消息类型和所提供的消息部分。</span><span class="sxs-lookup"><span data-stu-id="ebec5-114">Name the multi-part message type and the provided message part.</span></span>  
  
     <span data-ttu-id="ebec5-115">如果多个部分消息类型需要多个消息部分，你可以通过分配到名称添加其他部分\<新建 > 消息部件。</span><span class="sxs-lookup"><span data-stu-id="ebec5-115">If your multi-part message type requires more than one message part, you can add additional parts by assigning a name to the \<New> message part.</span></span>  
  
4.  <span data-ttu-id="ebec5-116">将每个消息部分与一个类型相关联，如 .NET 类或架构。</span><span class="sxs-lookup"><span data-stu-id="ebec5-116">Associate each message part with a type, such as a .NET class or schema.</span></span>  
  
## <a name="remove-a-multi-part-message-type"></a><span data-ttu-id="ebec5-117">删除多个部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ebec5-117">Remove a multi-part message type</span></span>  
  
-   <span data-ttu-id="ebec5-118">在**业务流程视图**窗口中，右键单击多部分消息你想要删除，然后单击的类型**删除**。</span><span class="sxs-lookup"><span data-stu-id="ebec5-118">In the **Orchestration View** window, right-click the multi-part message type you want to remove and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebec5-119">从业务流程中删除多部分消息类型还会从使用它的消息中删除类型信息。</span><span class="sxs-lookup"><span data-stu-id="ebec5-119">Removing a multi-part message type from your orchestration will also remove the type information from messages that use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebec5-120">显示为只读的项目将在其他业务流程中定义。</span><span class="sxs-lookup"><span data-stu-id="ebec5-120">Items that appear as read-only are defined in another orchestration.</span></span>  
  
## <a name="remove-a-part-from-a-multi-part-message-type"></a><span data-ttu-id="ebec5-121">从多个部分消息类型删除部件</span><span class="sxs-lookup"><span data-stu-id="ebec5-121">Remove a part from a multi-part message type</span></span>  
  
-   <span data-ttu-id="ebec5-122">在**业务流程视图**窗口中，右键单击你想要删除，然后单击的部分**删除**。</span><span class="sxs-lookup"><span data-stu-id="ebec5-122">In the **Orchestration View** window, right-click the part you want to remove and click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebec5-123">如果不能删除消息类型的消息部分**消息正文部分**属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="ebec5-123">You cannot delete a message type's message part if the **Message Body Part** property is set to true.</span></span> <span data-ttu-id="ebec5-124">首先必须设置**消息正文部分**属性设置为 True 的另一个消息类型的部件。</span><span class="sxs-lookup"><span data-stu-id="ebec5-124">You must first set the **Message Body Part** property to True for another of the message type's parts.</span></span>  
  
## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a><span data-ttu-id="ebec5-125">为多个部分消息类型设置的类型修饰符</span><span class="sxs-lookup"><span data-stu-id="ebec5-125">Set the type modifier for a multi-part message type</span></span>  
  
-   <span data-ttu-id="ebec5-126">在**属性**窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="ebec5-126">In the **Properties** window, set the following property:</span></span>  
  
    |<span data-ttu-id="ebec5-127">属性</span><span class="sxs-lookup"><span data-stu-id="ebec5-127">Property</span></span>|<span data-ttu-id="ebec5-128">Description</span><span class="sxs-lookup"><span data-stu-id="ebec5-128">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="ebec5-129">**类型修饰符**</span><span class="sxs-lookup"><span data-stu-id="ebec5-129">**Type Modifier**</span></span>|<span data-ttu-id="ebec5-130">确定多部分消息类型的作用域：</span><span class="sxs-lookup"><span data-stu-id="ebec5-130">Determines the scope of the multi-part message type:</span></span><br /><br /> <span data-ttu-id="ebec5-131">-   **私有-**到这种多个部分的消息类型的访问仅限于包含模块。</span><span class="sxs-lookup"><span data-stu-id="ebec5-131">-   **Private—**Access to this multi-part message type is limited to the containing module.</span></span><br /><span data-ttu-id="ebec5-132">-   **公共 —**访问此多个部分消息类型不受限制。</span><span class="sxs-lookup"><span data-stu-id="ebec5-132">-   **Public—**Access to this multi-part message type is not limited.</span></span><br /><span data-ttu-id="ebec5-133">-   **内部 —**到这种多个部分的消息类型的访问仅限于同一项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="ebec5-133">-   **Internal—**Access to this multi-part message type is limited to modules within the same project.</span></span>|  
  
## <a name="add-parts-to-an-existing-multi-part-message"></a><span data-ttu-id="ebec5-134">将部件添加到现有的多个部分消息</span><span class="sxs-lookup"><span data-stu-id="ebec5-134">Add parts to an existing multi-part message</span></span>  
  
-   <span data-ttu-id="ebec5-135">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以向多部分 XLANG 消息中添加部分，还可以使用大于最初声明的部分号的索引来引用消息部分（如果该部分存在）。</span><span class="sxs-lookup"><span data-stu-id="ebec5-135">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the ability to add parts to a multi part XLANG message and also to refer to a message part by an index greater than the originally declared number of parts if the part exists.</span></span> <span data-ttu-id="ebec5-136">在发送或接收附件数量不确定的 SMTP 邮件时，此功能可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="ebec5-136">This functionality may be useful for sending or receiving SMTP messages with a variable number of attachments.</span></span> <span data-ttu-id="ebec5-137">按照以下所述进行操作，即可实现此功能：</span><span class="sxs-lookup"><span data-stu-id="ebec5-137">This functionality is implemented as follows:</span></span>  
  
-   <span data-ttu-id="ebec5-138">从你的项目，添加对的引用**Microsoft.XLANGs.BaseTypes**。</span><span class="sxs-lookup"><span data-stu-id="ebec5-138">From your project, add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="ebec5-139">创建一个变量 (例如*xlangPart*) 类型的**Microsoft.XLANGs.BaseTypes.XLANGMessage**。</span><span class="sxs-lookup"><span data-stu-id="ebec5-139">Create a variable (for example *xlangPart*) of type **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span></span>  
  
-   <span data-ttu-id="ebec5-140">调用*xlangPart***。AddPart(...)**使用表达式形状从相应的参数。</span><span class="sxs-lookup"><span data-stu-id="ebec5-140">Call *xlangPart***.AddPart(…)** using the appropriate arguments from an Expression shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebec5-141">添加的部件属于类型**XmlDocument**无法添加自定义格式的消息部分使用**AddPart()**方法。</span><span class="sxs-lookup"><span data-stu-id="ebec5-141">The added parts are of type **XmlDocument** so you cannot add a custom formatted message part using the **AddPart()** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebec5-142">如果收到包含大于的声明部分数多部分消息时，有多少个部分是在消息中，业务流程引擎读取然后构造中声明的消息的部件的数量匹配的部件的正确部件类型类型，然后构造**XmlDocument**部件的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ebec5-142">If a multi part message that contains greater than the number of declared parts is received, the orchestration engine reads how many parts there are in the message, then constructs the proper part types for the parts that match the number of parts in the declared message type and then constructs **XmlDocument** parts for the remaining parts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebec5-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebec5-143">See Also</span></span>  
 <span data-ttu-id="ebec5-144">**IBaseMessage.AddPart 方法 (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ebec5-144">**IBaseMessage.AddPart Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
 <span data-ttu-id="ebec5-145">[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="ebec5-145">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 <span data-ttu-id="ebec5-146">[使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="ebec5-146">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="ebec5-147">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="ebec5-147">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)