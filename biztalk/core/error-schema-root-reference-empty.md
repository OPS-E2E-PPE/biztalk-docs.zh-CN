---
title: 错误-架构根引用为空 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7217f6f9ea328aff4864cfdf3bee9ea71de3741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-root-reference-empty"></a><span data-ttu-id="3d08e-102">错误-架构根引用为空</span><span class="sxs-lookup"><span data-stu-id="3d08e-102">Error - Schema Root Reference Empty</span></span>
<span data-ttu-id="3d08e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="3d08e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="3d08e-104">BEC2005</span><span class="sxs-lookup"><span data-stu-id="3d08e-104">BEC2005</span></span>  
  
 <span data-ttu-id="3d08e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="3d08e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="3d08e-106">**根引用**属性**架构**未设置节点。</span><span class="sxs-lookup"><span data-stu-id="3d08e-106">The **Root Reference** property of the **Schema** node is not set.</span></span> <span data-ttu-id="3d08e-107">当**标准**属性**架构**节点设置为值**XML**，必须设置**根引用**属性指示子节点**架构**旨在用作此架构定义的消息的根节点。</span><span class="sxs-lookup"><span data-stu-id="3d08e-107">When the **Standard** property of the **Schema** node is set to a value other than **XML**, you must set the **Root Reference** property to indicate which child node of the **Schema** node is meant to be used as the root of the message defined by this schema.</span></span>  
  
 <span data-ttu-id="3d08e-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="3d08e-108">**User Action**</span></span>  
  
 <span data-ttu-id="3d08e-109">根据您的架构的具体情况，请设置**标准**属性**架构**节点**XML**，或设置**根引用**属性**架构**到适当的子节点的节点**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="3d08e-109">As appropriate for your schema, either set the **Standard** property of the **Schema** node to **XML**, or set the **Root Reference** property of the **Schema** node to the appropriate child node of the **Schema** node.</span></span> <span data-ttu-id="3d08e-110">这些子节点位于**根引用**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3d08e-110">These child nodes are the available in the **Root Reference** property drop-down list.</span></span>