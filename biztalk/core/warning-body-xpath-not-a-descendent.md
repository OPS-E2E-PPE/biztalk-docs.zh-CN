---
title: 警告-正文 XPath 不派生 |Microsoft 文档
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
ms.openlocfilehash: 70b5d228e1119bc7c569b45cc6795f3f5b8454ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288021"
---
# <a name="warning---body-xpath-not-a-descendent"></a><span data-ttu-id="a69cd-102">警告-正文 XPath 不派生</span><span class="sxs-lookup"><span data-stu-id="a69cd-102">Warning - Body XPath Not A Descendent</span></span>
<span data-ttu-id="a69cd-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="a69cd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a69cd-104">BEC1004</span><span class="sxs-lookup"><span data-stu-id="a69cd-104">BEC1004</span></span>  
  
 <span data-ttu-id="a69cd-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="a69cd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a69cd-106">**正文 XPath**此信封架构中指定的根节点的属性引用不是该根节点，所需的子代节点。</span><span class="sxs-lookup"><span data-stu-id="a69cd-106">The **Body XPath** property of the indicated root node in this envelope schema references a node that is not a descendent of that root node, as required.</span></span> <span data-ttu-id="a69cd-107">除非应不会发生此错误**正文 XPath**之外 BizTalk 编辑器修改属性。</span><span class="sxs-lookup"><span data-stu-id="a69cd-107">This error should not occur unless the **Body XPath** property is modified outside of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="a69cd-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="a69cd-108">**User Action**</span></span>  
  
 <span data-ttu-id="a69cd-109">选择指定的根节点，选择的值**正文 XPath**正确标识关联的消息正文的顶级节点的属性。</span><span class="sxs-lookup"><span data-stu-id="a69cd-109">Select the indicated root node and select the value for the **Body XPath** property that correctly identifies the top-level node of the associated message body.</span></span>