---
title: 警告-字段数据类型不匹配 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af42f5c921333e34c9ee219020cdb0fba97a7b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---field-data-type-mismatch"></a><span data-ttu-id="64dd9-102">警告-字段数据类型不匹配</span><span class="sxs-lookup"><span data-stu-id="64dd9-102">Warning - Field Data Type Mismatch</span></span>
<span data-ttu-id="64dd9-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="64dd9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="64dd9-104">BEC1002</span><span class="sxs-lookup"><span data-stu-id="64dd9-104">BEC1002</span></span>  
  
 <span data-ttu-id="64dd9-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="64dd9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="64dd9-106">**数据类型**找到指定的节点的属性不同于**数据类型**属性**Field 元素**它将被提升到中的节点相应的属性架构。</span><span class="sxs-lookup"><span data-stu-id="64dd9-106">The **Data Type** property of the indicated node was found to be different than the **Data Type** property of the **Field Element** node to which it is being promoted in the corresponding property schema.</span></span> <span data-ttu-id="64dd9-107">架构中的节点的数据类型应与分配给数据类型匹配**Field 元素**节点用于其属性字段提升，或至少应分配的数据类型映射到相同的公共语言运行时 (CLR) 类型。</span><span class="sxs-lookup"><span data-stu-id="64dd9-107">The data type of a node in a schema should match the data type assigned to the **Field Element** node used for its Property Field promotion, or at least, the assigned data types should map to the same common language runtime (CLR) type.</span></span>  
  
 <span data-ttu-id="64dd9-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="64dd9-108">**User Action**</span></span>  
  
 <span data-ttu-id="64dd9-109">更改**数据类型**指示节点的属性和**Field 元素**它将被提升到相同的数据的节点键入值，或至少为数据类型值映射到相同的 CLR 数据类型。</span><span class="sxs-lookup"><span data-stu-id="64dd9-109">Change the **Data Type** properties of the indicated node and the **Field Element** node to which it is being promoted to the same data type value, or at least to data type values that map to the same CLR data type.</span></span>