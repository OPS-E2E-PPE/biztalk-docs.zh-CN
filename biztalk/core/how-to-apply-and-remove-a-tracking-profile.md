---
title: "如何将应用并删除跟踪配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955b2ccddb215b79fd7cdc7d51ed6f5160c297fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a><span data-ttu-id="1b4f3-102">如何应用和删除跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-102">How to Apply and Remove a Tracking Profile</span></span>
<span data-ttu-id="1b4f3-103">创建或修改完跟踪配置文件后，下一步是将其应用到测试数据库并通过集成测试来验证结果。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-103">Once you have created or modified the tracking profile, the next step is to apply it to a test database and verify the result through integration testing.</span></span> <span data-ttu-id="1b4f3-104">可以从跟踪配置文件编辑器 (TPE) 自身内应用跟踪配置文件，也可以使用命令行来应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-104">You can apply the tracking profile from within Tracking Profile Editor (TPE) itself or by using the command line.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b4f3-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-105">Prerequisites</span></span>  
 <span data-ttu-id="1b4f3-106">硬盘上保存有以前创建的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-106">A previously created tracking profile that you saved to your hard drive.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a><span data-ttu-id="1b4f3-107">从 TPE 内应用跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-107">To apply the tracking profile from within the TPE</span></span>  
  
1.  <span data-ttu-id="1b4f3-108">单击**启动**，指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-108">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f3-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="1b4f3-110">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-110">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="1b4f3-111">上**文件**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-111">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="1b4f3-112">导航到硬盘中需要的 .btt 文件。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-112">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="1b4f3-113">单击**打开**加载它。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-113">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="1b4f3-114">上**工具**菜单上，单击**应用跟踪配置文件**将.btt 文件应用到管理数据库设置从**设置管理数据库**上的菜单项**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-114">On the **Tools** menu, click **Apply Tracking Profile** to apply the .btt file to a management database that you have set from the **Set Management Database** menu item on the **Tools** menu.</span></span> <span data-ttu-id="1b4f3-115">通过集成测试验证结果。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-115">Verify the result through integration testing.</span></span>  
  
4.  <span data-ttu-id="1b4f3-116">通知您的组织中负责部署的人员跟踪配置文件测试正确并且已准备好进行部署。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-116">Notify the person in your organization responsible for deployment that the tracking profile tests correctly and is ready for deployment.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a><span data-ttu-id="1b4f3-117">通过命令行应用跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-117">To apply the tracking profile from the command line</span></span>  
  
-   <span data-ttu-id="1b4f3-118">在命令提示符处，运行位于 \Tracking 文件夹中的 bttdeploy.exe 工具，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b4f3-118">From the command prompt, run the bttdeploy.exe tool located in the \Tracking folder as follows:</span></span>  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="1b4f3-119">必须具有 BizTalk 管理员权限才能使用此工具。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-119">You must have BizTalk Administrator privileges to use this tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b4f3-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="1b4f3-121">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b4f3-122">在部署期间，bttdeploy 会验证跟踪配置文件中包含的程序集版本，并将其与已部署的程序集的版本进行比较。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-122">During the deployment, bttdeploy verifies the assembly version contained in the tracking profiles and matches it to the version of the deployed assembly.</span></span> <span data-ttu-id="1b4f3-123">如果当前未部署配置文件中指定的程序集，则 bttdeploy 将失败。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-123">Bttdeploy will fail if the assembly is not currently deployed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b4f3-124">通过命令行应用跟踪配置文件时，bttdeploy 会将跟踪配置文件应用到在运行配置向导时所指定的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-124">When applying a tracking profile from the command line, bttdeploy applies the profile to the BizTalk Management database that you indicated when you ran the configuration wizard.</span></span> <span data-ttu-id="1b4f3-125">如果您在跟踪配置文件编辑器选项“设置管理数据库”中指定了其他数据库设置，则会使用该设置。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-125">If you specify a different database setting in the Tracking Profile Editor Option "Set Management Database," then that setting is used.</span></span> <span data-ttu-id="1b4f3-126">如果将管理服务器和数据库指定为 bttdeploy 的命令行选项，则该命令行选项将覆盖所有其他设置。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-126">If you specify a management server and database as part of the command line option to bttdeploy, then the command line option overrides everything else.</span></span> <span data-ttu-id="1b4f3-127">有关使用 bttdeploy 的详细信息，请参阅[跟踪配置文件部署实用工具](../core/tracking-profile-deployment-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-127">For more information about using bttdeploy, see [Tracking Profile Deployment Utility](../core/tracking-profile-deployment-utility.md).</span></span>  
  
### <a name="to-remove-a-tracking-profile"></a><span data-ttu-id="1b4f3-128">删除跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-128">To remove a tracking profile</span></span>  
  
1.  <span data-ttu-id="1b4f3-129">单击**启动**，指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-129">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f3-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="1b4f3-131">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-131">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="1b4f3-132">上**文件**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-132">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="1b4f3-133">导航到硬盘中需要的 .btt 文件。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-133">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="1b4f3-134">单击**打开**加载它。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-134">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="1b4f3-135">上**工具**菜单上，单击**删除跟踪配置文件**删除基于.btt 文件从 BizTalk 管理数据库的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b4f3-135">On the **Tools** menu, click **Remove Tracking Profile** to remove the tracking profile based on the .btt file from the BizTalk Management database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4f3-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b4f3-136">See Also</span></span>  
 [<span data-ttu-id="1b4f3-137">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b4f3-137">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)