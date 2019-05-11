---
title: 错误-必需的目标具有可选源 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a73185c608df664fa41c3c44d9d1016f3bf41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347007"
---
# <a name="error---required-target-with-optional-source"></a><span data-ttu-id="0078f-102">错误-必需的目标具有可选源</span><span class="sxs-lookup"><span data-stu-id="0078f-102">Error - Required Target with Optional Source</span></span>
<span data-ttu-id="0078f-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="0078f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0078f-104">btm1001</span><span class="sxs-lookup"><span data-stu-id="0078f-104">btm1001</span></span>  
  
 <span data-ttu-id="0078f-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="0078f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0078f-106">目标架构中所指示的必需节点的数据来自源架构中的可选节点。</span><span class="sxs-lookup"><span data-stu-id="0078f-106">The data for the indicated required node in the destination schema comes from an optional node in the source schema.</span></span> <span data-ttu-id="0078f-107">因此，某些有效实例消息的映射将会失败。</span><span class="sxs-lookup"><span data-stu-id="0078f-107">Therefore, there may be valid instance messages for which mapping will fail.</span></span>  
  
 <span data-ttu-id="0078f-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="0078f-108">**User Action**</span></span>  
  
 <span data-ttu-id="0078f-109">分别确认所指定的源节点和目标节点的可选和必需设置，并考虑使这些设置匹配。</span><span class="sxs-lookup"><span data-stu-id="0078f-109">Confirm the optional and required characteristics of the specified source and destination nodes, respectively, and consider making these characteristics match.</span></span>