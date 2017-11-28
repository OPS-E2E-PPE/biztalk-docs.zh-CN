---
title: "如何升级业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd9fa8e98b62ec92b1313cc1028efc5320ce17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-upgrade-an-orchestration"></a><span data-ttu-id="76e19-102">如何升级业务流程</span><span class="sxs-lookup"><span data-stu-id="76e19-102">How to Upgrade an Orchestration</span></span>
<span data-ttu-id="76e19-103">如何更新业务流程处理长时间运行的事务或正在等待从请求-响应端口的响应时，生产环境中运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="76e19-103">How to update an orchestration that is running in a production environment when the orchestration handles long-running transactions or is waiting for a response from a solicit-response port.</span></span>

## <a name="overview"></a><span data-ttu-id="76e19-104">概述</span><span class="sxs-lookup"><span data-stu-id="76e19-104">Overview</span></span>
 <span data-ttu-id="76e19-105">在业务流程不处理长时间运行事务时，你可以更新它中所述[清单： 更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-105">When an orchestration does not handle long-running transactions, you can update it as described in [Checklist: Update the Artifacts in a BizTalk Application](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span></span> <span data-ttu-id="76e19-106">但是当某业务流程处理长期事务时，您不能立即转换到该业务流程的已更新版本。</span><span class="sxs-lookup"><span data-stu-id="76e19-106">When an orchestration handles long-running transactions, however, you cannot cut over to the updated version of the orchestration immediately.</span></span> <span data-ttu-id="76e19-107">必须允许原始版本完成其消息的处理，这样才不会丢失消息。</span><span class="sxs-lookup"><span data-stu-id="76e19-107">You must allow the original version to finish processing its messages, so that they are not lost.</span></span> <span data-ttu-id="76e19-108">为此，请将已更新的业务流程与原始版本部署到同一应用程序。</span><span class="sxs-lookup"><span data-stu-id="76e19-108">To accomplish this, you deploy the updated orchestration into the same application as the original one.</span></span> <span data-ttu-id="76e19-109">然后，停止原始版本并启动已更新的版本，以便在先前版本继续处理任何正在处理的消息时可以接收所有新消息。</span><span class="sxs-lookup"><span data-stu-id="76e19-109">You then stop the original version and start the updated version so that it receives all new messages while the previous version continues to process any in-flight messages.</span></span> <span data-ttu-id="76e19-110">在原始业务流程完成其所有消息的处理后，从其部署的 BizTalk 应用程序中取消对它的部署。</span><span class="sxs-lookup"><span data-stu-id="76e19-110">After the original orchestration has finished processing all of its messages, you undeploy it from the BizTalk application in which it was deployed.</span></span>  
  
 <span data-ttu-id="76e19-111">有关此方案的详细信息，请参阅[方案： 更新应用程序项目](../core/scenario-updating-application-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-111">For more information about this scenario, see [Scenario: Updating Application Artifacts](../core/scenario-updating-application-artifacts.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="76e19-112">如果多个业务流程绑定到同一接收端口，并且每个业务流程都已启动或登记，则会向系统引入重复的消息。</span><span class="sxs-lookup"><span data-stu-id="76e19-112">If more than one orchestration is bound to the same receive port, and each orchestration is started or enlisted, you will introduce duplicate messages into the system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76e19-113">在升级到新的业务流程时，由于升级期间旧业务流程和新业务流程之间的争用情况，在任务繁忙时某些业务流程实例可能会成为“已挂起（可恢复）”。</span><span class="sxs-lookup"><span data-stu-id="76e19-113">When upgrading to a new orchestration, some orchestration instances can become Suspended (resumable) under high stress because of the race condition between the old orchestration and the new orchestration during the upgrade.</span></span> <span data-ttu-id="76e19-114">若要手动恢复这些业务流程实例，请参阅[如何恢复挂起的业务流程实例](../core/how-to-resume-suspended-orchestration-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-114">To manually resume these orchestration instances, see [How to Resume Suspended Orchestration Instances](../core/how-to-resume-suspended-orchestration-instances.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76e19-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="76e19-115">Prerequisites</span></span>  
<span data-ttu-id="76e19-116">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="76e19-116">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="76e19-117">你的帐户还必须在本地文件系统和全局程序集缓存上的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="76e19-117">Your account also must have Read/Write permission on the local file system, and the global assembly cache.</span></span> <span data-ttu-id="76e19-118">本地计算机的管理员帐户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="76e19-118">The Administrators account on the local computer has this permission.</span></span>  

<span data-ttu-id="76e19-119">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="76e19-119">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
 
## <a name="update-an-orchestration"></a><span data-ttu-id="76e19-120">更新业务流程</span><span class="sxs-lookup"><span data-stu-id="76e19-120">Update an orchestration</span></span>  
  
1.  <span data-ttu-id="76e19-121">对业务流程进行必要的更改。</span><span class="sxs-lookup"><span data-stu-id="76e19-121">Make the necessary changes to the orchestration.</span></span>  
  
2.  <span data-ttu-id="76e19-122">递增程序集的版本号，如下所示：</span><span class="sxs-lookup"><span data-stu-id="76e19-122">Increment the assembly version number, as follows:</span></span>  
  
    1.  <span data-ttu-id="76e19-123">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="76e19-123">In Solution Explorer, right-click the BizTalk project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
    2.  <span data-ttu-id="76e19-124">单击**应用程序**选项卡上，如果尚未处于活动状态，并依次**程序集信息**。</span><span class="sxs-lookup"><span data-stu-id="76e19-124">Click the **Application** tab if it is not already active, and then click **Assembly Information**.</span></span>  
  
    3.  <span data-ttu-id="76e19-125">在右窗格中，递增程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="76e19-125">In the right pane, increase the assembly version number.</span></span> <span data-ttu-id="76e19-126">应该只递增主版本号或次版本号。</span><span class="sxs-lookup"><span data-stu-id="76e19-126">You should increase only the major or minor version number.</span></span> <span data-ttu-id="76e19-127">主版本号是序列中的第一个数字 (**0**.0.0.0); 的次版本号是序列中的第二个数字 (0。**0**.0.0)。</span><span class="sxs-lookup"><span data-stu-id="76e19-127">The major version number is the first digit in the sequence (**0**.0.0.0); the minor version number is the second digit in the sequence (0.**0**.0.0).</span></span> <span data-ttu-id="76e19-128">BizTalk Server 将无法识别序列，如 0.0 中更高版本的版本编号更改。**0**.0 或 0.0.0。**0**。</span><span class="sxs-lookup"><span data-stu-id="76e19-128">BizTalk Server will not recognize a version number change that is later in the sequence, such as 0.0.**0**.0 or 0.0.0.**0**.</span></span>  
  
    4.  <span data-ttu-id="76e19-129">单击**确定**关闭**程序集信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="76e19-129">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
    5.  <span data-ttu-id="76e19-130">保存项目。</span><span class="sxs-lookup"><span data-stu-id="76e19-130">Save the project.</span></span>  
  
3.  <span data-ttu-id="76e19-131">将程序集从 Visual Studio 部署到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="76e19-131">Deploy the assembly from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="76e19-132">有关说明，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-132">For instructions, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span> <span data-ttu-id="76e19-133">确保选择部署选项以在 GAC 中安装程序集。</span><span class="sxs-lookup"><span data-stu-id="76e19-133">Make sure you select the deployment option to install the assembly in the GAC.</span></span>  
  
4.  <span data-ttu-id="76e19-134">测试包含业务流程的程序集。</span><span class="sxs-lookup"><span data-stu-id="76e19-134">Test the assembly containing the orchestration.</span></span>  
  
5.  <span data-ttu-id="76e19-135">将程序集导出到.msi 文件，测试环境中的应用程序从中, 所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-135">Export the assembly from the application in your test environment into an .msi file, as described in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76e19-136">您可以使用以下步骤测试程序集并将程序集部署到您的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="76e19-136">You can use the following steps for testing the assembly as well as deploying it into your production environment.</span></span> <span data-ttu-id="76e19-137">有关在开发、 测试、 过渡和生产应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-137">For more information about application deployment tasks in development, test, staging, and production, see [Application Deployment Tasks](../core/application-deployment-tasks.md).</span></span>  
  
6.  <span data-ttu-id="76e19-138">导入生产环境中包含你想要更新中, 所述的业务流程的 BizTalk 应用程序的.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-138">Import the .msi file into the BizTalk application in your production environment that contains the orchestration that you want to update, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
7.  <span data-ttu-id="76e19-139">绑定更新业务流程作为原始业务流程，使用相同的绑定中所述[如何将绑定配置为业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-139">Bind the updated orchestration using the same bindings as the original orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
8.  <span data-ttu-id="76e19-140">取消登记原始业务流程，然后启动已更新的业务流程。</span><span class="sxs-lookup"><span data-stu-id="76e19-140">Unenlist the original orchestration, and then start the updated orchestration.</span></span> <span data-ttu-id="76e19-141">若要避免任何已删除的消息，你应执行此操作以编程方式中, 所述[部署和启动新版本的业务流程以编程方式](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-141">To avoid any dropped messages, you should do this programmatically, as described in [Deploying and Starting a New Version of an Orchestration Programmatically](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md).</span></span> <span data-ttu-id="76e19-142">或者，可以执行这些步骤中所述手动[如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)，[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)，和[如何启动 Orchestration](../core/how-to-start-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="76e19-142">Alternatively, you can perform these steps manually, as described in [How to Unenlist an Orchestration](../core/how-to-unenlist-an-orchestration.md), [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md), and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
9. <span data-ttu-id="76e19-143">监视的系统中所述，使用组中心数据库的原始 orchestration 版本的实例页上查询视图[如何查看实例信息为业务流程](../core/how-to-view-instance-information-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-143">Monitor the system for instances of the original orchestration version using the Group Hub page query view, as described in [How to View Instance Information for an Orchestration](../core/how-to-view-instance-information-for-an-orchestration.md).</span></span>  
  
10. <span data-ttu-id="76e19-144">完成所有活动、 已冻结，和挂起实例后，取消部署该应用程序，从原始的业务流程中所述[如何从应用程序删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="76e19-144">When all of its active, dehydrated, and suspended instances are complete, undeploy the original orchestration from the application, as described in [How to Remove an Orchestration from an Application](../core/how-to-remove-an-orchestration-from-an-application.md).</span></span>  
  
11. <span data-ttu-id="76e19-145">根据需要从运行该应用程序，每台计算机上的 GAC 卸载原始程序集版本中所述[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。</span><span class="sxs-lookup"><span data-stu-id="76e19-145">Optionally uninstall the original assembly version from the GAC on each computer running the application, as described in [How to Uninstall an Assembly from the GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e19-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76e19-146">See Also</span></span>  
 <span data-ttu-id="76e19-147">[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="76e19-147">[Updating BizTalk Applications](../core/updating-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="76e19-148">管理业务流程</span><span class="sxs-lookup"><span data-stu-id="76e19-148">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)