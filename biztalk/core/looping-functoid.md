---
title: 循环 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed86e27ebb2ff9a2eace4801906d61ed677c85af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380461"
---
# <a name="looping-functoid"></a><span data-ttu-id="82c21-102">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="82c21-102">Looping Functoid</span></span>

## <a name="overview--example"></a><span data-ttu-id="82c21-103">概述和示例</span><span class="sxs-lookup"><span data-stu-id="82c21-103">Overview & example</span></span>
<span data-ttu-id="82c21-104">**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。</span><span class="sxs-lookup"><span data-stu-id="82c21-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="82c21-105">下图显示**循环**functoid 在映射中用于将地址合并两个不同调查中收集到单个主地址列表。</span><span class="sxs-lookup"><span data-stu-id="82c21-105">The following figure shows a **Looping**functoid used in a map to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82c21-106">**循环**并**值映射 （平展）** functoid 不应在一起。</span><span class="sxs-lookup"><span data-stu-id="82c21-106">The **Looping** and **Value Mapping (Flattening)** functoids should not be used together.</span></span> <span data-ttu-id="82c21-107">如果一起使用，这会导致编译的映射，假定没有源循环依存关系如下的目标节点**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="82c21-107">If both are used together, it results in a compiled map that assumed there is no source looping dependency for the target nodes that are below the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="82c21-108">![映射的循环 functoid 用法。](../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="82c21-108">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
  
 <span data-ttu-id="82c21-109">**FoodSurvey**并**FlowerSurvey**源架构的循环记录映射到循环**地址**目标架构的记录。</span><span class="sxs-lookup"><span data-stu-id="82c21-109">The **FoodSurvey** and **FlowerSurvey** looping records of the source schema are mapped to the looping **Address** record of the destination schema.</span></span> <span data-ttu-id="82c21-110">如果输入的实例消息具有三个**FoodSurvey**记录和两个**FlowerSurvey**记录**循环**functoid 将合并这些创建五个**地址**输出实例消息中的记录。</span><span class="sxs-lookup"><span data-stu-id="82c21-110">If an input instance message has three **FoodSurvey** records and two **FlowerSurvey** records, the **Looping**functoid combines these to create five **Address** records in the output instance message.</span></span>  
  
 <span data-ttu-id="82c21-111">下面的代码是示例输入的实例消息。</span><span class="sxs-lookup"><span data-stu-id="82c21-111">The following code is a sample input instance message.</span></span>  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 <span data-ttu-id="82c21-112">此输入的实例消息生成以下输出实例消息处理在上图中的映射时。</span><span class="sxs-lookup"><span data-stu-id="82c21-112">This input instance message produces the following output instance message when processed by the map in the preceding figure.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="82c21-113">**FoodSurvey**并**FlowerSurvey**消息地址已合并。</span><span class="sxs-lookup"><span data-stu-id="82c21-113">The **FoodSurvey** and **FlowerSurvey** message addresses have been combined.</span></span> <span data-ttu-id="82c21-114">组合的消息不指示每个地址的源。</span><span class="sxs-lookup"><span data-stu-id="82c21-114">The combined message does not indicate the source of each address.</span></span> <span data-ttu-id="82c21-115">如果你想要跟踪源，将添加**源**归于**地址**的记录**MasterAddress**架构和映射的常量值。</span><span class="sxs-lookup"><span data-stu-id="82c21-115">If you want to track the source, add a **Source** attribute to the **Address** record of the **MasterAddress** schema and map a constant value.</span></span> <span data-ttu-id="82c21-116">若要设置此值，连接 **FoodSurvey** 字段对新 **源** 字段。</span><span class="sxs-lookup"><span data-stu-id="82c21-116">To set this value, connect the **FoodSurvey** field to the new **Source** field.</span></span> <span data-ttu-id="82c21-117">在连接器一行中，修改 **链接属性** &#124; **编译器** &#124; **源链接** 属性设置为"副本名称"。</span><span class="sxs-lookup"><span data-stu-id="82c21-117">On the connector line, modify the **Link Properties** &#124; **Compiler** &#124; **Source Links** property to "Copy name".</span></span> <span data-ttu-id="82c21-118">重复此流程的 **FlowerSurvey** 字段。</span><span class="sxs-lookup"><span data-stu-id="82c21-118">Repeat this process for the **FlowerSurvey** field.</span></span> <span data-ttu-id="82c21-119">重新处理从上面输入的消息将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="82c21-119">Reprocessing the input message from above yields the following output:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a><span data-ttu-id="82c21-120">与节点之间的关系</span><span class="sxs-lookup"><span data-stu-id="82c21-120">Relationships with nodes</span></span>

 <span data-ttu-id="82c21-121">节点间的关系影响的行为**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="82c21-121">Relationships among nodes affect the behavior of the **Looping** functoid.</span></span> <span data-ttu-id="82c21-122">例如，链接的子节点和源架构中的其父级**循环**functoid 禁止创建目标节点。</span><span class="sxs-lookup"><span data-stu-id="82c21-122">For example, linking both a child node and its parent in the source schema to the **Looping** functoid prevents the destination node from being created.</span></span>  
  
 <span data-ttu-id="82c21-123">Functoid 的源节点间的关系也会受到影响。</span><span class="sxs-lookup"><span data-stu-id="82c21-123">Functoids are also affected by the relationships among source nodes.</span></span> <span data-ttu-id="82c21-124">Functoid 连接到的源节点的非同级子字段**循环**functoid 可能产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="82c21-124">Connecting a functoid to non-sibling child fields of source nodes of the **Looping** functoid may produce unexpected results.</span></span> <span data-ttu-id="82c21-125">例如，使用**String Concatenate** functoid 将合并**FoodSurvey**名称字段和**FlowerSurvey** 中字段的地址名称到地址字段**MasterAddress**会生成以下输出实例消息：</span><span class="sxs-lookup"><span data-stu-id="82c21-125">For example, using the **String Concatenate** functoid to combine the **FoodSurvey** Name field and **FlowerSurvey** Address field into the Address Name field in **MasterAddress** would produce the following output instance message:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="82c21-126">请注意如何**名称**字段缺少**FoodSurvey**源消息，但存在可用于**FlowerSurvey**源消息。</span><span class="sxs-lookup"><span data-stu-id="82c21-126">Notice how the **Name** field is missing for **FoodSurvey** source messages but is present for **FlowerSurvey** source messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82c21-127">Functoid 连接到的源节点的子字段**循环**functoid 可能产生意外的结果，如果源节点不是同级。</span><span class="sxs-lookup"><span data-stu-id="82c21-127">Connecting a functoid to child fields of source nodes of the **Looping** functoid may produce unexpected results if the source nodes are not siblings.</span></span>  
  
 <span data-ttu-id="82c21-128">**循环**functoid 是一个功能强大的构造，可以使用用于创建条件循环并将架构映射到目录。</span><span class="sxs-lookup"><span data-stu-id="82c21-128">The **Looping** functoid is a powerful construct that you can use to create conditional loops and to map schemas to catalogs.</span></span> <span data-ttu-id="82c21-129">此外，还有一些效果的重叠**循环**functoid 路径需要考虑在内。</span><span class="sxs-lookup"><span data-stu-id="82c21-129">There are also some effects of overlapping **Looping** functoid paths you need to take into account.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="82c21-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82c21-130">Next steps</span></span>
  
-   [<span data-ttu-id="82c21-131">条件循环</span><span class="sxs-lookup"><span data-stu-id="82c21-131">Conditional Looping</span></span>](../core/conditional-looping.md)  
  
-   [<span data-ttu-id="82c21-132">将平面架构转换为目录</span><span class="sxs-lookup"><span data-stu-id="82c21-132">Flat Schema to Catalog</span></span>](../core/flat-schema-to-catalog.md)  
  
-   [<span data-ttu-id="82c21-133">循环路径</span><span class="sxs-lookup"><span data-stu-id="82c21-133">Loop Paths</span></span>](../core/loop-paths.md)  
  
## <a name="see-also"></a><span data-ttu-id="82c21-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="82c21-134">See Also</span></span>  
 <span data-ttu-id="82c21-135">**表循环 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="82c21-135">**Table Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>