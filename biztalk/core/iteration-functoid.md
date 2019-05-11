---
title: 迭代 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4074e5555a327ab18e1991727d88011b395ae8e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380688"
---
# <a name="iteration-functoid"></a><span data-ttu-id="4e5e2-102">迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="4e5e2-102">Iteration Functoid</span></span>
<span data-ttu-id="4e5e2-103">**迭代**functoid 输出循环中的当前记录的索引结构，从第一条记录，2 表示第二个记录 1 开始，依次类推。</span><span class="sxs-lookup"><span data-stu-id="4e5e2-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="4e5e2-104">下图显示**迭代**functoid 结合**大于或等于**functoid**小于或等于**functoid，和一个**和** functoid 创建的等效**为**循环。</span><span class="sxs-lookup"><span data-stu-id="4e5e2-104">The following figure shows an **Iteration** functoid combined with a **Greater Than or Equal To** functoid, a **Less Than or Equal To** functoid, and an **And** functoid to create the equivalent of a **For** loop.</span></span>  
  
 <span data-ttu-id="4e5e2-105">![说明如何使用迭代 functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")</span><span class="sxs-lookup"><span data-stu-id="4e5e2-105">![Map illustrating the use of the iteration functoid](../core/media/iterationfunctoid.gif "iterationfunctoid")</span></span>  
<span data-ttu-id="4e5e2-106">迭代 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="4e5e2-106">Iteration Functoid Map</span></span>  
  
 <span data-ttu-id="4e5e2-107">假定**大于或等于**functoid 测试的值大于或等于 2，并且**小于或等于**functoid 测试的值小于或等于 4。</span><span class="sxs-lookup"><span data-stu-id="4e5e2-107">Assume that the **Greater Than or Equal To** functoid tests for values greater than or equal to 2, and the **Less Than or Equal To** functoid tests for values less than or equal to 4.</span></span> <span data-ttu-id="4e5e2-108">在这种情况下，**并**functoid 将返回**true**仅对记录 2、 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="4e5e2-108">In that case, the **And** functoid will return **true** only for records 2, 3, and 4.</span></span> <span data-ttu-id="4e5e2-109">因此，输出实例将包含两个、 3 个或四个输入的实例消息的记录。</span><span class="sxs-lookup"><span data-stu-id="4e5e2-109">Thus, the output instance will contain records two, three, and four of the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5e2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e5e2-110">See Also</span></span>  
 <span data-ttu-id="4e5e2-111">[如何向映射添加迭代 Functoid](../core/how-to-add-iteration-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="4e5e2-111">[How to Add Iteration Functoids to a Map](../core/how-to-add-iteration-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="4e5e2-112">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="4e5e2-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="4e5e2-113">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="4e5e2-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="4e5e2-114">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="4e5e2-114">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="4e5e2-115">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="4e5e2-115">Record Count Functoid</span></span>](../core/record-count-functoid.md)