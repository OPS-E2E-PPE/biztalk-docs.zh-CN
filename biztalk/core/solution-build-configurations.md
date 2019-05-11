---
title: 解决方案生成配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e67898e3e24b98f9efbe92494e0f7fbe28b2fba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244323"
---
# <a name="solution-build-configurations"></a><span data-ttu-id="65504-102">解决方案生成配置</span><span class="sxs-lookup"><span data-stu-id="65504-102">Solution Build Configurations</span></span>
<span data-ttu-id="65504-103">与您在生成其他项目一样[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以使用配置管理器来指定解决方案生成配置。</span><span class="sxs-lookup"><span data-stu-id="65504-103">As with other projects that you build in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can use Configuration Manager to specify solution build configurations.</span></span> <span data-ttu-id="65504-104">解决方案生成配置，可以确定解决方案的生成中包含的项目中，如果将部署它们。</span><span class="sxs-lookup"><span data-stu-id="65504-104">Solution build configurations enable you to determine which projects to include in builds of a solution and if they will be deployed.</span></span> <span data-ttu-id="65504-105">BizTalk Server 同时支持两者**调试**并**发行**生成配置。</span><span class="sxs-lookup"><span data-stu-id="65504-105">BizTalk Server supports both **Debug** and **Release** build configurations.</span></span>  
  
 <span data-ttu-id="65504-106">一种解决方案生成配置中的复选标记**生成**列，您可以构建解决方案，并在完成时生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="65504-106">A solution build configuration with a check mark in the **Build** column enables you to build a solution and to generate an assembly when you are finished.</span></span> <span data-ttu-id="65504-107">如果一个复选标记还处在**部署**列，然后再应用程序将部署根据项目设计器中的部署设置。</span><span class="sxs-lookup"><span data-stu-id="65504-107">If a check mark is also present in the **Deploy** column, then the application will be deployed based on deployment settings in the Project Designer.</span></span>  
  
 <span data-ttu-id="65504-108">配置管理器和配置的完整参考资料选项提供由对话框框中，请参阅以下参考链接： [ http://go.microsoft.com/fwlink/?LinkId=125365 ](http://go.microsoft.com/fwlink/?LinkId=125365)。</span><span class="sxs-lookup"><span data-stu-id="65504-108">A complete reference to Configuration Manager and the configuration options provided by the dialog box can be found at the following reference link: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span></span>  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a><span data-ttu-id="65504-109">若要配置 Configuration Manager 中的生成属性</span><span class="sxs-lookup"><span data-stu-id="65504-109">To configure build properties in Configuration Manager</span></span>  
  
1.  <span data-ttu-id="65504-110">在“生成”  菜单上，单击“配置管理器” 。</span><span class="sxs-lookup"><span data-stu-id="65504-110">On the **Build** menu, click **Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="65504-111">在中**Configuration Manager**对话框中，选择以下操作来配置生成属性之一。</span><span class="sxs-lookup"><span data-stu-id="65504-111">In the **Configuration Manager** dialog box, select one of following to configure the build properties.</span></span>  
  
    |<span data-ttu-id="65504-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="65504-112">Use this</span></span>|<span data-ttu-id="65504-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="65504-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="65504-114">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="65504-114">**Configuration**</span></span>|<span data-ttu-id="65504-115">选择从**发行**或**调试**项目配置。</span><span class="sxs-lookup"><span data-stu-id="65504-115">Choose from **Release** or **Debug** configurations for the project.</span></span> <span data-ttu-id="65504-116">或者，创建新的配置或编辑现有。</span><span class="sxs-lookup"><span data-stu-id="65504-116">Alternatively, create a new configuration or edit an existing one.</span></span>|  
    |<span data-ttu-id="65504-117">**平台**</span><span class="sxs-lookup"><span data-stu-id="65504-117">**Platform**</span></span>|<span data-ttu-id="65504-118">选择一个平台，用于表示已编译的程序集的 CPU 体系结构的项目。</span><span class="sxs-lookup"><span data-stu-id="65504-118">Choose a platform for the project representing the CPU architecture of the compiled assembly.</span></span> <span data-ttu-id="65504-119">或者，创建一个新的平台或编辑现有。</span><span class="sxs-lookup"><span data-stu-id="65504-119">Alternatively, create a new platform or edit an existing one.</span></span>|  
    |<span data-ttu-id="65504-120">**生成**</span><span class="sxs-lookup"><span data-stu-id="65504-120">**Build**</span></span>|<span data-ttu-id="65504-121">检查项目的项目生成或重新生成解决方案的构建命令的响应中此列中的框。</span><span class="sxs-lookup"><span data-stu-id="65504-121">Check the box in this column for a project to have the project built or rebuilt in response to a build command for the solution.</span></span>|  
    |<span data-ttu-id="65504-122">**部署**</span><span class="sxs-lookup"><span data-stu-id="65504-122">**Deploy**</span></span>|<span data-ttu-id="65504-123">检查此列可以具有部署的项目中的框的解决方案或项目发出生成命令时根据部署设置。</span><span class="sxs-lookup"><span data-stu-id="65504-123">Check the box in this column to have the project deployed based on deployment settings when a build command is issued for the solution or project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65504-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="65504-124">See Also</span></span>  
 <span data-ttu-id="65504-125">[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="65504-125">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="65504-126">如何创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="65504-126">How to Create BizTalk Projects</span></span>](../core/how-to-create-biztalk-projects.md)