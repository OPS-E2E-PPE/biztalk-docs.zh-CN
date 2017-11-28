---
title: "错误-多个循环路径 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.multipleLoopPaths
ms.assetid: 3f7c0c1c-5aaa-4da9-99ab-78bac536b8dd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afdcb1a235c71163552fd5f6b255e572feef8dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-loop-paths"></a><span data-ttu-id="7803a-102">错误-多个循环路径</span><span class="sxs-lookup"><span data-stu-id="7803a-102">Error - Multiple Loop Paths</span></span>
<span data-ttu-id="7803a-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7803a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7803a-104">btm1030</span><span class="sxs-lookup"><span data-stu-id="7803a-104">btm1030</span></span>  
  
 <span data-ttu-id="7803a-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7803a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7803a-106">目标架构中所指示的节点包含多个源循环路径。</span><span class="sxs-lookup"><span data-stu-id="7803a-106">The indicated node in the destination schema has multiple source loop paths.</span></span>  
  
 <span data-ttu-id="7803a-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7803a-107">**User Action**</span></span>  
  
 <span data-ttu-id="7803a-108">使用**循环**functoid 来显式指定源架构对其将执行循环中的节点。</span><span class="sxs-lookup"><span data-stu-id="7803a-108">Use a **Looping** functoid to explicitly specify the node in the source schema over which the looping will be performed.</span></span>