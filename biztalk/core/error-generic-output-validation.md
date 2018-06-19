---
title: 错误-一般性输出验证 |Microsoft 文档
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
ms.openlocfilehash: 6c1bac5235788f6e369cc316ed1236357a51c004
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239869"
---
# <a name="error---generic-output-validation"></a><span data-ttu-id="7086e-102">错误-泛型输出验证</span><span class="sxs-lookup"><span data-stu-id="7086e-102">Error - Generic Output Validation</span></span>
<span data-ttu-id="7086e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7086e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7086e-104">btm1047</span><span class="sxs-lookup"><span data-stu-id="7086e-104">btm1047</span></span>  
  
 <span data-ttu-id="7086e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7086e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7086e-106">无法根据目标架构来验证测试映射操作创建的输出实例消息文件，具体原因并未指明。</span><span class="sxs-lookup"><span data-stu-id="7086e-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for an unspecified reason.</span></span>  
  
 <span data-ttu-id="7086e-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7086e-107">**User Action**</span></span>  
  
 <span data-ttu-id="7086e-108">在 BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，和**生成实例**命令中，右键单击时可用在解决方案资源管理器，以找出问题的架构。</span><span class="sxs-lookup"><span data-stu-id="7086e-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>