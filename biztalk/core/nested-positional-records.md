---
title: 嵌套位置记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eddb7925a34e79c1da45a6ec6e2670f9632695
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323617"
---
# <a name="nested-positional-records"></a><span data-ttu-id="2931f-102">嵌套位置记录</span><span class="sxs-lookup"><span data-stu-id="2931f-102">Nested Positional Records</span></span>
<span data-ttu-id="2931f-103">如果允许嵌套位置记录**Max Occurs**的子记录的属性设置为一个正整数。</span><span class="sxs-lookup"><span data-stu-id="2931f-103">Nested positional records are allowed if the **Max Occurs** property of child records is set to a positive integer.</span></span> <span data-ttu-id="2931f-104">字段自动计算应能够处理新的深度。</span><span class="sxs-lookup"><span data-stu-id="2931f-104">Field autocalculation should be able to handle the new depth.</span></span> <span data-ttu-id="2931f-105">但是，没有对此行为的方式的修改。</span><span class="sxs-lookup"><span data-stu-id="2931f-105">However, there is a modification to the way this behaves.</span></span> <span data-ttu-id="2931f-106">具体而言，由于可能存在空分隔符，自动计算的字段位置将函数仅当满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="2931f-106">Specifically, because of the possibility for null delimiters, autocalculation of field positions will function only if one of the following conditions is met:</span></span>  
  
- <span data-ttu-id="2931f-107">所选的节点具有中缀分隔的父级。</span><span class="sxs-lookup"><span data-stu-id="2931f-107">The selected node has a parent that is infix delimited.</span></span>  
  
- <span data-ttu-id="2931f-108">所选的节点具有指定的起始位置。</span><span class="sxs-lookup"><span data-stu-id="2931f-108">The selected node has a specified starting position.</span></span>  
  
  <span data-ttu-id="2931f-109">请注意，嵌套位置记录和位置记录的父级是分隔符为空的分隔的容器之间的区别。</span><span class="sxs-lookup"><span data-stu-id="2931f-109">Note that there is a distinction between nested positional records and positional records whose parent is a delimited container where the delimiter is null.</span></span> <span data-ttu-id="2931f-110">对于真正按位置嵌套的结构不能有任何多义性确定其长度。</span><span class="sxs-lookup"><span data-stu-id="2931f-110">For structures to be truly nested positionally, there must not be any ambiguity in determining their length.</span></span> <span data-ttu-id="2931f-111">例如，分隔的循环节点可以包含出现 0 到 N 次的重复位置记录。</span><span class="sxs-lookup"><span data-stu-id="2931f-111">For example, a delimited loop node can contain a repeating positional record that occurs 0 to N times.</span></span> <span data-ttu-id="2931f-112">但是，该循环节点本身为位置，并且可能还包含字段作为对等互连到重复的位置记录重复位置记录必须具有确定性的匹配项 （正整数）。</span><span class="sxs-lookup"><span data-stu-id="2931f-112">However, for that loop node itself to be positional, and possibly also contain fields as peers to the repeating positional record, the occurrence of the repeating positional record must be deterministic (a positive integer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2931f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2931f-113">See Also</span></span>  
 [<span data-ttu-id="2931f-114">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="2931f-114">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)