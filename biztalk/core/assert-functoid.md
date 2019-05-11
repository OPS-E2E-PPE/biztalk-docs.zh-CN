---
title: 添加 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e3f14c05d1d4fd6538c126659c27cdb8b25fe08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530618"
---
# <a name="assert-functoid"></a><span data-ttu-id="a57db-102">添加 Functoid</span><span class="sxs-lookup"><span data-stu-id="a57db-102">Assert Functoid</span></span>

## <a name="overview"></a><span data-ttu-id="a57db-103">概述</span><span class="sxs-lookup"><span data-stu-id="a57db-103">Overview</span></span>
<span data-ttu-id="a57db-104">**Assert** functoid 输出一个字符串值或引发异常，基于一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="a57db-104">The **Assert** functoid either outputs a string value or throws an exception based on a Boolean value.</span></span> <span data-ttu-id="a57db-105">如果将此 functoid 与一个或多个结合**逻辑**functoid，您可以有效地测试映射中的假设条件。</span><span class="sxs-lookup"><span data-stu-id="a57db-105">If you combine this functoid with one or more of the **Logical** functoids, you can effectively test assumptions about conditions in your map.</span></span> <span data-ttu-id="a57db-106">例如，如果有需要采购订单量从不超过某一阈值的映射，您可以测试采购订单值通过**Greater Than** functoid，然后连接到**Assert**functoid。</span><span class="sxs-lookup"><span data-stu-id="a57db-106">For example, if you have a map that expects purchase order amounts never to exceed a certain threshold, you can test the purchase order value by using the **Greater Than** functoid and then connect it to the **Assert** functoid.</span></span> <span data-ttu-id="a57db-107">如果判断 functoid 返回 **，则返回 True**，则**Assert** functoid 将引发异常使用您提供的字符串。</span><span class="sxs-lookup"><span data-stu-id="a57db-107">If the logical functoid returns **True**, the **Assert** functoid will throw an exception using a string you provide.</span></span>  
  
 <span data-ttu-id="a57db-108">![添加 Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span><span class="sxs-lookup"><span data-stu-id="a57db-108">![Assert Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57db-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a57db-109">See Also</span></span>  
 <span data-ttu-id="a57db-110">**声明 Functoid 参考**和**判断 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a57db-110">**Assert Functoid Reference** and **Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>