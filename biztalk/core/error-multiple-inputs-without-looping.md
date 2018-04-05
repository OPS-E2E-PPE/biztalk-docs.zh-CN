---
title: 错误-但不存在循环的多个输入 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-inputs-without-looping"></a><span data-ttu-id="6a79d-102">错误-但不存在循环的多个输入</span><span class="sxs-lookup"><span data-stu-id="6a79d-102">Error - Multiple Inputs Without Looping</span></span>
<span data-ttu-id="6a79d-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="6a79d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6a79d-104">btm1004</span><span class="sxs-lookup"><span data-stu-id="6a79d-104">btm1004</span></span>  
  
 <span data-ttu-id="6a79d-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a79d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6a79d-106">多个链接连接到指定的节点在目标架构中，当连接到指定的节点的祖先节点之一时才有效**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="6a79d-106">Multiple links are connected to the indicated node in the destination schema, which is only valid when one of the ancestor nodes of the indicated node is connected to a **Looping** functoid.</span></span>  
  
 <span data-ttu-id="6a79d-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="6a79d-107">**User Action**</span></span>  
  
 <span data-ttu-id="6a79d-108">只保留指向目标架构中所指示节点的一个链接，删除其他链接，或者将所指示节点的一个祖先节点连接到“循环”functoid。</span><span class="sxs-lookup"><span data-stu-id="6a79d-108">Either remove all but one of the links to the indicated node in the destination schema, or connect one of the ancestor nodes of the indicated node to a looping functoid.</span></span>