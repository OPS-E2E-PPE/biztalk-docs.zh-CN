---
title: 错误-无法生成多个等效的子节点 |Microsoft 文档
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
ms.openlocfilehash: 686899c2871ded25f6901e919e9283694b9bacf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---could-generate-multiple-equivalent-children"></a><span data-ttu-id="9876b-102">错误-无法生成多个等效的子节点</span><span class="sxs-lookup"><span data-stu-id="9876b-102">Error - Could Generate Multiple Equivalent Children</span></span>
<span data-ttu-id="9876b-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="9876b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9876b-104">btm1026</span><span class="sxs-lookup"><span data-stu-id="9876b-104">btm1026</span></span>  
  
 <span data-ttu-id="9876b-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="9876b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9876b-106">指向目标架构不正确，导致多个节点对**等效**组节点以便生成。</span><span class="sxs-lookup"><span data-stu-id="9876b-106">Links to the destination schema inappropriately enable multiple nodes within an **Equivalent** group node to be generated.</span></span>  
  
 <span data-ttu-id="9876b-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="9876b-107">**User Action**</span></span>  
  
 <span data-ttu-id="9876b-108">重新链接到目标架构，可能使用逻辑 functoid，因此，只有单个节点内的**等效**可以在映射过程中生成组节点。</span><span class="sxs-lookup"><span data-stu-id="9876b-108">Rework the links into the destination schema, potentially using logical functoids, so that only a single node within the **Equivalent** group node can be generated during mapping.</span></span>