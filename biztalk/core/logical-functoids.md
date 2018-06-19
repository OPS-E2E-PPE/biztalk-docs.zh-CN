---
title: 逻辑 Functoid |Microsoft 文档
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
ms.openlocfilehash: a7907d1045fde39d5ece963bd78e00d027e8a9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262461"
---
# <a name="logical-functoids"></a><span data-ttu-id="19f7f-102">“判断”Functoid</span><span class="sxs-lookup"><span data-stu-id="19f7f-102">Logical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="19f7f-103">概述</span><span class="sxs-lookup"><span data-stu-id="19f7f-103">Overview</span></span>
<span data-ttu-id="19f7f-104">**逻辑**functoid 用于执行以下类型的操作：</span><span class="sxs-lookup"><span data-stu-id="19f7f-104">**Logical** functoids are used to perform the following types of operations:</span></span>  
  
-   <span data-ttu-id="19f7f-105">在运行时执行特定的逻辑测试。</span><span class="sxs-lookup"><span data-stu-id="19f7f-105">Perform specific logical tests at run time.</span></span> <span data-ttu-id="19f7f-106">**逻辑或**，**不逻辑**和**逻辑和**functoid 可以用于确定是否创建一条记录中的目标实例消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="19f7f-106">The **Logical OR**, **Logical NOT** and **Logical AND** functoids can be used to determine whether a record is created in a destination instance message, such as the following:</span></span>  
  
     <span data-ttu-id="19f7f-107">如果 ShipTo**或**OrderedBy 是否存在后，创建帐单寄往地址记录。</span><span class="sxs-lookup"><span data-stu-id="19f7f-107">If ShipTo **OR** OrderedBy are present, create BillTo address record.</span></span>  
  
     <span data-ttu-id="19f7f-108">此外可以结合使用这些 functoid**循环**functoid 配置记录循环的次数。</span><span class="sxs-lookup"><span data-stu-id="19f7f-108">You can also use these functoids in conjunction with the **Looping** functoid to configure how many times a record loops.</span></span>  
  
-   <span data-ttu-id="19f7f-109">控制在运行时是否在目标实例消息中创建特定记录。</span><span class="sxs-lookup"><span data-stu-id="19f7f-109">Control whether a specific record is created in a destination instance message at run time.</span></span> <span data-ttu-id="19f7f-110">如 Functoid **IsNil**，**逻辑数值**，**小于**，和**大于**可以用于控制是否创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="19f7f-110">Functoids such as **IsNil**, **Logical Numeric**, **Less Than**, and **Greater Than** can be used to control whether a record is created.</span></span>  
  
     <span data-ttu-id="19f7f-111">如果这些逻辑 functoid 之一的结果是**True**，生成的目标实例消息中的相应记录。</span><span class="sxs-lookup"><span data-stu-id="19f7f-111">If the result of one of these logical functoids is **True**, the corresponding record in the destination instance message is generated.</span></span> <span data-ttu-id="19f7f-112">如果结果为**False**，目标实例消息中的相应记录不会生成。</span><span class="sxs-lookup"><span data-stu-id="19f7f-112">If the result is **False**, the corresponding record in the destination instance message is not generated.</span></span>  
  
 <span data-ttu-id="19f7f-113">Functoid **IsNil**，**逻辑日期**，**逻辑是否存在**，**不逻辑**，**逻辑数值**，和**逻辑字符串**接受只有一个参数。</span><span class="sxs-lookup"><span data-stu-id="19f7f-113">The functoids **IsNil**, **Logical Date**, **Logical Existence**, **Logical NOT**, **Logical Numeric**, and **Logical String** accept only one parameter.</span></span> <span data-ttu-id="19f7f-114">Functoid**相等**，**大于**，**大于或等于**，**小于**，**小于或等于**，和**不等于**接受两个输入参数。</span><span class="sxs-lookup"><span data-stu-id="19f7f-114">The functoids **Equal**, **Greater Than**, **Greater Than or Equal To**, **Less Than**, **Less Than or Equal To**, and **Not Equal** accept two input parameters.</span></span> <span data-ttu-id="19f7f-115">而、**逻辑和**和**逻辑或**functoid 接受介于 2 和 100 之间的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="19f7f-115">Whereas, the **Logical AND** and **Logical OR** functoids accept input parameters between 2 and 100.</span></span>  
  
 <span data-ttu-id="19f7f-116">输出**逻辑**functoid 还可以接受作为其他 functoid 映射中的输入。</span><span class="sxs-lookup"><span data-stu-id="19f7f-116">The output of a **Logical** functoid can also be accepted as input to other functoids in a map.</span></span> <span data-ttu-id="19f7f-117">如果这两个**逻辑**functoid 和循环 functoid 是链接在一起，，然后链接到目标架构中的记录，则使用循环 functoid 仅当**逻辑**functoid 输出，则**True**。</span><span class="sxs-lookup"><span data-stu-id="19f7f-117">If both a **Logical** functoid and a looping functoid are linked together, and then linked to a record in the destination schema, the looping functoid is used only when the **Logical** functoid output is **True**.</span></span>  
  
 <span data-ttu-id="19f7f-118">你还可以使用**逻辑**与 functoid**值映射**或**值映射 （平展）** functoid 来控制是否在目标实例消息中的记录创建。</span><span class="sxs-lookup"><span data-stu-id="19f7f-118">You can also use **Logical** functoids with the **Value Mapping** or **Value Mapping (Flattening)** functoids to control whether a record in the destination instance message is created.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="19f7f-119">如果你将两个记录或源架构中的域链接到两个不同**逻辑**functoid，然后将每个链接**逻辑**functoid 对同一记录在目标架构中，只有第一个**逻辑**functoid 使用中生成可扩展样式表语言转换 (XSLT)。</span><span class="sxs-lookup"><span data-stu-id="19f7f-119">If you link two records or fields in the source schema to two different **Logical** functoids, and then link each of the **Logical** functoids to the same record in the destination schema, only the first **Logical** functoid is used in the generated Extensible Stylesheet Language Transformations (XSLT).</span></span> <span data-ttu-id="19f7f-120">第二个链接，从第二个**逻辑**functoid，将被忽略。</span><span class="sxs-lookup"><span data-stu-id="19f7f-120">The second link, from the second **Logical** functoid, is ignored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19f7f-121">“判断”functoid 在比较两个字符串时区分大小写。</span><span class="sxs-lookup"><span data-stu-id="19f7f-121">Logical functoids are case-sensitive when comparing two strings.</span></span> <span data-ttu-id="19f7f-122">例如，“Abc”和“abc”并不等效。</span><span class="sxs-lookup"><span data-stu-id="19f7f-122">For example, "Abc" and "abc" are not equal.</span></span> <span data-ttu-id="19f7f-123">此规则的例外是当**逻辑**functoid 比较表示布尔值的字符串**True**和**False**。</span><span class="sxs-lookup"><span data-stu-id="19f7f-123">The exception to this rule is when **Logical** functoids compare strings that represent the Boolean values **True** and **False**.</span></span> <span data-ttu-id="19f7f-124">例如，“True”和“true”是等效的。</span><span class="sxs-lookup"><span data-stu-id="19f7f-124">For example, "True" and "true" are equal.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="19f7f-125">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="19f7f-125">Available functoids</span></span>  
 <span data-ttu-id="19f7f-126">**逻辑**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="19f7f-126">The **Logical** functoids are:</span></span> 

* <span data-ttu-id="19f7f-127">等于</span><span class="sxs-lookup"><span data-stu-id="19f7f-127">Equal</span></span>
* <span data-ttu-id="19f7f-128">大于</span><span class="sxs-lookup"><span data-stu-id="19f7f-128">Greater Than</span></span>
* <span data-ttu-id="19f7f-129">大于或等于</span><span class="sxs-lookup"><span data-stu-id="19f7f-129">Greater Than or Equal To</span></span>
* <span data-ttu-id="19f7f-130">IsNil</span><span class="sxs-lookup"><span data-stu-id="19f7f-130">IsNil</span></span>
* <span data-ttu-id="19f7f-131">小于</span><span class="sxs-lookup"><span data-stu-id="19f7f-131">Less Than</span></span>
* <span data-ttu-id="19f7f-132">小于或等于</span><span class="sxs-lookup"><span data-stu-id="19f7f-132">Less Than or Equal To</span></span>
* <span data-ttu-id="19f7f-133">逻辑与</span><span class="sxs-lookup"><span data-stu-id="19f7f-133">Logical AND</span></span>
* <span data-ttu-id="19f7f-134">日期判断</span><span class="sxs-lookup"><span data-stu-id="19f7f-134">Logical Date</span></span>
* <span data-ttu-id="19f7f-135">存在判断</span><span class="sxs-lookup"><span data-stu-id="19f7f-135">Logical Existence</span></span>
* <span data-ttu-id="19f7f-136">逻辑非</span><span class="sxs-lookup"><span data-stu-id="19f7f-136">Logical NOT</span></span>
* <span data-ttu-id="19f7f-137">数判断</span><span class="sxs-lookup"><span data-stu-id="19f7f-137">Logical Numeric</span></span>
* <span data-ttu-id="19f7f-138">逻辑或</span><span class="sxs-lookup"><span data-stu-id="19f7f-138">Logical OR</span></span>
* <span data-ttu-id="19f7f-139">字符串判断</span><span class="sxs-lookup"><span data-stu-id="19f7f-139">Logical String</span></span>
* <span data-ttu-id="19f7f-140">不等于</span><span class="sxs-lookup"><span data-stu-id="19f7f-140">Not Equal</span></span>

<span data-ttu-id="19f7f-141">这些函数的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="19f7f-141">More details on these functions are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19f7f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19f7f-142">See Also</span></span>  
-  [<span data-ttu-id="19f7f-143">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="19f7f-143">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="19f7f-144">**逻辑 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="19f7f-144">**Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>