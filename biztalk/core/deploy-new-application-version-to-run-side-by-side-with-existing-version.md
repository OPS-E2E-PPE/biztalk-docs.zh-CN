---
title: 如何部署与现有版本运行的并行应用程序的新版本 |Microsoft 文档
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
ms.openlocfilehash: 053145729546453b959dc35c7901932c1c8690c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241581"
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a><span data-ttu-id="9f671-102">如何将应用程序的新版本部署为与现有版本并行运行</span><span class="sxs-lookup"><span data-stu-id="9f671-102">How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version</span></span>
<span data-ttu-id="9f671-103">如何部署的应用程序将运行并排显示的新版本与现有版本。</span><span class="sxs-lookup"><span data-stu-id="9f671-103">How to deploy a new version of an application that will run side-by-side with an existing version.</span></span> 

## <a name="overview"></a><span data-ttu-id="9f671-104">概述</span><span class="sxs-lookup"><span data-stu-id="9f671-104">Overview</span></span>
<span data-ttu-id="9f671-105">您可能要在以增量方式实施主要应用程序升级时（例如，最初只是使它可用于一部分的业务合作伙伴，而不是一下子就可用于所有合作伙伴），执行此类部署。</span><span class="sxs-lookup"><span data-stu-id="9f671-105">You might want to do this to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="9f671-106">通过使用此方法，您可以继续运行现有应用程序，以便为尚未使用新版本的用户提供服务，直到您已准备就绪，可以完全转换到新版本。</span><span class="sxs-lookup"><span data-stu-id="9f671-106">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span> <span data-ttu-id="9f671-107">在这种情况下的背景信息，请参阅[方案： 部署两个版本的应用程序](../core/scenario-deploying-two-versions-of-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-107">For background information on this scenario, see [Scenario: Deploying Two Versions of an Application](../core/scenario-deploying-two-versions-of-an-application.md).</span></span>  
  
 <span data-ttu-id="9f671-108">您创建应用程序版本的方式与创建程序集版本（通过递增版本号）的方式不同。</span><span class="sxs-lookup"><span data-stu-id="9f671-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="9f671-109">与之相反，您创建与原始应用程序具有不同名称的新应用程序，并且用应用程序项目的新版本填充它。</span><span class="sxs-lookup"><span data-stu-id="9f671-109">Instead, you create a new application that has a different name than the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="9f671-110">因为许多类型的项目（例如程序集）只能存在于 BizTalk 组的一个应用程序中，所以，您必须首先递增已在该组中存在的所有程序集的版本号，然后才能将它们部署到新的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9f671-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span> <span data-ttu-id="9f671-111">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-111">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9f671-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="9f671-112">Prerequisites</span></span>  
<span data-ttu-id="9f671-113">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="9f671-113">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="9f671-114">你的帐户还必须在本地文件系统和全局程序集缓存上的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="9f671-114">Your account also must have Read/Write permission on the local file system, and the global assembly cache.</span></span> <span data-ttu-id="9f671-115">本地计算机的管理员帐户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="9f671-115">The Administrators account on the local computer has this permission.</span></span>  

<span data-ttu-id="9f671-116">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9f671-116">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-a-new-version-of-an-application"></a><span data-ttu-id="9f671-117">部署应用程序的新版本</span><span class="sxs-lookup"><span data-stu-id="9f671-117">Deploy a new version of an application</span></span>  
  
1.  <span data-ttu-id="9f671-118">在 Visual Studio 中，对您要部署到应用程序的新版本中的程序集进行必需的更改。</span><span class="sxs-lookup"><span data-stu-id="9f671-118">In Visual Studio, make any necessary changes to the assemblies that you want to deploy into the new version of the application</span></span>  
  
2.  <span data-ttu-id="9f671-119">按如下所示，递增每个程序集的版本号：</span><span class="sxs-lookup"><span data-stu-id="9f671-119">Increment the version number of each assembly, as follows:</span></span>  
  
    1.  <span data-ttu-id="9f671-120">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="9f671-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties** to launch Project Designer for the project.</span></span>  
  
    2.  <span data-ttu-id="9f671-121">单击**应用程序**如果处于非活动状态，选项卡，然后单击**程序集信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="9f671-121">Click the **Application** tab if it is not active, and then click **Assembly Information** button.</span></span>  
  
    3.  <span data-ttu-id="9f671-122">增加程序集版本号，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="9f671-122">Increase the assembly version number, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="9f671-123">保存项目。</span><span class="sxs-lookup"><span data-stu-id="9f671-123">Save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f671-124">使用管道设计器对象模型以避免架构冲突时递增程序集版本。</span><span class="sxs-lookup"><span data-stu-id="9f671-124">Use the Pipeline Designer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
3.  <span data-ttu-id="9f671-125">在解决方案的每个项目的部署属性中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9f671-125">In deployment properties for each project in the solution, do the following:</span></span>  
  
    -   <span data-ttu-id="9f671-126">将应用程序名称更改为您要用于新应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="9f671-126">Change the application name to the name you want to use for the new application.</span></span>  
  
    -   <span data-ttu-id="9f671-127">确保选择用于在全局程序集缓存 (GAC) 中安装这些程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="9f671-127">Ensure that the option to install the assemblies in the global assembly cache (GAC) is selected.</span></span>  
  
     <span data-ttu-id="9f671-128">有关说明，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-128">For instructions, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="9f671-129">在您部署该解决方案时，这些程序集将部署到新应用程序中并安装在 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="9f671-129">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>  
  
4.  <span data-ttu-id="9f671-130">部署包含程序集的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9f671-130">Deploy the solution(s) containing the assemblies.</span></span> <span data-ttu-id="9f671-131">有关说明，请参阅[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-131">For instructions, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
5.  <span data-ttu-id="9f671-132">创建新的接收端口和所需的任何接收位置，指定您希望合作伙伴将消息发送到的新 URL。</span><span class="sxs-lookup"><span data-stu-id="9f671-132">Create a new receive port and any needed receive locations specifying the new URL(s) to which you want partners to send messages.</span></span> <span data-ttu-id="9f671-133">有关说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-133">For instructions, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span> <span data-ttu-id="9f671-134">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-134">Also see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
6.  <span data-ttu-id="9f671-135">如有必要，创建相应的发送端口中所述[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-135">Create the appropriate send ports as necessary, as described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
7.  <span data-ttu-id="9f671-136">绑定到新创建新的应用程序接收和发送端口中, 所述[如何配置应用程序](../core/how-to-configure-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-136">Bind the new application to the newly created receive and send ports, as described in [How to Configure an Application](../core/how-to-configure-an-application.md).</span></span>  
  
8.  <span data-ttu-id="9f671-137">从测试环境中，导出应用程序置于.msi 文件中所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-137">Export the application into an .msi file from your test environment, as described in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f671-138">您可以使用以下步骤测试应用程序以及将应用程序部署到您的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9f671-138">You can use the following steps for testing the application as well as deploying it into your production environment.</span></span> <span data-ttu-id="9f671-139">有关在开发、 测试、 过渡和生产应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-139">For more information about application deployment tasks in development, test, staging, and production, see [Application Deployment Tasks](../core/application-deployment-tasks.md).</span></span>  
  
9. <span data-ttu-id="9f671-140">将应用程序.msi 文件导入到生产环境中的 BizTalk 组中所述[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-140">Import the application .msi file into the BizTalk group in your production environment, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="9f671-141">如果应用程序需要引用，你可以添加它们时使用导入 MSI 向导，或更高版本中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-141">If the application requires references, you can add them while using the Import MSI Wizard, or later as described in [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
10. <span data-ttu-id="9f671-142">将运行它时，每个主机实例上安装新的应用程序中所述[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-142">Install the new application on each host instance that will run it, as described in [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span> <span data-ttu-id="9f671-143">请确认每个更新的程序集都已安装在作为该程序集宿主的各计算机上的 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="9f671-143">Verify that each updated assembly has been installed in the GAC on each computer that hosts the assembly.</span></span> <span data-ttu-id="9f671-144">如有必要，安装程序集在 GAC 中中, 所述[如何将程序集安装在 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-144">If necessary, install the assemblies in the GAC, as described in [How to Install an Assembly in the GAC](../core/how-to-install-an-assembly-in-the-gac.md).</span></span>  
  
11. <span data-ttu-id="9f671-145">执行完整启动应用程序中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9f671-145">Perform a Full Start of the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
12. <span data-ttu-id="9f671-146">向您的合作伙伴发出通知，指示他们应开始将消息发送到新的 URLS。</span><span class="sxs-lookup"><span data-stu-id="9f671-146">Notify your partners that they should begin sending messages to the new URLS.</span></span> <span data-ttu-id="9f671-147">在他们发送后，应用程序将开始为指定合作伙伴处理消息。</span><span class="sxs-lookup"><span data-stu-id="9f671-147">Once they do this, the application begins processing messages for the specified partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f671-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f671-148">See Also</span></span>  
 [<span data-ttu-id="9f671-149">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="9f671-149">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)