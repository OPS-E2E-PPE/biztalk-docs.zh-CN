---
title: 错误-所需的目标具有选择源节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c9ad912b03bbb475efcc9eb8207a388400b43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240621"
---
# <a name="error---required-target-has-choice-node-source"></a><span data-ttu-id="d56b3-102">错误-必需的目标具有选择源节点</span><span class="sxs-lookup"><span data-stu-id="d56b3-102">Error - Required Target Has Choice Node Source</span></span>
<span data-ttu-id="d56b3-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="d56b3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d56b3-104">btm1029</span><span class="sxs-lookup"><span data-stu-id="d56b3-104">btm1029</span></span>  
  
 <span data-ttu-id="d56b3-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="d56b3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d56b3-106">指定目标架构中指定的节点作为所需但链接到位于源架构中的节点**选择**节点。</span><span class="sxs-lookup"><span data-stu-id="d56b3-106">The indicated node in the destination schema is specified as required but is linked to a node in the source schema that is within a **Choice** node.</span></span> <span data-ttu-id="d56b3-107">由于源架构中指定的节点不应出现在输入的实例消息，不可能从其目标架构中创建所需的节点的源。</span><span class="sxs-lookup"><span data-stu-id="d56b3-107">Because the indicated node in the source schema may not appear in an input instance message, there may not be a source from which to create the required node in the destination schema.</span></span>  
  
 <span data-ttu-id="d56b3-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="d56b3-108">**User Action**</span></span>  
  
 <span data-ttu-id="d56b3-109">根据需要，将目标架构中的指定的节点更改为可选的或者为必须出现在所有有效输入的实例消息的目标架构中的指定节点提供不同的源。</span><span class="sxs-lookup"><span data-stu-id="d56b3-109">As appropriate, either change the indicated node in the destination schema to optional, or provide a different source for the indicated node in the destination schema that must occur in all valid input instance messages.</span></span>