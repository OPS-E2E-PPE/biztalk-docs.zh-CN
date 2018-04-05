---
title: 错误-的大容量复制 Functoid 子级生成代码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68183a90be46b176d13100b02cbed2798fe24b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a><span data-ttu-id="8fc31-102">错误-的大容量复制 Functoid 子级生成代码</span><span class="sxs-lookup"><span data-stu-id="8fc31-102">Error - Children of Mass Copy Functoid Generate Code</span></span>
<span data-ttu-id="8fc31-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8fc31-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8fc31-104">btm1068</span><span class="sxs-lookup"><span data-stu-id="8fc31-104">btm1068</span></span>  
  
 <span data-ttu-id="8fc31-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8fc31-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8fc31-106">功能，这不符合的方案**大容量复制**functoid 找映射中。</span><span class="sxs-lookup"><span data-stu-id="8fc31-106">A scenario that contradicts the functionality of the **Mass Copy** functoid was found in the map.</span></span> <span data-ttu-id="8fc31-107">在目标架构中，链接到的输出的节点的子代节点**大容量复制**functoid 尝试生成其自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="8fc31-107">In the destination schema, descendent nodes of a node that is linked to the output of a **Mass Copy** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="8fc31-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8fc31-108">**User Action**</span></span>  
  
 <span data-ttu-id="8fc31-109">通过更改相关的使用情况删除不兼容性**大容量复制**functoid 或更改的子节点，以便它们不会再生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="8fc31-109">Remove the incompatibility by changing the usage of the relevant **Mass Copy** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>