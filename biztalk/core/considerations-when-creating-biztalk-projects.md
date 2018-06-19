---
title: 创建 BizTalk 项目时的注意事项 |Microsoft 文档
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
ms.openlocfilehash: f0302d2329f848352f55d15f0c6e21bbdf72b0ca
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005950"
---
# <a name="considerations-when-creating-biztalk-projects"></a><span data-ttu-id="1e9a8-102">创建 BizTalk 项目时的注意事项</span><span class="sxs-lookup"><span data-stu-id="1e9a8-102">Considerations When Creating BizTalk Projects</span></span>
<span data-ttu-id="1e9a8-103">本部分提供在创建 BizTalk 项目使用时应考虑的信息[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-103">This section provides information that you should take into consideration when creating BizTalk projects using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a><span data-ttu-id="1e9a8-104">避免由于项目过大而导致的编译错误</span><span class="sxs-lookup"><span data-stu-id="1e9a8-104">Avoid compilation errors caused by projects that are too large</span></span>  
 <span data-ttu-id="1e9a8-105">如果 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 编译器生成的程序集大于 75 MB，则该编译器将不能成功地编译项目。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-105">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler will not successfully compile a project if it would result in an assembly larger than 75 megabytes.</span></span> <span data-ttu-id="1e9a8-106">当编译器达到大小约束它将发出错误 CS0013"元数据写入文件的意外的错误\<filename\>"停止。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-106">When the compiler reaches a size constraint it will emit fatal error CS0013 "Unexpected error writing metadata to file \<filename\>" and halt.</span></span>  
  
 <span data-ttu-id="1e9a8-107">若要避免出现此问题，建议项目不要超过 10 MB，除非确实有此必要。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-107">To avoid this problem, we recommend that projects not exceed 10 megabytes unless absolutely necessary.</span></span> <span data-ttu-id="1e9a8-108">原因是什么？</span><span class="sxs-lookup"><span data-stu-id="1e9a8-108">Why?</span></span>  
  
-   <span data-ttu-id="1e9a8-109">项目越小，所需的部署步骤就越少，因此部署可能会越简单。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-109">Smaller projects are potentially simpler to deploy because there are fewer deployment steps.</span></span> <span data-ttu-id="1e9a8-110">此外，对于较小的项目，这些步骤之间的关联可能会更加紧密（管理贸易合作伙伴折扣或处理 RFP 的折扣）。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-110">And with smaller projects the steps are more likely to be closely related -- managing trading partner discounts or handling RFPs.</span></span>  
  
-   <span data-ttu-id="1e9a8-111">使用的项目越小，就越容易解决错误、部署问题及其他问题。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-111">It is easier to isolate bugs, deployment issues, and other problems when using smaller projects.</span></span> <span data-ttu-id="1e9a8-112">与在仅包含 10 个架构和少量自定义映射和脚本的项目中查找错误相比，在包含 140 个架构和许多自定义映射和脚本的项目中查找错误会困难得多。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-112">Finding a bug in a project with 140 schemas and many custom maps and scripts will be more difficult than finding one in a project with only 10 schemas and a few custom maps and scripts.</span></span>  
  
-   <span data-ttu-id="1e9a8-113">将一个大项目分成几个较小的项目可以降低复杂性。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-113">Separating a large project into smaller projects can reduce complexity.</span></span> <span data-ttu-id="1e9a8-114">项目越小，就越容易管理。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-114">The smaller projects are more manageable.</span></span>  
  
-   <span data-ttu-id="1e9a8-115">项目越小，编译速度就越快。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-115">Smaller projects compile faster.</span></span>  
  
-   <span data-ttu-id="1e9a8-116">将包含多个不相关架构的大项目拆分成只包含紧密相关的架构的较小项目，可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-116">Splitting a large project with many unrelated schemas into smaller projects with strongly related schemas may result in better performance.</span></span> <span data-ttu-id="1e9a8-117">这是因为只有某些程序集将加载一次。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-117">This is because only some of the assemblies will be loaded at a time.</span></span>  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a><span data-ttu-id="1e9a8-118">避免将项目名称用作映射类型名称</span><span class="sxs-lookup"><span data-stu-id="1e9a8-118">Avoid using the Project Name as the Map Type Name</span></span>  
 <span data-ttu-id="1e9a8-119">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中向 BizTalk 项目添加新映射时，请不要将项目名称用作类型名称。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-119">When adding a new map to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not use the project name as the type name.</span></span> <span data-ttu-id="1e9a8-120">如果这样做，则编译器将生成一个或多个错误类似于"的类型名称\<名称\>类型中不存在"。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-120">If you do, the compiler will generate one or more errors similar to "The type name \<name\>' does not exist in the type".</span></span>  
  
 <span data-ttu-id="1e9a8-121">若要更改从 BizTalk 项目中的映射的类型名称，单击解决方案资源管理器窗格中中的映射，然后检查属性窗格中的类型名称属性。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-121">To change the type name for a map from within a BizTalk project, click the map in the Solution Explorer pane, then verify the type name property in the Properties pane.</span></span> <span data-ttu-id="1e9a8-122">如果名称相同，则需要对其进行修改，以确保更改依赖于此名称的所有配置。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-122">If it is the same, you need to modify it making sure to change any configurations that rely on it.</span></span>  
  
## <a name="visual-studio-team-system-support"></a><span data-ttu-id="1e9a8-123">Visual Studio Team System 支持</span><span class="sxs-lookup"><span data-stu-id="1e9a8-123">Visual Studio Team System Support</span></span>  
 <span data-ttu-id="1e9a8-124">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 BizTalk 项目不直接支持 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System 的所有功能。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-124">BizTalk projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not directly support all features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System.</span></span> <span data-ttu-id="1e9a8-125">源代码管理功能的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System 支持 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-125">The source control features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System are supported for BizTalk Server.</span></span> <span data-ttu-id="1e9a8-126">Visual SourceSafe 也完全支持对 BizTalk 项目进行跟踪和版本控制。</span><span class="sxs-lookup"><span data-stu-id="1e9a8-126">Visual SourceSafe is also fully supported for the tracking and versioning of BizTalk project artifacts.</span></span>