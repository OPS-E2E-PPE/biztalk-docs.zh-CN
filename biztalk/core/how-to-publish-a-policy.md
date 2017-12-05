---
title: "如何发布策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5e9604e950710911d4324d5b329173d184617b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-publish-a-policy"></a><span data-ttu-id="11158-102">如何发布策略</span><span class="sxs-lookup"><span data-stu-id="11158-102">How to Publish a Policy</span></span>
<span data-ttu-id="11158-103">本主题介绍如何使用 BizTalk Server 管理控制台在 BizTalk 组中发布策略。</span><span class="sxs-lookup"><span data-stu-id="11158-103">This topic describes how to use the BizTalk Server Administration console to publish a policy in a BizTalk group.</span></span> <span data-ttu-id="11158-104">发布策略使它可将添加到 BizTalk 应用程序，如中所述[如何向应用程序添加策略](../core/how-to-add-a-policy-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="11158-104">Publishing a policy makes it available to add to a BizTalk application, as described in [How to Add a Policy to an Application](../core/how-to-add-a-policy-to-an-application.md).</span></span>  
  
 <span data-ttu-id="11158-105">在您可以发布某一策略前，该策略必须存在于 BizTalk 组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="11158-105">Before you can publish a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="11158-106">可以通过以下三种方式将策略导入规则引擎数据库中：</span><span class="sxs-lookup"><span data-stu-id="11158-106">There are three ways to import a policy into the Rule Engine database:</span></span>  
  
-   <span data-ttu-id="11158-107">可以导入包含策略的应用程序。</span><span class="sxs-lookup"><span data-stu-id="11158-107">You can import an application that contains a policy.</span></span> <span data-ttu-id="11158-108">在进行这一导入时，该策略自动导入到规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="11158-108">When you do this, the policy is automatically imported into the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="11158-109">你可以显式导入策略到规则引擎数据库通过使用管理控制台或 BTSTask 中, 所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="11158-109">You can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="11158-110">你可以将策略添加到规则引擎数据库通过使用规则引擎部署向导中中, 所述[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="11158-110">You can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11158-111">尽管可以通过导入的其他策略覆盖某一已发布策略，但如果您指定这一选项，则永远不会覆盖已发布的词汇。</span><span class="sxs-lookup"><span data-stu-id="11158-111">While a published policy can be overwritten by another policy that you import, should you specify this option, a published vocabulary can never be overwritten.</span></span> <span data-ttu-id="11158-112">若要更新某一已发布的词汇，必须从规则引擎数据库中删除它，然后导入新版本。</span><span class="sxs-lookup"><span data-stu-id="11158-112">To update a published vocabulary, you must remove it from the Rule Engine database and then import the new version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11158-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="11158-113">Prerequisites</span></span>  
 <span data-ttu-id="11158-114">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="11158-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="11158-115">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="11158-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-publish-a-policy"></a><span data-ttu-id="11158-116">若要发布策略</span><span class="sxs-lookup"><span data-stu-id="11158-116">To publish a policy</span></span>  
  
1.  <span data-ttu-id="11158-117">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="11158-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="11158-118">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含策略的 BizTalk 组将发布，则展开**应用程序**，然后展开**\<所有项目\>**。</span><span class="sxs-lookup"><span data-stu-id="11158-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the policy to publish, expand **Applications**, and then expand **\<All Artifacts\>**.</span></span>  
  
3.  <span data-ttu-id="11158-119">单击**策略**，右键单击的策略，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="11158-119">Click **Policies**, right-click the policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11158-120">若要发布策略，，由策略引用任何程序集必须安装在全局程序集缓存 (GAC) 的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机在打开之前**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="11158-120">In order to publish a policy, any assemblies that are referenced by the policy must be installed in the Global Assembly Cache (GAC) of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before you open **BizTalk Server Administration**.</span></span> <span data-ttu-id="11158-121">当**BizTalk Server 管理**是打开，维护安装到 GAC 的程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="11158-121">When **BizTalk Server Administration** is opened, it maintains a cache of the assemblies that are installed into the GAC.</span></span> <span data-ttu-id="11158-122">此缓存未更新直到**BizTalk Server 管理**关闭并重新打开。</span><span class="sxs-lookup"><span data-stu-id="11158-122">This cache is not updated until **BizTalk Server Administration** is closed and reopened.</span></span> <span data-ttu-id="11158-123">如果你尝试发布策略并发布将失败，因为被引用程序集未安装在 GAC 中，您必须关闭**BizTalk Server 管理**，将引用的程序集安装到 GAC 中，打开**BizTalk Server 管理**，然后发布该策略。</span><span class="sxs-lookup"><span data-stu-id="11158-123">If you attempt to publish a policy and publication fails because a referenced assembly is not installed in the GAC you must close **BizTalk Server Administration**, install the referenced assembly into the GAC, open **BizTalk Server Administration**, and then publish the policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11158-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11158-124">See Also</span></span>  
 [<span data-ttu-id="11158-125">管理策略</span><span class="sxs-lookup"><span data-stu-id="11158-125">Managing Policies</span></span>](../core/managing-policies.md)