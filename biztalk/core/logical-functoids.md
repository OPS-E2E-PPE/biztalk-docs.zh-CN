---
title: 判断 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873e2b0ea1189586f9cabfbcb43c6ef276f34e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007590"
---
# <a name="logical-functoids"></a><span data-ttu-id="af1d9-102">“判断”Functoid</span><span class="sxs-lookup"><span data-stu-id="af1d9-102">Logical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="af1d9-103">概述</span><span class="sxs-lookup"><span data-stu-id="af1d9-103">Overview</span></span>
<span data-ttu-id="af1d9-104">**逻辑**functoid 用于执行以下类型的操作：</span><span class="sxs-lookup"><span data-stu-id="af1d9-104">**Logical** functoids are used to perform the following types of operations:</span></span>  

- <span data-ttu-id="af1d9-105">在运行时执行特定的逻辑测试。</span><span class="sxs-lookup"><span data-stu-id="af1d9-105">Perform specific logical tests at run time.</span></span> <span data-ttu-id="af1d9-106">**逻辑或**，**逻辑非**并**逻辑和**functoid 可用于确定是否在目标实例消息中，如下所示创建一条记录：</span><span class="sxs-lookup"><span data-stu-id="af1d9-106">The **Logical OR**, **Logical NOT** and **Logical AND** functoids can be used to determine whether a record is created in a destination instance message, such as the following:</span></span>  

   <span data-ttu-id="af1d9-107">如果 ShipTo**或**orderedby 存在，创建 BillTo 地址记录。</span><span class="sxs-lookup"><span data-stu-id="af1d9-107">If ShipTo **OR** OrderedBy are present, create BillTo address record.</span></span>  

   <span data-ttu-id="af1d9-108">此外可以结合使用这些 functoid**循环**functoid 配置记录的循环的次数。</span><span class="sxs-lookup"><span data-stu-id="af1d9-108">You can also use these functoids in conjunction with the **Looping** functoid to configure how many times a record loops.</span></span>  

- <span data-ttu-id="af1d9-109">控制在运行时是否在目标实例消息中创建特定记录。</span><span class="sxs-lookup"><span data-stu-id="af1d9-109">Control whether a specific record is created in a destination instance message at run time.</span></span> <span data-ttu-id="af1d9-110">如 Functoid **IsNil**，**数判断**，**小于**，以及**大于**可以用于控制是否创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="af1d9-110">Functoids such as **IsNil**, **Logical Numeric**, **Less Than**, and **Greater Than** can be used to control whether a record is created.</span></span>  

   <span data-ttu-id="af1d9-111">如果一个这些判断 functoid 的结果是 **，则返回 True**，生成的目标实例消息中相应记录中。</span><span class="sxs-lookup"><span data-stu-id="af1d9-111">If the result of one of these logical functoids is **True**, the corresponding record in the destination instance message is generated.</span></span> <span data-ttu-id="af1d9-112">如果结果为**False**，不生成目标实例消息中的相应记录中。</span><span class="sxs-lookup"><span data-stu-id="af1d9-112">If the result is **False**, the corresponding record in the destination instance message is not generated.</span></span>  

  <span data-ttu-id="af1d9-113">这些 functoid **IsNil**，**逻辑日期**，**存在判断**，**逻辑非**，**逻辑数值**，并**字符串判断**只接受一个参数。</span><span class="sxs-lookup"><span data-stu-id="af1d9-113">The functoids **IsNil**, **Logical Date**, **Logical Existence**, **Logical NOT**, **Logical Numeric**, and **Logical String** accept only one parameter.</span></span> <span data-ttu-id="af1d9-114">这些 functoid**相等**，**大于**，**大于或等于**，**小于**，**小于或等于**，并**不等于**接受两个输入参数。</span><span class="sxs-lookup"><span data-stu-id="af1d9-114">The functoids **Equal**, **Greater Than**, **Greater Than or Equal To**, **Less Than**, **Less Than or Equal To**, and **Not Equal** accept two input parameters.</span></span> <span data-ttu-id="af1d9-115">而，则**逻辑和**并**逻辑或**functoid 接受 2 到 100 之间的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="af1d9-115">Whereas, the **Logical AND** and **Logical OR** functoids accept input parameters between 2 and 100.</span></span>  

  <span data-ttu-id="af1d9-116">输出**逻辑**functoid 还可以接受作为映射中其他 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="af1d9-116">The output of a **Logical** functoid can also be accepted as input to other functoids in a map.</span></span> <span data-ttu-id="af1d9-117">如果这两个**逻辑**functoid 和循环 functoid 链接在一起，并链接到目标架构中记录，然后，使用循环 functoid 时，才**逻辑**functoid 输出是**True**。</span><span class="sxs-lookup"><span data-stu-id="af1d9-117">If both a **Logical** functoid and a looping functoid are linked together, and then linked to a record in the destination schema, the looping functoid is used only when the **Logical** functoid output is **True**.</span></span>  

  <span data-ttu-id="af1d9-118">此外可以使用**逻辑**functoid 一起**值映射**或**值映射 （平展）** functoid，以控制是否在目标实例消息中的记录创建。</span><span class="sxs-lookup"><span data-stu-id="af1d9-118">You can also use **Logical** functoids with the **Value Mapping** or **Value Mapping (Flattening)** functoids to control whether a record in the destination instance message is created.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="af1d9-119">如果两个记录或源架构中的字段链接到两个不同**逻辑**functoid，然后将每个链接**逻辑**functoid 到目标架构中的相同记录仅在首**逻辑**functoid 用于在生成可扩展样式表语言转换 (XSLT)。</span><span class="sxs-lookup"><span data-stu-id="af1d9-119">If you link two records or fields in the source schema to two different **Logical** functoids, and then link each of the **Logical** functoids to the same record in the destination schema, only the first **Logical** functoid is used in the generated Extensible Stylesheet Language Transformations (XSLT).</span></span> <span data-ttu-id="af1d9-120">第二个链接，从第二个**逻辑**functoid，将被忽略。</span><span class="sxs-lookup"><span data-stu-id="af1d9-120">The second link, from the second **Logical** functoid, is ignored.</span></span>  

> [!NOTE]
>  <span data-ttu-id="af1d9-121">“判断”functoid 在比较两个字符串时区分大小写。</span><span class="sxs-lookup"><span data-stu-id="af1d9-121">Logical functoids are case-sensitive when comparing two strings.</span></span> <span data-ttu-id="af1d9-122">例如，“Abc”和“abc”并不等效。</span><span class="sxs-lookup"><span data-stu-id="af1d9-122">For example, "Abc" and "abc" are not equal.</span></span> <span data-ttu-id="af1d9-123">此规则的例外是何时**逻辑**functoid 比较表示布尔值的字符串**True**并**False**。</span><span class="sxs-lookup"><span data-stu-id="af1d9-123">The exception to this rule is when **Logical** functoids compare strings that represent the Boolean values **True** and **False**.</span></span> <span data-ttu-id="af1d9-124">例如，“True”和“true”是等效的。</span><span class="sxs-lookup"><span data-stu-id="af1d9-124">For example, "True" and "true" are equal.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="af1d9-125">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="af1d9-125">Available functoids</span></span>  
 <span data-ttu-id="af1d9-126">**逻辑**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="af1d9-126">The **Logical** functoids are:</span></span> 

* <span data-ttu-id="af1d9-127">等于</span><span class="sxs-lookup"><span data-stu-id="af1d9-127">Equal</span></span>
* <span data-ttu-id="af1d9-128">大于</span><span class="sxs-lookup"><span data-stu-id="af1d9-128">Greater Than</span></span>
* <span data-ttu-id="af1d9-129">大于或等于</span><span class="sxs-lookup"><span data-stu-id="af1d9-129">Greater Than or Equal To</span></span>
* <span data-ttu-id="af1d9-130">IsNil</span><span class="sxs-lookup"><span data-stu-id="af1d9-130">IsNil</span></span>
* <span data-ttu-id="af1d9-131">小于</span><span class="sxs-lookup"><span data-stu-id="af1d9-131">Less Than</span></span>
* <span data-ttu-id="af1d9-132">小于或等于</span><span class="sxs-lookup"><span data-stu-id="af1d9-132">Less Than or Equal To</span></span>
* <span data-ttu-id="af1d9-133">逻辑与</span><span class="sxs-lookup"><span data-stu-id="af1d9-133">Logical AND</span></span>
* <span data-ttu-id="af1d9-134">日期判断</span><span class="sxs-lookup"><span data-stu-id="af1d9-134">Logical Date</span></span>
* <span data-ttu-id="af1d9-135">存在判断</span><span class="sxs-lookup"><span data-stu-id="af1d9-135">Logical Existence</span></span>
* <span data-ttu-id="af1d9-136">逻辑非</span><span class="sxs-lookup"><span data-stu-id="af1d9-136">Logical NOT</span></span>
* <span data-ttu-id="af1d9-137">数判断</span><span class="sxs-lookup"><span data-stu-id="af1d9-137">Logical Numeric</span></span>
* <span data-ttu-id="af1d9-138">逻辑或</span><span class="sxs-lookup"><span data-stu-id="af1d9-138">Logical OR</span></span>
* <span data-ttu-id="af1d9-139">字符串判断</span><span class="sxs-lookup"><span data-stu-id="af1d9-139">Logical String</span></span>
* <span data-ttu-id="af1d9-140">不等于</span><span class="sxs-lookup"><span data-stu-id="af1d9-140">Not Equal</span></span>

<span data-ttu-id="af1d9-141">这些函数的更多详细信息是[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="af1d9-141">More details on these functions are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="af1d9-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="af1d9-142">See Also</span></span>  
- [<span data-ttu-id="af1d9-143">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="af1d9-143">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="af1d9-144">**判断 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="af1d9-144">**Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
