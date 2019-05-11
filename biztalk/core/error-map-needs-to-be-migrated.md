---
title: 错误-映射需要迁移 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b1b1bee4bcdedecb31dc4b648b505d8ae53b4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389028"
---
# <a name="error---map-needs-to-be-migrated"></a><span data-ttu-id="e0af0-102">错误-需要迁移映射</span><span class="sxs-lookup"><span data-stu-id="e0af0-102">Error - Map Needs to be Migrated</span></span>
<span data-ttu-id="e0af0-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="e0af0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e0af0-104">btm1064</span><span class="sxs-lookup"><span data-stu-id="e0af0-104">btm1064</span></span>  
  
 <span data-ttu-id="e0af0-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="e0af0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e0af0-106">无法编译该映射，因为它创建使用以前版本的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="e0af0-106">The map cannot be compiled because it was created using a previous version of BizTalk Mapper.</span></span> <span data-ttu-id="e0af0-107">它们可以编译之前，必须将此类映射迁移到此版本的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="e0af0-107">You must migrate such maps to this version of BizTalk Mapper before they can be compiled.</span></span>  
  
 <span data-ttu-id="e0af0-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="e0af0-108">**User Action**</span></span>  
  
 <span data-ttu-id="e0af0-109">通过更改文件扩展名从"xml"为"btm"，并将其添加到相关的 Microsoft BizTalk Server 项目，将映射迁移到当前版本的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="e0af0-109">Migrate the map to the current version of BizTalk Mapper by changing its file extension from "xml" to "btm", adding it to the relevant Microsoft BizTalk Server project.</span></span> <span data-ttu-id="e0af0-110">使用**添加现有项**上可用的命令**文件**菜单和快捷菜单上的 BizTalk 项目在解决方案资源管理器，然后通过双击解决方案资源管理器中打开该映射。</span><span class="sxs-lookup"><span data-stu-id="e0af0-110">Use the **Add Existing Item** command available on the **File** menu and on the shortcut menu for the BizTalk project in Solution Explorer, and then open the map by double-clicking it in Solution Explorer.</span></span> <span data-ttu-id="e0af0-111">因为你已达到本主题，你可能已经执行的前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="e0af0-111">Because you have reached this topic, you have probably already performed the first two steps.</span></span> <span data-ttu-id="e0af0-112">只需在当前版本的 BizTalk 映射器中打开该映射将执行在实时迁移映射。</span><span class="sxs-lookup"><span data-stu-id="e0af0-112">Simply opening the map in the current version of BizTalk Mapper will perform an on-the-fly migration of the map.</span></span>