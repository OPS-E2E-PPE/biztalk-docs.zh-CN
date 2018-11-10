---
title: 如何将程序集安装到 GAC 中 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e843d74b5420f8973f9d3663cfd05210c26996
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752362"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a><span data-ttu-id="ff128-102">如何在 GAC 中安装程序集</span><span class="sxs-lookup"><span data-stu-id="ff128-102">How to Install an Assembly in the GAC</span></span>
<span data-ttu-id="ff128-103">手动安装和卸载使用附带的 Gacutil 工具在全局程序集缓存 (GAC) 中的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ff128-103">Manually install and uninstall a BizTalk assembly in the global assembly cache (GAC) using the Gacutil tool included with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ff128-104">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以在 BizTalk 程序集从部署时自动安装在 GAC 中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ff128-104">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can have BizTalk assemblies automatically installed in the GAC when they are deployed from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="ff128-105">BizTalk 项目中; 在部署属性中设置此选项请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="ff128-105">Set this option in the Deployment Properties of the BizTalk project; see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="ff128-106">不能请使用此方法在 GAC 中; 中安装非 BizTalk.NET 程序集必须按本主题中所述手动安装它们。</span><span class="sxs-lookup"><span data-stu-id="ff128-106">You cannot, use this method to install non-BizTalk .NET assemblies in the GAC; you must install them manually, as described in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff128-107">也可以在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将程序集部署到 BizTalk 应用程序之后，再指定程序集的部署选项。</span><span class="sxs-lookup"><span data-stu-id="ff128-107">You can also specify deployment options for assemblies after they are deployed into a BizTalk application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ff128-108">请参阅[如何修改 BizTalk 程序集的部署选项](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)，并[如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)。</span><span class="sxs-lookup"><span data-stu-id="ff128-108">See [How to Modify the Deployment Options of a BizTalk Assembly](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md), and [How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff128-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="ff128-109">Prerequisites</span></span>  
<span data-ttu-id="ff128-110">使用对 GAC 具有写入权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ff128-110">Sign in with an account that has Write permission to the GAC.</span></span> <span data-ttu-id="ff128-111">本地计算机的管理员帐户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="ff128-111">The Administrators account on the local computer has this permission.</span></span>  

  
## <a name="install-using-gacutil"></a><span data-ttu-id="ff128-112">使用 gacutil 安装</span><span class="sxs-lookup"><span data-stu-id="ff128-112">Install using gacutil</span></span>
  
1.  <span data-ttu-id="ff128-113">将 BizTalk 程序集复制到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ff128-113">Copy the BizTalk assembly to your local computer.</span></span>  
  
2.  <span data-ttu-id="ff128-114">打开**Visual Studio 的开发人员命令提示**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="ff128-114">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span>  
  
3.  <span data-ttu-id="ff128-115">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff128-115">Type the following:</span></span>  
  
     `gacutil /i path_to_assembly_file /f`

    <span data-ttu-id="ff128-116">例如，键入：</span><span class="sxs-lookup"><span data-stu-id="ff128-116">For example, type:</span></span>  
    `gacutil /i c:\temp\filename.dll /f`
    
<span data-ttu-id="ff128-117">`/f`选项将覆盖任何现有的程序集都具有相同的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="ff128-117">The `/f` option overwrites any existing assembly that has the same assembly name.</span></span> <span data-ttu-id="ff128-118">有关的 gacutil 命令和选项的详细信息，键入`gacutil /?`。</span><span class="sxs-lookup"><span data-stu-id="ff128-118">For more info on the gacutil commands and options, type `gacutil /?`.</span></span> 

## <a name="uninstall-using-gacutil"></a><span data-ttu-id="ff128-119">使用 gacutil 卸载</span><span class="sxs-lookup"><span data-stu-id="ff128-119">Uninstall using gacutil</span></span>
<span data-ttu-id="ff128-120">卸载程序集从全局程序集缓存 (GAC 中) 有必要完全取消部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="ff128-120">Uninstalling an assembly from the global assembly cache (GAC) is necessary to completely undeploy an application.</span></span> <span data-ttu-id="ff128-121">可以自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="ff128-121">You can automate this process.</span></span> <span data-ttu-id="ff128-122">应用程序部署到生产环境中之前, 编写卸载程序集从 gac 中自动卸载该应用程序时的预处理脚本。</span><span class="sxs-lookup"><span data-stu-id="ff128-122">Before deploying the application into a production environment, write a pre-processing script that uninstalls the assembly from the GAC automatically when the application is uninstalled.</span></span> <span data-ttu-id="ff128-123">请参阅[使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="ff128-123">See [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="ff128-124">此外可以使用脚本来删除其他文件和设置。</span><span class="sxs-lookup"><span data-stu-id="ff128-124">You can also use a script to remove additional files and settings.</span></span> <span data-ttu-id="ff128-125">请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ff128-125">See [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
 
#### <a name="using-the-windows-interface"></a><span data-ttu-id="ff128-126">使用 Windows 介面</span><span class="sxs-lookup"><span data-stu-id="ff128-126">Using the Windows interface</span></span>  
  
1.  <span data-ttu-id="ff128-127">打开到 systemdrive%\Windows\Assembly。</span><span class="sxs-lookup"><span data-stu-id="ff128-127">Open to %systemdrive%\Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="ff128-128">右键单击包含在应用程序中，选择每个程序集文件**卸载**，然后选择**是**以确认。</span><span class="sxs-lookup"><span data-stu-id="ff128-128">Right-click each assembly file included in your application, select **Uninstall**, and then select **Yes** to confirm.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="ff128-129">使用命令行</span><span class="sxs-lookup"><span data-stu-id="ff128-129">Using the command line</span></span>  
  
1.  <span data-ttu-id="ff128-130">打开**Visual Studio 的开发人员命令提示**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="ff128-130">Open **Developer Command Prompt for Visual Studio** as administrator.</span></span> 
  
2.  <span data-ttu-id="ff128-131">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff128-131">Type the following:</span></span>  
  
     <span data-ttu-id="ff128-132">`gacutil /u` \<*完全限定的程序集名称*\></span><span class="sxs-lookup"><span data-stu-id="ff128-132">`gacutil /u` \<*fully qualified assembly name*\></span></span>  
  
     <span data-ttu-id="ff128-133">例如，键入：</span><span class="sxs-lookup"><span data-stu-id="ff128-133">For example, type:</span></span>  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a><span data-ttu-id="ff128-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff128-134">See Also</span></span>  
 [<span data-ttu-id="ff128-135">将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ff128-135">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
<span data-ttu-id="ff128-136">[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ff128-136">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 <span data-ttu-id="ff128-137">[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="ff128-137">[How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="ff128-138">如何从 BizTalk 组中删除 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ff128-138">How to Delete a BizTalk Application from the BizTalk Group</span></span>](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 
