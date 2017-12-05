---
title: "如何部署或取消部署策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d6e7f9f70e6f1f0f09ae1d006172fdc00dc1bc0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="677ed-102">如何部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="677ed-102">How to Deploy or Undeploy a Policy</span></span>
<span data-ttu-id="677ed-103">本主题介绍如何使用 BizTalk Server 管理控制台来部署或手动取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="677ed-103">This topic describes how to use the BizTalk Server Administration console to deploy or undeploy a policy manually.</span></span> <span data-ttu-id="677ed-104">此外，自动启动应用程序部署包含，任何策略，并自动停止应用程序取消部署其策略。</span><span class="sxs-lookup"><span data-stu-id="677ed-104">In addition, starting an application automatically deploys any policies it contains, and stopping an application automatically undeploys its policies.</span></span> <span data-ttu-id="677ed-105">部署策略可将其放到中使用它的应用程序的效果。</span><span class="sxs-lookup"><span data-stu-id="677ed-105">Deploying a policy puts it into effect in the application that uses it.</span></span> <span data-ttu-id="677ed-106">取消部署策略使它处于非活动状态，以便它不再函数中使用 BizTalk 组中任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="677ed-106">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
 <span data-ttu-id="677ed-107">当部署或取消部署策略时，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="677ed-107">When deploying or undeploying a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="677ed-108">你可以部署策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="677ed-108">Before you can deploy a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="677ed-109">如果导入的应用程序包含策略、 策略会自动导入到规则引擎数据库中，你可以显式使用或导入策略到规则引擎数据库的管理控制台或 BTSTask，中所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="677ed-109">If you import an application that contains a policy, the policy is automatically imported into the Rule Engine database, or you can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span> <span data-ttu-id="677ed-110">或者，你可以将策略添加到规则引擎数据库通过使用规则引擎部署向导中中, 所述[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="677ed-110">Alternatively, you can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="677ed-111">你可以部署策略之前，它必须发布中, 所述[如何发布策略](../core/how-to-publish-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="677ed-111">Before you can deploy a policy, it must be published, as described in [How to Publish a Policy](../core/how-to-publish-a-policy.md).</span></span>  
  
-   <span data-ttu-id="677ed-112">无法修改已部署的策略。</span><span class="sxs-lookup"><span data-stu-id="677ed-112">A deployed policy cannot be modified.</span></span> <span data-ttu-id="677ed-113">如果你想要修改已部署的策略，你必须首先取消部署它。</span><span class="sxs-lookup"><span data-stu-id="677ed-113">If you want to modify a deployed policy, you must first undeploy it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="677ed-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="677ed-114">Prerequisites</span></span>  
 <span data-ttu-id="677ed-115">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="677ed-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="677ed-116">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="677ed-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="677ed-117">部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="677ed-117">To deploy or undeploy a policy</span></span>  
  
1.  <span data-ttu-id="677ed-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="677ed-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="677ed-119">在控制台树中，展开**BizTalk Server 管理**，展开包含你想要部署或取消部署，然后展开该策略的 BizTalk 组**\<所有项目\>**.</span><span class="sxs-lookup"><span data-stu-id="677ed-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the policy that you want to deploy or undeploy, and then expand **\<All Artifacts\>**.</span></span>  
  
3.  <span data-ttu-id="677ed-120">单击**策略**，右键单击的策略，然后单击**部署**或**取消部署后再次**。</span><span class="sxs-lookup"><span data-stu-id="677ed-120">Click **Policies**, right-click the policy, and then click **Deploy** or **Undeploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677ed-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="677ed-121">See Also</span></span>  
 <span data-ttu-id="677ed-122">[管理策略](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="677ed-122">[Managing Policies](../core/managing-policies.md) </span></span>  
 [<span data-ttu-id="677ed-123">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="677ed-123">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)