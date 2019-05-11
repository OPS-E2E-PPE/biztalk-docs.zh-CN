---
title: 警告-正文 XPath 不是节点后代 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.bodyXPathNotDescendant
ms.assetid: bfeff370-9b84-4fd9-81e9-1e54b166f561
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e37a2cd645053ce22f6e2f2536b4f647f4738f11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279593"
---
# <a name="warning---body-xpath-not-a-descendent"></a><span data-ttu-id="f09f4-102">警告-正文 XPath 不是节点后代</span><span class="sxs-lookup"><span data-stu-id="f09f4-102">Warning - Body XPath Not A Descendent</span></span>
<span data-ttu-id="f09f4-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="f09f4-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f09f4-104">BEC1004</span><span class="sxs-lookup"><span data-stu-id="f09f4-104">BEC1004</span></span>  
  
 <span data-ttu-id="f09f4-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="f09f4-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f09f4-106">**正文 XPath**此信封架构中指示的根节点的属性引用不是该根节点，所需的子代的节点。</span><span class="sxs-lookup"><span data-stu-id="f09f4-106">The **Body XPath** property of the indicated root node in this envelope schema references a node that is not a descendent of that root node, as required.</span></span> <span data-ttu-id="f09f4-107">此错误不应发生，除非**正文 XPath**属性 BizTalk 编辑器之外修改。</span><span class="sxs-lookup"><span data-stu-id="f09f4-107">This error should not occur unless the **Body XPath** property is modified outside of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="f09f4-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="f09f4-108">**User Action**</span></span>  
  
 <span data-ttu-id="f09f4-109">选择指示的根节点，然后选择的值**正文 XPath**正确地标识相关联的消息正文的顶级节点的属性。</span><span class="sxs-lookup"><span data-stu-id="f09f4-109">Select the indicated root node and select the value for the **Body XPath** property that correctly identifies the top-level node of the associated message body.</span></span>