---
title: 错误-可能会生成多个选择子节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleChoiceChildren
ms.assetid: 64e69ebb-781f-4ecb-9d91-6fdcca949d4b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70f3aa4a9f03d084f1190b0e94808888310f3c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348977"
---
# <a name="error---could-generate-multiple-choice-children"></a><span data-ttu-id="cab33-102">错误-可能会生成多个选择子节点</span><span class="sxs-lookup"><span data-stu-id="cab33-102">Error - Could Generate Multiple Choice Children</span></span>
<span data-ttu-id="cab33-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="cab33-103">**Error Code**</span></span>  
  
 <span data-ttu-id="cab33-104">btm1027</span><span class="sxs-lookup"><span data-stu-id="cab33-104">btm1027</span></span>  
  
 <span data-ttu-id="cab33-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="cab33-105">**Explanation**</span></span>  
  
 <span data-ttu-id="cab33-106">指向目标架构不正确，导致在多个节点**选择**要生成的组节点。</span><span class="sxs-lookup"><span data-stu-id="cab33-106">Links to the destination schema inappropriately enable multiple nodes within a **Choice** group node to be generated.</span></span>  
  
 <span data-ttu-id="cab33-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="cab33-107">**User Action**</span></span>  
  
 <span data-ttu-id="cab33-108">因此重新链接到目标架构，只有单个节点内的**选择**可以生成组节点。</span><span class="sxs-lookup"><span data-stu-id="cab33-108">Rework the links into the destination schema so that only a single node within the **Choice** group node can be generated.</span></span>