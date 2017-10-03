---
title: "错误-缺少属性字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d77311e4c8585cfb7f6108364e6a5085619595a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-field-missing"></a><span data-ttu-id="563f2-102">错误-缺少属性字段</span><span class="sxs-lookup"><span data-stu-id="563f2-102">Error - Property Field Missing</span></span>
<span data-ttu-id="563f2-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="563f2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="563f2-104">BEC2008</span><span class="sxs-lookup"><span data-stu-id="563f2-104">BEC2008</span></span>  
  
 <span data-ttu-id="563f2-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="563f2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="563f2-106">此架构中的指定的节点提升为**Field 元素**不存在的属性对应的架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="563f2-106">The indicated node in this schema is being promoted to a **Field Element** node in the corresponding property schema that does not exist.</span></span> <span data-ttu-id="563f2-107">可能会发生此问题时**Field 元素**节点被删除，或重命名，属性架构作为属性提升的目标用完之后。</span><span class="sxs-lookup"><span data-stu-id="563f2-107">This condition can occur when a **Field Element** node is removed from, or renamed in, a property schema after it has been used as the target of a property promotion.</span></span>  
  
 <span data-ttu-id="563f2-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="563f2-108">**User Action**</span></span>  
  
 <span data-ttu-id="563f2-109">请修改属性架构，以使其包含缺少**Field 元素**节点或使用**升级属性**对话框中删除，或者修改相关属性提升。</span><span class="sxs-lookup"><span data-stu-id="563f2-109">Either modify the property schema so that it contains the missing **Field Element** node, or use the **Promote Properties** dialog box to delete or otherwise modify the relevant property promotion.</span></span>