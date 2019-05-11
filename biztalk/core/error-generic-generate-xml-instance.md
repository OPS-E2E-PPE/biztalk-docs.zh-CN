---
title: 错误-常规生成 XML 实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a24f4143e2619809071d3b414c9a122c8121b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348255"
---
# <a name="error---generic-generate-xml-instance"></a><span data-ttu-id="06b6a-102">错误-常规生成 XML 实例</span><span class="sxs-lookup"><span data-stu-id="06b6a-102">Error - Generic Generate XML Instance</span></span>
<span data-ttu-id="06b6a-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="06b6a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="06b6a-104">btm1038</span><span class="sxs-lookup"><span data-stu-id="06b6a-104">btm1038</span></span>  
  
 <span data-ttu-id="06b6a-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="06b6a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="06b6a-106">BizTalk 映射器无法生成该映射的源架构的 XML 实例消息文件。</span><span class="sxs-lookup"><span data-stu-id="06b6a-106">BizTalk Mapper was not able to generate an XML instance message file for the source schema of the map.</span></span> <span data-ttu-id="06b6a-107">这表明，没有源架构与映射关联的问题。</span><span class="sxs-lookup"><span data-stu-id="06b6a-107">This suggests that there is a problem with the source schema associated with the map.</span></span>  
  
 <span data-ttu-id="06b6a-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="06b6a-108">**User Action**</span></span>  
  
 <span data-ttu-id="06b6a-109">使用 BizTalk 编辑器打开源架构与映射相关联，然后开始调查是否有问题的源架构。</span><span class="sxs-lookup"><span data-stu-id="06b6a-109">Use BizTalk Editor to open the source schema associated with the map and begin investigating whether there are problems with the source schema.</span></span> <span data-ttu-id="06b6a-110">此外，**验证架构**并**生成实例**命令中，右键单击解决方案资源管理器中的架构后即可可用于找出架构错误。</span><span class="sxs-lookup"><span data-stu-id="06b6a-110">Also, the **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>