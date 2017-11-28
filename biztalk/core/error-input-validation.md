---
title: "错误-输入验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputValidation
ms.assetid: 3529481d-11ae-4334-9ff7-24342cb2bab4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f6392c6f5aad85442659beb9f6f1e3ef989299
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-validation"></a><span data-ttu-id="982c9-102">错误-输入验证</span><span class="sxs-lookup"><span data-stu-id="982c9-102">Error - Input Validation</span></span>
<span data-ttu-id="982c9-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="982c9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="982c9-104">btm1044</span><span class="sxs-lookup"><span data-stu-id="982c9-104">btm1044</span></span>  
  
 <span data-ttu-id="982c9-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="982c9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="982c9-106">由于错误消息所指示的原因，无法根据源架构来验证为测试映射操作指定的输入实例消息文件。</span><span class="sxs-lookup"><span data-stu-id="982c9-106">The input instance message file specified for the Test Map operation could not be validated against the source schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="982c9-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="982c9-107">**User Action**</span></span>  
  
 <span data-ttu-id="982c9-108">根据所指示的原因，适当修改输入实例消息文件或源架构，或者对二者同时进行修改。</span><span class="sxs-lookup"><span data-stu-id="982c9-108">Based on the indicated reason, make the appropriate corrections to either the input instance message file or to the source schema, or to both.</span></span> <span data-ttu-id="982c9-109">它可能有助于 BizTalk 编辑器中打开源架构以及使用**验证架构**和**生成实例**右键单击解决方案资源管理器中的架构时可用命令。</span><span class="sxs-lookup"><span data-stu-id="982c9-109">It may be helpful to open the source schema in BizTalk Editor and use the **Validate Schema** and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>