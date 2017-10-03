---
title: "断言 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assert-functoid"></a><span data-ttu-id="f8604-102">“添加”Functoid</span><span class="sxs-lookup"><span data-stu-id="f8604-102">Assert Functoid</span></span>

## <a name="overview"></a><span data-ttu-id="f8604-103">概述</span><span class="sxs-lookup"><span data-stu-id="f8604-103">Overview</span></span>
<span data-ttu-id="f8604-104">**断言**functoid 输出一个字符串值或引发异常基于布尔值。</span><span class="sxs-lookup"><span data-stu-id="f8604-104">The **Assert** functoid either outputs a string value or throws an exception based on a Boolean value.</span></span> <span data-ttu-id="f8604-105">如果使用一个或多个组合此 functoid**逻辑**functoid，你可以有效地测试你的代码图中的假设条件。</span><span class="sxs-lookup"><span data-stu-id="f8604-105">If you combine this functoid with one or more of the **Logical** functoids, you can effectively test assumptions about conditions in your map.</span></span> <span data-ttu-id="f8604-106">例如，如果你有需要采购订单金额，决不要超过特定阈值的映射，你可以测试采购订单值使用**大于**functoid，然后连接到**断言**functoid。</span><span class="sxs-lookup"><span data-stu-id="f8604-106">For example, if you have a map that expects purchase order amounts never to exceed a certain threshold, you can test the purchase order value by using the **Greater Than** functoid and then connect it to the **Assert** functoid.</span></span> <span data-ttu-id="f8604-107">如果逻辑 functoid 返回**True**、**断言**functoid 将引发异常使用您提供的字符串。</span><span class="sxs-lookup"><span data-stu-id="f8604-107">If the logical functoid returns **True**, the **Assert** functoid will throw an exception using a string you provide.</span></span>  
  
 <span data-ttu-id="f8604-108">![断言 Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span><span class="sxs-lookup"><span data-stu-id="f8604-108">![Assert Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8604-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8604-109">See Also</span></span>  
 <span data-ttu-id="f8604-110">**断言 Functoid 引用**和**逻辑 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f8604-110">**Assert Functoid Reference** and **Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>