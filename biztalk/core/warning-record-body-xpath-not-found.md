---
title: 警告-找不到记录正文 XPath |Microsoft 文档
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
ms.openlocfilehash: ebd6640aa469fe9383b615d70235ab488c8798f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288101"
---
# <a name="warning---record-body-xpath-not-found"></a><span data-ttu-id="2c43e-102">警告-找不到记录正文 XPath</span><span class="sxs-lookup"><span data-stu-id="2c43e-102">Warning - Record Body XPath Not Found</span></span>
<span data-ttu-id="2c43e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="2c43e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2c43e-104">BEC1008</span><span class="sxs-lookup"><span data-stu-id="2c43e-104">BEC1008</span></span>  
  
 <span data-ttu-id="2c43e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c43e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2c43e-106">**正文 XPath**找到此信封架构中指定的根节点的属性为空或引用不存在的节点。</span><span class="sxs-lookup"><span data-stu-id="2c43e-106">The **Body XPath** property of the indicated root node in this envelope schema was found to be empty or referencing a nonexistent node.</span></span> <span data-ttu-id="2c43e-107">信封架构，由指定**信封**属性**架构**节点，都需要有一个有效的值**正文 XPath**指定根的属性架构中的引用节点。</span><span class="sxs-lookup"><span data-stu-id="2c43e-107">Envelope schemas, as specified by the **Envelope** property of the **Schema** node, are required to have a valid value in the **Body XPath** property of the specified root reference node in the schema.</span></span>  
  
 <span data-ttu-id="2c43e-108">如果不指定任何根参考节点**根引用**属性**架构**节点，第一个根节点在架构中，默认根引用节点时，需要在其具有有效的值**正文 XPath**属性。</span><span class="sxs-lookup"><span data-stu-id="2c43e-108">If no root reference node is specified by the **Root Reference** property of the **Schema** node, the first root node in the schema, the default root reference node, is required to have a valid value in its **Body XPath** property.</span></span> <span data-ttu-id="2c43e-109">**正文 XPath**属性值用于标识每个信封中包含的消息的架构。</span><span class="sxs-lookup"><span data-stu-id="2c43e-109">**Body XPath** property values are used to identify the schema for the each of the messages contained within the envelope.</span></span>  
  
 <span data-ttu-id="2c43e-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="2c43e-110">**User Action**</span></span>  
  
 <span data-ttu-id="2c43e-111">选择指定的根节点，然后选择的值**正文 XPath**正确标识关联的消息正文的架构的属性。</span><span class="sxs-lookup"><span data-stu-id="2c43e-111">Select the indicated root node and then select the value for the **Body XPath** property that correctly identifies the schema of the associated message body.</span></span>