---
title: 警告-字段数据类型不匹配 |Microsoft Docs
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
ms.openlocfilehash: 50d74dfb16dbd03eb92e6880681721608389840a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393679"
---
# <a name="warning---field-data-type-mismatch"></a><span data-ttu-id="b49cd-102">警告-字段数据类型不匹配</span><span class="sxs-lookup"><span data-stu-id="b49cd-102">Warning - Field Data Type Mismatch</span></span>
<span data-ttu-id="b49cd-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b49cd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b49cd-104">BEC1002</span><span class="sxs-lookup"><span data-stu-id="b49cd-104">BEC1002</span></span>  
  
 <span data-ttu-id="b49cd-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b49cd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b49cd-106">**数据类型**找到所指示的节点属性不同于**数据类型**属性**字段元素**它将被提升到中的节点相应属性架构。</span><span class="sxs-lookup"><span data-stu-id="b49cd-106">The **Data Type** property of the indicated node was found to be different than the **Data Type** property of the **Field Element** node to which it is being promoted in the corresponding property schema.</span></span> <span data-ttu-id="b49cd-107">在架构中节点的数据类型应与分配给数据类型匹配**Field 元素**节点用于其属性字段升级，或至少，应分配的数据类型映射到相同的公共语言运行时 (CLR) 类型。</span><span class="sxs-lookup"><span data-stu-id="b49cd-107">The data type of a node in a schema should match the data type assigned to the **Field Element** node used for its Property Field promotion, or at least, the assigned data types should map to the same common language runtime (CLR) type.</span></span>  
  
 <span data-ttu-id="b49cd-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b49cd-108">**User Action**</span></span>  
  
 <span data-ttu-id="b49cd-109">更改**数据类型**所指示的节点的属性和**Field 元素**它将被提升到相同的数据节点键入值，或至少对数据类型值映射到相同的 CLR 数据类型。</span><span class="sxs-lookup"><span data-stu-id="b49cd-109">Change the **Data Type** properties of the indicated node and the **Field Element** node to which it is being promoted to the same data type value, or at least to data type values that map to the same CLR data type.</span></span>