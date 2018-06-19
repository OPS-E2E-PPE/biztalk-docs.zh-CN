---
title: 属性架构 |Microsoft 文档
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
ms.openlocfilehash: d2fb50536b2521e77994baf0b6457206614b7eed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270037"
---
# <a name="property-schemas"></a><span data-ttu-id="ce3ab-102">属性架构</span><span class="sxs-lookup"><span data-stu-id="ce3ab-102">Property Schemas</span></span>

## <a name="promoted-properties"></a><span data-ttu-id="ce3ab-103">提升的属性</span><span class="sxs-lookup"><span data-stu-id="ce3ab-103">Promoted properties</span></span>
<span data-ttu-id="ce3ab-104">在 Microsoft 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，提升属性启用各种 BizTalk 服务器组件访问的数据的键项，在此上下文中称为可分辨的字段和属性而无需知道如何查找到达实例消息中的字段这些消息本身中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], promoted properties enable various BizTalk Server components to access key items of data, known in this context as distinguished fields and property fields that arrive within an instance message without needing to know how to look for them within the message itself.</span></span> <span data-ttu-id="ce3ab-105">对于不同类型的消息，您可以决定需要将哪些数据项升级到更高的可见级别。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-105">For different types of messages, you can determine which items of data require promotion to a more visible level.</span></span> <span data-ttu-id="ce3ab-106">根据所选择的用于升级此类字段的方式，您可能需要创建和定义一个关联属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-106">Depending on how you choose to promote such fields, you may need to create and define an associated property schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce3ab-107">升级属性仅限于非重复元素/特性。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-107">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
 <span data-ttu-id="ce3ab-108">可分辨字段只能在业务流程中进行访问，不需要创建相应的属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-108">Distinguished fields are accessible only within orchestrations and do not require the creation of a corresponding property schema.</span></span> <span data-ttu-id="ce3ab-109">如果仅需要在业务流程中访问升级的消息数据，您可以将数据升级为一个或多个可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-109">If you only need to access promoted message data from within an orchestration, you can promote the data as one or more distinguished fields.</span></span>  
  
 <span data-ttu-id="ce3ab-110">属性字段可以在各个 BizTalk Server 组件（包括管道和业务流程）中进行访问。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-110">Property fields are accessible from within various BizTalk Server components, including pipelines and orchestrations.</span></span> <span data-ttu-id="ce3ab-111">属性字段还可用于消息路由。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-111">Property fields can also be used for message routing.</span></span> <span data-ttu-id="ce3ab-112">如果需要在上下文（而不是在业务流程）中访问升级的消息数据，您必须创建一个或多个属性架构来描述要升级的数据。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-112">If you need to access promoted message data from contexts other than within orchestrations, you must create one or more property schemas to describe the data you are promoting.</span></span>  
  
 <span data-ttu-id="ce3ab-113">属性架构是一种与消息架构相关联的特殊架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-113">A property schema is a special schema that you associate with a message schema.</span></span> <span data-ttu-id="ce3ab-114">它用于将实例消息中的特定值升级到消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-114">It is used for promoting specific values from within an instance message into the message context.</span></span> <span data-ttu-id="ce3ab-115">属性升级提供了一种集中机制，通过该机制，您可以从实例消息中请求所定义的关键信息，并使其可更方便地被负责对通过 BizTalk Server 的消息进行处理的 BizTalk Server 组件访问。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-115">Property promotion provides a centralized mechanism for pulling key pieces of information that you define from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span>  
  
## <a name="create-property-schema-overview"></a><span data-ttu-id="ce3ab-116">创建属性架构概述</span><span class="sxs-lookup"><span data-stu-id="ce3ab-116">Create property schema overview</span></span>
 <span data-ttu-id="ce3ab-117">您可以通过使用 BizTalk Server 的快速升级功能自动创建默认属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-117">You can automatically create a default property schema by using the quick promotion feature of BizTalk Server.</span></span> <span data-ttu-id="ce3ab-118">这是创建属性字段升级所需的属性架构最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-118">This is the easiest way to create the property schema required for property field promotion.</span></span> <span data-ttu-id="ce3ab-119">有关如何执行快速提升的详细信息，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-119">For more information about how to perform quick promotions, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="ce3ab-120">你还可以创建新属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-120">You can also create new property schema.</span></span> <span data-ttu-id="ce3ab-121">打开 BizTalk 项目时，选择 BizTalk 项目，右键单击并选择**添加**，单击**新项**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-121">When a BizTalk project is open, select the BizTalk project, right-click and select **Add**, click **New Item**, and then click **Schema**.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="ce3ab-122">如果属性架构与消息架构相关联，则这两个架构必须位于同一 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-122">If a property schema is associated with a message schema, then these two must be in the same BizTalk project.</span></span> <span data-ttu-id="ce3ab-123">不支持将属性架构与其所关联的消息架构分隔在不同的 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-123">Separating property schema from its associated message schema in different BizTalk projects is not supported.</span></span>  
>
>  - <span data-ttu-id="ce3ab-124">如果有两个属性架构具有相同的命名空间，即使它们定义在不同的程序集中，在运行时也不能正确解析。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-124">If you have two property schemas that have the same namespace, even though they are defined in different assemblies, the schemas will not resolve properly at runtime.</span></span> <span data-ttu-id="ce3ab-125">在运行时将发生路由失败。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-125">You will get a routing failure at runtime.</span></span>  

## <a name="distinguished-fields-and-property-fields"></a><span data-ttu-id="ce3ab-126">可分辨的字段和属性字段</span><span class="sxs-lookup"><span data-stu-id="ce3ab-126">Distinguished fields and property fields</span></span> 
 <span data-ttu-id="ce3ab-127">属性升级有两种类型：可分辨字段和属性字段。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-127">There are two types of property promotion: distinguished fields and property fields.</span></span> <span data-ttu-id="ce3ab-128">后一种类型使用属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-128">The latter type uses property schemas.</span></span> <span data-ttu-id="ce3ab-129">在 BizTalk 编辑器中，你通过进行管理这两种类型的属性提升**升级属性**对话框中，你通过使用访问**升级属性**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-129">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which you access by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="ce3ab-130">对于可以升级的值有一些限制。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-130">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="ce3ab-131">有关详细信息，请参阅中的表[提升属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-131">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
>
>  - <span data-ttu-id="ce3ab-132">可分辨字段不显示在筛选器表达式中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-132">Distinguished fields do not appear in filter expressions.</span></span> <span data-ttu-id="ce3ab-133">只有属性字段才显示在筛选器表达式中。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-133">Only property fields appear in filter expressions.</span></span>  
  
 <span data-ttu-id="ce3ab-134">与消息架构相比，属性架构十分简单。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-134">Property schemas are simple when compared to message schemas.</span></span> <span data-ttu-id="ce3ab-135">在架构树中，你仅允许插入**Field 元素**的即时子节点的节点**架构**节点，创建结构，它是两个级别。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-135">In the schema tree, you are only allowed to insert **Field Element** nodes as immediate child nodes of the **Schema** node, creating a structure that is two levels deep.</span></span> <span data-ttu-id="ce3ab-136">大多数情况下，你设置的属性**Field 元素**作为你的节点将为**Field 元素**显示在消息架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-136">For the most part, you set the properties of the **Field Element** nodes as you would for **Field Element** nodes appearing in a message schema.</span></span> <span data-ttu-id="ce3ab-137">您只能使用 XSD 简单类型。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-137">You are limited to using only XSD simple types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce3ab-138">不应对正在由其他架构使用的架构进行重命名。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-138">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="ce3ab-139">包括已为其建立了升级的属性架构。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-139">This includes property schemas for which promotions have already been established.</span></span> <span data-ttu-id="ce3ab-140">如果这样做，正在使用的架构不能以查找其他架构，因为它包含的名称将不再准确。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-140">If you do so, the schema that is being used will not be able to find the other schema because the name it contains will no longer be accurate.</span></span>  
  
 <span data-ttu-id="ce3ab-141">**属性架构基**属性是唯一的**Field 元素**节点在属性架构中显示。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-141">The **Property Schema Base** property is unique to **Field Element** nodes as they appear in property schemas.</span></span> <span data-ttu-id="ce3ab-142">此属性默认情况下，为空，但可以设置为**MessageDataPropertyBase**或**MessageContextPropertyBase**，这会导致在**propSchFieldBase**属性添加到**fieldInfo**具有一个或多个这些值的批注元素。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-142">This property is blank by default, but can be set to either **MessageDataPropertyBase** or **MessageContextPropertyBase**, resulting in a **propSchFieldBase** attribute being added to the **fieldInfo** annotation element with one or the other of these values.</span></span>  
  
 <span data-ttu-id="ce3ab-143">当**propSchFieldBase**属性设置为**MessageDataPropertyBase**，这意味着提升属性的值对应于在消息中，如某些字段值的数据。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-143">When the **propSchFieldBase** attribute is set to **MessageDataPropertyBase**, it means that the value of the promoted property corresponds to data in the message, such as the value of some field.</span></span> <span data-ttu-id="ce3ab-144">当**propSchFieldBase**属性设置为**MessageContextPropertyBase**，则表明提升属性的值可能来自，如信封的其他位置，或者它可能是由设置管道组件。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-144">When the **propSchFieldBase** attribute is set to **MessageContextPropertyBase**, it means that the value of the promoted property may be from somewhere else, such as an envelope, or that it may be set by a pipeline component.</span></span>  
  
 <span data-ttu-id="ce3ab-145">**字段元素**属性架构中的节点还具有一个名为属性**敏感信息**，后者当设置为**是**，将会使相应的值不能从中查看BizTalk 资源管理器和消息事件和服务实例跟踪，这样既保留了其敏感的性质。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-145">**Field Element** nodes in property schemas also have a property called **Sensitive Information**, which when set to **Yes**, will keep the corresponding value from being visible from within BizTalk Explorer and message event and service instance tracking, thereby preserving its sensitive nature.</span></span>  <span data-ttu-id="ce3ab-146">请参阅**敏感信息**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-146">See **Sensitive Information** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for more details.</span></span>
  
 <span data-ttu-id="ce3ab-147">下面的属性架构的 XML 架构定义 (XSD) 语言表示形式包含一个批注，该批注与将该架构标识为属性架构 (schema_type="property") 的架构元素相关联。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-147">The following XML Schema definition (XSD) language representation of a property schema contains an annotation associated with the schema element that identifies this schema as a property schema (schema_type="property").</span></span> <span data-ttu-id="ce3ab-148">它还包含三个**Field 元素**节点下面**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-148">It also contains three **Field Element** nodes below the **Schema** node.</span></span> <span data-ttu-id="ce3ab-149">第一个**Field 元素**节点，名为 PromProp1，没有为定义的值其**属性架构基**属性，但后两个**Field 元素**节点具有属性设置为**MessageDataPropertyBase**和**MessageContextPropertyBase**分别。</span><span class="sxs-lookup"><span data-stu-id="ce3ab-149">The first **Field Element** node, named PromProp1, does not have a value defined for its **Property Schema Base** property, but the latter two **Field Element** nodes have that property set to **MessageDataPropertyBase** and **MessageContextPropertyBase**, respectively.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce3ab-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce3ab-150">See Also</span></span>  
 [<span data-ttu-id="ce3ab-151">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="ce3ab-151">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)