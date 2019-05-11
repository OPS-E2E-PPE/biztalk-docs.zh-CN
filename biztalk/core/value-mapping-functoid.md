---
title: 值映射 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca60ff3024eb1b4cadc42e42c65a0c44c82ef5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292614"
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="41675-102">值映射 Functoid</span><span class="sxs-lookup"><span data-stu-id="41675-102">Value Mapping Functoid</span></span>
<span data-ttu-id="41675-103">**值映射**functoid 在其第一个参数为 true，则返回其第二个参数的值。</span><span class="sxs-lookup"><span data-stu-id="41675-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="41675-104">提取 functoid 的一个常见用途是将一个字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="41675-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="41675-105">若要通过将多个记录转换为一条记录平展输入消息的一部分，请使用[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="41675-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="41675-106">下图显示了具有的地图**值映射**functoid 用于将一个字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="41675-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="41675-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="41675-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span></span>  
<span data-ttu-id="41675-108">值映射 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="41675-108">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="41675-109">下面的代码演示的输入的实例消息中的一对名称和值分配给**名称**并**值**属性。</span><span class="sxs-lookup"><span data-stu-id="41675-109">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
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
  
 <span data-ttu-id="41675-110">上面的映射可以将此消息转换为一个其中值分配给具有单独的记录中的相应名称的属性。</span><span class="sxs-lookup"><span data-stu-id="41675-110">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="41675-111">**相等**functoid 测试的值**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="41675-111">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="41675-112">第一个**相等**的值的 functoid 测试**名称**是否为"WindSpeed"。</span><span class="sxs-lookup"><span data-stu-id="41675-112">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="41675-113">当**名称**为"WindSpeed，"第一个**相等**functoid 将返回**True**。</span><span class="sxs-lookup"><span data-stu-id="41675-113">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="41675-114">这反过来允许**值映射**若要设置的值的 functoid **WindSpeed**输出实例消息中的属性。</span><span class="sxs-lookup"><span data-stu-id="41675-114">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="41675-115">取消创建空标记</span><span class="sxs-lookup"><span data-stu-id="41675-115">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="41675-116">若要取消空标记，请使用控制值映射 functoid，如果或不创建某个标记。</span><span class="sxs-lookup"><span data-stu-id="41675-116">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="41675-117">如果值的计算结果为 true，目标将创建字段;否则将不创建目标字段。</span><span class="sxs-lookup"><span data-stu-id="41675-117">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="41675-118">在循环方案中，使用判断 functoid 并将其连接到的目标记录或字段。</span><span class="sxs-lookup"><span data-stu-id="41675-118">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="41675-119">如果条件的计算结果为 false，将不会创建该标记。</span><span class="sxs-lookup"><span data-stu-id="41675-119">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="41675-120">有关示例，请参阅[条件循环](../core/conditional-looping.md)。</span><span class="sxs-lookup"><span data-stu-id="41675-120">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="41675-121">强制创建空标记</span><span class="sxs-lookup"><span data-stu-id="41675-121">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="41675-122">若要强制创建空标记，可以添加一个值的目标字段或链接值属性中**Concatenate** functoid 到目标字段。</span><span class="sxs-lookup"><span data-stu-id="41675-122">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="41675-123">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则可以通过选择强制生成空标记"\<空\>"目标字段的值属性中的值。</span><span class="sxs-lookup"><span data-stu-id="41675-123">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty\>" value in the Value property of the destination field.</span></span> <span data-ttu-id="41675-124">在这种情况下将使用空值创建字段。</span><span class="sxs-lookup"><span data-stu-id="41675-124">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41675-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="41675-125">See Also</span></span>  
 <span data-ttu-id="41675-126">[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="41675-126">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="41675-127">[如何添加值映射 Functoid 映射到](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="41675-127">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="41675-128">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="41675-128">Advanced Functoids</span></span>](../core/advanced-functoids.md)