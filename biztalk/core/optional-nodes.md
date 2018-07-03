---
title: 可选节点 |Microsoft Docs
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
ms.openlocfilehash: 91fe82709df36b374d8744e2060798074835b891
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994086"
---
# <a name="optional-nodes"></a><span data-ttu-id="ffe02-102">可选节点</span><span class="sxs-lookup"><span data-stu-id="ffe02-102">Optional Nodes</span></span>
<span data-ttu-id="ffe02-103">使用可选节点将导致在测试映射时出现警告。</span><span class="sxs-lookup"><span data-stu-id="ffe02-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="ffe02-104">在以下两种情况中源节点可能会被视为可选节点：</span><span class="sxs-lookup"><span data-stu-id="ffe02-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
- <span data-ttu-id="ffe02-105">实际的记录或字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="ffe02-105">The actual record or field is optional.</span></span>  
  
- <span data-ttu-id="ffe02-106">源记录或源字段是必需的，但是其父级、祖父级或更高级别的层次是可选的。</span><span class="sxs-lookup"><span data-stu-id="ffe02-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
  <span data-ttu-id="ffe02-107">可能存在这样的情况，源架构中的记录和字段是可选的，但目标架构却需要相应的记录或字段。</span><span class="sxs-lookup"><span data-stu-id="ffe02-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
  <span data-ttu-id="ffe02-108">在这种可能的情况，测试您的映射生成中的警告**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="ffe02-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="ffe02-109">此外，输出数据将不包含目标节点。</span><span class="sxs-lookup"><span data-stu-id="ffe02-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe02-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffe02-110">See Also</span></span>  
 [<span data-ttu-id="ffe02-111">测试映射</span><span class="sxs-lookup"><span data-stu-id="ffe02-111">Testing Maps</span></span>](../core/testing-maps.md)