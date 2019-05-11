---
title: 错误-XSLT 脚本 Functoid 的相关子节点生成代码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4111d359c0a764c92fc9736fdd2fcbc879252274
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388990"
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a><span data-ttu-id="1325d-102">错误-XSLT 脚本 Functoid 的相关子节点生成代码</span><span class="sxs-lookup"><span data-stu-id="1325d-102">Error - Children of XSLT Scripting Functoid Generate Code</span></span>
<span data-ttu-id="1325d-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="1325d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="1325d-104">btm1063</span><span class="sxs-lookup"><span data-stu-id="1325d-104">btm1063</span></span>  
  
 <span data-ttu-id="1325d-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="1325d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="1325d-106">这不符合的使用方案**脚本**在映射中发现已配置为使用内联 XSLT 或 XSLT 调用模板的 functoid。</span><span class="sxs-lookup"><span data-stu-id="1325d-106">A scenario that contradicts the use of a **Scripting** functoid that is configured to use inline XSLT or an XSLT Call Template was found in the map.</span></span> <span data-ttu-id="1325d-107">在目标架构中，链接到此类输出节点的后代节点**脚本**functoid 试图生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="1325d-107">In the destination schema, descendent nodes of a node that is linked to the output of such a **Scripting** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="1325d-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="1325d-108">**User Action**</span></span>  
  
 <span data-ttu-id="1325d-109">通过更改相关的使用情况来删除不兼容性**脚本**functoid 或更改的子节点，以便它们不会再生成它们自己的 XSLT 代码。</span><span class="sxs-lookup"><span data-stu-id="1325d-109">Remove the incompatibility by changing the usage of the relevant **Scripting** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>