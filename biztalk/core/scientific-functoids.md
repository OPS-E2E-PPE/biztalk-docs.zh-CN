---
title: 科学计数法 Functoid |Microsoft Docs
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
ms.openlocfilehash: cf7a181f200948335aab0ffa2a06d43d38408afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977413"
---
# <a name="scientific-functoids"></a><span data-ttu-id="b316a-102">科学计数法 Functoid</span><span class="sxs-lookup"><span data-stu-id="b316a-102">Scientific Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="b316a-103">概述</span><span class="sxs-lookup"><span data-stu-id="b316a-103">Overview</span></span>
<span data-ttu-id="b316a-104">**科学记数法**functoid 用于执行各种标准的三角、 对数和指数计算。</span><span class="sxs-lookup"><span data-stu-id="b316a-104">**Scientific** functoids are used to perform a variety of standard trigonometric, logarithmic, and exponential calculations.</span></span>  

 <span data-ttu-id="b316a-105">除**指定底的对数**并**X ^ Y**采用两个输入的参数，functoid**科学记数**functoid 均采用单个参数。</span><span class="sxs-lookup"><span data-stu-id="b316a-105">With the exception of the **Base-Specified Logarithm** and **X^Y** functoids, which each take two input parameters, the **Scientific** functoids all take a single parameter.</span></span>  

 <span data-ttu-id="b316a-106">四个三角**科学记数**functoid (**反正切值**，**余弦**，**正弦**，和**正切**) 所有使用弧度而不是度作为单位为其相关输入或输出参数。</span><span class="sxs-lookup"><span data-stu-id="b316a-106">The four trigonometric **Scientific** functoids (**Arc Tangent**, **Cosine**, **Sine**, and **Tangent**) all use radians rather than degrees as the units for their relevant input or output parameters.</span></span> <span data-ttu-id="b316a-107">弧度是一种角度度量单位，如一个整圆的弧度为 2π。</span><span class="sxs-lookup"><span data-stu-id="b316a-107">A radian is a unit of measure of angles, such that there are 2π radians in a circle.</span></span> <span data-ttu-id="b316a-108">它遵循的：</span><span class="sxs-lookup"><span data-stu-id="b316a-108">It follows that:</span></span>  

- <span data-ttu-id="b316a-109">2π 弧度 = 360 度</span><span class="sxs-lookup"><span data-stu-id="b316a-109">2π radians equals 360 degrees</span></span>  

- <span data-ttu-id="b316a-110">1 弧度 = 180/π 度</span><span class="sxs-lookup"><span data-stu-id="b316a-110">1 radian = 180/π degrees</span></span>  

- <span data-ttu-id="b316a-111">1 度 = π/180 弧度</span><span class="sxs-lookup"><span data-stu-id="b316a-111">1 degree = π/180 radians</span></span>  

  <span data-ttu-id="b316a-112">如果你输入或输出实例消息使用度作为的度量单位的角度，你需要使用**数学**结合使用三角 functoid**科学记数**到 functoid获得正确的结果。</span><span class="sxs-lookup"><span data-stu-id="b316a-112">If your input or output instance messages use degrees as their unit of measure for angles, you will need to use a **Mathematical** functoid in conjunction with a trigonometric **Scientific** functoid to achieve the correct result.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="b316a-113">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="b316a-113">Available functoids</span></span>  
 <span data-ttu-id="b316a-114">**科学记数**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="b316a-114">The **Scientific** functoids are:</span></span> 

* <span data-ttu-id="b316a-115">10^n</span><span class="sxs-lookup"><span data-stu-id="b316a-115">10^n</span></span>
* <span data-ttu-id="b316a-116">反正切值</span><span class="sxs-lookup"><span data-stu-id="b316a-116">Arc Tangent</span></span>
* <span data-ttu-id="b316a-117">指定底的对数</span><span class="sxs-lookup"><span data-stu-id="b316a-117">Base-Specified Logarithm</span></span>
* <span data-ttu-id="b316a-118">常用对数</span><span class="sxs-lookup"><span data-stu-id="b316a-118">Common Logarithm</span></span>
* <span data-ttu-id="b316a-119">余弦值</span><span class="sxs-lookup"><span data-stu-id="b316a-119">Cosine</span></span>
* <span data-ttu-id="b316a-120">自然指数函数</span><span class="sxs-lookup"><span data-stu-id="b316a-120">Natural Exponential Function</span></span>
* <span data-ttu-id="b316a-121">自然对数</span><span class="sxs-lookup"><span data-stu-id="b316a-121">Natural Logarithm</span></span>
* <span data-ttu-id="b316a-122">正弦值</span><span class="sxs-lookup"><span data-stu-id="b316a-122">Sine</span></span>
* <span data-ttu-id="b316a-123">正切</span><span class="sxs-lookup"><span data-stu-id="b316a-123">Tangent</span></span>
* <span data-ttu-id="b316a-124">X^Y</span><span class="sxs-lookup"><span data-stu-id="b316a-124">X^Y</span></span>

## <a name="see-also"></a><span data-ttu-id="b316a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b316a-125">See Also</span></span>  
- [<span data-ttu-id="b316a-126">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="b316a-126">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="b316a-127">**科学计数法 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b316a-127">**Scientific Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
