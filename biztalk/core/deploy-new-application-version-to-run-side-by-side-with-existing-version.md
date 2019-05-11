---
title: 如何部署与现有版本运行的并行应用程序的新版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1677c6a5-2c4c-4d70-ab83-f7e0bb3aaf6e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef3e42eef210c9c88e24e1b00c650392f184c8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389642"
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a><span data-ttu-id="20457-102">如何部署与现有版本运行的并行应用程序的新版本</span><span class="sxs-lookup"><span data-stu-id="20457-102">How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version</span></span>
<span data-ttu-id="20457-103">如何部署新版本的应用程序将运行的同时与现有版本。</span><span class="sxs-lookup"><span data-stu-id="20457-103">How to deploy a new version of an application that will run side-by-side with an existing version.</span></span> 

## <a name="overview"></a><span data-ttu-id="20457-104">概述</span><span class="sxs-lookup"><span data-stu-id="20457-104">Overview</span></span>
<span data-ttu-id="20457-105">您可能想要执行此操作以推出升级主要应用程序以增量方式，例如使其可供业务合作伙伴的子集最初，而不是所有合作伙伴在一次。</span><span class="sxs-lookup"><span data-stu-id="20457-105">You might want to do this to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="20457-106">使用此方法使您可以继续运行现有应用程序服务尚未使用新版本直到您就可以完全转换到新版本的用户。</span><span class="sxs-lookup"><span data-stu-id="20457-106">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span> <span data-ttu-id="20457-107">在此方案的背景信息，请参阅[方案：部署应用程序的两个版本](../core/scenario-deploying-two-versions-of-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-107">For background information on this scenario, see [Scenario: Deploying Two Versions of an Application](../core/scenario-deploying-two-versions-of-an-application.md).</span></span>  
  
 <span data-ttu-id="20457-108">不与通过递增版本号创建程序集版本相同的方式来创建应用程序版本。</span><span class="sxs-lookup"><span data-stu-id="20457-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="20457-109">相反，您创建新的应用程序具有不同于原始应用程序的名称，并填充的新版本的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="20457-109">Instead, you create a new application that has a different name than the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="20457-110">因为许多类型的项目，如程序集，可以存在于 BizTalk 组中只有一个应用程序，则必须增加之前可以将它们部署到新的应用程序组中已存在的任何程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="20457-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span> <span data-ttu-id="20457-111">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-111">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="20457-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="20457-112">Prerequisites</span></span>  
<span data-ttu-id="20457-113">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="20457-113">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="20457-114">你的帐户还必须具有本地文件系统和全局程序集缓存的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="20457-114">Your account also must have Read/Write permission on the local file system, and the global assembly cache.</span></span> <span data-ttu-id="20457-115">在本地计算机上的管理员帐户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="20457-115">The Administrators account on the local computer has this permission.</span></span>  

<span data-ttu-id="20457-116">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20457-116">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-a-new-version-of-an-application"></a><span data-ttu-id="20457-117">部署应用程序的新版本</span><span class="sxs-lookup"><span data-stu-id="20457-117">Deploy a new version of an application</span></span>  
  
1. <span data-ttu-id="20457-118">在 Visual Studio 中，对你想要部署到应用程序的新版本的程序集进行任何必要的更改</span><span class="sxs-lookup"><span data-stu-id="20457-118">In Visual Studio, make any necessary changes to the assemblies that you want to deploy into the new version of the application</span></span>  
  
2. <span data-ttu-id="20457-119">每个程序集的版本号递增，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20457-119">Increment the version number of each assembly, as follows:</span></span>  
  
   1.  <span data-ttu-id="20457-120">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**项目启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="20457-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties** to launch Project Designer for the project.</span></span>  
  
   2.  <span data-ttu-id="20457-121">单击**应用程序**未处于活动状态，如果选项卡，然后单击**程序集信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="20457-121">Click the **Application** tab if it is not active, and then click **Assembly Information** button.</span></span>  
  
   3.  <span data-ttu-id="20457-122">增加程序集的版本号，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20457-122">Increase the assembly version number, and then click **OK**.</span></span>  
  
   4.  <span data-ttu-id="20457-123">保存项目。</span><span class="sxs-lookup"><span data-stu-id="20457-123">Save the project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="20457-124">使用管道设计器对象模型以避免架构冲突时递增程序集版本。</span><span class="sxs-lookup"><span data-stu-id="20457-124">Use the Pipeline Designer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
3. <span data-ttu-id="20457-125">在解决方案中的每个项目的部署属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20457-125">In deployment properties for each project in the solution, do the following:</span></span>  
  
   - <span data-ttu-id="20457-126">将应用程序名称更改为你想要使用新的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="20457-126">Change the application name to the name you want to use for the new application.</span></span>  
  
   - <span data-ttu-id="20457-127">确保选择程序集安装在全局程序集缓存 (GAC) 中的选项。</span><span class="sxs-lookup"><span data-stu-id="20457-127">Ensure that the option to install the assemblies in the global assembly cache (GAC) is selected.</span></span>  
  
     <span data-ttu-id="20457-128">有关说明，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-128">For instructions, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="20457-129">在部署解决方案时，将部署到新的应用程序并安装到 GAC 中程序集。</span><span class="sxs-lookup"><span data-stu-id="20457-129">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>  
  
4. <span data-ttu-id="20457-130">部署包含的程序集的解决方案。</span><span class="sxs-lookup"><span data-stu-id="20457-130">Deploy the solution(s) containing the assemblies.</span></span> <span data-ttu-id="20457-131">有关说明，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-131">For instructions, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
5. <span data-ttu-id="20457-132">创建一个新的接收端口和任何所需接收位置，指定您想合作伙伴将消息发送到的新 URL。</span><span class="sxs-lookup"><span data-stu-id="20457-132">Create a new receive port and any needed receive locations specifying the new URL(s) to which you want partners to send messages.</span></span> <span data-ttu-id="20457-133">有关说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-133">For instructions, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span> <span data-ttu-id="20457-134">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-134">Also see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
6. <span data-ttu-id="20457-135">在必要时，创建相应的发送端口，如中所述[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-135">Create the appropriate send ports as necessary, as described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
7. <span data-ttu-id="20457-136">绑定到新创建新的应用程序接收和发送端口，如中所述[如何配置应用程序](../core/how-to-configure-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-136">Bind the new application to the newly created receive and send ports, as described in [How to Configure an Application](../core/how-to-configure-an-application.md).</span></span>  
  
8. <span data-ttu-id="20457-137">从测试环境中，导出到.msi 文件的应用程序，如中所述[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-137">Export the application into an .msi file from your test environment, as described in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="20457-138">您可以使用以下步骤来测试应用程序，以及将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="20457-138">You can use the following steps for testing the application as well as deploying it into your production environment.</span></span> <span data-ttu-id="20457-139">有关开发、 测试、 过渡和生产环境中的应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-139">For more information about application deployment tasks in development, test, staging, and production, see [Application Deployment Tasks](../core/application-deployment-tasks.md).</span></span>  
  
9. <span data-ttu-id="20457-140">应用程序.msi 文件导入生产环境中的 BizTalk 组，如中所述[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-140">Import the application .msi file into the BizTalk group in your production environment, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="20457-141">如果应用程序要求引用，您可以将其添加在使用导入 MSI 向导，或更高版本中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-141">If the application requires references, you can add them while using the Import MSI Wizard, or later as described in [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
10. <span data-ttu-id="20457-142">将运行它，每个主机实例上安装新的应用程序，如中所述[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-142">Install the new application on each host instance that will run it, as described in [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span> <span data-ttu-id="20457-143">验证已托管程序集的每台计算机上的 GAC 中安装每个更新的程序集中。</span><span class="sxs-lookup"><span data-stu-id="20457-143">Verify that each updated assembly has been installed in the GAC on each computer that hosts the assembly.</span></span> <span data-ttu-id="20457-144">如有必要，安装程序集在 GAC 中，如中所述[如何将程序集安装到 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-144">If necessary, install the assemblies in the GAC, as described in [How to Install an Assembly in the GAC](../core/how-to-install-an-assembly-in-the-gac.md).</span></span>  
  
11. <span data-ttu-id="20457-145">执行的完全启动该应用程序，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20457-145">Perform a Full Start of the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
12. <span data-ttu-id="20457-146">通知你的合作伙伴，他们应开始将消息发送到新的 URL。</span><span class="sxs-lookup"><span data-stu-id="20457-146">Notify your partners that they should begin sending messages to the new URLS.</span></span> <span data-ttu-id="20457-147">一旦他们执行此操作，应用程序开始为指定合作伙伴处理消息。</span><span class="sxs-lookup"><span data-stu-id="20457-147">Once they do this, the application begins processing messages for the specified partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20457-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="20457-148">See Also</span></span>  
 [<span data-ttu-id="20457-149">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="20457-149">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)