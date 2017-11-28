---
title: "循环 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="looping-functoid"></a><span data-ttu-id="639b5-102">“循环”Functoid</span><span class="sxs-lookup"><span data-stu-id="639b5-102">Looping Functoid</span></span>

## <a name="overview--example"></a><span data-ttu-id="639b5-103">概述和示例</span><span class="sxs-lookup"><span data-stu-id="639b5-103">Overview & example</span></span>
<span data-ttu-id="639b5-104">**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。</span><span class="sxs-lookup"><span data-stu-id="639b5-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="639b5-105">下图显示**循环**functoid 映射中用于组合地址从两个不同的调查问卷收集到单个主地址列表。</span><span class="sxs-lookup"><span data-stu-id="639b5-105">The following figure shows a **Looping**functoid used in a map to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="639b5-106">**循环**和**值映射 （平展）** functoid 应不能一起使用。</span><span class="sxs-lookup"><span data-stu-id="639b5-106">The **Looping** and **Value Mapping (Flattening)** functoids should not be used together.</span></span> <span data-ttu-id="639b5-107">如果两者共同使用，这会导致的编译的地图，假定循环依赖关系如下的目标节点没有源**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="639b5-107">If both are used together, it results in a compiled map that assumed there is no source looping dependency for the target nodes that are below the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="639b5-108">![映射的循环 functoid 用法。] (../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="639b5-108">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
  
 <span data-ttu-id="639b5-109">**FoodSurvey**和**FlowerSurvey**的源架构的循环记录映射到循环**地址**记录的目标架构。</span><span class="sxs-lookup"><span data-stu-id="639b5-109">The **FoodSurvey** and **FlowerSurvey** looping records of the source schema are mapped to the looping **Address** record of the destination schema.</span></span> <span data-ttu-id="639b5-110">如果输入的实例消息具有三个**FoodSurvey**记录和第二个**FlowerSurvey**记录，**循环**functoid 将合并这些文件以创建五个**地址**输出实例消息中的记录。</span><span class="sxs-lookup"><span data-stu-id="639b5-110">If an input instance message has three **FoodSurvey** records and two **FlowerSurvey** records, the **Looping**functoid combines these to create five **Address** records in the output instance message.</span></span>  
  
 <span data-ttu-id="639b5-111">下面的代码是示例输入的实例消息。</span><span class="sxs-lookup"><span data-stu-id="639b5-111">The following code is a sample input instance message.</span></span>  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 <span data-ttu-id="639b5-112">此输入的实例消息生成以下输出实例消息时由前面的图中的映射。</span><span class="sxs-lookup"><span data-stu-id="639b5-112">This input instance message produces the following output instance message when processed by the map in the preceding figure.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="639b5-113">**FoodSurvey**和**FlowerSurvey**现在合并的邮件地址。</span><span class="sxs-lookup"><span data-stu-id="639b5-113">The **FoodSurvey** and **FlowerSurvey** message addresses have been combined.</span></span> <span data-ttu-id="639b5-114">合并的消息不指示每个地址的源。</span><span class="sxs-lookup"><span data-stu-id="639b5-114">The combined message does not indicate the source of each address.</span></span> <span data-ttu-id="639b5-115">如果你想要跟踪源，将添加**源**属性设为**地址**记录的**MasterAddress**架构和映射的常量值。</span><span class="sxs-lookup"><span data-stu-id="639b5-115">If you want to track the source, add a **Source** attribute to the **Address** record of the **MasterAddress** schema and map a constant value.</span></span> <span data-ttu-id="639b5-116">若要设置此值，连接**FoodSurvey**字段对新**源**字段。</span><span class="sxs-lookup"><span data-stu-id="639b5-116">To set this value, connect the **FoodSurvey** field to the new **Source** field.</span></span> <span data-ttu-id="639b5-117">在连接器一行中，修改**链接属性**&#124;**编译器**&#124;**源链接**属性设置为"副本名称"。</span><span class="sxs-lookup"><span data-stu-id="639b5-117">On the connector line, modify the **Link Properties** &#124; **Compiler** &#124; **Source Links** property to "Copy name".</span></span> <span data-ttu-id="639b5-118">重复此流程的**FlowerSurvey**字段。</span><span class="sxs-lookup"><span data-stu-id="639b5-118">Repeat this process for the **FlowerSurvey** field.</span></span> <span data-ttu-id="639b5-119">重新处理输入的消息从上面生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="639b5-119">Reprocessing the input message from above yields the following output:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a><span data-ttu-id="639b5-120">与节点之间的关系</span><span class="sxs-lookup"><span data-stu-id="639b5-120">Relationships with nodes</span></span>

 <span data-ttu-id="639b5-121">在节点之间的关系会影响的行为**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="639b5-121">Relationships among nodes affect the behavior of the **Looping** functoid.</span></span> <span data-ttu-id="639b5-122">例如，链接的子节点和到源架构中的其父**循环**functoid 阻止创建目标节点。</span><span class="sxs-lookup"><span data-stu-id="639b5-122">For example, linking both a child node and its parent in the source schema to the **Looping** functoid prevents the destination node from being created.</span></span>  
  
 <span data-ttu-id="639b5-123">Functoid 也受源节点之间的关系。</span><span class="sxs-lookup"><span data-stu-id="639b5-123">Functoids are also affected by the relationships among source nodes.</span></span> <span data-ttu-id="639b5-124">连接到的源节点的同级子字段 functoid**循环**functoid 可能产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="639b5-124">Connecting a functoid to non-sibling child fields of source nodes of the **Looping** functoid may produce unexpected results.</span></span> <span data-ttu-id="639b5-125">例如，使用**字符串连接**functoid 组合**FoodSurvey**名称字段和**FlowerSurvey** 中字段的地址名称到地址字段**MasterAddress**会产生以下输出实例消息：</span><span class="sxs-lookup"><span data-stu-id="639b5-125">For example, using the **String Concatenate** functoid to combine the **FoodSurvey** Name field and **FlowerSurvey** Address field into the Address Name field in **MasterAddress** would produce the following output instance message:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="639b5-126">请注意如何**名称**字段是缺少**FoodSurvey**源消息，但呈现的**FlowerSurvey**源消息。</span><span class="sxs-lookup"><span data-stu-id="639b5-126">Notice how the **Name** field is missing for **FoodSurvey** source messages but is present for **FlowerSurvey** source messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="639b5-127">连接到的源节点的子字段 functoid**循环**functoid 可能产生意外的结果，如果源节点不是同级。</span><span class="sxs-lookup"><span data-stu-id="639b5-127">Connecting a functoid to child fields of source nodes of the **Looping** functoid may produce unexpected results if the source nodes are not siblings.</span></span>  
  
 <span data-ttu-id="639b5-128">**循环**functoid 是一个功能强大的构造，可以使用创建条件循环并将架构映射到目录。</span><span class="sxs-lookup"><span data-stu-id="639b5-128">The **Looping** functoid is a powerful construct that you can use to create conditional loops and to map schemas to catalogs.</span></span> <span data-ttu-id="639b5-129">也有一些副作用的重叠**循环**functoid 路径需要考虑在内。</span><span class="sxs-lookup"><span data-stu-id="639b5-129">There are also some effects of overlapping **Looping** functoid paths you need to take into account.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="639b5-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="639b5-130">Next steps</span></span>
  
-   [<span data-ttu-id="639b5-131">循环的条件</span><span class="sxs-lookup"><span data-stu-id="639b5-131">Conditional Looping</span></span>](../core/conditional-looping.md)  
  
-   [<span data-ttu-id="639b5-132">平面架构到目录</span><span class="sxs-lookup"><span data-stu-id="639b5-132">Flat Schema to Catalog</span></span>](../core/flat-schema-to-catalog.md)  
  
-   [<span data-ttu-id="639b5-133">循环路径</span><span class="sxs-lookup"><span data-stu-id="639b5-133">Loop Paths</span></span>](../core/loop-paths.md)  
  
## <a name="see-also"></a><span data-ttu-id="639b5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="639b5-134">See Also</span></span>  
 <span data-ttu-id="639b5-135">**循环 Functoid 引用的表**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="639b5-135">**Table Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>