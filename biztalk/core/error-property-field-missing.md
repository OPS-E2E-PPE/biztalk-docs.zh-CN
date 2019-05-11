---
title: 错误-缺少属性字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b1ce11e6b4bb140f6effe657bff060410a0e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388497"
---
# <a name="error---property-field-missing"></a><span data-ttu-id="b700e-102">错误-缺少属性字段</span><span class="sxs-lookup"><span data-stu-id="b700e-102">Error - Property Field Missing</span></span>
<span data-ttu-id="b700e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b700e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b700e-104">BEC2008</span><span class="sxs-lookup"><span data-stu-id="b700e-104">BEC2008</span></span>  
  
 <span data-ttu-id="b700e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b700e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b700e-106">此架构中所指示的节点被升级为**Field 元素**中不存在的相应属性架构的节点。</span><span class="sxs-lookup"><span data-stu-id="b700e-106">The indicated node in this schema is being promoted to a **Field Element** node in the corresponding property schema that does not exist.</span></span> <span data-ttu-id="b700e-107">会出现此情况时**Field 元素**节点中，删除或重命名属性架构中作为目标的属性升级用完之后。</span><span class="sxs-lookup"><span data-stu-id="b700e-107">This condition can occur when a **Field Element** node is removed from, or renamed in, a property schema after it has been used as the target of a property promotion.</span></span>  
  
 <span data-ttu-id="b700e-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b700e-108">**User Action**</span></span>  
  
 <span data-ttu-id="b700e-109">请修改属性架构，使其包含缺少**Field 元素**节点或使用**升级属性**对话框可以删除或修改相关的属性升级。</span><span class="sxs-lookup"><span data-stu-id="b700e-109">Either modify the property schema so that it contains the missing **Field Element** node, or use the **Promote Properties** dialog box to delete or otherwise modify the relevant property promotion.</span></span>