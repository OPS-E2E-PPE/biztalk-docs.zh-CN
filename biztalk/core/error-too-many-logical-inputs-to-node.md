---
title: 错误-节点的太多逻辑输入 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241701"
---
# <a name="error---too-many-logical-inputs-to-node"></a><span data-ttu-id="7695a-102">错误-节点的逻辑输入太多</span><span class="sxs-lookup"><span data-stu-id="7695a-102">Error - Too Many Logical Inputs to Node</span></span>
<span data-ttu-id="7695a-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7695a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7695a-104">btm1006</span><span class="sxs-lookup"><span data-stu-id="7695a-104">btm1006</span></span>  
  
 <span data-ttu-id="7695a-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7695a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7695a-106">有更多的逻辑链接连接到比数输入指向目标架构中的指定节点**循环**functoid 连接到指定的节点的祖先节点。</span><span class="sxs-lookup"><span data-stu-id="7695a-106">There are a greater number of logical links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="7695a-107">前一类型和后一类型的链接数应该一致。</span><span class="sxs-lookup"><span data-stu-id="7695a-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="7695a-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7695a-108">**User Action**</span></span>  
  
 <span data-ttu-id="7695a-109">链接数连接到指定的节点和返工**循环**functoid 连接到祖先节点以便将它们与匹配。</span><span class="sxs-lookup"><span data-stu-id="7695a-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>