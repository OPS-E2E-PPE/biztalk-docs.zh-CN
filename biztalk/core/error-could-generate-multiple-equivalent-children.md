---
title: 错误-可能会生成多个等价子节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfce7d5a5d4db35ae6677d3b45bad4df7842fbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389216"
---
# <a name="error---could-generate-multiple-equivalent-children"></a><span data-ttu-id="6628c-102">错误-可能会生成多个等价子节点</span><span class="sxs-lookup"><span data-stu-id="6628c-102">Error - Could Generate Multiple Equivalent Children</span></span>
<span data-ttu-id="6628c-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="6628c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6628c-104">btm1026</span><span class="sxs-lookup"><span data-stu-id="6628c-104">btm1026</span></span>  
  
 <span data-ttu-id="6628c-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="6628c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6628c-106">指向目标架构不正确，导致在多个节点**等效**要生成的组节点。</span><span class="sxs-lookup"><span data-stu-id="6628c-106">Links to the destination schema inappropriately enable multiple nodes within an **Equivalent** group node to be generated.</span></span>  
  
 <span data-ttu-id="6628c-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="6628c-107">**User Action**</span></span>  
  
 <span data-ttu-id="6628c-108">重新链接到目标架构，可能会使用判断 functoid，因此，只有单个节点内的**等效**组节点可以在映射过程中生成。</span><span class="sxs-lookup"><span data-stu-id="6628c-108">Rework the links into the destination schema, potentially using logical functoids, so that only a single node within the **Equivalent** group node can be generated during mapping.</span></span>