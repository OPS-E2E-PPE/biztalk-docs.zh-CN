---
title: 错误-无法生成多个选择的子节点 |Microsoft 文档
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
ms.openlocfilehash: 9322897f6fab9bc4b9c3e098214c19fb339b58d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240685"
---
# <a name="error---could-generate-multiple-choice-children"></a><span data-ttu-id="6cd64-102">错误-无法生成多个选择的子节点</span><span class="sxs-lookup"><span data-stu-id="6cd64-102">Error - Could Generate Multiple Choice Children</span></span>
<span data-ttu-id="6cd64-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="6cd64-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6cd64-104">btm1027</span><span class="sxs-lookup"><span data-stu-id="6cd64-104">btm1027</span></span>  
  
 <span data-ttu-id="6cd64-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="6cd64-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6cd64-106">指向目标架构不正确，导致多个节点对**选择**组节点以便生成。</span><span class="sxs-lookup"><span data-stu-id="6cd64-106">Links to the destination schema inappropriately enable multiple nodes within a **Choice** group node to be generated.</span></span>  
  
 <span data-ttu-id="6cd64-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="6cd64-107">**User Action**</span></span>  
  
 <span data-ttu-id="6cd64-108">因此重新链接到目标架构，只有单个节点内的**选择**可以生成组节点。</span><span class="sxs-lookup"><span data-stu-id="6cd64-108">Rework the links into the destination schema so that only a single node within the **Choice** group node can be generated.</span></span>