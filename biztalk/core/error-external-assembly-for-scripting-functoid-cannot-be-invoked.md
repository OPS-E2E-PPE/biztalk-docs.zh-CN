---
title: 错误-用于脚本编写 Functoid 的外部程序集不能调用 |Microsoft 文档
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
ms.openlocfilehash: 37f6df36a955f2f40da35368fd72fd2d1fcbb7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240917"
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a><span data-ttu-id="24566-102">错误-用于脚本编写 Functoid 的外部程序集不能调用</span><span class="sxs-lookup"><span data-stu-id="24566-102">Error - External Assembly for Scripting Functoid Cannot Be Invoked</span></span>
<span data-ttu-id="24566-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="24566-103">**Error Code**</span></span>  
  
 <span data-ttu-id="24566-104">btm1067</span><span class="sxs-lookup"><span data-stu-id="24566-104">btm1067</span></span>  
  
 <span data-ttu-id="24566-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="24566-105">**Explanation**</span></span>  
  
 <span data-ttu-id="24566-106">外部程序集方法与相关的**脚本**functoid 不能调用。</span><span class="sxs-lookup"><span data-stu-id="24566-106">The external assembly method that is associated with the relevant **Scripting** functoid cannot be invoked.</span></span> <span data-ttu-id="24566-107">尽管不需要编译映射，但是测试映射操作仍要求此类外部程序集位于全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="24566-107">Although not required for map compilation, the Test Map operation requires that such external assemblies be present in the global assembly cache (GAC).</span></span> <span data-ttu-id="24566-108">正常情况下，运行时操作也要求外部程序集位于 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="24566-108">Normal, run time operation also requires that external assemblies be present in the GAC.</span></span>  
  
 <span data-ttu-id="24566-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="24566-109">**User Action**</span></span>  
  
 <span data-ttu-id="24566-110">确保引用相关的外部程序集**脚本**functoid 位于 gac。</span><span class="sxs-lookup"><span data-stu-id="24566-110">Ensure that the external assembly referenced by the relevant **Scripting** functoid is in the GAC.</span></span>