---
title: 错误-批量复制 Functoid 的相关子节点生成代码 |Microsoft Docs
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
ms.openlocfilehash: c11f96b753b100a9662671ff0c20d5671ad07055
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349007"
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a><span data-ttu-id="9a9a3-102">错误-批量复制 Functoid 的相关子节点生成代码</span><span class="sxs-lookup"><span data-stu-id="9a9a3-102">Error - Children of Mass Copy Functoid Generate Code</span></span>
<span data-ttu-id="9a9a3-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="9a9a3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9a9a3-104">btm1068</span><span class="sxs-lookup"><span data-stu-id="9a9a3-104">btm1068</span></span>  
  
 <span data-ttu-id="9a9a3-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a9a3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9a9a3-106">冲突的功能的情况**批量复制**functoid 在映射中找到。</span><span class="sxs-lookup"><span data-stu-id="9a9a3-106">A scenario that contradicts the functionality of the **Mass Copy** functoid was found in the map.</span></span> <span data-ttu-id="9a9a3-107">在目标架构中，链接到的输出节点的后代节点**批量复制**functoid 试图生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="9a9a3-107">In the destination schema, descendent nodes of a node that is linked to the output of a **Mass Copy** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="9a9a3-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="9a9a3-108">**User Action**</span></span>  
  
 <span data-ttu-id="9a9a3-109">通过更改相关的使用情况来删除不兼容性**批量复制**functoid 或更改的子节点，以便它们不会再生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="9a9a3-109">Remove the incompatibility by changing the usage of the relevant **Mass Copy** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>