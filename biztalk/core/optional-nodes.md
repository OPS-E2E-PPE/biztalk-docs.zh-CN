---
title: 可选节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263341"
---
# <a name="optional-nodes"></a><span data-ttu-id="65365-102">可选的节点</span><span class="sxs-lookup"><span data-stu-id="65365-102">Optional Nodes</span></span>
<span data-ttu-id="65365-103">使用可选节点将导致在测试映射时出现警告。</span><span class="sxs-lookup"><span data-stu-id="65365-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="65365-104">在以下两种情况中源节点可能会被视为可选节点：</span><span class="sxs-lookup"><span data-stu-id="65365-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
-   <span data-ttu-id="65365-105">实际的记录或字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="65365-105">The actual record or field is optional.</span></span>  
  
-   <span data-ttu-id="65365-106">源记录或源字段是必需的，但是其父级、祖父级或更高级别的层次是可选的。</span><span class="sxs-lookup"><span data-stu-id="65365-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
 <span data-ttu-id="65365-107">可能存在这样的情况，源架构中的记录和字段是可选的，但目标架构却需要相应的记录或字段。</span><span class="sxs-lookup"><span data-stu-id="65365-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
 <span data-ttu-id="65365-108">在这两种可能的情况，测试你的代码图生成中的某个警告**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="65365-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="65365-109">此外，输出数据将不包含目标节点。</span><span class="sxs-lookup"><span data-stu-id="65365-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65365-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65365-110">See Also</span></span>  
 [<span data-ttu-id="65365-111">测试映射</span><span class="sxs-lookup"><span data-stu-id="65365-111">Testing Maps</span></span>](../core/testing-maps.md)