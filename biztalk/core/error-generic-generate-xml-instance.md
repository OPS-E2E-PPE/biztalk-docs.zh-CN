---
title: "错误-泛型生成 XML 实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c859cfc775e74ab817e66dbb8b896f51458f0301
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-generate-xml-instance"></a><span data-ttu-id="e7784-102">错误-泛型生成 XML 实例</span><span class="sxs-lookup"><span data-stu-id="e7784-102">Error - Generic Generate XML Instance</span></span>
<span data-ttu-id="e7784-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="e7784-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e7784-104">btm1038</span><span class="sxs-lookup"><span data-stu-id="e7784-104">btm1038</span></span>  
  
 <span data-ttu-id="e7784-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7784-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e7784-106">BizTalk 映射器不能为该映射的源架构生成 XML 实例消息文件。</span><span class="sxs-lookup"><span data-stu-id="e7784-106">BizTalk Mapper was not able to generate an XML instance message file for the source schema of the map.</span></span> <span data-ttu-id="e7784-107">这表明与该映射相关联的源架构有问题。</span><span class="sxs-lookup"><span data-stu-id="e7784-107">This suggests that there is a problem with the source schema associated with the map.</span></span>  
  
 <span data-ttu-id="e7784-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="e7784-108">**User Action**</span></span>  
  
 <span data-ttu-id="e7784-109">使用 BizTalk 编辑器打开与该映射相关联的源架构，并查明源架构是否有问题。</span><span class="sxs-lookup"><span data-stu-id="e7784-109">Use BizTalk Editor to open the source schema associated with the map and begin investigating whether there are problems with the source schema.</span></span> <span data-ttu-id="e7784-110">此外，**验证架构**和**生成实例**右键单击解决方案资源管理器中的架构时可用命令可用于查找架构错误。</span><span class="sxs-lookup"><span data-stu-id="e7784-110">Also, the **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>