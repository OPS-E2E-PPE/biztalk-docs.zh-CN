---
title: 警告-目标为空 Namespace |Microsoft Docs
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
ms.openlocfilehash: 856127f1bee020e550f9fac88cf9b09838489d8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393699"
---
# <a name="warning---empty-target-namespace"></a><span data-ttu-id="1ec4c-102">警告-目标为空 Namespace</span><span class="sxs-lookup"><span data-stu-id="1ec4c-102">Warning - Empty Target Namespace</span></span>
<span data-ttu-id="1ec4c-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="1ec4c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="1ec4c-104">BEC1007</span><span class="sxs-lookup"><span data-stu-id="1ec4c-104">BEC1007</span></span>  
  
 <span data-ttu-id="1ec4c-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="1ec4c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="1ec4c-106">**目标 Namespace**的属性**架构**尚未设置节点。</span><span class="sxs-lookup"><span data-stu-id="1ec4c-106">The **Target Namespace** property of the **Schema** node has not been set.</span></span> <span data-ttu-id="1ec4c-107">尽管没有要求，建议为每个架构定义唯一目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="1ec4c-107">Although not required, it is recommended that you define a unique target namespace for each of your schemas.</span></span>  
  
 <span data-ttu-id="1ec4c-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="1ec4c-108">**User Action**</span></span>  
  
 <span data-ttu-id="1ec4c-109">如果没有充分的理由不到，选择**架构**节点的此架构，然后在 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供的值**Target Namespace**是唯一的属性对此架构。</span><span class="sxs-lookup"><span data-stu-id="1ec4c-109">Unless there is a good reason not to, select the **Schema** node of this schema, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a value for the **Target Namespace** property that is unique to this schema.</span></span>