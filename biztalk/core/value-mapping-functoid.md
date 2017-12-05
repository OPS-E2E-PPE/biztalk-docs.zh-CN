---
title: "值映射 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038d59827a62c9f4e83879ec7cf2e0b47fd738f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="f96dc-102">“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="f96dc-102">Value Mapping Functoid</span></span>
<span data-ttu-id="f96dc-103">**值映射**functoid 返回其第二个参数的值，如果其第一个参数为 true。</span><span class="sxs-lookup"><span data-stu-id="f96dc-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="f96dc-104">该 functoid 通常用于将字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="f96dc-105">若要通过将多个记录转换为单个记录平展输入消息的一部分，使用[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="f96dc-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="f96dc-106">下图显示具有的映射**值映射**functoid 用于将字段的特性更改为一条记录的属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="f96dc-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="f96dc-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span></span>  
<span data-ttu-id="f96dc-108">“值映射”Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="f96dc-108">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="f96dc-109">下面的代码演示输入的实例消息中的一对名称和值将赋给**名称**和**值**属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-109">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 <span data-ttu-id="f96dc-110">上面的映射可以将此消息转换为以下消息，其中值分配给独立记录中具有相应名称的属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-110">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="f96dc-111">**相等**functoid 测试的值**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-111">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="f96dc-112">第一个**相等**functoid 测试的值**名称**正在"WindSpeed。"</span><span class="sxs-lookup"><span data-stu-id="f96dc-112">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="f96dc-113">当**名称**是"WindSpeed，"第一个**相等**functoid 返回**True**。</span><span class="sxs-lookup"><span data-stu-id="f96dc-113">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="f96dc-114">这样，反过来，**值映射**functoid，若要设置的值**WindSpeed**输出实例消息中的属性。</span><span class="sxs-lookup"><span data-stu-id="f96dc-114">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="f96dc-115">取消创建空标记</span><span class="sxs-lookup"><span data-stu-id="f96dc-115">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="f96dc-116">若要取消空标记，可以使用“值映射”functoid 控制是否创建某个标记。</span><span class="sxs-lookup"><span data-stu-id="f96dc-116">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="f96dc-117">如果值的计算结果为 True，则将创建目标字段，否则，不创建目标字段。</span><span class="sxs-lookup"><span data-stu-id="f96dc-117">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="f96dc-118">在循环方案中，使用“判断”functoid 并将其连接到目标记录或目标字段。</span><span class="sxs-lookup"><span data-stu-id="f96dc-118">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="f96dc-119">如果条件的计算结果为 false，则不创建标记。</span><span class="sxs-lookup"><span data-stu-id="f96dc-119">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="f96dc-120">有关示例，请参阅[条件循环](../core/conditional-looping.md)。</span><span class="sxs-lookup"><span data-stu-id="f96dc-120">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="f96dc-121">强制创建空标记</span><span class="sxs-lookup"><span data-stu-id="f96dc-121">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="f96dc-122">若要强制空标记来创建，可以添加一个值的目标字段或链接的值属性中**Concatenate** functoid 到目标字段。</span><span class="sxs-lookup"><span data-stu-id="f96dc-122">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="f96dc-123">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以通过选择强制生成空标记"\<空\>"目标字段的值属性中的值。</span><span class="sxs-lookup"><span data-stu-id="f96dc-123">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty\>" value in the Value property of the destination field.</span></span> <span data-ttu-id="f96dc-124">在这种情况下，将使用空值创建字段。</span><span class="sxs-lookup"><span data-stu-id="f96dc-124">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96dc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f96dc-125">See Also</span></span>  
 <span data-ttu-id="f96dc-126">[映射 （拼合） Functoid 的值](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="f96dc-126">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="f96dc-127">[如何添加值映射到图 Functoid](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="f96dc-127">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="f96dc-128">高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="f96dc-128">Advanced Functoids</span></span>](../core/advanced-functoids.md)