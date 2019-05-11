---
title: 引擎控制功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, functions
ms.assetid: a7900e59-c52c-4a6d-9ca3-ee4ec659f9b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7339462fb21b77bb16627c5671a6246a2eefc4db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349454"
---
# <a name="engine-control-functions"></a><span data-ttu-id="206ea-102">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="206ea-102">Engine Control Functions</span></span>
<span data-ttu-id="206ea-103">本部分介绍与若干业务规则引擎控制功能，允许应用程序或策略来控制规则引擎工作内存中的事实数据关联的行为。</span><span class="sxs-lookup"><span data-stu-id="206ea-103">This section explains the behaviors associated with several Business Rule engine control functions that allow an application or policy to control the facts in the rule engine's working memory.</span></span> <span data-ttu-id="206ea-104">存在的工作内存中事实数据驱动器进行评估的条件和执行的操作。</span><span class="sxs-lookup"><span data-stu-id="206ea-104">The presence of facts in the working memory drives the conditions that are evaluated and the actions that are executed.</span></span>  
  
 <span data-ttu-id="206ea-105">本部分将检查**Assert**， **Retract**， **RetractByType**，**重新添加**，并**更新**函数用于不同事实：.NET 对象**TypedXmlDocument**， **DataConnection**，并**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="206ea-105">This section examines the **Assert**, **Retract**, **RetractByType**, **Reassert**, and **Update** functions for different facts: .NET objects, **TypedXmlDocument**, **DataConnection**, and **TypedDataTable**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="206ea-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="206ea-106">In This Section</span></span>  
  
-   [<span data-ttu-id="206ea-107">Assert</span><span class="sxs-lookup"><span data-stu-id="206ea-107">Assert</span></span>](../core/assert.md)  
  
-   [<span data-ttu-id="206ea-108">Retract</span><span class="sxs-lookup"><span data-stu-id="206ea-108">Retract</span></span>](../core/retract.md)  
  
-   [<span data-ttu-id="206ea-109">RetractByType</span><span class="sxs-lookup"><span data-stu-id="206ea-109">RetractByType</span></span>](../core/retractbytype.md)  
  
-   [<span data-ttu-id="206ea-110">Reassert</span><span class="sxs-lookup"><span data-stu-id="206ea-110">Reassert</span></span>](../core/reassert.md)  
  
-   [<span data-ttu-id="206ea-111">Update</span><span class="sxs-lookup"><span data-stu-id="206ea-111">Update</span></span>](../core/update1.md)  
  
-   [<span data-ttu-id="206ea-112">Halt</span><span class="sxs-lookup"><span data-stu-id="206ea-112">Halt</span></span>](../core/halt.md)