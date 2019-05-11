---
title: 创建 BizTalk 项目时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b8749928891f963f3ca75032cc133c0ddf7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390358"
---
# <a name="considerations-when-creating-biztalk-projects"></a><span data-ttu-id="f410d-102">创建 BizTalk 项目时的注意事项</span><span class="sxs-lookup"><span data-stu-id="f410d-102">Considerations When Creating BizTalk Projects</span></span>
<span data-ttu-id="f410d-103">本部分提供创建 BizTalk 项目使用时应考虑的信息[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f410d-103">This section provides information that you should take into consideration when creating BizTalk projects using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a><span data-ttu-id="f410d-104">避免太大的项目所导致的编译错误</span><span class="sxs-lookup"><span data-stu-id="f410d-104">Avoid compilation errors caused by projects that are too large</span></span>  
 <span data-ttu-id="f410d-105">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器将不能成功编译项目这是如果这会导致在程序集大于 75 兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="f410d-105">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler will not successfully compile a project if it would result in an assembly larger than 75 megabytes.</span></span> <span data-ttu-id="f410d-106">该编译器达到大小限制时它会发出错误 CS0013"将元数据写入到文件的意外的错误\<文件名\>"并停止。</span><span class="sxs-lookup"><span data-stu-id="f410d-106">When the compiler reaches a size constraint it will emit fatal error CS0013 "Unexpected error writing metadata to file \<filename\>" and halt.</span></span>  
  
 <span data-ttu-id="f410d-107">若要避免此问题，我们建议项目不要超过 10 兆字节，除非绝对必要。</span><span class="sxs-lookup"><span data-stu-id="f410d-107">To avoid this problem, we recommend that projects not exceed 10 megabytes unless absolutely necessary.</span></span> <span data-ttu-id="f410d-108">原因是什么？</span><span class="sxs-lookup"><span data-stu-id="f410d-108">Why?</span></span>  
  
-   <span data-ttu-id="f410d-109">较小的项目是可能会越简单部署，因为有更少的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="f410d-109">Smaller projects are potentially simpler to deploy because there are fewer deployment steps.</span></span> <span data-ttu-id="f410d-110">并使用较小的项目的步骤是更有可能密切相关-管理贸易合作伙伴折扣或处理 Rfp。</span><span class="sxs-lookup"><span data-stu-id="f410d-110">And with smaller projects the steps are more likely to be closely related -- managing trading partner discounts or handling RFPs.</span></span>  
  
-   <span data-ttu-id="f410d-111">它很容易隔离 bug、 部署问题和其他问题时使用较小的项目。</span><span class="sxs-lookup"><span data-stu-id="f410d-111">It is easier to isolate bugs, deployment issues, and other problems when using smaller projects.</span></span> <span data-ttu-id="f410d-112">使用 140 个架构和许多自定义映射和脚本项目中查找错误将会比只有 10 个架构和少量自定义映射和脚本项目中查找更加困难。</span><span class="sxs-lookup"><span data-stu-id="f410d-112">Finding a bug in a project with 140 schemas and many custom maps and scripts will be more difficult than finding one in a project with only 10 schemas and a few custom maps and scripts.</span></span>  
  
-   <span data-ttu-id="f410d-113">将一个大项目分成较小的项目可以降低复杂性。</span><span class="sxs-lookup"><span data-stu-id="f410d-113">Separating a large project into smaller projects can reduce complexity.</span></span> <span data-ttu-id="f410d-114">较小的项目是更易于管理。</span><span class="sxs-lookup"><span data-stu-id="f410d-114">The smaller projects are more manageable.</span></span>  
  
-   <span data-ttu-id="f410d-115">较小的项目编译速度更快。</span><span class="sxs-lookup"><span data-stu-id="f410d-115">Smaller projects compile faster.</span></span>  
  
-   <span data-ttu-id="f410d-116">将具有多个不相关架构的大项目拆分为较小的项目与紧密相关的架构可能会导致更好的性能。</span><span class="sxs-lookup"><span data-stu-id="f410d-116">Splitting a large project with many unrelated schemas into smaller projects with strongly related schemas may result in better performance.</span></span> <span data-ttu-id="f410d-117">这是因为只有某些程序集将加载一次。</span><span class="sxs-lookup"><span data-stu-id="f410d-117">This is because only some of the assemblies will be loaded at a time.</span></span>  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a><span data-ttu-id="f410d-118">避免将项目名称用作映射类型名称</span><span class="sxs-lookup"><span data-stu-id="f410d-118">Avoid using the Project Name as the Map Type Name</span></span>  
 <span data-ttu-id="f410d-119">将新的映射添加到的 BizTalk 项目中时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]不使用作为类型名称的项目名称。</span><span class="sxs-lookup"><span data-stu-id="f410d-119">When adding a new map to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not use the project name as the type name.</span></span> <span data-ttu-id="f410d-120">如果这样做，编译器将生成一个或多个错误类似于"的类型名称\<名称\>类型中不存在"。</span><span class="sxs-lookup"><span data-stu-id="f410d-120">If you do, the compiler will generate one or more errors similar to "The type name \<name\>' does not exist in the type".</span></span>  
  
 <span data-ttu-id="f410d-121">若要更改从 BizTalk 项目中的映射的类型名称，单击解决方案资源管理器窗格中的映射，然后验证属性窗格中的类型名称属性。</span><span class="sxs-lookup"><span data-stu-id="f410d-121">To change the type name for a map from within a BizTalk project, click the map in the Solution Explorer pane, then verify the type name property in the Properties pane.</span></span> <span data-ttu-id="f410d-122">如果它是相同的您需要修改它以确保更改依赖于它的所有配置。</span><span class="sxs-lookup"><span data-stu-id="f410d-122">If it is the same, you need to modify it making sure to change any configurations that rely on it.</span></span>  
  
## <a name="visual-studio-team-system-support"></a><span data-ttu-id="f410d-123">Visual Studio Team System 支持</span><span class="sxs-lookup"><span data-stu-id="f410d-123">Visual Studio Team System Support</span></span>  
 <span data-ttu-id="f410d-124">中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]进行不直接支持的所有功能[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System。</span><span class="sxs-lookup"><span data-stu-id="f410d-124">BizTalk projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not directly support all features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System.</span></span> <span data-ttu-id="f410d-125">源代码管理功能的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System 支持 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="f410d-125">The source control features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System are supported for BizTalk Server.</span></span> <span data-ttu-id="f410d-126">Visual SourceSafe 也完全支持跟踪和版本控制的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="f410d-126">Visual SourceSafe is also fully supported for the tracking and versioning of BizTalk project artifacts.</span></span>