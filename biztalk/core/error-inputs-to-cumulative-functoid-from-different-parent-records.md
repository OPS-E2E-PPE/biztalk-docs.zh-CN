---
title: 错误-累计 Functoid 为输入来自不同父记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01e55e1d4bf09ecdb086ec99fde44008cf85829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388786"
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a><span data-ttu-id="fbdea-102">错误-累计 Functoid 输入来自不同父记录</span><span class="sxs-lookup"><span data-stu-id="fbdea-102">Error - Inputs to Cumulative Functoid from Different Parent Records</span></span>
<span data-ttu-id="fbdea-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="fbdea-103">**Error Code**</span></span>  
  
 <span data-ttu-id="fbdea-104">btm1032</span><span class="sxs-lookup"><span data-stu-id="fbdea-104">btm1032</span></span>  
  
 <span data-ttu-id="fbdea-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="fbdea-105">**Explanation**</span></span>  
  
 <span data-ttu-id="fbdea-106">为所指示**累计**functoid，第二个输入的参数 （累计作用域） 是与节点作为第一个输入参数 （要累计的节点） 的源架构的其他部分。</span><span class="sxs-lookup"><span data-stu-id="fbdea-106">For the indicated **Cumulative** functoid, the second input parameter (the accumulation scope) is from a different part of the source schema than the node serving as the first input parameter (the node to accumulate).</span></span>  
  
 <span data-ttu-id="fbdea-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="fbdea-107">**User Action**</span></span>  
  
 <span data-ttu-id="fbdea-108">确保两个输入参数所指示**累计**functoid 共享同一个父级记录，或您提供第二个输入的参数 （累计作用域） 具有常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="fbdea-108">Ensure that both input parameters to the indicated **Cumulative** functoid share the same parent record, or that the second input parameter (the accumulation scope) you provide has a constant input parameter.</span></span>