---
title: 如何将应用和删除跟踪配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e98745e48edc1dea194e33bb8ac3cde9a70d8b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387202"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a><span data-ttu-id="c2f73-102">如何将应用和删除跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c2f73-102">How to Apply and Remove a Tracking Profile</span></span>
<span data-ttu-id="c2f73-103">创建或修改跟踪配置文件后下, 一步是将其应用到测试数据库并验证通过集成测试的结果。</span><span class="sxs-lookup"><span data-stu-id="c2f73-103">Once you have created or modified the tracking profile, the next step is to apply it to a test database and verify the result through integration testing.</span></span> <span data-ttu-id="c2f73-104">您可以应用跟踪配置文件与在跟踪配置文件编辑器 (TPE) 自身或使用命令行。</span><span class="sxs-lookup"><span data-stu-id="c2f73-104">You can apply the tracking profile from within Tracking Profile Editor (TPE) itself or by using the command line.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c2f73-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="c2f73-105">Prerequisites</span></span>  
 <span data-ttu-id="c2f73-106">以前创建的跟踪配置文件保存到您的硬盘。</span><span class="sxs-lookup"><span data-stu-id="c2f73-106">A previously created tracking profile that you saved to your hard drive.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a><span data-ttu-id="c2f73-107">若要将跟踪配置文件从 TPE 内应用</span><span class="sxs-lookup"><span data-stu-id="c2f73-107">To apply the tracking profile from within the TPE</span></span>  
  
1. <span data-ttu-id="c2f73-108">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-108">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c2f73-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c2f73-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c2f73-110">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-110">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="c2f73-111">上**文件**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-111">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="c2f73-112">导航到你硬盘上的.btt 文件。</span><span class="sxs-lookup"><span data-stu-id="c2f73-112">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="c2f73-113">单击**打开**加载它。</span><span class="sxs-lookup"><span data-stu-id="c2f73-113">Click **Open** to load it.</span></span>  
  
3. <span data-ttu-id="c2f73-114">上**工具**菜单上，单击**应用跟踪配置文件**将该.btt 文件应用于已从设置管理数据库**设置管理数据库**上的菜单项**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="c2f73-114">On the **Tools** menu, click **Apply Tracking Profile** to apply the .btt file to a management database that you have set from the **Set Management Database** menu item on the **Tools** menu.</span></span> <span data-ttu-id="c2f73-115">验证通过集成测试的结果。</span><span class="sxs-lookup"><span data-stu-id="c2f73-115">Verify the result through integration testing.</span></span>  
  
4. <span data-ttu-id="c2f73-116">通知的人员负责部署在组织中的跟踪配置文件测试正确并且已准备好进行部署。</span><span class="sxs-lookup"><span data-stu-id="c2f73-116">Notify the person in your organization responsible for deployment that the tracking profile tests correctly and is ready for deployment.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a><span data-ttu-id="c2f73-117">若要从命令行应用跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c2f73-117">To apply the tracking profile from the command line</span></span>  
  
-   <span data-ttu-id="c2f73-118">从命令提示符处，运行位于 \Tracking 文件夹中，如下所示的 bttdeploy.exe 工具：</span><span class="sxs-lookup"><span data-stu-id="c2f73-118">From the command prompt, run the bttdeploy.exe tool located in the \Tracking folder as follows:</span></span>  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="c2f73-119">必须具有 BizTalk 管理员权限才能使用此工具。</span><span class="sxs-lookup"><span data-stu-id="c2f73-119">You must have BizTalk Administrator privileges to use this tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2f73-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c2f73-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c2f73-121">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c2f73-122">在部署期间，bttdeploy 验证跟踪配置文件中包含的程序集版本，并其与已部署的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="c2f73-122">During the deployment, bttdeploy verifies the assembly version contained in the tracking profiles and matches it to the version of the deployed assembly.</span></span> <span data-ttu-id="c2f73-123">如果当前未部署该程序集，则 Bttdeploy 将失败。</span><span class="sxs-lookup"><span data-stu-id="c2f73-123">Bttdeploy will fail if the assembly is not currently deployed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c2f73-124">当从命令行应用跟踪配置文件，bttdeploy 将适用于运行配置向导时所指定的 BizTalk 管理数据库配置文件。</span><span class="sxs-lookup"><span data-stu-id="c2f73-124">When applying a tracking profile from the command line, bttdeploy applies the profile to the BizTalk Management database that you indicated when you ran the configuration wizard.</span></span> <span data-ttu-id="c2f73-125">如果在跟踪配置文件编辑器选项中指定了其他数据库设置为使用"设置管理数据库"，然后该设置。</span><span class="sxs-lookup"><span data-stu-id="c2f73-125">If you specify a different database setting in the Tracking Profile Editor Option "Set Management Database," then that setting is used.</span></span> <span data-ttu-id="c2f73-126">如果您指定为 bttdeploy 的命令行选项的一部分的管理服务器和数据库，然后在命令行选项将覆盖所有其他。</span><span class="sxs-lookup"><span data-stu-id="c2f73-126">If you specify a management server and database as part of the command line option to bttdeploy, then the command line option overrides everything else.</span></span> <span data-ttu-id="c2f73-127">有关使用 bttdeploy 的详细信息，请参阅[跟踪配置文件部署实用程序](../core/tracking-profile-deployment-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f73-127">For more information about using bttdeploy, see [Tracking Profile Deployment Utility](../core/tracking-profile-deployment-utility.md).</span></span>  
  
### <a name="to-remove-a-tracking-profile"></a><span data-ttu-id="c2f73-128">若要删除的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c2f73-128">To remove a tracking profile</span></span>  
  
1. <span data-ttu-id="c2f73-129">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-129">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c2f73-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c2f73-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c2f73-131">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-131">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="c2f73-132">上**文件**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c2f73-132">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="c2f73-133">导航到你硬盘上的.btt 文件。</span><span class="sxs-lookup"><span data-stu-id="c2f73-133">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="c2f73-134">单击**打开**加载它。</span><span class="sxs-lookup"><span data-stu-id="c2f73-134">Click **Open** to load it.</span></span>  
  
3. <span data-ttu-id="c2f73-135">上**工具**菜单上，单击**删除跟踪配置文件**删除跟踪配置文件基于该.btt 文件从 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="c2f73-135">On the **Tools** menu, click **Remove Tracking Profile** to remove the tracking profile based on the .btt file from the BizTalk Management database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f73-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2f73-136">See Also</span></span>  
 [<span data-ttu-id="c2f73-137">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c2f73-137">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)