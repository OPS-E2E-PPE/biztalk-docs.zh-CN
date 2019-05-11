---
title: 属性架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8ffc953ecc4b68f2f3c0f195b3dd268f526b86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398457"
---
# <a name="property-schemas"></a><span data-ttu-id="c6bc0-102">属性架构</span><span class="sxs-lookup"><span data-stu-id="c6bc0-102">Property Schemas</span></span>

## <a name="promoted-properties"></a><span data-ttu-id="c6bc0-103">升级的属性</span><span class="sxs-lookup"><span data-stu-id="c6bc0-103">Promoted properties</span></span>
<span data-ttu-id="c6bc0-104">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，升级属性允许各个 BizTalk Server 组件访问的数据的键项，在此上下文中称为可分辨的字段和属性字段，而无需了解如何查找的实例消息中到达这些消息本身中。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], promoted properties enable various BizTalk Server components to access key items of data, known in this context as distinguished fields and property fields that arrive within an instance message without needing to know how to look for them within the message itself.</span></span> <span data-ttu-id="c6bc0-105">对于不同类型的消息，可以确定哪些数据需要提升到更可见级别。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-105">For different types of messages, you can determine which items of data require promotion to a more visible level.</span></span> <span data-ttu-id="c6bc0-106">具体取决于如何选择升级此类字段，您可能需要创建和定义关联的属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-106">Depending on how you choose to promote such fields, you may need to create and define an associated property schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6bc0-107">升级的属性仅限于非重复元素/属性。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-107">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
 <span data-ttu-id="c6bc0-108">可分辨的字段只能在业务流程中访问，并且不需要创建相应属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-108">Distinguished fields are accessible only within orchestrations and do not require the creation of a corresponding property schema.</span></span> <span data-ttu-id="c6bc0-109">如果仅需要访问升级的消息数据从业务流程中，可以将数据升级为一个或多个可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-109">If you only need to access promoted message data from within an orchestration, you can promote the data as one or more distinguished fields.</span></span>  
  
 <span data-ttu-id="c6bc0-110">属性字段是可从各种 BizTalk Server 组件，包括管道和业务流程内部访问。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-110">Property fields are accessible from within various BizTalk Server components, including pipelines and orchestrations.</span></span> <span data-ttu-id="c6bc0-111">属性字段还可以用于消息路由。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-111">Property fields can also be used for message routing.</span></span> <span data-ttu-id="c6bc0-112">如果你需要访问升级消息数据从上下文以外的其他业务流程中，则必须创建一个或多个属性架构来描述您要升级的数据。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-112">If you need to access promoted message data from contexts other than within orchestrations, you must create one or more property schemas to describe the data you are promoting.</span></span>  
  
 <span data-ttu-id="c6bc0-113">属性架构是使用消息架构相关联的特殊架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-113">A property schema is a special schema that you associate with a message schema.</span></span> <span data-ttu-id="c6bc0-114">它用于将实例消息中的特定值升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-114">It is used for promoting specific values from within an instance message into the message context.</span></span> <span data-ttu-id="c6bc0-115">属性升级提供了一种用于提取关键信息来自定义实例消息中，并使其更轻松地访问 BizTalk Server 组件，处理消息，则通过 BizTalk 的集中式的机制服务器。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-115">Property promotion provides a centralized mechanism for pulling key pieces of information that you define from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span>  
  
## <a name="create-property-schema-overview"></a><span data-ttu-id="c6bc0-116">创建属性架构概述</span><span class="sxs-lookup"><span data-stu-id="c6bc0-116">Create property schema overview</span></span>
 <span data-ttu-id="c6bc0-117">通过使用 BizTalk Server 的快速升级功能，可以自动创建默认属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-117">You can automatically create a default property schema by using the quick promotion feature of BizTalk Server.</span></span> <span data-ttu-id="c6bc0-118">这是创建用于属性字段升级所需的属性架构的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-118">This is the easiest way to create the property schema required for property field promotion.</span></span> <span data-ttu-id="c6bc0-119">有关如何执行快速升级的详细信息，请参阅[如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-119">For more information about how to perform quick promotions, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="c6bc0-120">此外可以创建新的属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-120">You can also create new property schema.</span></span> <span data-ttu-id="c6bc0-121">打开 BizTalk 项目时，选择 BizTalk 项目中，右键单击并选择**外**，单击**新项**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-121">When a BizTalk project is open, select the BizTalk project, right-click and select **Add**, click **New Item**, and then click **Schema**.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="c6bc0-122">如果与消息架构相关联的属性架构，这两个必须在相同的 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-122">If a property schema is associated with a message schema, then these two must be in the same BizTalk project.</span></span> <span data-ttu-id="c6bc0-123">不支持从不同的 BizTalk 项目中其关联的消息架构分隔属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-123">Separating property schema from its associated message schema in different BizTalk projects is not supported.</span></span>  
>
>  - <span data-ttu-id="c6bc0-124">如果您有两个属性架构具有相同的命名空间，即使它们在不同的程序集定义，架构将无法解析正确地在运行时。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-124">If you have two property schemas that have the same namespace, even though they are defined in different assemblies, the schemas will not resolve properly at runtime.</span></span> <span data-ttu-id="c6bc0-125">在运行时，将发生路由失败。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-125">You will get a routing failure at runtime.</span></span>  

## <a name="distinguished-fields-and-property-fields"></a><span data-ttu-id="c6bc0-126">可分辨的字段和属性字段</span><span class="sxs-lookup"><span data-stu-id="c6bc0-126">Distinguished fields and property fields</span></span> 
 <span data-ttu-id="c6bc0-127">有两种类型的属性升级： 可分辨字段和属性字段。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-127">There are two types of property promotion: distinguished fields and property fields.</span></span> <span data-ttu-id="c6bc0-128">后一种类型使用属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-128">The latter type uses property schemas.</span></span> <span data-ttu-id="c6bc0-129">在 BizTalk 编辑器中，这两种类型的属性升级使用来管理**升级属性**对话框中，使用访问**升级属性**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-129">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which you access by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="c6bc0-130">有一些限制，您可以将升级的值。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-130">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="c6bc0-131">有关详细信息，请参阅中的表[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-131">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
>
>  - <span data-ttu-id="c6bc0-132">可分辨的字段不显示在筛选表达式中。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-132">Distinguished fields do not appear in filter expressions.</span></span> <span data-ttu-id="c6bc0-133">只有属性字段显示在筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-133">Only property fields appear in filter expressions.</span></span>  
  
 <span data-ttu-id="c6bc0-134">属性架构十分简单与消息架构进行比较时。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-134">Property schemas are simple when compared to message schemas.</span></span> <span data-ttu-id="c6bc0-135">在架构树中，仅允许您插入**Field 元素**节点的直接子节点作为节点**架构**节点，创建两层级别的结构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-135">In the schema tree, you are only allowed to insert **Field Element** nodes as immediate child nodes of the **Schema** node, creating a structure that is two levels deep.</span></span> <span data-ttu-id="c6bc0-136">大多数情况下，设置的属性**字段元素**作为您的节点一样**Field 元素**出现在消息架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-136">For the most part, you set the properties of the **Field Element** nodes as you would for **Field Element** nodes appearing in a message schema.</span></span> <span data-ttu-id="c6bc0-137">您仅限于使用 XSD 简单类型。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-137">You are limited to using only XSD simple types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6bc0-138">不应重命名任何正由另一个架构的架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-138">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="c6bc0-139">这包括已为其建立升级的属性架构。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-139">This includes property schemas for which promotions have already been established.</span></span> <span data-ttu-id="c6bc0-140">如果这样做，正在使用的架构不能以查找其他架构，因为它包含的名称将不再准确。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-140">If you do so, the schema that is being used will not be able to find the other schema because the name it contains will no longer be accurate.</span></span>  
  
 <span data-ttu-id="c6bc0-141">**Property Schema Base**属性仅适用于**Field 元素**节点属性架构中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-141">The **Property Schema Base** property is unique to **Field Element** nodes as they appear in property schemas.</span></span> <span data-ttu-id="c6bc0-142">此属性默认情况下，为空白，但可以设置为**MessageDataPropertyBase**或**MessageContextPropertyBase**，从而导致**propSchFieldBase**属性要添加到**fieldInfo**批注元素包含一个或多个这些值。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-142">This property is blank by default, but can be set to either **MessageDataPropertyBase** or **MessageContextPropertyBase**, resulting in a **propSchFieldBase** attribute being added to the **fieldInfo** annotation element with one or the other of these values.</span></span>  
  
 <span data-ttu-id="c6bc0-143">当**propSchFieldBase**属性设置为**MessageDataPropertyBase**，这意味着升级属性的值对应于消息，例如，某些字段的值中的数据。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-143">When the **propSchFieldBase** attribute is set to **MessageDataPropertyBase**, it means that the value of the promoted property corresponds to data in the message, such as the value of some field.</span></span> <span data-ttu-id="c6bc0-144">当**propSchFieldBase**属性设置为**MessageContextPropertyBase**，这意味着升级属性的值可能是从其他，信封，如位置或，它可能是由设置管道组件。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-144">When the **propSchFieldBase** attribute is set to **MessageContextPropertyBase**, it means that the value of the promoted property may be from somewhere else, such as an envelope, or that it may be set by a pipeline component.</span></span>  
  
 <span data-ttu-id="c6bc0-145">**字段元素**属性架构中的节点还具有一个名为属性**敏感信息**，它设置为时**是**，将使相应的值在中不可见BizTalk 浏览器和消息事件和服务实例跟踪，从而保留其敏感性。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-145">**Field Element** nodes in property schemas also have a property called **Sensitive Information**, which when set to **Yes**, will keep the corresponding value from being visible from within BizTalk Explorer and message event and service instance tracking, thereby preserving its sensitive nature.</span></span>  <span data-ttu-id="c6bc0-146">请参阅**敏感信息**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-146">See **Sensitive Information** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for more details.</span></span>
  
 <span data-ttu-id="c6bc0-147">以下 XML 架构定义 (XSD) 语言表示的属性架构包含批注与该架构标识为属性架构的架构元素相关联 (schema_type ="property")。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-147">The following XML Schema definition (XSD) language representation of a property schema contains an annotation associated with the schema element that identifies this schema as a property schema (schema_type="property").</span></span> <span data-ttu-id="c6bc0-148">它还包含三个**Field 元素**节点下面**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-148">It also contains three **Field Element** nodes below the **Schema** node.</span></span> <span data-ttu-id="c6bc0-149">第一个**Field 元素**节点，名为 PromProp1，没有值定义为其**Property Schema Base**属性，但后两个**字段元素**节点具有属性设置为**MessageDataPropertyBase**并**MessageContextPropertyBase**分别。</span><span class="sxs-lookup"><span data-stu-id="c6bc0-149">The first **Field Element** node, named PromProp1, does not have a value defined for its **Property Schema Base** property, but the latter two **Field Element** nodes have that property set to **MessageDataPropertyBase** and **MessageContextPropertyBase**, respectively.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
           targetNamespace="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
       <xs:appinfo>  
  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6bc0-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6bc0-150">See Also</span></span>  
 [<span data-ttu-id="c6bc0-151">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="c6bc0-151">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)