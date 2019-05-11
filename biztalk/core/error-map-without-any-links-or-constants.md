---
title: 错误-映射不含任何链接或常数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapWithoutAnyLinksOrConstants
ms.assetid: 8d1cdbcd-4bd0-4ddc-9e94-746e82b6ec48
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa01eff9df2582a00418530e87e9658565722c23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347810"
---
# <a name="error---map-without-any-links-or-constants"></a><span data-ttu-id="5f28c-102">错误-映射不含任何链接或常数</span><span class="sxs-lookup"><span data-stu-id="5f28c-102">Error - Map Without Any Links or Constants</span></span>
<span data-ttu-id="5f28c-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="5f28c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5f28c-104">btm1000</span><span class="sxs-lookup"><span data-stu-id="5f28c-104">btm1000</span></span>  
  
 <span data-ttu-id="5f28c-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f28c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5f28c-106">映射不包含架构之间的任何链接或不包含目标架构中的常数值。</span><span class="sxs-lookup"><span data-stu-id="5f28c-106">The map does not contain any links between the schemas, or constant values in the destination schema.</span></span> <span data-ttu-id="5f28c-107">因此，此映射无法创建输出。</span><span class="sxs-lookup"><span data-stu-id="5f28c-107">Therefore, no output can be created from this map.</span></span>  
  
 <span data-ttu-id="5f28c-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="5f28c-108">**User Action**</span></span>  
  
 <span data-ttu-id="5f28c-109">在映射网格中添加适当的链接，如果需要，还可添加 functoid，或者在目标架构中添加常数，以指定与源架构一致的实例消息应如何转换为与目标架构一致的实例消息。</span><span class="sxs-lookup"><span data-stu-id="5f28c-109">Add the appropriate links and, if appropriate, functoids to the map grid, or constants to the destination schema, to specify how instance messages conforming to the source schema should be transformed into instance messages conforming to the destination schema.</span></span>