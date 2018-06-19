---
title: 错误-输出验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputValidation
ms.assetid: 18a251a9-6bd4-4fd1-a774-2ea1b7870891
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7410fba7cebbf5183a02e79aa3c179eb86cd8395
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241189"
---
# <a name="error---output-validation"></a><span data-ttu-id="8a7fb-102">错误-输出验证</span><span class="sxs-lookup"><span data-stu-id="8a7fb-102">Error - Output Validation</span></span>
<span data-ttu-id="8a7fb-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8a7fb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8a7fb-104">btm1046</span><span class="sxs-lookup"><span data-stu-id="8a7fb-104">btm1046</span></span>  
  
 <span data-ttu-id="8a7fb-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8a7fb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8a7fb-106">所指明的那样，无法验证针对目标架构创建测试映射操作的输出实例消息文件。</span><span class="sxs-lookup"><span data-stu-id="8a7fb-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="8a7fb-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8a7fb-107">**User Action**</span></span>  
  
 <span data-ttu-id="8a7fb-108">在映射中，指定的转换或目标架构，或者对二者同时，根据指定的原因，进行合适的更正。</span><span class="sxs-lookup"><span data-stu-id="8a7fb-108">Based on the indicated reason, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="8a7fb-109">它可能有助于 BizTalk 编辑器中打开目标架构以及使用**验证架构**，**验证实例**，和**生成实例**命令可用右键单击解决方案资源管理器中的架构。</span><span class="sxs-lookup"><span data-stu-id="8a7fb-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>