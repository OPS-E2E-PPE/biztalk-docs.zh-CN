---
title: 错误-属性字段升级重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d105b1df7d934842b3c72be3a9e2068bc9e70021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388938"
---
# <a name="error---duplicate-property-field-promotion"></a><span data-ttu-id="3057e-102">错误-属性字段升级重复</span><span class="sxs-lookup"><span data-stu-id="3057e-102">Error - Duplicate Property Field Promotion</span></span>
<span data-ttu-id="3057e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="3057e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="3057e-104">BEC2016</span><span class="sxs-lookup"><span data-stu-id="3057e-104">BEC2016</span></span>  
  
 <span data-ttu-id="3057e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="3057e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="3057e-106">正在此架构中的多个节点作为属性字段升级到同一**Field 元素**相同的属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="3057e-106">Multiple nodes in this schema are being promoted as Property Fields to the same **Field Element** node in the same property schema.</span></span>  
  
 <span data-ttu-id="3057e-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="3057e-107">**User Action**</span></span>  
  
 <span data-ttu-id="3057e-108">使用**属性字段**选项卡**升级属性**对话框中，通过访问**升级属性**属性**架构**节点，删除所有只保留一个具有相同关联属性字段升级**字段元素**属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="3057e-108">Use the **Property Fields** tab of the **Promote Properties** dialog box, accessed through the **Promote Properties** property of the **Schema** node, to delete all but one of the Property Field promotions that are associated with the same **Field Element** node in the property schema.</span></span> <span data-ttu-id="3057e-109">您可能想要添加新**字段元素**到属性架构的节点，以便删除的升级可能会重新升级为各自**Field 元素**节点。</span><span class="sxs-lookup"><span data-stu-id="3057e-109">You may want to add new **Field Element** nodes to the property schema so that the deleted promotions can be re-promoted to their own **Field Element** nodes.</span></span>