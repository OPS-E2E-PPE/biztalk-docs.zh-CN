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
ms.openlocfilehash: 618d5475842a9e5844f289a7ca77e4d9a725b130
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990214"
---
# <a name="nested-positional-records"></a><span data-ttu-id="e9bfe-102">嵌套位置记录</span><span class="sxs-lookup"><span data-stu-id="e9bfe-102">Nested Positional Records</span></span>
<span data-ttu-id="e9bfe-103">如果允许嵌套位置记录**Max Occurs**的子记录的属性设置为一个正整数。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-103">Nested positional records are allowed if the **Max Occurs** property of child records is set to a positive integer.</span></span> <span data-ttu-id="e9bfe-104">字段自动计算应能够处理新的深度。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-104">Field autocalculation should be able to handle the new depth.</span></span> <span data-ttu-id="e9bfe-105">但是，此行为方式已修改。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-105">However, there is a modification to the way this behaves.</span></span> <span data-ttu-id="e9bfe-106">具体而言，由于可能存在空分隔符，所以仅在满足以下条件之一时，字段位置的自动计算才能进行：</span><span class="sxs-lookup"><span data-stu-id="e9bfe-106">Specifically, because of the possibility for null delimiters, autocalculation of field positions will function only if one of the following conditions is met:</span></span>  
  
- <span data-ttu-id="e9bfe-107">选定节点具有以中缀分隔的父节点。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-107">The selected node has a parent that is infix delimited.</span></span>  
  
- <span data-ttu-id="e9bfe-108">选定节点具有指定的起始位置。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-108">The selected node has a specified starting position.</span></span>  
  
  <span data-ttu-id="e9bfe-109">请注意，嵌套位置记录和其父记录为分隔容器（其中分隔符为空）的位置记录不同。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-109">Note that there is a distinction between nested positional records and positional records whose parent is a delimited container where the delimiter is null.</span></span> <span data-ttu-id="e9bfe-110">对于真正按位置嵌套的结构，确定其长度时不能有任何多义性。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-110">For structures to be truly nested positionally, there must not be any ambiguity in determining their length.</span></span> <span data-ttu-id="e9bfe-111">例如，分隔的循环节点可以包含出现 0 到 N 次的重复的位置记录。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-111">For example, a delimited loop node can contain a repeating positional record that occurs 0 to N times.</span></span> <span data-ttu-id="e9bfe-112">但是，对于本身为位置记录的循环节点，可能还包含与重复位置记录对等的字段，重复位置记录的出现次数必须是确定的（正整数）。</span><span class="sxs-lookup"><span data-stu-id="e9bfe-112">However, for that loop node itself to be positional, and possibly also contain fields as peers to the repeating positional record, the occurrence of the repeating positional record must be deterministic (a positive integer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9bfe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9bfe-113">See Also</span></span>  
 [<span data-ttu-id="e9bfe-114">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="e9bfe-114">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)