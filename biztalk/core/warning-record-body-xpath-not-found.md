---
title: 警告-找不到记录正文 XPath |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.recordBodyXPathNotFound
ms.assetid: d46e0732-08ce-4292-84d8-56dc020063e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a651748c16862bbb3a23b3e792c0ab17fc3687f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393648"
---
# <a name="warning---record-body-xpath-not-found"></a><span data-ttu-id="201b3-102">警告-找不到记录正文 XPath</span><span class="sxs-lookup"><span data-stu-id="201b3-102">Warning - Record Body XPath Not Found</span></span>
<span data-ttu-id="201b3-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="201b3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="201b3-104">BEC1008</span><span class="sxs-lookup"><span data-stu-id="201b3-104">BEC1008</span></span>  
  
 <span data-ttu-id="201b3-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="201b3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="201b3-106">**正文 XPath**找到此信封架构中指示的根节点的属性为空或引用的节点不存在。</span><span class="sxs-lookup"><span data-stu-id="201b3-106">The **Body XPath** property of the indicated root node in this envelope schema was found to be empty or referencing a nonexistent node.</span></span> <span data-ttu-id="201b3-107">信封架构，由指定**信封**的属性**架构**节点，需要具有有效的值**正文 XPath**指定根的属性在架构中的引用节点。</span><span class="sxs-lookup"><span data-stu-id="201b3-107">Envelope schemas, as specified by the **Envelope** property of the **Schema** node, are required to have a valid value in the **Body XPath** property of the specified root reference node in the schema.</span></span>  
  
 <span data-ttu-id="201b3-108">如果不指定任何根引用节点**根引用**的属性**架构**节点，第一个根节点在架构中，默认根引用节点，需在其具有有效的值**正文 XPath**属性。</span><span class="sxs-lookup"><span data-stu-id="201b3-108">If no root reference node is specified by the **Root Reference** property of the **Schema** node, the first root node in the schema, the default root reference node, is required to have a valid value in its **Body XPath** property.</span></span> <span data-ttu-id="201b3-109">**正文 XPath**属性值用于标识信封中包含的消息的每个架构。</span><span class="sxs-lookup"><span data-stu-id="201b3-109">**Body XPath** property values are used to identify the schema for the each of the messages contained within the envelope.</span></span>  
  
 <span data-ttu-id="201b3-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="201b3-110">**User Action**</span></span>  
  
 <span data-ttu-id="201b3-111">选择指示的根节点，然后选择的值**正文 XPath**正确地标识相关联的消息正文的架构的属性。</span><span class="sxs-lookup"><span data-stu-id="201b3-111">Select the indicated root node and then select the value for the **Body XPath** property that correctly identifies the schema of the associated message body.</span></span>