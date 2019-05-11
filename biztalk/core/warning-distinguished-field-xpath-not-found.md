---
title: 警告-找不到可分辨的字段 XPath |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.distingFieldXPathNotFound
ms.assetid: a925c39c-9ae1-4334-b329-aa2f5afd97ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48306b164a3ce3bc0ef999ad8eb7d0d6bbedd444
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393722"
---
# <a name="warning---distinguished-field-xpath-not-found"></a><span data-ttu-id="b2d0e-102">警告-找不到可分辨的字段 XPath</span><span class="sxs-lookup"><span data-stu-id="b2d0e-102">Warning - Distinguished Field XPath Not Found</span></span>
<span data-ttu-id="b2d0e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b2d0e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b2d0e-104">BEC1006</span><span class="sxs-lookup"><span data-stu-id="b2d0e-104">BEC1006</span></span>  
  
 <span data-ttu-id="b2d0e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b2d0e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b2d0e-106">在架构中可能不存在与所指示的可分辨字段升级相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="b2d0e-106">The node corresponding to the indicated Distinguished Field promotion may not exist in the schema.</span></span> <span data-ttu-id="b2d0e-107">BizTalk 编辑器无法解析复杂的 XPath 规范，如果编辑已升级的属性 XPath 中**编辑实例 XPath**对话框中，它可能会或可能无法正确识别您要升级的节点。</span><span class="sxs-lookup"><span data-stu-id="b2d0e-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="b2d0e-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b2d0e-108">**User Action**</span></span>  
  
 <span data-ttu-id="b2d0e-109">可以保留此警告使其不显示通过更改中的升级属性的 XPath**编辑实例 XPath**对话框中，您可以从中单元格访问**节点路径**上表的列**可分辨字段**选项卡**升级属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="b2d0e-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the table on the **Distinguished Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="b2d0e-110">您可以访问**升级属性**对话框从**升级属性**属性**架构**Microsoft® 中的节点[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。</span><span class="sxs-lookup"><span data-stu-id="b2d0e-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>