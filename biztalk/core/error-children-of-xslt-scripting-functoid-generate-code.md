---
title: "错误-的 XSLT 脚本 Functoid 子级生成代码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a><span data-ttu-id="71f0c-102">错误-的 XSLT 脚本 Functoid 子级生成代码</span><span class="sxs-lookup"><span data-stu-id="71f0c-102">Error - Children of XSLT Scripting Functoid Generate Code</span></span>
<span data-ttu-id="71f0c-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="71f0c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="71f0c-104">btm1063</span><span class="sxs-lookup"><span data-stu-id="71f0c-104">btm1063</span></span>  
  
 <span data-ttu-id="71f0c-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="71f0c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="71f0c-106">这不符合的使用方案**脚本**配置为使用内联 XSLT 或 XSLT 调用模板的 functoid 找映射中。</span><span class="sxs-lookup"><span data-stu-id="71f0c-106">A scenario that contradicts the use of a **Scripting** functoid that is configured to use inline XSLT or an XSLT Call Template was found in the map.</span></span> <span data-ttu-id="71f0c-107">在目标架构中，链接到此类的输出的节点的子代节点**脚本**functoid 尝试生成其自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="71f0c-107">In the destination schema, descendent nodes of a node that is linked to the output of such a **Scripting** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="71f0c-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="71f0c-108">**User Action**</span></span>  
  
 <span data-ttu-id="71f0c-109">通过更改相关的使用情况删除不兼容性**脚本**functoid 或更改的子节点，以便它们不会再生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="71f0c-109">Remove the incompatibility by changing the usage of the relevant **Scripting** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>