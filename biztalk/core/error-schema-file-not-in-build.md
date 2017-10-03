---
title: "错误-不在生成的架构文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3b5d6d11bec6b9f263e2f204f004a9a162de471
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-file-not-in-build"></a><span data-ttu-id="5078c-102">错误-不在生成的架构文件</span><span class="sxs-lookup"><span data-stu-id="5078c-102">Error - Schema File Not In Build</span></span>
<span data-ttu-id="5078c-103">**说明**</span><span class="sxs-lookup"><span data-stu-id="5078c-103">**Explanation**</span></span>  
  
 <span data-ttu-id="5078c-104">该命令 (**验证实例**，**生成实例**，或**验证架构**) 无法执行，因为**生成操作**架构文件的属性设置为**无**，阻止此架构参与这些命令。</span><span class="sxs-lookup"><span data-stu-id="5078c-104">The command (**Validate Instance**, **Generate Instance**, or **Validate Schema**) could not be performed because the **Build Action** property of the schema file is set to **None**, preventing this schema from participating in these commands.</span></span>  
  
 <span data-ttu-id="5078c-105">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="5078c-105">**User Action**</span></span>  
  
 <span data-ttu-id="5078c-106">在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**生成操作**属性**编译**。</span><span class="sxs-lookup"><span data-stu-id="5078c-106">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Build Action** property to a **Compile**.</span></span> <span data-ttu-id="5078c-107">然后尝试**验证实例**，**生成实例**，或**验证架构**试命令。</span><span class="sxs-lookup"><span data-stu-id="5078c-107">Then attempt the **Validate Instance**, **Generate Instance**, or **Validate Schema** command again.</span></span>