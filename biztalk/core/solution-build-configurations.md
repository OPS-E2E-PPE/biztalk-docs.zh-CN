---
title: "解决方案生成配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c48791d26842b7224bb950334d6b184452a54d6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="solution-build-configurations"></a><span data-ttu-id="30ee7-102">解决方案生成配置</span><span class="sxs-lookup"><span data-stu-id="30ee7-102">Solution Build Configurations</span></span>
<span data-ttu-id="30ee7-103">就像在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中生成的其他项目一样，您可以使用配置管理器来指定解决方案生成配置。</span><span class="sxs-lookup"><span data-stu-id="30ee7-103">As with other projects that you build in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can use Configuration Manager to specify solution build configurations.</span></span> <span data-ttu-id="30ee7-104">解决方案生成配置使你可以确定要在中包含的项目版本解决方案，并且如果将部署它们。</span><span class="sxs-lookup"><span data-stu-id="30ee7-104">Solution build configurations enable you to determine which projects to include in builds of a solution and if they will be deployed.</span></span> <span data-ttu-id="30ee7-105">BizTalk Server 同时支持**调试**和**版本**生成配置。</span><span class="sxs-lookup"><span data-stu-id="30ee7-105">BizTalk Server supports both **Debug** and **Release** build configurations.</span></span>  
  
 <span data-ttu-id="30ee7-106">解决方案生成配置中的复选标记**生成**列使您能够构建一个解决方案，并在完成时生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="30ee7-106">A solution build configuration with a check mark in the **Build** column enables you to build a solution and to generate an assembly when you are finished.</span></span> <span data-ttu-id="30ee7-107">如果还中存在一个复选标记，则**部署**列，然后再应用程序将部署基于项目设计器中的部署设置。</span><span class="sxs-lookup"><span data-stu-id="30ee7-107">If a check mark is also present in the **Deploy** column, then the application will be deployed based on deployment settings in the Project Designer.</span></span>  
  
 <span data-ttu-id="30ee7-108">Configuration Manager 和配置的完整参考选项提供通过对话框框中，请参阅以下参考链接： [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)。</span><span class="sxs-lookup"><span data-stu-id="30ee7-108">A complete reference to Configuration Manager and the configuration options provided by the dialog box can be found at the following reference link: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span></span>  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a><span data-ttu-id="30ee7-109">在配置管理器中配置生成属性</span><span class="sxs-lookup"><span data-stu-id="30ee7-109">To configure build properties in Configuration Manager</span></span>  
  
1.  <span data-ttu-id="30ee7-110">在“生成”  菜单上，单击“配置管理器” 。</span><span class="sxs-lookup"><span data-stu-id="30ee7-110">On the **Build** menu, click **Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="30ee7-111">在**Configuration Manager**对话框中，选择下列内容来配置生成属性之一。</span><span class="sxs-lookup"><span data-stu-id="30ee7-111">In the **Configuration Manager** dialog box, select one of following to configure the build properties.</span></span>  
  
    |<span data-ttu-id="30ee7-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="30ee7-112">Use this</span></span>|<span data-ttu-id="30ee7-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="30ee7-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="30ee7-114">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="30ee7-114">**Configuration**</span></span>|<span data-ttu-id="30ee7-115">选择从**版本**或**调试**项目的配置。</span><span class="sxs-lookup"><span data-stu-id="30ee7-115">Choose from **Release** or **Debug** configurations for the project.</span></span> <span data-ttu-id="30ee7-116">另外，创建新配置或编辑现有配置。</span><span class="sxs-lookup"><span data-stu-id="30ee7-116">Alternatively, create a new configuration or edit an existing one.</span></span>|  
    |<span data-ttu-id="30ee7-117">**平台**</span><span class="sxs-lookup"><span data-stu-id="30ee7-117">**Platform**</span></span>|<span data-ttu-id="30ee7-118">为项目选择一个表示已编译程序集 CPU 体系结构的平台。</span><span class="sxs-lookup"><span data-stu-id="30ee7-118">Choose a platform for the project representing the CPU architecture of the compiled assembly.</span></span> <span data-ttu-id="30ee7-119">另外，创建新平台或编辑现有平台。</span><span class="sxs-lookup"><span data-stu-id="30ee7-119">Alternatively, create a new platform or edit an existing one.</span></span>|  
    |<span data-ttu-id="30ee7-120">**生成**</span><span class="sxs-lookup"><span data-stu-id="30ee7-120">**Build**</span></span>|<span data-ttu-id="30ee7-121">为了响应解决方案的构建命令，请为某个项目选中此列中的框，以构建或重新构建项目。</span><span class="sxs-lookup"><span data-stu-id="30ee7-121">Check the box in this column for a project to have the project built or rebuilt in response to a build command for the solution.</span></span>|  
    |<span data-ttu-id="30ee7-122">**部署**</span><span class="sxs-lookup"><span data-stu-id="30ee7-122">**Deploy**</span></span>|<span data-ttu-id="30ee7-123">选中此列中的框，以在针对解决方案或项目发出生成命令时，根据部署设置部署项目。</span><span class="sxs-lookup"><span data-stu-id="30ee7-123">Check the box in this column to have the project deployed based on deployment settings when a build command is issued for the solution or project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30ee7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30ee7-124">See Also</span></span>  
 <span data-ttu-id="30ee7-125">[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="30ee7-125">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="30ee7-126">如何创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="30ee7-126">How to Create BizTalk Projects</span></span>](../core/how-to-create-biztalk-projects.md)