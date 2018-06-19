---
title: 科学 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b23f65ecede9082ec93041ddab45fa92029851a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269501"
---
# <a name="scientific-functoids"></a><span data-ttu-id="953a3-102">科学 Functoid</span><span class="sxs-lookup"><span data-stu-id="953a3-102">Scientific Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="953a3-103">概述</span><span class="sxs-lookup"><span data-stu-id="953a3-103">Overview</span></span>
<span data-ttu-id="953a3-104">**科学**functoid 用于执行各种标准三角函数、 对数和指数计算。</span><span class="sxs-lookup"><span data-stu-id="953a3-104">**Scientific** functoids are used to perform a variety of standard trigonometric, logarithmic, and exponential calculations.</span></span>  
  
 <span data-ttu-id="953a3-105">除**Base-Specified 对数**和**X ^ Y** functoid，其中的每个采用两个输入的参数，**科学记数法**functoid 所有采用单个参数。</span><span class="sxs-lookup"><span data-stu-id="953a3-105">With the exception of the **Base-Specified Logarithm** and **X^Y** functoids, which each take two input parameters, the **Scientific** functoids all take a single parameter.</span></span>  
  
 <span data-ttu-id="953a3-106">四个三角**科学记数法**functoid (**反正切值**，**余弦**，**正弦值**，和**正切**) 所有使用弧度表示，而不是度为单位为其相关的输入或输出参数。</span><span class="sxs-lookup"><span data-stu-id="953a3-106">The four trigonometric **Scientific** functoids (**Arc Tangent**, **Cosine**, **Sine**, and **Tangent**) all use radians rather than degrees as the units for their relevant input or output parameters.</span></span> <span data-ttu-id="953a3-107">弧度是一种角度度量单位，如一个整圆的弧度为 2π。</span><span class="sxs-lookup"><span data-stu-id="953a3-107">A radian is a unit of measure of angles, such that there are 2π radians in a circle.</span></span> <span data-ttu-id="953a3-108">下述：</span><span class="sxs-lookup"><span data-stu-id="953a3-108">It follows that:</span></span>  
  
-   <span data-ttu-id="953a3-109">2π 弧度 = 360 度</span><span class="sxs-lookup"><span data-stu-id="953a3-109">2π radians equals 360 degrees</span></span>  
  
-   <span data-ttu-id="953a3-110">1 弧度 = 180/π 度</span><span class="sxs-lookup"><span data-stu-id="953a3-110">1 radian = 180/π degrees</span></span>  
  
-   <span data-ttu-id="953a3-111">1 度 = π/180 弧度</span><span class="sxs-lookup"><span data-stu-id="953a3-111">1 degree = π/180 radians</span></span>  
  
 <span data-ttu-id="953a3-112">如果你输入或输出实例消息使用度角度作为其所在部门的度量值，你将需要使用**数学**结合三角 functoid**科学记数法**到 functoid实现正确的结果。</span><span class="sxs-lookup"><span data-stu-id="953a3-112">If your input or output instance messages use degrees as their unit of measure for angles, you will need to use a **Mathematical** functoid in conjunction with a trigonometric **Scientific** functoid to achieve the correct result.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="953a3-113">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="953a3-113">Available functoids</span></span>  
 <span data-ttu-id="953a3-114">**科学记数法**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="953a3-114">The **Scientific** functoids are:</span></span> 

* <span data-ttu-id="953a3-115">10^n</span><span class="sxs-lookup"><span data-stu-id="953a3-115">10^n</span></span>
* <span data-ttu-id="953a3-116">反正切值</span><span class="sxs-lookup"><span data-stu-id="953a3-116">Arc Tangent</span></span>
* <span data-ttu-id="953a3-117">指定底的对数</span><span class="sxs-lookup"><span data-stu-id="953a3-117">Base-Specified Logarithm</span></span>
* <span data-ttu-id="953a3-118">常用对数</span><span class="sxs-lookup"><span data-stu-id="953a3-118">Common Logarithm</span></span>
* <span data-ttu-id="953a3-119">余弦值</span><span class="sxs-lookup"><span data-stu-id="953a3-119">Cosine</span></span>
* <span data-ttu-id="953a3-120">自然指数函数</span><span class="sxs-lookup"><span data-stu-id="953a3-120">Natural Exponential Function</span></span>
* <span data-ttu-id="953a3-121">自然对数</span><span class="sxs-lookup"><span data-stu-id="953a3-121">Natural Logarithm</span></span>
* <span data-ttu-id="953a3-122">正弦值</span><span class="sxs-lookup"><span data-stu-id="953a3-122">Sine</span></span>
* <span data-ttu-id="953a3-123">正切</span><span class="sxs-lookup"><span data-stu-id="953a3-123">Tangent</span></span>
* <span data-ttu-id="953a3-124">X^Y</span><span class="sxs-lookup"><span data-stu-id="953a3-124">X^Y</span></span>
  
## <a name="see-also"></a><span data-ttu-id="953a3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="953a3-125">See Also</span></span>  
-  [<span data-ttu-id="953a3-126">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="953a3-126">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="953a3-127">**科学 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="953a3-127">**Scientific Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>