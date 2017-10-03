---
title: "使用可分辨的字段和属性字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- messages, properties
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa0f969be7dfdd7cca991be134c9a25329f559a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-distinguished-fields-and-property-fields"></a><span data-ttu-id="c80db-102">使用可分辨的字段和属性字段</span><span class="sxs-lookup"><span data-stu-id="c80db-102">Using Distinguished Fields and Property Fields</span></span>
<span data-ttu-id="c80db-103">可分辨字段是具有特殊作用的消息数据，主要用于决策或处理业务流程中的数据。</span><span class="sxs-lookup"><span data-stu-id="c80db-103">Distinguished fields are message data of special interest that you use primarily to make decisions or to manipulate data in your orchestration.</span></span>  
  
 <span data-ttu-id="c80db-104">消息属性或者是数据（消息本身的内容），或者是元数据（与消息有关的上下文信息，例如时间戳或路由信息）。</span><span class="sxs-lookup"><span data-stu-id="c80db-104">Message properties are either data—contents of the message itself—or "metadata"—context information about the message such as time stamps or routing information.</span></span> <span data-ttu-id="c80db-105">您可以使用系统定义的消息上下文属性或传输上下文属性，或者可以通过引用属性架构内的架构字段来定义您自己的属性。</span><span class="sxs-lookup"><span data-stu-id="c80db-105">You can use system-defined message context properties or transport context properties, or you can define your own properties by making reference to schema fields from within a property schema.</span></span> <span data-ttu-id="c80db-106">属性用于订阅和相关。</span><span class="sxs-lookup"><span data-stu-id="c80db-106">Properties are used in subscriptions and correlations.</span></span>  
  
-   <span data-ttu-id="c80db-107">可以通过使用作为可分辨的字段或属性字段中指定架构中的字段**升级属性**从编辑器内的对话框。</span><span class="sxs-lookup"><span data-stu-id="c80db-107">You can designate a field in a schema as a distinguished field or property field by using the **Promote Properties** dialog box from within the Editor.</span></span> <span data-ttu-id="c80db-108">有关详细信息，请参阅[升级属性](../core/promoting-properties.md)</span><span class="sxs-lookup"><span data-stu-id="c80db-108">For more information, see [Promoting Properties](../core/promoting-properties.md)</span></span>  
  
-   <span data-ttu-id="c80db-109">您可以通过使用 DistinguishedField 属性修饰 .NET 类型中的字段来将这一字段指定为可分辨字段，或者通过 Property 属性将该字段指定为属性字段。</span><span class="sxs-lookup"><span data-stu-id="c80db-109">You can designate a field in a .NET type as a distinguished field by decorating it with the DistinguishedField attribute, or as a property by the Property attribute.</span></span>  
  
## <a name="using-distinguished-fields"></a><span data-ttu-id="c80db-110">使用可分辨字段</span><span class="sxs-lookup"><span data-stu-id="c80db-110">Using Distinguished Fields</span></span>  
 <span data-ttu-id="c80db-111">可分辨字段通过指向消息中的字段的路径进行引用，并且使用句点来分隔消息名称、包含该字段的任何记录的名称以及字段本身的名称：</span><span class="sxs-lookup"><span data-stu-id="c80db-111">Distinguished fields are referred to by the path to the field in the message, using periods to separate the message name, the names of any records that enclose the field, and the name of the field itself:</span></span>  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a><span data-ttu-id="c80db-112">使用属性字段</span><span class="sxs-lookup"><span data-stu-id="c80db-112">Using Property Fields</span></span>  
 <span data-ttu-id="c80db-113">一旦您将某一字段添加到某一属性架构后，就可以在含代码的业务流程和筛选器表达式中访问其值。</span><span class="sxs-lookup"><span data-stu-id="c80db-113">Once you have added a field to a property schema, its value can be accessed in the orchestration with code and in filter expressions.</span></span> <span data-ttu-id="c80db-114">有关属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c80db-114">For more information about property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c80db-115">消息内容或数据属性是实质上是对基础数据的快捷方式： 如果你修改属性，将修改的数据，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c80db-115">Message content or data properties are essentially shortcuts to the underlying data: if you modify the property, the data will be modified, and vice versa.</span></span>  
  
 <span data-ttu-id="c80db-116">消息属性通过消息名称后随括号中的命名空间（架构）和属性名称引用：</span><span class="sxs-lookup"><span data-stu-id="c80db-116">Message properties are referred to by the name of the message followed by the namespace (the schema) and property name in parentheses:</span></span>  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  <span data-ttu-id="c80db-117">当保留的关键字用作在架构中，字段的名称，并将该字段提升通过选择快速升级时，该字段的属性名称将更改为 __\<保留关键字 >。</span><span class="sxs-lookup"><span data-stu-id="c80db-117">When you use a reserved keyword as the name of a field in a schema, and you promote the field by selecting Quick Promotion, the property name of the field is changed to __\<Reserved Keyword>.</span></span> <span data-ttu-id="c80db-118">（双下划线添加到属性名称之前。）但是，如果您在业务流程表达式中使用此属性名称，则在生成业务流程时将会收到一个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c80db-118">(The double underscore is added before the property name.) However, if you use this property name in an orchestration expression, you will receive a compiler error when building the orchestration.</span></span>  <span data-ttu-id="c80db-119">若要更正这一错误，需要在双下划线前手动添加 @。</span><span class="sxs-lookup"><span data-stu-id="c80db-119">To work around this error, you need to manually add @ before the double underscore.</span></span> <span data-ttu-id="c80db-120">例如：</span><span class="sxs-lookup"><span data-stu-id="c80db-120">For example,</span></span>  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a><span data-ttu-id="c80db-121">属性集</span><span class="sxs-lookup"><span data-stu-id="c80db-121">Property Sets</span></span>  
 <span data-ttu-id="c80db-122">您还可以将一个消息的所有上下文属性（属性集）都分配给其他消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c80db-122">You can also assign all of the context properties of one message (a property set) to the context properties of another message.</span></span> <span data-ttu-id="c80db-123">若要分配某一属性集，只需将用括号括起来的星号放置于两个消息名称后，其方式与在括号中放置属性相同：</span><span class="sxs-lookup"><span data-stu-id="c80db-123">To assign a property set, you simply place an asterisk in parentheses after both message names, in the same way you would put a property in parentheses:</span></span>  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 <span data-ttu-id="c80db-124">在上例中将该属性集分配给 MyMessage2 后，MyMessage2 中的所有属性都将包含与 MyMessage1 中的属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="c80db-124">After the property set has been assigned to MyMessage2 in the example, all of the properties in MyMessage2 contain the same values as the properties in MyMessage1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80db-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c80db-125">See Also</span></span>  
 <span data-ttu-id="c80db-126">[提升属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c80db-126">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="c80db-127">[使用接收消息形状使用筛选器](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="c80db-127">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 <span data-ttu-id="c80db-128">[在业务流程中使用消息](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="c80db-128">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="c80db-129">有关 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="c80db-129">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)