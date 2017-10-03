---
title: "引擎控制功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rules Engine, functions
ms.assetid: a7900e59-c52c-4a6d-9ca3-ee4ec659f9b5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 033a4213a6552319f44a98e23562d7e8703fdd42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="engine-control-functions"></a><span data-ttu-id="c769e-102">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="c769e-102">Engine Control Functions</span></span>
<span data-ttu-id="c769e-103">本部分将介绍与若干业务规则引擎控制功能相关联的行为，这些引擎控制功能允许应用程序或策略控制规则引擎的工作内存中的事实。</span><span class="sxs-lookup"><span data-stu-id="c769e-103">This section explains the behaviors associated with several Business Rule engine control functions that allow an application or policy to control the facts in the rule engine's working memory.</span></span> <span data-ttu-id="c769e-104">工作内存中存在的事实可以驱动要进行评估的条件和要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c769e-104">The presence of facts in the working memory drives the conditions that are evaluated and the actions that are executed.</span></span>  
  
 <span data-ttu-id="c769e-105">本节讨论**断言**，**收回**， **RetractByType**，**重新声明**，和**更新**函数的不同事实：.NET 对象**TypedXmlDocument**，**该组**，和**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="c769e-105">This section examines the **Assert**, **Retract**, **RetractByType**, **Reassert**, and **Update** functions for different facts: .NET objects, **TypedXmlDocument**, **DataConnection**, and **TypedDataTable**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c769e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c769e-106">In This Section</span></span>  
  
-   [<span data-ttu-id="c769e-107">ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="c769e-107">Assert</span></span>](../core/assert.md)  
  
-   [<span data-ttu-id="c769e-108">收回</span><span class="sxs-lookup"><span data-stu-id="c769e-108">Retract</span></span>](../core/retract.md)  
  
-   [<span data-ttu-id="c769e-109">RetractByType</span><span class="sxs-lookup"><span data-stu-id="c769e-109">RetractByType</span></span>](../core/retractbytype.md)  
  
-   [<span data-ttu-id="c769e-110">重新声明</span><span class="sxs-lookup"><span data-stu-id="c769e-110">Reassert</span></span>](../core/reassert.md)  
  
-   [<span data-ttu-id="c769e-111">Update</span><span class="sxs-lookup"><span data-stu-id="c769e-111">Update</span></span>](../core/update1.md)  
  
-   [<span data-ttu-id="c769e-112">异常终止</span><span class="sxs-lookup"><span data-stu-id="c769e-112">Halt</span></span>](../core/halt.md)