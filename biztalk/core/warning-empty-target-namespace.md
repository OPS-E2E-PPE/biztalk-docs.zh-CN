---
title: 警告-空目标 Namespace |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.emptyTargetNamespace
ms.assetid: 00d43bcc-6fd6-4766-b91d-f6c33608c6c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b40194d0bb3c7d64bfe738d6e9f37d4032a5a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287925"
---
# <a name="warning---empty-target-namespace"></a><span data-ttu-id="a6ebd-102">警告-空目标 Namespace</span><span class="sxs-lookup"><span data-stu-id="a6ebd-102">Warning - Empty Target Namespace</span></span>
<span data-ttu-id="a6ebd-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="a6ebd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a6ebd-104">BEC1007</span><span class="sxs-lookup"><span data-stu-id="a6ebd-104">BEC1007</span></span>  
  
 <span data-ttu-id="a6ebd-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="a6ebd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a6ebd-106">**目标 Namespace**属性**架构**尚未设置节点。</span><span class="sxs-lookup"><span data-stu-id="a6ebd-106">The **Target Namespace** property of the **Schema** node has not been set.</span></span> <span data-ttu-id="a6ebd-107">虽然不是必需的，但还是建议您为每个架构定义唯一的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="a6ebd-107">Although not required, it is recommended that you define a unique target namespace for each of your schemas.</span></span>  
  
 <span data-ttu-id="a6ebd-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="a6ebd-108">**User Action**</span></span>  
  
 <span data-ttu-id="a6ebd-109">如果没有充分的理由不到，则选择**架构**节点此架构，然后在 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供一个值**目标 Namespace**是唯一的属性这种架构。</span><span class="sxs-lookup"><span data-stu-id="a6ebd-109">Unless there is a good reason not to, select the **Schema** node of this schema, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a value for the **Target Namespace** property that is unique to this schema.</span></span>