---
title: 错误-架构根引用为空 |Microsoft Docs
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
ms.openlocfilehash: c56119e88948211f7b2e93add1d6e23d08e1b9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346885"
---
# <a name="error---schema-root-reference-empty"></a><span data-ttu-id="9d7db-102">错误-架构根引用为空</span><span class="sxs-lookup"><span data-stu-id="9d7db-102">Error - Schema Root Reference Empty</span></span>
<span data-ttu-id="9d7db-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="9d7db-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9d7db-104">BEC2005</span><span class="sxs-lookup"><span data-stu-id="9d7db-104">BEC2005</span></span>  
  
 <span data-ttu-id="9d7db-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d7db-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9d7db-106">**根引用**的属性**架构**未设置节点。</span><span class="sxs-lookup"><span data-stu-id="9d7db-106">The **Root Reference** property of the **Schema** node is not set.</span></span> <span data-ttu-id="9d7db-107">当**标准**的属性**架构**节点设置为值**XML**，则必须设置**根引用**属性设置为指示的哪个子节点**架构**旨在用作此架构所定义的消息的根节点。</span><span class="sxs-lookup"><span data-stu-id="9d7db-107">When the **Standard** property of the **Schema** node is set to a value other than **XML**, you must set the **Root Reference** property to indicate which child node of the **Schema** node is meant to be used as the root of the message defined by this schema.</span></span>  
  
 <span data-ttu-id="9d7db-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="9d7db-108">**User Action**</span></span>  
  
 <span data-ttu-id="9d7db-109">根据您的架构的具体情况，请设置**标准**的属性**架构**节点**XML**，或设置**根引用**属性的**架构**对其相应的子节点的节点**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="9d7db-109">As appropriate for your schema, either set the **Standard** property of the **Schema** node to **XML**, or set the **Root Reference** property of the **Schema** node to the appropriate child node of the **Schema** node.</span></span> <span data-ttu-id="9d7db-110">这些子节点是中提供**根引用**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9d7db-110">These child nodes are the available in the **Root Reference** property drop-down list.</span></span>