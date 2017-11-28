---
title: "警告-找不到可分辨的字段 XPath |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.distingFieldXPathNotFound
ms.assetid: a925c39c-9ae1-4334-b329-aa2f5afd97ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9df2e34c27fe3e5e3540ac384443f86143bf741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---distinguished-field-xpath-not-found"></a><span data-ttu-id="ddcac-102">警告-找不到可分辨的字段 XPath</span><span class="sxs-lookup"><span data-stu-id="ddcac-102">Warning - Distinguished Field XPath Not Found</span></span>
<span data-ttu-id="ddcac-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="ddcac-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ddcac-104">BEC1006</span><span class="sxs-lookup"><span data-stu-id="ddcac-104">BEC1006</span></span>  
  
 <span data-ttu-id="ddcac-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="ddcac-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ddcac-106">架构中可能不存在与所指示的可分辨字段升级相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="ddcac-106">The node corresponding to the indicated Distinguished Field promotion may not exist in the schema.</span></span> <span data-ttu-id="ddcac-107">BizTalk 编辑器无法解决复杂的 XPath 规范，如果你编辑提升的属性 XPath 中**编辑实例 XPath**对话框中，它可能或可能无法正确标识你想要升级的节点。</span><span class="sxs-lookup"><span data-stu-id="ddcac-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="ddcac-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="ddcac-108">**User Action**</span></span>  
  
 <span data-ttu-id="ddcac-109">你仍可以保留此警告出现通过更改在提升的属性的 XPath**编辑实例 XPath**对话框中，你可以访问从中单元格**节点路径**上的表的列**可分辨字段**选项卡中**升级属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ddcac-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the table on the **Distinguished Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="ddcac-110">你可以访问**升级属性**对话框中，从**升级属性**属性**架构**中 Microsoft® 节点[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。</span><span class="sxs-lookup"><span data-stu-id="ddcac-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>