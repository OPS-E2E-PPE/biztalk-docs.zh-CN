---
title: 管理策略 |Microsoft Docs
description: 快速链接以便在导入，发布、 添加、 部署、 删除或导出 BizTalk Server 中的策略
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99c3dbc60bde3fdf82dc44a68e34345d3225b92c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380274"
---
# <a name="manage-policies"></a><span data-ttu-id="7c30c-103">管理策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-103">Manage policies</span></span>

## <a name="overview"></a><span data-ttu-id="7c30c-104">概述</span><span class="sxs-lookup"><span data-stu-id="7c30c-104">Overview</span></span>
<span data-ttu-id="7c30c-105">在本部分中的主题提供有关使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理策略的说明。</span><span class="sxs-lookup"><span data-stu-id="7c30c-105">The topics in this section provide instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage policies.</span></span> <span data-ttu-id="7c30c-106">策略是业务规则的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="7c30c-106">A policy is a logical grouping of business rules.</span></span> <span data-ttu-id="7c30c-107">有关策略的背景信息，请参阅[策略](../core/policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7c30c-107">For background information on policies, see [Policies](../core/policies.md).</span></span>  
  
## <a name="import-publish-deploy-and-remove-policies"></a><span data-ttu-id="7c30c-108">导入、 发布、 部署和删除策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-108">Import, publish, deploy, and remove policies</span></span>
 <span data-ttu-id="7c30c-109">解决方案开发人员可以创建和使用业务规则编辑器中，查看策略，如中所述[使用业务规则编辑器创建业务规则](../core/creating-business-rules-using-the-business-rule-composer.md)。</span><span class="sxs-lookup"><span data-stu-id="7c30c-109">Solution developers can create and view policies by using the Business Rule Composer, as described in [Creating Business Rules Using the Business Rule Composer](../core/creating-business-rules-using-the-business-rule-composer.md).</span></span> <span data-ttu-id="7c30c-110">然后，开发人员和 IT 管理员可以执行以下任务，在本部分中，若要部署和管理 BizTalk 组和应用程序中的策略中的主题中所述：</span><span class="sxs-lookup"><span data-stu-id="7c30c-110">Developers and IT administrators can then perform the following tasks, which are described in the topics in this section, to deploy and manage policies in a BizTalk group and application:</span></span>  
  
-   <span data-ttu-id="7c30c-111">**将策略导入 BizTalk 组。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-111">**Import the policy into a BizTalk group.**</span></span> <span data-ttu-id="7c30c-112">执行此操作时，策略添加到组的规则引擎数据库和 BizTalk Server 管理控制台中显示\<的所有项目\>BizTalk 组节点。</span><span class="sxs-lookup"><span data-stu-id="7c30c-112">When you do this, the policy is added to the Rule Engine database for the group and displays in the BizTalk Server Administration console in the \<All Artifacts\> node for the BizTalk group.</span></span> <span data-ttu-id="7c30c-113">这不会使策略生效的任何特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="7c30c-113">This does not put the policy into effect for any particular application.</span></span> <span data-ttu-id="7c30c-114">必须先发布策略，将其添加到应用程序，并部署它，如本部分中的其他主题中所述。</span><span class="sxs-lookup"><span data-stu-id="7c30c-114">You must first publish the policy, add it to an application, and then deploy it, as described in other topics in this section.</span></span> <span data-ttu-id="7c30c-115">规则引擎数据库是包含所有 BizTalk 组中的策略的数据库。</span><span class="sxs-lookup"><span data-stu-id="7c30c-115">The Rule Engine database is a database that contains all of the policies in a BizTalk group.</span></span>  
  
-   <span data-ttu-id="7c30c-116">**发布策略。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-116">**Publish a policy.**</span></span> <span data-ttu-id="7c30c-117">这使得可以在 BizTalk 应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="7c30c-117">This makes it available to use in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="7c30c-118">**将策略添加到 BizTalk 应用程序。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-118">**Add a policy to a BizTalk application.**</span></span> <span data-ttu-id="7c30c-119">这允许应用程序使用策略，但不会使策略生效。</span><span class="sxs-lookup"><span data-stu-id="7c30c-119">This allows the application to use the policy, but does not put the policy into effect.</span></span> <span data-ttu-id="7c30c-120">在部署时，该策略将生效。</span><span class="sxs-lookup"><span data-stu-id="7c30c-120">The policy takes effect when it is deployed.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7c30c-121">如果在两个或多个应用程序之间共享一个策略，则应创建单独的应用程序以包含此策略，然后创建从使用策略来包含该策略的应用程序的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="7c30c-121">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="7c30c-122">这是因为如果停止包含策略的应用程序，该策略将自动取消部署并不再为任何应用程序使用它的函数。</span><span class="sxs-lookup"><span data-stu-id="7c30c-122">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span>  
  
-   <span data-ttu-id="7c30c-123">**部署策略。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-123">**Deploy a policy.**</span></span> <span data-ttu-id="7c30c-124">执行此操作会将其放到操作。</span><span class="sxs-lookup"><span data-stu-id="7c30c-124">Doing this puts it into operation.</span></span> <span data-ttu-id="7c30c-125">（这类似于启动业务流程。）可以部署和手动取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="7c30c-125">(This is similar to starting an orchestration.) You can deploy and undeploy a policy manually.</span></span> <span data-ttu-id="7c30c-126">此外，当启动应用程序时，会自动部署其策略，并且其策略应用程序停止时，会自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="7c30c-126">In addition, when an application is started, its policies are automatically deployed, and when an application is stopped, its policies are automatically undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c30c-127">一旦部署了策略，可以再修改。</span><span class="sxs-lookup"><span data-stu-id="7c30c-127">Once a policy is deployed, it can no longer be modified.</span></span> <span data-ttu-id="7c30c-128">如果你想要修改已部署的策略，必须取消部署它，或通过使用业务规则编辑器重新创建对象并为其提供新的版本号。</span><span class="sxs-lookup"><span data-stu-id="7c30c-128">If you want to modify a deployed policy, you must either undeploy it, or recreate it by using the Business Rule Composer and give it a new version number.</span></span>  
  
-   <span data-ttu-id="7c30c-129">**从 BizTalk 应用程序和 BizTalk 组中删除策略。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-129">**Remove a policy from a BizTalk application and the BizTalk group.**</span></span> <span data-ttu-id="7c30c-130">这将取消部署策略，并将其删除应用程序和组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="7c30c-130">This undeploys the policy and removes it from the application as well as the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="7c30c-131">**导出策略。**</span><span class="sxs-lookup"><span data-stu-id="7c30c-131">**Export the policy.**</span></span> <span data-ttu-id="7c30c-132">然后，可以将其导入其他 BizTalk 组进行使用。</span><span class="sxs-lookup"><span data-stu-id="7c30c-132">You can then import it into a different BizTalk group to use there.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c30c-133">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c30c-133">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="7c30c-134">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="7c30c-134">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7c30c-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7c30c-135">Next steps</span></span>
  
-   [<span data-ttu-id="7c30c-136">导入策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-136">Import a Policy</span></span>](../core/how-to-import-a-policy.md)  
  
-   [<span data-ttu-id="7c30c-137">发布策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-137">Publish a Policy</span></span>](../core/how-to-publish-a-policy.md)  
  
-   [<span data-ttu-id="7c30c-138">向应用程序添加策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-138">Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="7c30c-139">部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-139">Deploy or Undeploy a Policy</span></span>](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [<span data-ttu-id="7c30c-140">为策略配置跟踪</span><span class="sxs-lookup"><span data-stu-id="7c30c-140">Configure Tracking for a Policy</span></span>](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [<span data-ttu-id="7c30c-141">从应用程序和 BizTalk 组中删除策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-141">Remove a Policy from an Application and the BizTalk Group</span></span>](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [<span data-ttu-id="7c30c-142">导出策略</span><span class="sxs-lookup"><span data-stu-id="7c30c-142">Export a Policy</span></span>](../core/how-to-export-a-policy.md)