---
title: 如何部署或取消部署策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a5470c96bfb768528c255325681ce45a9af36c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338499"
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="df391-102">如何部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="df391-102">How to Deploy or Undeploy a Policy</span></span>
<span data-ttu-id="df391-103">本主题介绍如何使用 BizTalk Server 管理控制台来部署或手动取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="df391-103">This topic describes how to use the BizTalk Server Administration console to deploy or undeploy a policy manually.</span></span> <span data-ttu-id="df391-104">此外，自动启动应用程序部署它所包含的任何策略，并停止应用程序会自动取消部署其策略。</span><span class="sxs-lookup"><span data-stu-id="df391-104">In addition, starting an application automatically deploys any policies it contains, and stopping an application automatically undeploys its policies.</span></span> <span data-ttu-id="df391-105">部署策略会将其放在使用它的应用程序中生效。</span><span class="sxs-lookup"><span data-stu-id="df391-105">Deploying a policy puts it into effect in the application that uses it.</span></span> <span data-ttu-id="df391-106">取消部署策略使它处于非活动状态，以便它不再使用 BizTalk 组中的任何应用程序中的函数。</span><span class="sxs-lookup"><span data-stu-id="df391-106">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
 <span data-ttu-id="df391-107">当部署或取消部署策略时，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="df391-107">When deploying or undeploying a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="df391-108">可以部署策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="df391-108">Before you can deploy a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="df391-109">如果导入包含策略的应用程序，该策略将自动导入到规则引擎数据库中，也可以显式导入策略到规则引擎数据库中通过使用管理控制台或 BTSTask，中所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="df391-109">If you import an application that contains a policy, the policy is automatically imported into the Rule Engine database, or you can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span> <span data-ttu-id="df391-110">或者，您可以将策略添加到规则引擎数据库中使用规则引擎部署向导，如中所述[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="df391-110">Alternatively, you can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="df391-111">你可以部署策略之前，必须发布它，如中所述[如何发布策略](../core/how-to-publish-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="df391-111">Before you can deploy a policy, it must be published, as described in [How to Publish a Policy](../core/how-to-publish-a-policy.md).</span></span>  
  
-   <span data-ttu-id="df391-112">不能修改已部署的策略。</span><span class="sxs-lookup"><span data-stu-id="df391-112">A deployed policy cannot be modified.</span></span> <span data-ttu-id="df391-113">如果你想要修改已部署的策略，您必须先取消部署它。</span><span class="sxs-lookup"><span data-stu-id="df391-113">If you want to modify a deployed policy, you must first undeploy it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df391-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="df391-114">Prerequisites</span></span>  
 <span data-ttu-id="df391-115">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="df391-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="df391-116">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="df391-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="df391-117">若要部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="df391-117">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="df391-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="df391-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="df391-119">在控制台树中，展开**BizTalk Server 管理**，展开包含你想要部署或取消部署，然后展开该策略的 BizTalk 组**\<的所有项目\>**.</span><span class="sxs-lookup"><span data-stu-id="df391-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the policy that you want to deploy or undeploy, and then expand **\<All Artifacts\>**.</span></span>  
  
3. <span data-ttu-id="df391-120">单击**策略**，右键单击该策略，然后单击**部署**或**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="df391-120">Click **Policies**, right-click the policy, and then click **Deploy** or **Undeploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df391-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="df391-121">See Also</span></span>  
 <span data-ttu-id="df391-122">[管理策略](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="df391-122">[Managing Policies](../core/managing-policies.md) </span></span>  
 [<span data-ttu-id="df391-123">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="df391-123">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)