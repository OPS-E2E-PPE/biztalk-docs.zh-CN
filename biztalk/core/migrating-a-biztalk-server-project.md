---
title: 迁移 BizTalk Server 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a4dde72-6555-4bf6-b90e-676aa65312ff
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2752203b0498a6cd5a4a8b6df6bc558c444e355
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973459"
---
# <a name="migrating-a-biztalk-server-project"></a><span data-ttu-id="bb226-102">迁移 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="bb226-102">Migrating a BizTalk Server Project</span></span>
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="bb226-103"> 为开发项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可迁移到较新的环境中，通过使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换。</span><span class="sxs-lookup"><span data-stu-id="bb226-103"> projects developed for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be migrated to the newer environments by using  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversion.</span></span> <span data-ttu-id="bb226-104">有关支持的迁移版本的列表，请参阅 [支持升级路径和安装指南](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bb226-104">For a list of the supported migration versions, see [Supported Upgrade Paths and Installation Guides](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx).</span></span>  
  
## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a><span data-ttu-id="bb226-105">BizTalk 项目更改后运行转换向导</span><span class="sxs-lookup"><span data-stu-id="bb226-105">BizTalk Project Changes After Running the Conversion Wizard</span></span>  
 <span data-ttu-id="bb226-106">下表显示如何[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]项目配置名称更改，而其中一些特定的配置属性重新项目后定位到较新转换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="bb226-106">The following table shows how [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project configuration names change, and where some specific configuration properties relocate after the project is converted to a newer [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="bb226-107">大部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关的项目设置位于**部署**项目设计器选项卡。</span><span class="sxs-lookup"><span data-stu-id="bb226-107">Most of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related project settings are located on the **Deployment** tab of Project Designer.</span></span>  
  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]<span data-ttu-id="bb226-108"> 项目</span><span class="sxs-lookup"><span data-stu-id="bb226-108"> project</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bb226-109"> 项目</span><span class="sxs-lookup"><span data-stu-id="bb226-109"> project</span></span>|  
|------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|  
|<span data-ttu-id="bb226-110">**跟踪信息嵌入** 输出配置属性</span><span class="sxs-lookup"><span data-stu-id="bb226-110">**Embed Tracking Information** output configuration property</span></span>|<span data-ttu-id="bb226-111">**定义 TRACE 常数** 生成选项 **生成** 项目设计器选项卡</span><span class="sxs-lookup"><span data-stu-id="bb226-111">**Define TRACE constant** build option on the **Build** tab of Project Designer</span></span>|  
|<span data-ttu-id="bb226-112">**生成调试信息** 输出配置属性</span><span class="sxs-lookup"><span data-stu-id="bb226-112">**Generate Debugging Information** output configuration property</span></span>|<span data-ttu-id="bb226-113">**定义 DEBUG 常数** 生成选项 **生成** 项目设计器选项卡</span><span class="sxs-lookup"><span data-stu-id="bb226-113">**Define DEBUG constant** build option on the **Build** tab of Project Designer</span></span>|  
|<span data-ttu-id="bb226-114">**BPEL 法规遵从性** 代码生成配置属性</span><span class="sxs-lookup"><span data-stu-id="bb226-114">**BPEL Compliance** code generation configuration property</span></span>|<span data-ttu-id="bb226-115">**BPEL 法规遵从性** 代码项目属性窗口中的生成属性</span><span class="sxs-lookup"><span data-stu-id="bb226-115">**BPEL Compliance** code generation property in the project properties window</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bb226-116">BizTalk 项目现在有两个生成类型︰ **版本** 和 **调试**, ，哪些替换 **开发** 和 **部署** 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="bb226-116">BizTalk projects now have two build types: **Release** and **Debug**, which replaces **Development** and **Deployment** of earlier versions.</span></span> <span data-ttu-id="bb226-117">但是，你仍然可以看到**开发**和**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb226-117">However, you will continue to see the **Development** and **Deployment** configurations for the projects that are migrated from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bb226-118">仅 *.btproj 和 \*。 由于选择转换过程中的选项备份备份 btproj.user 项目文件。</span><span class="sxs-lookup"><span data-stu-id="bb226-118">Only the *.btproj and \*.btproj.user project files are backed up as a result of choosing the back up option during the conversion.</span></span> <span data-ttu-id="bb226-119">其他文件必须手动备份。</span><span class="sxs-lookup"><span data-stu-id="bb226-119">Other files must be manually backed up.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bb226-120">对自动生成的项目（例如 XSD 和 ODX 文件）的任何自定义都将在转换过程中丢失。</span><span class="sxs-lookup"><span data-stu-id="bb226-120">Any customizations to auto-generated items such XSD and ODX files will be lost during conversion.</span></span> <span data-ttu-id="bb226-121">这适用于生成的 web 引用添加到 BizTalk 项目时的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="bb226-121">This applies to XSD files generated when a web reference is added to a BizTalk project as well.</span></span>  
  
## <a name="project-migration-and-delay-signing"></a><span data-ttu-id="bb226-122">项目迁移和延迟签名</span><span class="sxs-lookup"><span data-stu-id="bb226-122">Project Migration and Delay Signing</span></span>  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]<span data-ttu-id="bb226-123"> 项目使用[延迟签名](http://go.microsoft.com/fwlink/p/?LinkId=140992)后可能失败并在生成过程中要转换为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb226-123"> projects that use [Delay Signing](http://go.microsoft.com/fwlink/p/?LinkId=140992) may fail during the build process after being converted for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bb226-124">可能的原因是 **生成序列化程序集** 已迁移的项目配置未设置为生成设置 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="bb226-124">This can happen if **Generate serialization assembly** build setting for the migrated project configuration is not set to **Off**.</span></span>  
  
## <a name="project-migration-and-msmqt"></a><span data-ttu-id="bb226-125">项目迁移和 MSMQT</span><span class="sxs-lookup"><span data-stu-id="bb226-125">Project Migration and MSMQT</span></span>  
 <span data-ttu-id="bb226-126">MSMQT 不再是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb226-126">MSMQT is no longer part of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bb226-127">有关如何这可能会影响项目迁移的详细信息，请参阅主题[MSMQT 弃用](../core/msmqt-deprecation.md)。</span><span class="sxs-lookup"><span data-stu-id="bb226-127">For more information on how this can affect project migration, see the topic [MSMQT Deprecation](../core/msmqt-deprecation.md).</span></span>  
  
## <a name="project-conversion-requires-the-project-and-solution-file"></a><span data-ttu-id="bb226-128">项目转换需要项目和解决方案文件</span><span class="sxs-lookup"><span data-stu-id="bb226-128">Project Conversion requires the project and solution file</span></span>  
 <span data-ttu-id="bb226-129">如果您尝试转换 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目但没有解决方案文件，则您将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="bb226-129">If you attempt to convert a [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project and do not have the solution file you will receive the following error:</span></span>  
  
 <span data-ttu-id="bb226-130">**转换项目文件时出错。子元素\<BIZTALK\>元素的\<VisualStudioProject\>无效。**</span><span class="sxs-lookup"><span data-stu-id="bb226-130">**Error converting project file. Child element \<BIZTALK\> of element \<VisualStudioProject\> is not valid.**</span></span>  
  
 <span data-ttu-id="bb226-131">项目转换需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中的解决方案文件 (.sln)。</span><span class="sxs-lookup"><span data-stu-id="bb226-131">Project conversion requires the solution file (.sln) from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="bb226-132">如果该解决方案文件不可用，则您必须使用 [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] 创建一个解决方案文件，并将 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目添加到该解决方案。</span><span class="sxs-lookup"><span data-stu-id="bb226-132">If the solution file is not available, you must create one with [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] and add the [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project to the solution.</span></span> <span data-ttu-id="bb226-133">然后运行 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 转换向导。</span><span class="sxs-lookup"><span data-stu-id="bb226-133">Then run the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversion wizard.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb226-134">你可能能够将转换的项目文件 (.btproj) 仅使用 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="bb226-134">You may be able to convert the project using only the project file (.btproj) with Visual Studio.</span></span>