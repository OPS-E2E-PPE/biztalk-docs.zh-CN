---
title: 级联 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020ff5eeb4bed7e5f1c6a09b1757300f2db525e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357610"
---
# <a name="cascading-functoids"></a><span data-ttu-id="ccec1-102">级联 Functoid</span><span class="sxs-lookup"><span data-stu-id="ccec1-102">Cascading Functoids</span></span>
<span data-ttu-id="ccec1-103">如果某个 functoid 在链接到目标架构中的记录或字段之前先链接到其他 functoid，此时称为对 Functoid 进行级联。</span><span class="sxs-lookup"><span data-stu-id="ccec1-103">Functoids are said to be cascaded when one functoid is linked to another functoid before it is linked to a record or field in the destination schema.</span></span> <span data-ttu-id="ccec1-104">例如，可以创建如下级联 functoid，其中两个串连的字符串产生第三个字符串来填充到目标架构的字段中。</span><span class="sxs-lookup"><span data-stu-id="ccec1-104">For example, you can create cascading functoids in which two concatenated strings produce a third string fed into a field in the destination schema.</span></span>  
  
 <span data-ttu-id="ccec1-105">在对 functoid 进行级联时，可以在网格页中创建多个连续的转换。</span><span class="sxs-lookup"><span data-stu-id="ccec1-105">When you cascade functoids, you can create multiple, consecutive transformations in the grid page.</span></span> <span data-ttu-id="ccec1-106">虽然对可以在一页中级联的 functoid 数量没有限制，但仍需谨慎使用级联。</span><span class="sxs-lookup"><span data-stu-id="ccec1-106">While there is no limit to the number of functoids that you can cascade in a page, use cascading wisely.</span></span> <span data-ttu-id="ccec1-107">复杂的级联会增加将输入实例消息转换为输出实例消息的时间，从而显著降低运行时的性能。</span><span class="sxs-lookup"><span data-stu-id="ccec1-107">Complex cascading can increase the time to transform an input instance message into an output instance message, significantly reducing run time performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccec1-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccec1-108">See Also</span></span>  
 <span data-ttu-id="ccec1-109">[映射中的 Functoid](../core/functoids-in-maps.md) </span><span class="sxs-lookup"><span data-stu-id="ccec1-109">[Functoids in Maps](../core/functoids-in-maps.md) </span></span>  
 [<span data-ttu-id="ccec1-110">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="ccec1-110">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)