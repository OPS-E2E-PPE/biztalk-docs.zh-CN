---
title: 错误-一般性输出验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericOutputValidation
ms.assetid: 27fb2233-3add-42f8-a96b-872e2e38f797
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b776561e1e6034242fa74c4d401e5e2b775ed8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348167"
---
# <a name="error---generic-output-validation"></a><span data-ttu-id="19de6-102">错误-一般性输出验证</span><span class="sxs-lookup"><span data-stu-id="19de6-102">Error - Generic Output Validation</span></span>
<span data-ttu-id="19de6-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="19de6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="19de6-104">btm1047</span><span class="sxs-lookup"><span data-stu-id="19de6-104">btm1047</span></span>  
  
 <span data-ttu-id="19de6-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="19de6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="19de6-106">测试映射操作创建输出实例消息文件不是根据目标架构验证原因不明。</span><span class="sxs-lookup"><span data-stu-id="19de6-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for an unspecified reason.</span></span>  
  
 <span data-ttu-id="19de6-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="19de6-107">**User Action**</span></span>  
  
 <span data-ttu-id="19de6-108">在 BizTalk 编辑器中打开目标架构并使用**验证架构**，**验证实例**，并**生成实例**命令中，右键单击时可用在解决方案资源管理器，以找出问题的架构。</span><span class="sxs-lookup"><span data-stu-id="19de6-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>