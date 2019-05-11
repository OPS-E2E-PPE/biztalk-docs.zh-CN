---
title: 错误-多个等价节点相同的目标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4cf66fe587f483385c4729e4c34b0179c1710e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388646"
---
# <a name="error---multiple-equivalent-node-same-target"></a><span data-ttu-id="eac53-102">错误-多个等价节点相同的目标</span><span class="sxs-lookup"><span data-stu-id="eac53-102">Error - Multiple Equivalent Node Same Target</span></span>
<span data-ttu-id="eac53-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="eac53-103">**Error Code**</span></span>  
  
 <span data-ttu-id="eac53-104">btm1025</span><span class="sxs-lookup"><span data-stu-id="eac53-104">btm1025</span></span>  
  
 <span data-ttu-id="eac53-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="eac53-105">**Explanation**</span></span>  
  
 <span data-ttu-id="eac53-106">在指定的节点在源架构中，这是冲突子节点的**等效**组节点，都链接到目标架构中所指示的节点。</span><span class="sxs-lookup"><span data-stu-id="eac53-106">The indicated nodes in the source schema, which are conflicting child nodes of an **Equivalent** group node, are both linked to the indicated node in the destination schema.</span></span> <span data-ttu-id="eac53-107">仅有一个源架构中节点可以出现在给定的实例消息中。</span><span class="sxs-lookup"><span data-stu-id="eac53-107">Only one of these nodes in the source schema can occur in a given instance message.</span></span>  
  
 <span data-ttu-id="eac53-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="eac53-108">**User Action**</span></span>  
  
 <span data-ttu-id="eac53-109">确保只有一个子节点**等效**组节点连接到目标架构中的给定节点。</span><span class="sxs-lookup"><span data-stu-id="eac53-109">Ensure that only one of the child nodes of the **Equivalent** group node is connected to a given node in the destination schema.</span></span>