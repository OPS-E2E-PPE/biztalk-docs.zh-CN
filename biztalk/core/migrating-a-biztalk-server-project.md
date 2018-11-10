---
title: 迁移 BizTalk Server 项目 |Microsoft Docs
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
ms.openlocfilehash: b0fd15de7aec81c046ab6b2fc23b6c63a1ec0615
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752701"
---
# <a name="migrating-a-biztalk-server-project"></a><span data-ttu-id="afbcf-102">迁移 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="afbcf-102">Migrating a BizTalk Server Project</span></span>
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="afbcf-103">有关开发的项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用迁移到较新的环境[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换。</span><span class="sxs-lookup"><span data-stu-id="afbcf-103">projects developed for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be migrated to the newer environments by using  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversion.</span></span> <span data-ttu-id="afbcf-104">有关支持的迁移版本的列表，请参阅[支持的升级路径和安装指南](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx)。</span><span class="sxs-lookup"><span data-stu-id="afbcf-104">For a list of the supported migration versions, see [Supported Upgrade Paths and Installation Guides](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx).</span></span>  

## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a><span data-ttu-id="afbcf-105">在运行转换向导之后更改 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="afbcf-105">BizTalk Project Changes After Running the Conversion Wizard</span></span>  
 <span data-ttu-id="afbcf-106">下表显示如何[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]项目配置名称的更改，而其中一些特定的配置属性会重新定位项目之后转换到更新版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="afbcf-106">The following table shows how [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project configuration names change, and where some specific configuration properties relocate after the project is converted to a newer [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="afbcf-107">大部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关的项目设置位于**部署**项目设计器选项卡。</span><span class="sxs-lookup"><span data-stu-id="afbcf-107">Most of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related project settings are located on the **Deployment** tab of Project Designer.</span></span>  


| [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] <span data-ttu-id="afbcf-108">项目</span><span class="sxs-lookup"><span data-stu-id="afbcf-108">project</span></span> | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="afbcf-109">项目</span><span class="sxs-lookup"><span data-stu-id="afbcf-109">project</span></span> |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|             <span data-ttu-id="afbcf-110">**嵌入跟踪信息**输出配置属性</span><span class="sxs-lookup"><span data-stu-id="afbcf-110">**Embed Tracking Information** output configuration property</span></span>             |      <span data-ttu-id="afbcf-111">**定义 TRACE 常数**上生成选项**生成**项目设计器选项卡</span><span class="sxs-lookup"><span data-stu-id="afbcf-111">**Define TRACE constant** build option on the **Build** tab of Project Designer</span></span>       |
|           <span data-ttu-id="afbcf-112">**生成调试信息**输出配置属性</span><span class="sxs-lookup"><span data-stu-id="afbcf-112">**Generate Debugging Information** output configuration property</span></span>           |      <span data-ttu-id="afbcf-113">**定义 DEBUG 常数**上生成选项**生成**项目设计器选项卡</span><span class="sxs-lookup"><span data-stu-id="afbcf-113">**Define DEBUG constant** build option on the **Build** tab of Project Designer</span></span>       |
|              <span data-ttu-id="afbcf-114">**符合 BPEL 规范**代码生成配置属性</span><span class="sxs-lookup"><span data-stu-id="afbcf-114">**BPEL Compliance** code generation configuration property</span></span>              |       <span data-ttu-id="afbcf-115">**符合 BPEL 规范**代码项目属性窗口中的生成属性</span><span class="sxs-lookup"><span data-stu-id="afbcf-115">**BPEL Compliance** code generation property in the project properties window</span></span>        |

> [!NOTE]
>  <span data-ttu-id="afbcf-116">现在 BizTalk 项目有两种生成类型：**发行**并**调试**，它取代了**开发**并**部署**的前面版本。</span><span class="sxs-lookup"><span data-stu-id="afbcf-116">BizTalk projects now have two build types: **Release** and **Debug**, which replaces **Development** and **Deployment** of earlier versions.</span></span> <span data-ttu-id="afbcf-117">但是，您仍然可以看到**开发**并**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="afbcf-117">However, you will continue to see the **Development** and **Deployment** configurations for the projects that are migrated from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].</span></span>  
> 
> [!CAUTION]
>  <span data-ttu-id="afbcf-118">仅\*.btproj 和\*。 由于选择的备份选项在转换期间备份 btproj.user 项目文件。</span><span class="sxs-lookup"><span data-stu-id="afbcf-118">Only the \*.btproj and \*.btproj.user project files are backed up as a result of choosing the back up option during the conversion.</span></span> <span data-ttu-id="afbcf-119">其他文件必须手动备份。</span><span class="sxs-lookup"><span data-stu-id="afbcf-119">Other files must be manually backed up.</span></span>  
> 
> [!CAUTION]
>  <span data-ttu-id="afbcf-120">对自动生成的项目（例如 XSD 和 ODX 文件）的任何自定义都将在转换过程中丢失。</span><span class="sxs-lookup"><span data-stu-id="afbcf-120">Any customizations to auto-generated items such XSD and ODX files will be lost during conversion.</span></span> <span data-ttu-id="afbcf-121">这适用于 web 引用添加到 BizTalk 项目时生成的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="afbcf-121">This applies to XSD files generated when a web reference is added to a BizTalk project as well.</span></span>  

## <a name="project-migration-and-delay-signing"></a><span data-ttu-id="afbcf-122">项目迁移和延迟签名</span><span class="sxs-lookup"><span data-stu-id="afbcf-122">Project Migration and Delay Signing</span></span>  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] <span data-ttu-id="afbcf-123">项目使用[延迟签名](http://go.microsoft.com/fwlink/p/?LinkId=140992)可能会在转换为在生成过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="afbcf-123">projects that use [Delay Signing](http://go.microsoft.com/fwlink/p/?LinkId=140992) may fail during the build process after being converted for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="afbcf-124">如果发生这种情况**生成序列化程序集**已迁移的项目配置未设置为生成设置**关闭**。</span><span class="sxs-lookup"><span data-stu-id="afbcf-124">This can happen if **Generate serialization assembly** build setting for the migrated project configuration is not set to **Off**.</span></span>  

## <a name="project-migration-and-msmqt"></a><span data-ttu-id="afbcf-125">项目迁移和 MSMQT</span><span class="sxs-lookup"><span data-stu-id="afbcf-125">Project Migration and MSMQT</span></span>  
 <span data-ttu-id="afbcf-126">MSMQT 不再是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="afbcf-126">MSMQT is no longer part of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="afbcf-127">这会如何影响项目迁移的详细信息，请参阅主题[MSMQT 弃用](../core/msmqt-deprecation.md)。</span><span class="sxs-lookup"><span data-stu-id="afbcf-127">For more information on how this can affect project migration, see the topic [MSMQT Deprecation](../core/msmqt-deprecation.md).</span></span>  

## <a name="project-conversion-requires-the-project-and-solution-file"></a><span data-ttu-id="afbcf-128">项目转换需要项目和解决方案文件</span><span class="sxs-lookup"><span data-stu-id="afbcf-128">Project Conversion requires the project and solution file</span></span>  
 <span data-ttu-id="afbcf-129">如果您尝试转换 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目但没有解决方案文件，则您将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="afbcf-129">If you attempt to convert a [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project and do not have the solution file you will receive the following error:</span></span>  

 <span data-ttu-id="afbcf-130">**转换项目文件时出错。子元素\<BIZTALK\>元素的\<VisualStudioProject\>无效。**</span><span class="sxs-lookup"><span data-stu-id="afbcf-130">**Error converting project file. Child element \<BIZTALK\> of element \<VisualStudioProject\> is not valid.**</span></span>  

 <span data-ttu-id="afbcf-131">项目转换需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中的解决方案文件 (.sln)。</span><span class="sxs-lookup"><span data-stu-id="afbcf-131">Project conversion requires the solution file (.sln) from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="afbcf-132">如果该解决方案文件不可用，则您必须使用 [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] 创建一个解决方案文件，并将 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目添加到该解决方案。</span><span class="sxs-lookup"><span data-stu-id="afbcf-132">If the solution file is not available, you must create one with [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] and add the [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] project to the solution.</span></span> <span data-ttu-id="afbcf-133">然后运行 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 转换向导。</span><span class="sxs-lookup"><span data-stu-id="afbcf-133">Then run the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversion wizard.</span></span>  

> [!NOTE]
>  <span data-ttu-id="afbcf-134">您可以将项目与 Visual Studio 中使用仅在项目文件 (.btproj) 转换。</span><span class="sxs-lookup"><span data-stu-id="afbcf-134">You may be able to convert the project using only the project file (.btproj) with Visual Studio.</span></span>