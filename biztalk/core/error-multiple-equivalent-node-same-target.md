---
title: 错误-多个等效节点相同的目标 |Microsoft 文档
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
ms.openlocfilehash: 12df4f7a68bb1eceaa3211c6aad6e9a581f17a4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-equivalent-node-same-target"></a><span data-ttu-id="c4f9e-102">错误-多个等效节点相同的目标</span><span class="sxs-lookup"><span data-stu-id="c4f9e-102">Error - Multiple Equivalent Node Same Target</span></span>
<span data-ttu-id="c4f9e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="c4f9e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c4f9e-104">btm1025</span><span class="sxs-lookup"><span data-stu-id="c4f9e-104">btm1025</span></span>  
  
 <span data-ttu-id="c4f9e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4f9e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c4f9e-106">源架构中的指定的节点相冲突的子节点的**等效**组节点，节点都链接到目标架构中指定的节点。</span><span class="sxs-lookup"><span data-stu-id="c4f9e-106">The indicated nodes in the source schema, which are conflicting child nodes of an **Equivalent** group node, are both linked to the indicated node in the destination schema.</span></span> <span data-ttu-id="c4f9e-107">在源架构中只能有一个节点可以出现在给定的实例消息中。</span><span class="sxs-lookup"><span data-stu-id="c4f9e-107">Only one of these nodes in the source schema can occur in a given instance message.</span></span>  
  
 <span data-ttu-id="c4f9e-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="c4f9e-108">**User Action**</span></span>  
  
 <span data-ttu-id="c4f9e-109">确保的节点的子确定只有一个**等效**组节点都连接到目标架构中给定的节点。</span><span class="sxs-lookup"><span data-stu-id="c4f9e-109">Ensure that only one of the child nodes of the **Equivalent** group node is connected to a given node in the destination schema.</span></span>