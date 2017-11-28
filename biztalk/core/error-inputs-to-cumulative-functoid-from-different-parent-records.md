---
title: "错误-输入到累积 Functoid 从不同的父记录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3c919001e05ca99383ffce72c8d450f6d04624b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a><span data-ttu-id="cd480-102">错误-累积 Functoid 输入从不同的父记录</span><span class="sxs-lookup"><span data-stu-id="cd480-102">Error - Inputs to Cumulative Functoid from Different Parent Records</span></span>
<span data-ttu-id="cd480-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="cd480-103">**Error Code**</span></span>  
  
 <span data-ttu-id="cd480-104">btm1032</span><span class="sxs-lookup"><span data-stu-id="cd480-104">btm1032</span></span>  
  
 <span data-ttu-id="cd480-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd480-105">**Explanation**</span></span>  
  
 <span data-ttu-id="cd480-106">用于指示**的累积**functoid，第二个输入的参数 （累计作用域） 是比充当第一个输入参数 （累积的节点） 的节点的源架构的其他部分。</span><span class="sxs-lookup"><span data-stu-id="cd480-106">For the indicated **Cumulative** functoid, the second input parameter (the accumulation scope) is from a different part of the source schema than the node serving as the first input parameter (the node to accumulate).</span></span>  
  
 <span data-ttu-id="cd480-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="cd480-107">**User Action**</span></span>  
  
 <span data-ttu-id="cd480-108">确保同时输入到指示的参数**的累积**functoid 共享相同的父记录，或者你提供第二个输入的参数 （累计作用域） 具有常量的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cd480-108">Ensure that both input parameters to the indicated **Cumulative** functoid share the same parent record, or that the second input parameter (the accumulation scope) you provide has a constant input parameter.</span></span>