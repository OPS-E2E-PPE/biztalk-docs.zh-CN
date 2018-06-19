---
title: 版本控制业务流程管理解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af8afd3666a35b827ff25b243c1bfb4c81262273
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288645"
---
# <a name="versioning-the-business-process-management-solution"></a><span data-ttu-id="2c44a-102">版本控制业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2c44a-102">Versioning the Business Process Management Solution</span></span>
<span data-ttu-id="2c44a-103">业务流程管理解决方案的设计使您可以根据需要替换阶段。</span><span class="sxs-lookup"><span data-stu-id="2c44a-103">The Business Process Management solution is designed so that you can replace stages if necessary.</span></span> <span data-ttu-id="2c44a-104">该设计还提供了架构版本控制的更简易方法。</span><span class="sxs-lookup"><span data-stu-id="2c44a-104">The design also provides for an easier method of versioning schemas.</span></span>  
  
 <span data-ttu-id="2c44a-105">有关将业务流程划分为阶段的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="2c44a-105">For information about dividing a business process into stages, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c44a-106">解决方案的元素高度依赖于消息结构。</span><span class="sxs-lookup"><span data-stu-id="2c44a-106">Elements of the solution are highly dependent on the message structures.</span></span> <span data-ttu-id="2c44a-107">更改消息结构将需要对业务流程进行大量更改。</span><span class="sxs-lookup"><span data-stu-id="2c44a-107">Changing message structures requires substantial changes to the orchestrations.</span></span>  
  
 <span data-ttu-id="2c44a-108">有关更新中部署的解决方案和指引，用于编写脚本的程序集来处理更新的常规说明，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="2c44a-108">For general directions about updating assemblies in a deployed solution and guidelines for writing scripts to handle the update, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
## <a name="adding-replacing-or-removing-stages"></a><span data-ttu-id="2c44a-109">添加、替换或删除阶段</span><span class="sxs-lookup"><span data-stu-id="2c44a-109">Adding, Replacing, or Removing Stages</span></span>  
 <span data-ttu-id="2c44a-110">订单处理阶段业务流程包含两种类型的代码： 实现业务流程和提供的基础结构，以便它可以运行解决方案中的代码的代码。</span><span class="sxs-lookup"><span data-stu-id="2c44a-110">The order processing stage orchestrations contain two kinds of code: code that implements the business process and code that provides the infrastructure so that it can operate in the solution.</span></span> <span data-ttu-id="2c44a-111">在这两个阶段业务流程， **CableOrder1**和**CableOrder2**，业务进程代码组形状内部标记为"业务处理。"</span><span class="sxs-lookup"><span data-stu-id="2c44a-111">In both of the stage orchestrations, **CableOrder1** and **CableOrder2**, the business process code is inside a group shape labeled "Business Processing."</span></span>  
  
 <span data-ttu-id="2c44a-112">创建新阶段最简单的方法是复制其中一个阶段，使用您的代码替换“业务处理”组中的代码，并保留基础结构代码不变。</span><span class="sxs-lookup"><span data-stu-id="2c44a-112">The easiest way to create a new stage is to copy one of the stages, replace the code in the "Business Processing" group with your code, and leave the infrastructure code intact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c44a-113">**CableOrder2** orchestration 具有两个"业务处理"组，第二解决更新历史记录发送形状。</span><span class="sxs-lookup"><span data-stu-id="2c44a-113">The **CableOrder2** orchestration has two "Business Processing" groups, the second around the Update History Send shape.</span></span> <span data-ttu-id="2c44a-114">发送形状是有效发送作用域的组成部分。</span><span class="sxs-lookup"><span data-stu-id="2c44a-114">The Send shape is part of an efficient send scope.</span></span> <span data-ttu-id="2c44a-115">(有关详细信息，请参阅"提高性能与嵌套作用域"中[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。)由于组形状不能与作用域形状的组成部分重叠，因此第二个组被标记，以指示它是业务流程代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="2c44a-115">(For more information, see "Improving Performance with Nested Scopes" in [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).) Because a Group shape cannot overlap part of a scope shape, the second group is labeled to indicate it is part of the business process code.</span></span>  
  
 <span data-ttu-id="2c44a-116">必须按新业务流程在序列中的编号来设置其筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="2c44a-116">You must set the filter expression on the new orchestration to its number in the sequence.</span></span> <span data-ttu-id="2c44a-117">**OrderManager**假定阶段数字开头和增加一个用于每个后续阶段 （1、 2、 3...）。</span><span class="sxs-lookup"><span data-stu-id="2c44a-117">The **OrderManager** assumes stage numbers begin with one and increase by one for each following stage (1, 2, 3 …).</span></span> <span data-ttu-id="2c44a-118">若要筛选第三个阶段，则应将筛选器表达式设置为：</span><span class="sxs-lookup"><span data-stu-id="2c44a-118">To filter for a third stage, you would set the filter expression to the following:</span></span>  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 <span data-ttu-id="2c44a-119">解决方案使用 BAM API 来跟踪解决方案中的事件，包括订单处理阶段。</span><span class="sxs-lookup"><span data-stu-id="2c44a-119">The solution uses the BAM API to track events in the solution, including the order processing stages.</span></span> <span data-ttu-id="2c44a-120">第一个阶段将启动 BAM 活动；最后一个阶段则结束该活动。</span><span class="sxs-lookup"><span data-stu-id="2c44a-120">The first stage starts the BAM activity; the final stage ends it.</span></span> <span data-ttu-id="2c44a-121">如果有异常，则解决方案中的处理程序将结束所涉及的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="2c44a-121">If there exceptions, the handlers in the solution end the BAM activities involved.</span></span> <span data-ttu-id="2c44a-122">BAM 将不连续的操作有效地重新组装成连续的视图，以便进行监视。</span><span class="sxs-lookup"><span data-stu-id="2c44a-122">BAM effectively re-assembles the discontinuous operations into a continuous view for monitoring.</span></span>  
  
## <a name="changing-configuration"></a><span data-ttu-id="2c44a-123">更改配置</span><span class="sxs-lookup"><span data-stu-id="2c44a-123">Changing Configuration</span></span>  
 <span data-ttu-id="2c44a-124">如果所做更改增加或减少了阶段数，则必须更改存储在企业单一登录 (SSO) 密钥存储区中的配置信息。</span><span class="sxs-lookup"><span data-stu-id="2c44a-124">If your changes increase or decrease the number of stages, you must change the configuration information stored in the Enterprise Single Sign-On (SSO) secret store.</span></span>  
  
 <span data-ttu-id="2c44a-125">如果你尚未部署应用程序，则可以修改的配置设置**TotalStages** CreateSouthridgeVideoApplication.cmd 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="2c44a-125">If you haven't deployed the application, you can modify the configuration setting for **TotalStages** in the CreateSouthridgeVideoApplication.cmd script file.</span></span> <span data-ttu-id="2c44a-126">在部署期间运行该脚本时，该值将发生更改。</span><span class="sxs-lookup"><span data-stu-id="2c44a-126">The value will change when the script is run during deployment.</span></span>  
  
 <span data-ttu-id="2c44a-127">如果已经部署应用程序，则可以通过运行命令行实用工具 BTSScnSSOApplicationConfig（位于 SDK\Common\SsoApplicationConfig 文件夹中）来更改值。</span><span class="sxs-lookup"><span data-stu-id="2c44a-127">If you have already deployed the application, you can change value by running a command line utility, BTSScnSSOApplicationConfig, in the SDK\Common\SsoApplicationConfig folder.</span></span> <span data-ttu-id="2c44a-128">若要将阶段的总数设置为三，请使用以下命令行：</span><span class="sxs-lookup"><span data-stu-id="2c44a-128">To set the total number of stages to three, you'd use the following command line:</span></span>  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 <span data-ttu-id="2c44a-129">由于解决方案会缓存配置值，因此必须等到刷新间隔过后，新值才能生效。</span><span class="sxs-lookup"><span data-stu-id="2c44a-129">Because the solution caches the configuration values, you must wait until the  refresh interval passes for the new value to take effect.</span></span>  
  
## <a name="versioning-schemas"></a><span data-ttu-id="2c44a-130">对架构的版本控制</span><span class="sxs-lookup"><span data-stu-id="2c44a-130">Versioning Schemas</span></span>  
 <span data-ttu-id="2c44a-131">BizTalk 从包含它的最新版本的程序集中获取架构。</span><span class="sxs-lookup"><span data-stu-id="2c44a-131">BizTalk takes a schema from the most recent version of the assembly containing it.</span></span> <span data-ttu-id="2c44a-132">这意味着，如果创建新版本的架构，则它会完全替换所有以前版本的架构。</span><span class="sxs-lookup"><span data-stu-id="2c44a-132">This means that if you create a new version of a schema it completely replaces all previous versions of the schema.</span></span> <span data-ttu-id="2c44a-133">此操作在事务寿命很短时能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="2c44a-133">This works well when transactions are short-lived.</span></span> <span data-ttu-id="2c44a-134">但是，业务流程管理解决方案中的事务寿命很长：订单可能需要一年时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="2c44a-134">However, transactions in the Business Process Management solution are long-lived: an order may take up to a year to complete.</span></span>  
  
 <span data-ttu-id="2c44a-135">为了允许使用正在使用的架构的多个版本，解决方案中的每个架构在其命名空间中都包括版本号。</span><span class="sxs-lookup"><span data-stu-id="2c44a-135">To allow for the possibility of using multiple versions of a schema being in use, each schema in the solution includes a version number in its namespace.</span></span> <span data-ttu-id="2c44a-136">例如，订单架构的命名空间如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c44a-136">For example, the namespace for the Order schema is as follows:</span></span>  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 <span data-ttu-id="2c44a-137">由于命名空间标识架构，并且通过包括版本号使命名空间对于架构来说是唯一的，新的架构有别于旧版本。</span><span class="sxs-lookup"><span data-stu-id="2c44a-137">Because the namespace identifies the schema and inclusion of the version number makes the namespace unique to the schema, the new schema will be distinct from the older version.</span></span> <span data-ttu-id="2c44a-138">因此，无需取代旧架构就可以使用新架构。</span><span class="sxs-lookup"><span data-stu-id="2c44a-138">Thus, a new schema can be used without supplanting the old schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c44a-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c44a-139">See Also</span></span>  
 [<span data-ttu-id="2c44a-140">开发一个业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2c44a-140">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)