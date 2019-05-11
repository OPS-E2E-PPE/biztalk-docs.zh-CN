---
title: 添加高级 Functoid 映射到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbec5e9c-65b3-4734-a7fc-4ee66cf26eee
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2af647b8d39b7cb9d4b451537675ac55927462
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361036"
---
# <a name="adding-advanced-functoids-to-a-map"></a><span data-ttu-id="0cbbc-102">向映射添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-102">Adding Advanced Functoids to a Map</span></span>
<span data-ttu-id="0cbbc-103">中的 Functoid**高级**类别会更难理解和使用比其他类别中，组合在一起被归类为基本 functoid 的 functoid。</span><span class="sxs-lookup"><span data-stu-id="0cbbc-103">Functoids in the **Advanced** category are more complex to understand and use than the functoids in the other categories, together classified as basic functoids.</span></span> <span data-ttu-id="0cbbc-104">如果需要更复杂的映射，请使用高级的 functoid。</span><span class="sxs-lookup"><span data-stu-id="0cbbc-104">You use advanced functoids when you need more complex maps.</span></span> <span data-ttu-id="0cbbc-105">这些映射可能需要的记录进行计数、 遍历记录数目不定的记录，或运行任意复杂的脚本。</span><span class="sxs-lookup"><span data-stu-id="0cbbc-105">These maps might need to count records, loop through records with a variable number of subrecords, or run an arbitrarily complex script.</span></span>  
  
 <span data-ttu-id="0cbbc-106">本部分提供有关将添加中的 functoid 的分步说明**高级**类别与您的映射，包括正确地设置其输入和输出参数。</span><span class="sxs-lookup"><span data-stu-id="0cbbc-106">This section provides step-by-step instructions for adding functoids in the **Advanced** category to your maps, including correctly setting their input and output parameters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0cbbc-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="0cbbc-107">In This Section</span></span>  
  
-   [<span data-ttu-id="0cbbc-108">如何添加循环 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="0cbbc-108">How to Add Looping Functoids to a Map</span></span>](../core/how-to-add-looping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-109">如何添加值映射 （平展） Functoid 映射到</span><span class="sxs-lookup"><span data-stu-id="0cbbc-109">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-110">如何添加添加 Functoid 映射到</span><span class="sxs-lookup"><span data-stu-id="0cbbc-110">How to Add Assert Functoids to a Map</span></span>](../core/how-to-add-assert-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-111">如何添加表循环和表提取程序 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="0cbbc-111">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-112">如何向映射添加脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-112">How to Add Scripting Functoids to a Map</span></span>](../core/how-to-add-scripting-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-113">如何向映射中添加 Nil 值 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-113">How to Add Nil Value Functoids to a Map</span></span>](../core/how-to-add-nil-value-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-114">如何添加值映射 Functoid 映射到</span><span class="sxs-lookup"><span data-stu-id="0cbbc-114">How to Add Value Mapping Functoids to a Map</span></span>](../core/how-to-add-value-mapping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-115">如何向映射添加批量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-115">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-116">如何向映射添加迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-116">How to Add Iteration Functoids to a Map</span></span>](../core/how-to-add-iteration-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-117">如何向映射添加索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-117">How to Add Index Functoids to a Map</span></span>](../core/how-to-add-index-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="0cbbc-118">如何向映射添加记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="0cbbc-118">How to Add Record Count Functoids to a Map</span></span>](../core/how-to-add-record-count-functoids-to-a-map.md)