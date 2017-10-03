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
ms.openlocfilehash: b2bb8e89ed790fe9916efe69685ad667d9fe9403
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="3878f-102">“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="3878f-102">Value Mapping Functoid</span></span>
<span data-ttu-id="3878f-103">**值映射**functoid 返回其第二个参数的值，如果其第一个参数为 true。</span><span class="sxs-lookup"><span data-stu-id="3878f-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="3878f-104">该 functoid 通常用于将字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="3878f-105">若要通过将多个记录转换为单个记录平展输入消息的一部分，使用[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="3878f-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="3878f-106">下图显示具有的映射**值映射**functoid 用于将字段的特性更改为一条记录的属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
<span data-ttu-id="3878f-107">“值映射”Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="3878f-107">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="3878f-108">下面的代码演示输入的实例消息中的一对名称和值将赋给**名称**和**值**属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-108">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
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
  
 <span data-ttu-id="3878f-109">上面的映射可以将此消息转换为以下消息，其中值分配给独立记录中具有相应名称的属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-109">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="3878f-110">**相等**functoid 测试的值**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-110">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="3878f-111">第一个**相等**functoid 测试的值**名称**正在"WindSpeed。"</span><span class="sxs-lookup"><span data-stu-id="3878f-111">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="3878f-112">当**名称**是"WindSpeed，"第一个**相等**functoid 返回**True**。</span><span class="sxs-lookup"><span data-stu-id="3878f-112">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="3878f-113">这样，反过来，**值映射**functoid，若要设置的值**WindSpeed**输出实例消息中的属性。</span><span class="sxs-lookup"><span data-stu-id="3878f-113">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="3878f-114">取消创建空标记</span><span class="sxs-lookup"><span data-stu-id="3878f-114">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="3878f-115">若要取消空标记，可以使用“值映射”functoid 控制是否创建某个标记。</span><span class="sxs-lookup"><span data-stu-id="3878f-115">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="3878f-116">如果值的计算结果为 True，则将创建目标字段，否则，不创建目标字段。</span><span class="sxs-lookup"><span data-stu-id="3878f-116">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="3878f-117">在循环方案中，使用“判断”functoid 并将其连接到目标记录或目标字段。</span><span class="sxs-lookup"><span data-stu-id="3878f-117">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="3878f-118">如果条件的计算结果为 false，则不创建标记。</span><span class="sxs-lookup"><span data-stu-id="3878f-118">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="3878f-119">有关示例，请参阅[条件循环](../core/conditional-looping.md)。</span><span class="sxs-lookup"><span data-stu-id="3878f-119">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="3878f-120">强制创建空标记</span><span class="sxs-lookup"><span data-stu-id="3878f-120">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="3878f-121">若要强制空标记来创建，可以添加一个值的目标字段或链接的值属性中**Concatenate** functoid 到目标字段。</span><span class="sxs-lookup"><span data-stu-id="3878f-121">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="3878f-122">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以通过选择强制生成空标记"\<空 >"的目标字段的值属性中的值。</span><span class="sxs-lookup"><span data-stu-id="3878f-122">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty>" value in the Value property of the destination field.</span></span> <span data-ttu-id="3878f-123">在这种情况下，将使用空值创建字段。</span><span class="sxs-lookup"><span data-stu-id="3878f-123">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3878f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3878f-124">See Also</span></span>  
 <span data-ttu-id="3878f-125">[映射 （拼合） Functoid 的值](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="3878f-125">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="3878f-126">[如何添加值映射到图 Functoid](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="3878f-126">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="3878f-127">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="3878f-127">Advanced Functoids</span></span>](../core/advanced-functoids.md)