---
title: 添加到图高级 Functoid |Microsoft 文档
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
ms.openlocfilehash: fad75ed2c5c6779801e38f0c4b8f4505696bb476
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229901"
---
# <a name="adding-advanced-functoids-to-a-map"></a><span data-ttu-id="89e3e-102">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-102">Adding Advanced Functoids to a Map</span></span>
<span data-ttu-id="89e3e-103">中的 Functoid**高级**类别是更复杂，了解和使用比其他类别中，组合在一起被归类为基本 functoid functoid。</span><span class="sxs-lookup"><span data-stu-id="89e3e-103">Functoids in the **Advanced** category are more complex to understand and use than the functoids in the other categories, together classified as basic functoids.</span></span> <span data-ttu-id="89e3e-104">如果需要更复杂的映射，则可以使用高级 functoid。</span><span class="sxs-lookup"><span data-stu-id="89e3e-104">You use advanced functoids when you need more complex maps.</span></span> <span data-ttu-id="89e3e-105">这些映射可能需要对记录进行计数、遍历子记录数目不定的记录或者运行复杂的任意脚本。</span><span class="sxs-lookup"><span data-stu-id="89e3e-105">These maps might need to count records, loop through records with a variable number of subrecords, or run an arbitrarily complex script.</span></span>  
  
 <span data-ttu-id="89e3e-106">本部分提供有关将添加在 functoid 的分步说明**高级**到你的映射，包括正确地设置其输入和输出参数的类别。</span><span class="sxs-lookup"><span data-stu-id="89e3e-106">This section provides step-by-step instructions for adding functoids in the **Advanced** category to your maps, including correctly setting their input and output parameters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89e3e-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="89e3e-107">In This Section</span></span>  
  
-   [<span data-ttu-id="89e3e-108">如何添加循环到图 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-108">How to Add Looping Functoids to a Map</span></span>](../core/how-to-add-looping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-109">如何添加值映射到图 （拼合） Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-109">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-110">如何添加断言向地图 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-110">How to Add Assert Functoids to a Map</span></span>](../core/how-to-add-assert-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-111">如何添加表循环以及到地图表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-111">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-112">如何在向地图添加脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-112">How to Add Scripting Functoids to a Map</span></span>](../core/how-to-add-scripting-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-113">如何在向地图添加 Nil 值 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-113">How to Add Nil Value Functoids to a Map</span></span>](../core/how-to-add-nil-value-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-114">如何添加值映射到图 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-114">How to Add Value Mapping Functoids to a Map</span></span>](../core/how-to-add-value-mapping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-115">如何在向地图添加大容量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-115">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-116">如何在向地图添加迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-116">How to Add Iteration Functoids to a Map</span></span>](../core/how-to-add-iteration-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-117">如何在向地图添加索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-117">How to Add Index Functoids to a Map</span></span>](../core/how-to-add-index-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="89e3e-118">如何在向地图添加记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="89e3e-118">How to Add Record Count Functoids to a Map</span></span>](../core/how-to-add-record-count-functoids-to-a-map.md)