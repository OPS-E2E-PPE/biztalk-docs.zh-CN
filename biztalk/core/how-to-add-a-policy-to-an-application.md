---
title: 如何向应用程序添加策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c67abd388f91e18072599e1697bde4acacaee8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387232"
---
# <a name="how-to-add-a-policy-to-an-application"></a><span data-ttu-id="4a6c2-102">如何向应用程序添加策略</span><span class="sxs-lookup"><span data-stu-id="4a6c2-102">How to Add a Policy to an Application</span></span>
<span data-ttu-id="4a6c2-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加策略。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a policy to a BizTalk application.</span></span> <span data-ttu-id="4a6c2-104">使用管理控制台时，可以一次添加多个策略。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-104">When using the administration console, you can add more than one policy at a time.</span></span> <span data-ttu-id="4a6c2-105">将策略添加到应用程序使其可用于使用由该应用程序，以及对其进行引用的任何其他应用程序中。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-105">Adding a policy to an application makes it available for use by that application as well as any other applications that reference it.</span></span>  
  
 <span data-ttu-id="4a6c2-106">当应用程序中添加一个策略，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="4a6c2-106">When adding a policy to an application, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="4a6c2-107">之前可以将策略添加到应用程序，该策略必须存在于 BizTalk 组中，规则引擎数据库中并且必须发布它，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-107">Before you can add a policy to an application, the policy must exist in the Rule Engine database for the BizTalk group, and it must be published, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a6c2-108">当使用规则引擎部署向导从规则引擎数据库中删除策略时，它仍将显示在管理控制台中，但您将无法再将其发布。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-108">When you remove a policy from the Rule Engine database by using the Rule Engine Deployment Wizard, it will still display in the administration console, but, you will not be able to publish it.</span></span> <span data-ttu-id="4a6c2-109">有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-109">For more information about the Rule Engine Deployment Wizard, see [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="4a6c2-110">该策略不能已存在于 BizTalk 组中的另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-110">The policy cannot already exist in another application in the BizTalk group.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4a6c2-111">如果在两个或多个应用程序之间共享一个策略，则应创建单独的应用程序以包含此策略，然后创建从使用策略来包含该策略的应用程序的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-111">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="4a6c2-112">这是因为如果停止包含策略的应用程序，该策略将自动取消部署并不再为任何应用程序使用它的函数。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-112">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span> <span data-ttu-id="4a6c2-113">有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-113">For instructions on adding a reference, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="4a6c2-114">对于策略才会生效并开始正常运行，它还必须部署。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-114">For the policy to take effect and begin functioning, it must also be deployed.</span></span> <span data-ttu-id="4a6c2-115">策略自动部署应用程序启动时，或者你可以手动将它们部署中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-115">Policies are automatically deployed when the application starts, or you can manually deploy them as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a6c2-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="4a6c2-116">Prerequisites</span></span>  
 <span data-ttu-id="4a6c2-117">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-117">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4a6c2-118">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-policy-to-an-application"></a><span data-ttu-id="4a6c2-119">若要将策略添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="4a6c2-119">To add a policy to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="4a6c2-120">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4a6c2-120">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="4a6c2-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4a6c2-122">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]和 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-122">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and the BizTalk group.</span></span>  
  
3. <span data-ttu-id="4a6c2-123">展开应用程序中，展开你想要添加的策略，然后右键单击该应用的程序**策略**。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-123">Expand Applications, expand the application to which you want to add a policy, and then right-click **Policies**.</span></span>  
  
4. <span data-ttu-id="4a6c2-124">指向**外**然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-124">Point to **Add** and click **Policy**.</span></span>  
  
5. <span data-ttu-id="4a6c2-125">选择的每个策略和版本，以添加，然后单击复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-125">Select the check box of each policy and version to add, and then click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="4a6c2-126">使用命令行</span><span class="sxs-lookup"><span data-stu-id="4a6c2-126">Using the command line</span></span>  
  
1. <span data-ttu-id="4a6c2-127">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="4a6c2-128">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="4a6c2-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="4a6c2-129">**BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Rules** [**覆盖**] **/Name:**<em>值</em>**/Version:**<em>值</em>[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="4a6c2-129">**BTSTask AddResource** [**/ApplicationName:**<em>value</em>] **/Type:System.BizTalk:Rules** [**Overwrite**] **/Name:**<em>value</em>**/Version:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4a6c2-130">参数值都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-130">Parameter values are case sensitive.</span></span> <span data-ttu-id="4a6c2-131">参数名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-131">Parameter names are not case sensitive.</span></span> <span data-ttu-id="4a6c2-132">此外，当通过使用此命令可将策略添加到应用程序中，该策略使用的任何词汇自动还将添加。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-132">Also, when you add a policy to an application by using this command, any vocabularies used by the policy are automatically added as well.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4a6c2-133">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
    <span data-ttu-id="4a6c2-134">例如：</span><span class="sxs-lookup"><span data-stu-id="4a6c2-134">Example:</span></span>  
  
    <span data-ttu-id="4a6c2-135">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-135">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="4a6c2-136">参数</span><span class="sxs-lookup"><span data-stu-id="4a6c2-136">Parameter</span></span>|<span data-ttu-id="4a6c2-137">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="4a6c2-137">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="4a6c2-138">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-138">**/ApplicationName**</span></span>|<span data-ttu-id="4a6c2-139">要将策略添加到 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-139">Name of the BizTalk application to which to add the policy.</span></span> <span data-ttu-id="4a6c2-140">如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-140">If the application name is not specified, the default BizTalk application for the group is used.</span></span> <span data-ttu-id="4a6c2-141">包含空格的名称必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-141">Names that include spaces must be enclosed in double quotation marks (").</span></span>|  
   |<span data-ttu-id="4a6c2-142">**/Type**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-142">**/Type**</span></span>|<span data-ttu-id="4a6c2-143">**System.BizTalk:Rules**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-143">**System.BizTalk:Rules**</span></span>|  
   |<span data-ttu-id="4a6c2-144">**/Overwrite**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-144">**/Overwrite**</span></span>|<span data-ttu-id="4a6c2-145">若要更新现有策略的选项。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-145">Option to update an existing policy.</span></span> <span data-ttu-id="4a6c2-146">如果未指定，且策略已存在具有相同的名称作为要添加的策略的应用程序中，则 AddResource 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-146">If not specified, and a policy already exists in the application that has the same name as the policy being added, the AddResource operation fails.</span></span>|  
   |<span data-ttu-id="4a6c2-147">**/Name**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-147">**/Name**</span></span>|<span data-ttu-id="4a6c2-148">策略的名称。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-148">Name of the policy.</span></span>|  
   |<span data-ttu-id="4a6c2-149">**/ 版本**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-149">**/Version**</span></span>|<span data-ttu-id="4a6c2-150">策略的版本号。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-150">Version number of the policy.</span></span>|  
   |<span data-ttu-id="4a6c2-151">**/Server**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-151">**/Server**</span></span>|<span data-ttu-id="4a6c2-152">承载 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-152">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="4a6c2-153">如果指定的 Database 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-153">Required if you specify the Database parameter.</span></span> <span data-ttu-id="4a6c2-154">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-154">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="4a6c2-155">**/Database**</span><span class="sxs-lookup"><span data-stu-id="4a6c2-155">**/Database**</span></span>|<span data-ttu-id="4a6c2-156">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-156">Name of the BizTalk Management database.</span></span> <span data-ttu-id="4a6c2-157">如果指定的 Server 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-157">Required if you specify the Server parameter.</span></span> <span data-ttu-id="4a6c2-158">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="4a6c2-158">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a6c2-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6c2-159">See Also</span></span>  
 <span data-ttu-id="4a6c2-160">[管理策略](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="4a6c2-160">[Managing Policies](../core/managing-policies.md) </span></span>  
 <span data-ttu-id="4a6c2-161">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="4a6c2-161">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="4a6c2-162">AddResource 命令：策略</span><span class="sxs-lookup"><span data-stu-id="4a6c2-162">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)