---
title: 错误-需要迁移映射 |Microsoft 文档
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
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---map-needs-to-be-migrated"></a><span data-ttu-id="a2228-102">错误-需要迁移映射</span><span class="sxs-lookup"><span data-stu-id="a2228-102">Error - Map Needs to be Migrated</span></span>
<span data-ttu-id="a2228-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="a2228-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a2228-104">btm1064</span><span class="sxs-lookup"><span data-stu-id="a2228-104">btm1064</span></span>  
  
 <span data-ttu-id="a2228-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="a2228-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a2228-106">由于映射是使用以前版本的 BizTalk 映射器创建的，因此无法编译。</span><span class="sxs-lookup"><span data-stu-id="a2228-106">The map cannot be compiled because it was created using a previous version of BizTalk Mapper.</span></span> <span data-ttu-id="a2228-107">在编译这些映射之前，必须先将它们迁移到此版本的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="a2228-107">You must migrate such maps to this version of BizTalk Mapper before they can be compiled.</span></span>  
  
 <span data-ttu-id="a2228-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="a2228-108">**User Action**</span></span>  
  
 <span data-ttu-id="a2228-109">通过将映射的文件扩展名从“xml”更改为“btm”，并将其添加到相关的 Microsoft BizTalk Server 项目中，可将映射迁移到当前版本的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="a2228-109">Migrate the map to the current version of BizTalk Mapper by changing its file extension from "xml" to "btm", adding it to the relevant Microsoft BizTalk Server project.</span></span> <span data-ttu-id="a2228-110">使用**添加现有项**上可用的命令**文件**菜单和快捷菜单上的 BizTalk 项目在解决方案资源管理器，然后打开该映射，通过在解决方案资源管理器中双击它。</span><span class="sxs-lookup"><span data-stu-id="a2228-110">Use the **Add Existing Item** command available on the **File** menu and on the shortcut menu for the BizTalk project in Solution Explorer, and then open the map by double-clicking it in Solution Explorer.</span></span> <span data-ttu-id="a2228-111">由于已学至此主题，想必已执行了前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="a2228-111">Because you have reached this topic, you have probably already performed the first two steps.</span></span> <span data-ttu-id="a2228-112">此时只需在当前版本的 BizTalk 映射器中打开该映射，就可以自动迁移映射。</span><span class="sxs-lookup"><span data-stu-id="a2228-112">Simply opening the map in the current version of BizTalk Mapper will perform an on-the-fly migration of the map.</span></span>