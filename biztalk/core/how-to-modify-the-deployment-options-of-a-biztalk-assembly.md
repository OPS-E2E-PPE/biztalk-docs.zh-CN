---
title: 如何修改 BizTalk 程序集的部署选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cf808f35d4ce33a2ea821f2bb07bf1b98d0a76d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384556"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="6eca4-102">如何修改 BizTalk 程序集的部署选项</span><span class="sxs-lookup"><span data-stu-id="6eca4-102">How to Modify the Deployment Options of a BizTalk Assembly</span></span>
<span data-ttu-id="6eca4-103">本主题介绍如何使用 BizTalk Server 管理控制台修改 BizTalk 程序集的部署选项。</span><span class="sxs-lookup"><span data-stu-id="6eca4-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of a BizTalk assembly.</span></span>  
  
 <span data-ttu-id="6eca4-104">可以指定以下部署选项：</span><span class="sxs-lookup"><span data-stu-id="6eca4-104">You can specify the following deployment options:</span></span>  
  
-   <span data-ttu-id="6eca4-105">**将添加到全局程序集缓存添加资源 (gacutil)。**</span><span class="sxs-lookup"><span data-stu-id="6eca4-105">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="6eca4-106">如果选择此选项，该程序集时将添加到全局程序集缓存 (GAC) 在本地计算机上该程序集添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="6eca4-106">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="6eca4-107">此外，如果您以后刷新该程序集 (右键单击它，然后单击**刷新**)，该程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="6eca4-107">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="6eca4-108">清除此选项的复选框不会删除该程序集从 GAC 中，如果当前存在。</span><span class="sxs-lookup"><span data-stu-id="6eca4-108">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="6eca4-109">**将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="6eca4-109">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="6eca4-110">导入应用程序.msi 文件时，将程序集安装到本地计算机上的 GAC。</span><span class="sxs-lookup"><span data-stu-id="6eca4-110">Install the assembly to the GAC on the local computer when the application .msi file is imported.</span></span>  
  
-   <span data-ttu-id="6eca4-111">**添加到全局程序集缓存 (gacutil) 安装 MSI 文件。**</span><span class="sxs-lookup"><span data-stu-id="6eca4-111">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="6eca4-112">从.msi 文件安装应用程序时，将程序集安装到本地计算机上的 GAC。</span><span class="sxs-lookup"><span data-stu-id="6eca4-112">Install the assembly to the GAC on the local computer when the application is installed from the .msi file.</span></span>  
  
-   <span data-ttu-id="6eca4-113">**目标位置：** 在安装应用程序的程序集文件将复制到的路径。</span><span class="sxs-lookup"><span data-stu-id="6eca4-113">**Destination location:** Path to which the assembly file will be copied when the application is installed.</span></span> <span data-ttu-id="6eca4-114">如果未提供路径，程序集文件不会复制到本地文件系统上安装。</span><span class="sxs-lookup"><span data-stu-id="6eca4-114">If a path is not provided, the assembly file is not copied to the local file system on installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6eca4-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="6eca4-115">Prerequisites</span></span>  
 <span data-ttu-id="6eca4-116">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="6eca4-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6eca4-117">此外，如果您选择立即将程序集添加到 GAC 的选项，你的帐户还必须是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="6eca4-117">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="6eca4-118">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6eca4-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="6eca4-119">若要修改的 BizTalk 程序集的部署选项</span><span class="sxs-lookup"><span data-stu-id="6eca4-119">To modify the deployment options of a BizTalk assembly</span></span>  
  
1. <span data-ttu-id="6eca4-120">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6eca4-120">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6eca4-121">在控制台树中，依次展开 BizTalk Server 管理、 包含要修改其部署选项的 BizTalk 程序集的 BizTalk 组和包含 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6eca4-121">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly for which to modify deployment options, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="6eca4-122">单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="6eca4-122">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="6eca4-123">在中**选项**，选中所需的部署选项的复选框。</span><span class="sxs-lookup"><span data-stu-id="6eca4-123">In **Options**, select the check boxes of the deployment options that you want.</span></span>  
  
5. <span data-ttu-id="6eca4-124">如果需要，在**目标位置**编辑的路径，该程序集将安装该应用程序时，复制，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6eca4-124">If necessary, in **Destination location** edit the path where the assembly will be copied when the application is installed, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eca4-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6eca4-125">See Also</span></span>  
 [<span data-ttu-id="6eca4-126">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="6eca4-126">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)