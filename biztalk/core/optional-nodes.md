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
ms.openlocfilehash: bbab14a66f0ac88f32e945bf7b9c738eb419b654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323399"
---
# <a name="optional-nodes"></a><span data-ttu-id="0df52-102">可选节点</span><span class="sxs-lookup"><span data-stu-id="0df52-102">Optional Nodes</span></span>
<span data-ttu-id="0df52-103">使用可选节点会在测试映射时生成警告。</span><span class="sxs-lookup"><span data-stu-id="0df52-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="0df52-104">有在其中一个源节点可能会被视为可选的两个条件：</span><span class="sxs-lookup"><span data-stu-id="0df52-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
- <span data-ttu-id="0df52-105">实际的记录或字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="0df52-105">The actual record or field is optional.</span></span>  
  
- <span data-ttu-id="0df52-106">源记录或字段是必需的但父级、 祖父级和更高级别的层次结构是可选的。</span><span class="sxs-lookup"><span data-stu-id="0df52-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
  <span data-ttu-id="0df52-107">您可能会存在这样的情况的记录和源架构中的字段是可选的但目标架构所需的相应记录或字段。</span><span class="sxs-lookup"><span data-stu-id="0df52-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
  <span data-ttu-id="0df52-108">在这种可能的情况，测试您的映射生成中的警告**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="0df52-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="0df52-109">此外，输出数据将不包括目标节点。</span><span class="sxs-lookup"><span data-stu-id="0df52-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df52-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="0df52-110">See Also</span></span>  
 [<span data-ttu-id="0df52-111">测试映射</span><span class="sxs-lookup"><span data-stu-id="0df52-111">Testing Maps</span></span>](../core/testing-maps.md)