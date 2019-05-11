---
title: 错误-脚本 Functoid 的外部程序集不能调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf4b387dd33900130e8aa5adff29b8de8d79ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348338"
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a><span data-ttu-id="7fdc5-102">不能调用错误-脚本 Functoid 的外部程序集</span><span class="sxs-lookup"><span data-stu-id="7fdc5-102">Error - External Assembly for Scripting Functoid Cannot Be Invoked</span></span>
<span data-ttu-id="7fdc5-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7fdc5-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7fdc5-104">btm1067</span><span class="sxs-lookup"><span data-stu-id="7fdc5-104">btm1067</span></span>  
  
 <span data-ttu-id="7fdc5-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7fdc5-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7fdc5-106">与相关相关联的外部程序集方法**脚本**functoid 不能调用。</span><span class="sxs-lookup"><span data-stu-id="7fdc5-106">The external assembly method that is associated with the relevant **Scripting** functoid cannot be invoked.</span></span> <span data-ttu-id="7fdc5-107">尽管不需要编译映射，测试映射操作需要此类外部程序集位于全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="7fdc5-107">Although not required for map compilation, the Test Map operation requires that such external assemblies be present in the global assembly cache (GAC).</span></span> <span data-ttu-id="7fdc5-108">正常、 运行时操作还要求外部程序集必须位于 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="7fdc5-108">Normal, run time operation also requires that external assemblies be present in the GAC.</span></span>  
  
 <span data-ttu-id="7fdc5-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7fdc5-109">**User Action**</span></span>  
  
 <span data-ttu-id="7fdc5-110">确保引用相关的外部程序集**脚本**functoid 位于 gac。</span><span class="sxs-lookup"><span data-stu-id="7fdc5-110">Ensure that the external assembly referenced by the relevant **Scripting** functoid is in the GAC.</span></span>