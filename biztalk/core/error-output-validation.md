---
title: 错误-输出验证 |Microsoft Docs
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
ms.openlocfilehash: 392ec887e3352940257f268e589280eb361c0d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347118"
---
# <a name="error---output-validation"></a><span data-ttu-id="8d3f7-102">错误-输出验证</span><span class="sxs-lookup"><span data-stu-id="8d3f7-102">Error - Output Validation</span></span>
<span data-ttu-id="8d3f7-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8d3f7-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8d3f7-104">btm1046</span><span class="sxs-lookup"><span data-stu-id="8d3f7-104">btm1046</span></span>  
  
 <span data-ttu-id="8d3f7-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8d3f7-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8d3f7-106">测试映射操作创建输出实例消息文件不是根据目标架构验证所指示的原因。</span><span class="sxs-lookup"><span data-stu-id="8d3f7-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for the indicated reason.</span></span>  
  
 <span data-ttu-id="8d3f7-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8d3f7-107">**User Action**</span></span>  
  
 <span data-ttu-id="8d3f7-108">在映射中指定的转换或目标架构中，或者对二者同时，根据所指示的原因，进行合适的更正。</span><span class="sxs-lookup"><span data-stu-id="8d3f7-108">Based on the indicated reason, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="8d3f7-109">可能会有帮助，BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，并**生成实例**命令可用右键单击解决方案资源管理器中的架构。</span><span class="sxs-lookup"><span data-stu-id="8d3f7-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>