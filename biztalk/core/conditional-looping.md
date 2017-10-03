---
title: "条件循环 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5452f6b8768442b95ac6bddde0e84ba07f68c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="conditional-looping"></a><span data-ttu-id="063d1-102">循环的条件</span><span class="sxs-lookup"><span data-stu-id="063d1-102">Conditional Looping</span></span>
<span data-ttu-id="063d1-103">您可以添加到条件**循环**通过链接的输出的 functoid**循环**functoid 和**逻辑**functoid 到相同的目标记录。</span><span class="sxs-lookup"><span data-stu-id="063d1-103">You can add conditions to a **Looping** functoid by linking the output of a **Looping** functoid and a **Logical** functoid to the same destination record.</span></span> <span data-ttu-id="063d1-104">目标记录只有在符合逻辑条件时才会创建。</span><span class="sxs-lookup"><span data-stu-id="063d1-104">The destination records are created only when the logical condition is met.</span></span>  
  
## <a name="conditional-looping-map"></a><span data-ttu-id="063d1-105">条件循环映射</span><span class="sxs-lookup"><span data-stu-id="063d1-105">Conditional Looping Map</span></span>  
 <span data-ttu-id="063d1-106">![映射来说明条件循环 functoid。] (../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span><span class="sxs-lookup"><span data-stu-id="063d1-106">![Map illustrating conditional looping functoid.](../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")</span></span>  
  
 <span data-ttu-id="063d1-107">在前面的图中，第一个**相等**functoid 比较**名称**字段**FoodSurvey**到"Wendy Wheeler"。</span><span class="sxs-lookup"><span data-stu-id="063d1-107">In the preceding figure, the first **Equal** functoid compares the **Name** field under **FoodSurvey** to "Wendy Wheeler".</span></span> <span data-ttu-id="063d1-108">第二个**相等**functoid 比较**名称**字段**FlowerSurvey**到"李伟"。</span><span class="sxs-lookup"><span data-stu-id="063d1-108">The second **Equal** functoid compares the **Name** field under **FlowerSurvey** to "Kelly Focht".</span></span> <span data-ttu-id="063d1-109">因此，地图创建目标**地址**仅为两个名称的记录。</span><span class="sxs-lookup"><span data-stu-id="063d1-109">Thus, the map creates the destination **Address** records only for the two names.</span></span> <span data-ttu-id="063d1-110">使用中的示例数据**循环**functoid 的示例中，输出实例消息将出现，如下所示。</span><span class="sxs-lookup"><span data-stu-id="063d1-110">Using the sample data from the **Looping** functoid example, the output instance message would appear as follows.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a><span data-ttu-id="063d1-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="063d1-111">See Also</span></span>  
 <span data-ttu-id="063d1-112">[如何添加循环到图 Functoid](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="063d1-112">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="063d1-113">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="063d1-113">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="063d1-114">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="063d1-114">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="063d1-115">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="063d1-115">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="063d1-116">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="063d1-116">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="063d1-117">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="063d1-117">Record Count Functoid</span></span>](../core/record-count-functoid.md)