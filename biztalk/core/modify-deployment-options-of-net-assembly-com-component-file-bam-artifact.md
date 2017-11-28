---
title: "如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6469f06b7b42ae1f8b45419fa0214682bd9fa67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a><span data-ttu-id="3dd46-102">如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项</span><span class="sxs-lookup"><span data-stu-id="3dd46-102">How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>
<span data-ttu-id="3dd46-103">本主题将介绍如何使用 BizTalk Server 管理控制台修改以下资源项目的部署选项：</span><span class="sxs-lookup"><span data-stu-id="3dd46-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of the following resource artifacts:</span></span>  
  
-   <span data-ttu-id="3dd46-104">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="3dd46-104">.NET assemblies</span></span>  
  
-   <span data-ttu-id="3dd46-105">COM 组件</span><span class="sxs-lookup"><span data-stu-id="3dd46-105">COM components</span></span>  
  
-   <span data-ttu-id="3dd46-106">特别文件</span><span class="sxs-lookup"><span data-stu-id="3dd46-106">Ad hoc files</span></span>  
  
-   <span data-ttu-id="3dd46-107">BAM 项目</span><span class="sxs-lookup"><span data-stu-id="3dd46-107">BAM artifacts</span></span>  
  
 <span data-ttu-id="3dd46-108">您可能要修改部署属性，以便更改在本地计算机上安装应用程序时项目文件将复制到的目标位置。</span><span class="sxs-lookup"><span data-stu-id="3dd46-108">You might want to modify the deployment properties to change the destination location to which the artifact file will be copied when the application is installed on the local computer.</span></span> <span data-ttu-id="3dd46-109">如果未提供路径，则在安装时该文件将不会复制到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3dd46-109">If you do not provide a path, the file will not be copied to the local computer on installation.</span></span>  
  
 <span data-ttu-id="3dd46-110">此外，您可能要修改 .NET 程序集的以下选项：</span><span class="sxs-lookup"><span data-stu-id="3dd46-110">In addition, you might want to modify the following options for a .NET assembly:</span></span>  
  
-   <span data-ttu-id="3dd46-111">**将添加到全局程序集缓存在添加资源 (gacutil)。**</span><span class="sxs-lookup"><span data-stu-id="3dd46-111">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="3dd46-112">如果选择此选项，则在将程序集添加到应用程序时，该程序集将添加到本地计算机上的全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="3dd46-112">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="3dd46-113">此外，如果你更高版本刷新程序集 (右键单击它，然后单击**刷新**)，此程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="3dd46-113">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="3dd46-114">清除此选项的复选框并不从 GAC 删除该程序集（如果该程序集当前在 GAC 中存在）。</span><span class="sxs-lookup"><span data-stu-id="3dd46-114">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="3dd46-115">**将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="3dd46-115">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="3dd46-116">如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后该 .msi 文件导入到 BizTalk 组时，程序集将作为导入过程的一部分安装到本地计算机上的 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="3dd46-116">When you select this option, if the application is exported to an .msi file, and the .msi file is imported into a BizTalk group, the assembly is installed in the GAC on the local computer as part of the import process.</span></span>  
  
-   <span data-ttu-id="3dd46-117">**将添加到 MSI 文件安装 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="3dd46-117">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="3dd46-118">如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后应用程序根据该 .msi 文件安装到某一计算机时，程序集将作为安装过程的一部分安装到本地计算机上的 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="3dd46-118">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, the assembly is installed in the GAC on the local computer as part of the installation process.</span></span>  
  
-   <span data-ttu-id="3dd46-119">**使对 COM 组件 (regasm) 可见。**</span><span class="sxs-lookup"><span data-stu-id="3dd46-119">**Make visible to COM components (regasm).**</span></span> <span data-ttu-id="3dd46-120">在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="3dd46-120">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="3dd46-121">如果您指定该选项，则还必须为目标中的文件指定位置。</span><span class="sxs-lookup"><span data-stu-id="3dd46-121">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
-   <span data-ttu-id="3dd46-122">**提供服务的注册组件 (regsvcs)。**</span><span class="sxs-lookup"><span data-stu-id="3dd46-122">**Register serviced components (regsvcs).**</span></span> <span data-ttu-id="3dd46-123">在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM+ 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="3dd46-123">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM+ assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="3dd46-124">如果您指定该选项，则还必须为目标中的文件指定位置。</span><span class="sxs-lookup"><span data-stu-id="3dd46-124">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3dd46-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="3dd46-125">Prerequisites</span></span>  
 <span data-ttu-id="3dd46-126">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3dd46-126">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3dd46-127">此外，如果您选择立即将程序集添加到 GAC 中的选项，则您的帐户必须也是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="3dd46-127">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="3dd46-128">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd46-128">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a><span data-ttu-id="3dd46-129">修改资源项目的部署属性</span><span class="sxs-lookup"><span data-stu-id="3dd46-129">To modify the deployment properties of a resource artifact</span></span>  
  
1.  <span data-ttu-id="3dd46-130">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3dd46-130">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3dd46-131">在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、包含要修改其部署选项的项目的 BizTalk 组，以及包含该项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3dd46-131">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the artifact for which to modify deployment options, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="3dd46-132">单击**资源**文件夹，右键单击该项目，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="3dd46-132">Click the **Resources** folder, right-click the artifact, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="3dd46-133">上**选项**选项卡上，根据需要，修改的部署选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3dd46-133">On the **Options** tab, modify the deployment options as necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd46-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd46-134">See Also</span></span>  
 [<span data-ttu-id="3dd46-135">管理.NET 程序集、 证书和其他资源</span><span class="sxs-lookup"><span data-stu-id="3dd46-135">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)