---
title: 如何修改 BizTalk 程序集的部署选项 |Microsoft 文档
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
ms.openlocfilehash: 58365383b1981ae40e87ee23891929bf05c8530e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007750"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="a44d5-102">如何修改 BizTalk 程序集的部署选项</span><span class="sxs-lookup"><span data-stu-id="a44d5-102">How to Modify the Deployment Options of a BizTalk Assembly</span></span>
<span data-ttu-id="a44d5-103">本主题介绍如何使用 BizTalk Server 管理控制台修改 BizTalk 程序集的部署选项。</span><span class="sxs-lookup"><span data-stu-id="a44d5-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of a BizTalk assembly.</span></span>  
  
 <span data-ttu-id="a44d5-104">您可以指定以下部署选项：</span><span class="sxs-lookup"><span data-stu-id="a44d5-104">You can specify the following deployment options:</span></span>  
  
-   <span data-ttu-id="a44d5-105">**将添加到全局程序集缓存在添加资源 (gacutil)。**</span><span class="sxs-lookup"><span data-stu-id="a44d5-105">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="a44d5-106">如果选择此选项，则在将程序集添加到应用程序时，该程序集将添加到本地计算机上的全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="a44d5-106">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="a44d5-107">此外，如果你更高版本刷新程序集 (右键单击它，然后单击**刷新**)，此程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="a44d5-107">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="a44d5-108">清除此选项的复选框并不从 GAC 删除该程序集（如果该程序集当前在 GAC 中存在）。</span><span class="sxs-lookup"><span data-stu-id="a44d5-108">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="a44d5-109">**将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="a44d5-109">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="a44d5-110">导入应用程序 .msi 文件时将程序集安装到本地计算机的 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="a44d5-110">Install the assembly to the GAC on the local computer when the application .msi file is imported.</span></span>  
  
-   <span data-ttu-id="a44d5-111">**将添加到 MSI 文件安装 (gacutil) 上的全局程序集缓存。**</span><span class="sxs-lookup"><span data-stu-id="a44d5-111">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="a44d5-112">从 .msi 文件安装应用程序时将程序集安装到本地计算机的 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="a44d5-112">Install the assembly to the GAC on the local computer when the application is installed from the .msi file.</span></span>  
  
-   <span data-ttu-id="a44d5-113">**目标位置：** 时安装的应用程序，则将复制到此程序集文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a44d5-113">**Destination location:** Path to which the assembly file will be copied when the application is installed.</span></span> <span data-ttu-id="a44d5-114">如果不提供此路径，则在安装过程中，该程序集文件将不会被复制到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="a44d5-114">If a path is not provided, the assembly file is not copied to the local file system on installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a44d5-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="a44d5-115">Prerequisites</span></span>  
 <span data-ttu-id="a44d5-116">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a44d5-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a44d5-117">此外，如果您选择立即将程序集添加到 GAC 中的选项，则您的帐户必须也是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="a44d5-117">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="a44d5-118">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a44d5-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="a44d5-119">修改 BizTalk 程序集的部署选项</span><span class="sxs-lookup"><span data-stu-id="a44d5-119">To modify the deployment options of a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="a44d5-120">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a44d5-120">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a44d5-121">在控制台树中，展开 BizTalk Server 管理，展开包含要修改的部署选项的 BizTalk 程序集的 BizTalk 组，然后展开包含 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a44d5-121">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly for which to modify deployment options, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="a44d5-122">单击**资源**文件夹中，右键单击 BizTalk 程序集，并依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="a44d5-122">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="a44d5-123">在**选项**，选中所需的部署选项的复选框。</span><span class="sxs-lookup"><span data-stu-id="a44d5-123">In **Options**, select the check boxes of the deployment options that you want.</span></span>  
  
5.  <span data-ttu-id="a44d5-124">如有必要，在**目标位置**编辑的路径，其中程序集将安装应用程序时，复制，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a44d5-124">If necessary, in **Destination location** edit the path where the assembly will be copied when the application is installed, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44d5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a44d5-125">See Also</span></span>  
 [<span data-ttu-id="a44d5-126">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="a44d5-126">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)