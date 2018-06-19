---
title: 警告-提升找不到字段 XPath |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoFieldXPathNotFound
ms.assetid: 21b8c240-5d6f-499d-8211-6e3f2ce2a79c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f45bd1539817f010864226d07b76ca2feee8b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288525"
---
# <a name="warning---promoted-field-xpath-not-found"></a><span data-ttu-id="aa322-102">警告-提升字段 XPath 找不到</span><span class="sxs-lookup"><span data-stu-id="aa322-102">Warning - Promoted Field XPath Not Found</span></span>
<span data-ttu-id="aa322-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="aa322-103">**Error Code**</span></span>  
  
 <span data-ttu-id="aa322-104">BEC1005</span><span class="sxs-lookup"><span data-stu-id="aa322-104">BEC1005</span></span>  
  
 <span data-ttu-id="aa322-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa322-105">**Explanation**</span></span>  
  
 <span data-ttu-id="aa322-106">架构中可能不存在与所指示的属性字段升级相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="aa322-106">The node corresponding to the indicated property field promotion may not exist in the schema.</span></span> <span data-ttu-id="aa322-107">BizTalk 编辑器无法解决复杂的 XPath 规范，如果你编辑提升的属性 XPath 中**编辑实例 XPath**对话框中，它可能或可能无法正确标识你想要升级的节点。</span><span class="sxs-lookup"><span data-stu-id="aa322-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="aa322-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="aa322-108">**User Action**</span></span>  
  
 <span data-ttu-id="aa322-109">你仍可以保留此警告出现通过更改在提升的属性的 XPath**编辑实例 XPath**对话框中，你可以访问从中单元格**节点路径**列**属性字段列表**表上**属性字段**选项卡中**升级属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="aa322-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the **Property Field List** table on the **Property Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="aa322-110">你可以访问**升级属性**对话框中，从**升级属性**属性**架构**中 Microsoft® 节点[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。</span><span class="sxs-lookup"><span data-stu-id="aa322-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>