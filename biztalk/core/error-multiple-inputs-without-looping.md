---
title: 错误-多个输入但不存在循环 |Microsoft Docs
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
ms.openlocfilehash: 3ce2cdef2a80e6e58b635cf9fed0dbc52c817e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347315"
---
# <a name="error---multiple-inputs-without-looping"></a><span data-ttu-id="f5fea-102">错误-多个输入但不存在循环</span><span class="sxs-lookup"><span data-stu-id="f5fea-102">Error - Multiple Inputs Without Looping</span></span>
<span data-ttu-id="f5fea-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="f5fea-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f5fea-104">btm1004</span><span class="sxs-lookup"><span data-stu-id="f5fea-104">btm1004</span></span>  
  
 <span data-ttu-id="f5fea-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5fea-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f5fea-106">多个链接连接到所指示的节点在目标架构中，当连接到所指示的节点的祖先节点之一时才有效**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="f5fea-106">Multiple links are connected to the indicated node in the destination schema, which is only valid when one of the ancestor nodes of the indicated node is connected to a **Looping** functoid.</span></span>  
  
 <span data-ttu-id="f5fea-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="f5fea-107">**User Action**</span></span>  
  
 <span data-ttu-id="f5fea-108">一个指向目标架构中所指示的节点的删除，或者将所指示的节点的祖先节点之一连接到循环 functoid。</span><span class="sxs-lookup"><span data-stu-id="f5fea-108">Either remove all but one of the links to the indicated node in the destination schema, or connect one of the ancestor nodes of the indicated node to a looping functoid.</span></span>