---
title: 错误-节点的逻辑输入太多 |Microsoft Docs
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
ms.openlocfilehash: 4892eca0fc65fe281ab9464eba914603f7ab392b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346312"
---
# <a name="error---too-many-logical-inputs-to-node"></a><span data-ttu-id="a5a4a-102">错误-节点的逻辑输入太多</span><span class="sxs-lookup"><span data-stu-id="a5a4a-102">Error - Too Many Logical Inputs to Node</span></span>
<span data-ttu-id="a5a4a-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="a5a4a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a5a4a-104">btm1006</span><span class="sxs-lookup"><span data-stu-id="a5a4a-104">btm1006</span></span>  
  
 <span data-ttu-id="a5a4a-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="a5a4a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a5a4a-106">有大量的逻辑链接连接到的输入链接数比目标架构中所指示的节点**循环**functoid 连接到所指示的节点的祖先节点。</span><span class="sxs-lookup"><span data-stu-id="a5a4a-106">There are a greater number of logical links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="a5a4a-107">前者和后者类型的链接数应与匹配。</span><span class="sxs-lookup"><span data-stu-id="a5a4a-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="a5a4a-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="a5a4a-108">**User Action**</span></span>  
  
 <span data-ttu-id="a5a4a-109">链接的数目已连接到所指示的节点和返工**循环**functoid 连接到祖先节点，使其匹配。</span><span class="sxs-lookup"><span data-stu-id="a5a4a-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>