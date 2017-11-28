---
title: "如何向应用程序添加策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad9eaf1e2f14e51e60ad3f18e31cdaa72fa906a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-policy-to-an-application"></a><span data-ttu-id="90823-102">如何将策略添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="90823-102">How to Add a Policy to an Application</span></span>
<span data-ttu-id="90823-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加策略。</span><span class="sxs-lookup"><span data-stu-id="90823-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a policy to a BizTalk application.</span></span> <span data-ttu-id="90823-104">使用管理控制台时，可以一次添加多个策略。</span><span class="sxs-lookup"><span data-stu-id="90823-104">When using the administration console, you can add more than one policy at a time.</span></span> <span data-ttu-id="90823-105">将策略添加到应用程序后，该策略可供该应用程序以及引用它的任何其他应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="90823-105">Adding a policy to an application makes it available for use by that application as well as any other applications that reference it.</span></span>  
  
 <span data-ttu-id="90823-106">向应用程序中添加策略时，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="90823-106">When adding a policy to an application, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="90823-107">之前可以将策略添加到应用程序，该策略必须存在 BizTalk 组的规则引擎数据库中并且它必须发布中, 所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="90823-107">Before you can add a policy to an application, the policy must exist in the Rule Engine database for the BizTalk group, and it must be published, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90823-108">当使用规则引擎部署向导从规则引擎数据库中删除某个策略时，该策略仍将显示在管理控制台中，但您将无法发布该策略。</span><span class="sxs-lookup"><span data-stu-id="90823-108">When you remove a policy from the Rule Engine database by using the Rule Engine Deployment Wizard, it will still display in the administration console, but, you will not be able to publish it.</span></span> <span data-ttu-id="90823-109">有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="90823-109">For more information about the Rule Engine Deployment Wizard, see [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="90823-110">该策略不能存在于 BizTalk 组的其他应用程序中。</span><span class="sxs-lookup"><span data-stu-id="90823-110">The policy cannot already exist in another application in the BizTalk group.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="90823-111">如果有两个或更多应用程序共享一个策略，应创建一个单独的应用程序以包含此策略，然后创建从使用该策略的应用程序到包含该策略的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="90823-111">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="90823-112">这是因为，如果您停止一个包含策略的应用程序，该策略将自动取消部署，并且不能再为使用它的任何应用程序发挥作用。</span><span class="sxs-lookup"><span data-stu-id="90823-112">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span> <span data-ttu-id="90823-113">有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="90823-113">For instructions on adding a reference, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="90823-114">若要使策略生效并发挥作用，还必须部署此策略。</span><span class="sxs-lookup"><span data-stu-id="90823-114">For the policy to take effect and begin functioning, it must also be deployed.</span></span> <span data-ttu-id="90823-115">策略自动部署应用程序启动时，或者你可以手动将它们部署中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="90823-115">Policies are automatically deployed when the application starts, or you can manually deploy them as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="90823-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="90823-116">Prerequisites</span></span>  
 <span data-ttu-id="90823-117">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="90823-117">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="90823-118">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="90823-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-policy-to-an-application"></a><span data-ttu-id="90823-119">向应用程序添加策略</span><span class="sxs-lookup"><span data-stu-id="90823-119">To add a policy to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="90823-120">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="90823-120">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="90823-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="90823-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="90823-122">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”和“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="90823-122">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="90823-123">展开应用程序，展开你想要添加的策略，然后右键单击该应用的程序**策略**。</span><span class="sxs-lookup"><span data-stu-id="90823-123">Expand Applications, expand the application to which you want to add a policy, and then right-click **Policies**.</span></span>  
  
4.  <span data-ttu-id="90823-124">指向**添加**单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="90823-124">Point to **Add** and click **Policy**.</span></span>  
  
5.  <span data-ttu-id="90823-125">选择的每个策略和版本以添加，然后单击复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="90823-125">Select the check box of each policy and version to add, and then click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="90823-126">使用命令行</span><span class="sxs-lookup"><span data-stu-id="90823-126">Using the command line</span></span>  
  
1.  <span data-ttu-id="90823-127">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="90823-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="90823-128">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="90823-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="90823-129">**BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Rules** [**覆盖**] **Name:***值***/Version:***值*[**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="90823-129">**BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Rules** [**Overwrite**] **/Name:***value***/Version:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90823-130">参数值是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="90823-130">Parameter values are case sensitive.</span></span> <span data-ttu-id="90823-131">参数名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="90823-131">Parameter names are not case sensitive.</span></span> <span data-ttu-id="90823-132">此外，当使用此命令向应用程序添加策略时，还将自动添加该策略使用的所有词汇。</span><span class="sxs-lookup"><span data-stu-id="90823-132">Also, when you add a policy to an application by using this command, any vocabularies used by the policy are automatically added as well.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90823-133">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="90823-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="90823-134">例如：</span><span class="sxs-lookup"><span data-stu-id="90823-134">Example:</span></span>  
  
     <span data-ttu-id="90823-135">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules / 覆盖 /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="90823-135">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="90823-136">参数</span><span class="sxs-lookup"><span data-stu-id="90823-136">Parameter</span></span>|<span data-ttu-id="90823-137">值</span><span class="sxs-lookup"><span data-stu-id="90823-137">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="90823-138">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="90823-138">**/ApplicationName**</span></span>|<span data-ttu-id="90823-139">向其添加策略的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="90823-139">Name of the BizTalk application to which to add the policy.</span></span> <span data-ttu-id="90823-140">如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="90823-140">If the application name is not specified, the default BizTalk application for the group is used.</span></span> <span data-ttu-id="90823-141">包含空格的名称必须括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="90823-141">Names that include spaces must be enclosed in double quotation marks (").</span></span>|  
    |<span data-ttu-id="90823-142">**/ 类型**</span><span class="sxs-lookup"><span data-stu-id="90823-142">**/Type**</span></span>|<span data-ttu-id="90823-143">**System.BizTalk:Rules**</span><span class="sxs-lookup"><span data-stu-id="90823-143">**System.BizTalk:Rules**</span></span>|  
    |<span data-ttu-id="90823-144">**/ 覆盖**</span><span class="sxs-lookup"><span data-stu-id="90823-144">**/Overwrite**</span></span>|<span data-ttu-id="90823-145">更新现有策略的选项。</span><span class="sxs-lookup"><span data-stu-id="90823-145">Option to update an existing policy.</span></span> <span data-ttu-id="90823-146">如果未指定，且应用程序中已经存在与要添加的策略名称相同的策略，则 AddResource 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="90823-146">If not specified, and a policy already exists in the application that has the same name as the policy being added, the AddResource operation fails.</span></span>|  
    |<span data-ttu-id="90823-147">**/ 名称**</span><span class="sxs-lookup"><span data-stu-id="90823-147">**/Name**</span></span>|<span data-ttu-id="90823-148">策略的名称。</span><span class="sxs-lookup"><span data-stu-id="90823-148">Name of the policy.</span></span>|  
    |<span data-ttu-id="90823-149">**/ 版本**</span><span class="sxs-lookup"><span data-stu-id="90823-149">**/Version**</span></span>|<span data-ttu-id="90823-150">策略的版本号。</span><span class="sxs-lookup"><span data-stu-id="90823-150">Version number of the policy.</span></span>|  
    |<span data-ttu-id="90823-151">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="90823-151">**/Server**</span></span>|<span data-ttu-id="90823-152">承载 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="90823-152">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="90823-153">如果指定了“Database”参数，则此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="90823-153">Required if you specify the Database parameter.</span></span> <span data-ttu-id="90823-154">如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="90823-154">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="90823-155">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="90823-155">**/Database**</span></span>|<span data-ttu-id="90823-156">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="90823-156">Name of the BizTalk Management database.</span></span> <span data-ttu-id="90823-157">如果指定了“Server”参数，则此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="90823-157">Required if you specify the Server parameter.</span></span> <span data-ttu-id="90823-158">如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="90823-158">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90823-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90823-159">See Also</span></span>  
 <span data-ttu-id="90823-160">[管理策略](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="90823-160">[Managing Policies](../core/managing-policies.md) </span></span>  
 <span data-ttu-id="90823-161">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="90823-161">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="90823-162">AddResource 命令： 策略</span><span class="sxs-lookup"><span data-stu-id="90823-162">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)