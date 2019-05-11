---
title: 如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a516857d6f790dfd1d5f4c7ad51c34144913785b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324585"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a><span data-ttu-id="ded2f-102">如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项</span><span class="sxs-lookup"><span data-stu-id="ded2f-102">How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>
<span data-ttu-id="ded2f-103">本主题介绍如何使用 BizTalk Server 管理控制台来修改以下资源项目的部署选项：</span><span class="sxs-lookup"><span data-stu-id="ded2f-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of the following resource artifacts:</span></span>  
  
- <span data-ttu-id="ded2f-104">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="ded2f-104">.NET assemblies</span></span>  
  
- <span data-ttu-id="ded2f-105">COM 组件</span><span class="sxs-lookup"><span data-stu-id="ded2f-105">COM components</span></span>  
  
- <span data-ttu-id="ded2f-106">特别文件</span><span class="sxs-lookup"><span data-stu-id="ded2f-106">Ad hoc files</span></span>  
  
- <span data-ttu-id="ded2f-107">BAM 项目</span><span class="sxs-lookup"><span data-stu-id="ded2f-107">BAM artifacts</span></span>  
  
  <span data-ttu-id="ded2f-108">你可能想要修改部署属性，以便更改在本地计算机上安装应用程序项目文件将复制到的目标位置。</span><span class="sxs-lookup"><span data-stu-id="ded2f-108">You might want to modify the deployment properties to change the destination location to which the artifact file will be copied when the application is installed on the local computer.</span></span> <span data-ttu-id="ded2f-109">如果未提供路径，该文件将不复制到本地计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="ded2f-109">If you do not provide a path, the file will not be copied to the local computer on installation.</span></span>  
  
  <span data-ttu-id="ded2f-110">此外，你可能想要修改.NET 程序集的以下选项：</span><span class="sxs-lookup"><span data-stu-id="ded2f-110">In addition, you might want to modify the following options for a .NET assembly:</span></span>  
  
- <span data-ttu-id="ded2f-111">**将添加到全局程序集缓存添加资源 (gacutil)。**</span><span class="sxs-lookup"><span data-stu-id="ded2f-111">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="ded2f-112">如果选择此选项，该程序集时将添加到全局程序集缓存 (GAC) 在本地计算机上该程序集添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="ded2f-112">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="ded2f-113">此外，如果您以后刷新该程序集 (右键单击它，然后单击**刷新**)，该程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="ded2f-113">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="ded2f-114">清除此选项的复选框不会删除该程序集从 GAC 中，如果当前存在。</span><span class="sxs-lookup"><span data-stu-id="ded2f-114">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
- <span data-ttu-id="ded2f-115">**将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="ded2f-115">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="ded2f-116">当选中此选项时，如果应用程序导出到.msi 文件，并且该.msi 文件导入到 BizTalk 组，导入过程的一部分在本地计算机上的 GAC 中安装该程序集。</span><span class="sxs-lookup"><span data-stu-id="ded2f-116">When you select this option, if the application is exported to an .msi file, and the .msi file is imported into a BizTalk group, the assembly is installed in the GAC on the local computer as part of the import process.</span></span>  
  
- <span data-ttu-id="ded2f-117">**添加到全局程序集缓存 (gacutil) 安装 MSI 文件。**</span><span class="sxs-lookup"><span data-stu-id="ded2f-117">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="ded2f-118">当选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序时，作为安装过程的一部分在本地计算机上的 GAC 中安装该程序集。</span><span class="sxs-lookup"><span data-stu-id="ded2f-118">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, the assembly is installed in the GAC on the local computer as part of the installation process.</span></span>  
  
- <span data-ttu-id="ded2f-119">**请对 COM 组件可见 (regasm)。**</span><span class="sxs-lookup"><span data-stu-id="ded2f-119">**Make visible to COM components (regasm).**</span></span> <span data-ttu-id="ded2f-120">时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="ded2f-120">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="ded2f-121">如果指定此选项，还必须指定目标中的文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ded2f-121">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
- <span data-ttu-id="ded2f-122">**注册服务组件 (regsvcs)。**</span><span class="sxs-lookup"><span data-stu-id="ded2f-122">**Register serviced components (regsvcs).**</span></span> <span data-ttu-id="ded2f-123">时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM + 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="ded2f-123">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM+ assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="ded2f-124">如果指定此选项，还必须指定目标中的文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ded2f-124">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ded2f-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="ded2f-125">Prerequisites</span></span>  
 <span data-ttu-id="ded2f-126">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ded2f-126">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ded2f-127">此外，如果您选择立即将程序集添加到 GAC 的选项，你的帐户还必须是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="ded2f-127">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="ded2f-128">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ded2f-128">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a><span data-ttu-id="ded2f-129">若要修改资源项目的部署属性</span><span class="sxs-lookup"><span data-stu-id="ded2f-129">To modify the deployment properties of a resource artifact</span></span>  
  
1. <span data-ttu-id="ded2f-130">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ded2f-130">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ded2f-131">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含要修改部署选项，该项目的 BizTalk 组，然后展开包含该项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ded2f-131">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the artifact for which to modify deployment options, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="ded2f-132">单击**资源**文件夹，右键单击该项目，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="ded2f-132">Click the **Resources** folder, right-click the artifact, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="ded2f-133">上**选项**选项卡上，根据需要，修改部署选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ded2f-133">On the **Options** tab, modify the deployment options as necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded2f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ded2f-134">See Also</span></span>  
 [<span data-ttu-id="ded2f-135">管理 .NET 程序集、证书和其他资源</span><span class="sxs-lookup"><span data-stu-id="ded2f-135">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)