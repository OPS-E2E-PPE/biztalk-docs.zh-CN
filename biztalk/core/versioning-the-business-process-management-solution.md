---
title: 版本控制业务流程管理解决方案 |Microsoft Docs
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
ms.openlocfilehash: 4f3b030ed67745e37b9808d888a5f0df07e57bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393748"
---
# <a name="versioning-the-business-process-management-solution"></a><span data-ttu-id="d1adc-102">版本控制业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="d1adc-102">Versioning the Business Process Management Solution</span></span>
<span data-ttu-id="d1adc-103">设计业务流程管理解决方案是使您可以根据需要替换阶段。</span><span class="sxs-lookup"><span data-stu-id="d1adc-103">The Business Process Management solution is designed so that you can replace stages if necessary.</span></span> <span data-ttu-id="d1adc-104">设计还提供了更简单的方法的架构版本控制。</span><span class="sxs-lookup"><span data-stu-id="d1adc-104">The design also provides for an easier method of versioning schemas.</span></span>  
  
 <span data-ttu-id="d1adc-105">有关将业务流程划分成阶段的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="d1adc-105">For information about dividing a business process into stages, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1adc-106">该解决方案中的元素都高度依赖于消息结构。</span><span class="sxs-lookup"><span data-stu-id="d1adc-106">Elements of the solution are highly dependent on the message structures.</span></span> <span data-ttu-id="d1adc-107">更改消息结构需要向业务流程的重大更改。</span><span class="sxs-lookup"><span data-stu-id="d1adc-107">Changing message structures requires substantial changes to the orchestrations.</span></span>  
  
 <span data-ttu-id="d1adc-108">有关更新已部署的解决方案和编写脚本的指南中的程序集来处理更新的常规说明，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="d1adc-108">For general directions about updating assemblies in a deployed solution and guidelines for writing scripts to handle the update, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
## <a name="adding-replacing-or-removing-stages"></a><span data-ttu-id="d1adc-109">添加、 替换或删除阶段</span><span class="sxs-lookup"><span data-stu-id="d1adc-109">Adding, Replacing, or Removing Stages</span></span>  
 <span data-ttu-id="d1adc-110">订单处理阶段业务流程包含两种类型的代码： 代码实现的业务流程和提供的基础结构，以便它可以在解决方案中进行操作的代码。</span><span class="sxs-lookup"><span data-stu-id="d1adc-110">The order processing stage orchestrations contain two kinds of code: code that implements the business process and code that provides the infrastructure so that it can operate in the solution.</span></span> <span data-ttu-id="d1adc-111">在这两个阶段业务流程**CableOrder1**并**CableOrder2**，业务流程代码组形状内标记为"业务处理"。</span><span class="sxs-lookup"><span data-stu-id="d1adc-111">In both of the stage orchestrations, **CableOrder1** and **CableOrder2**, the business process code is inside a group shape labeled "Business Processing."</span></span>  
  
 <span data-ttu-id="d1adc-112">若要创建新的阶段的最简单方法是复制其中一个阶段，在"业务处理"组中的代码替换为你的代码，并保留基础结构代码保持不变。</span><span class="sxs-lookup"><span data-stu-id="d1adc-112">The easiest way to create a new stage is to copy one of the stages, replace the code in the "Business Processing" group with your code, and leave the infrastructure code intact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1adc-113">**CableOrder2**业务流程具有两个"业务处理"组，第二个围绕更新历史发送形状。</span><span class="sxs-lookup"><span data-stu-id="d1adc-113">The **CableOrder2** orchestration has two "Business Processing" groups, the second around the Update History Send shape.</span></span> <span data-ttu-id="d1adc-114">发送形状是有效发送作用域的一部分。</span><span class="sxs-lookup"><span data-stu-id="d1adc-114">The Send shape is part of an efficient send scope.</span></span> <span data-ttu-id="d1adc-115">(详细信息，请参阅"使用嵌套作用域提高性能"中[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。)组形状不能重叠作用域形状的一部分，因为第二个组被标记，以指示它是业务流程代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="d1adc-115">(For more information, see "Improving Performance with Nested Scopes" in [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).) Because a Group shape cannot overlap part of a scope shape, the second group is labeled to indicate it is part of the business process code.</span></span>  
  
 <span data-ttu-id="d1adc-116">必须为它的数字序列中新的业务流程上设置筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="d1adc-116">You must set the filter expression on the new orchestration to its number in the sequence.</span></span> <span data-ttu-id="d1adc-117">**OrderManager**假定阶段编号一开始，并增加另一个用于每个后续阶段 （1、 2、 3...）。</span><span class="sxs-lookup"><span data-stu-id="d1adc-117">The **OrderManager** assumes stage numbers begin with one and increase by one for each following stage (1, 2, 3 …).</span></span> <span data-ttu-id="d1adc-118">若要筛选的第三个阶段，将设置为以下筛选器表达式：</span><span class="sxs-lookup"><span data-stu-id="d1adc-118">To filter for a third stage, you would set the filter expression to the following:</span></span>  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 <span data-ttu-id="d1adc-119">该解决方案使用 BAM API 来跟踪解决方案，包括订单处理阶段中的事件。</span><span class="sxs-lookup"><span data-stu-id="d1adc-119">The solution uses the BAM API to track events in the solution, including the order processing stages.</span></span> <span data-ttu-id="d1adc-120">第一个阶段将启动 BAM 活动中;最后一个阶段则结束。</span><span class="sxs-lookup"><span data-stu-id="d1adc-120">The first stage starts the BAM activity; the final stage ends it.</span></span> <span data-ttu-id="d1adc-121">如果那里异常，该解决方案中的处理程序结束所涉及的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="d1adc-121">If there exceptions, the handlers in the solution end the BAM activities involved.</span></span> <span data-ttu-id="d1adc-122">BAM 有效地重新组装成连续的视图用于监视不连续的操作。</span><span class="sxs-lookup"><span data-stu-id="d1adc-122">BAM effectively re-assembles the discontinuous operations into a continuous view for monitoring.</span></span>  
  
## <a name="changing-configuration"></a><span data-ttu-id="d1adc-123">更改配置</span><span class="sxs-lookup"><span data-stu-id="d1adc-123">Changing Configuration</span></span>  
 <span data-ttu-id="d1adc-124">如果所做的更改增加或减少阶段数，则必须更改存储在企业单一登录 (SSO) 密钥存储区中的配置信息。</span><span class="sxs-lookup"><span data-stu-id="d1adc-124">If your changes increase or decrease the number of stages, you must change the configuration information stored in the Enterprise Single Sign-On (SSO) secret store.</span></span>  
  
 <span data-ttu-id="d1adc-125">如果尚未部署应用程序，则可以修改的配置设置**TotalStages** CreateSouthridgeVideoApplication.cmd 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="d1adc-125">If you haven't deployed the application, you can modify the configuration setting for **TotalStages** in the CreateSouthridgeVideoApplication.cmd script file.</span></span> <span data-ttu-id="d1adc-126">在部署期间运行该脚本时，会更改值。</span><span class="sxs-lookup"><span data-stu-id="d1adc-126">The value will change when the script is run during deployment.</span></span>  
  
 <span data-ttu-id="d1adc-127">如果你已部署应用程序，您可以通过在位于 SDK\Common\SsoApplicationConfig 文件夹中运行命令行实用工具 BTSScnSSOApplicationConfig，更改值。</span><span class="sxs-lookup"><span data-stu-id="d1adc-127">If you have already deployed the application, you can change value by running a command line utility, BTSScnSSOApplicationConfig, in the SDK\Common\SsoApplicationConfig folder.</span></span> <span data-ttu-id="d1adc-128">若要设置为三个阶段的总数目，将使用以下命令行：</span><span class="sxs-lookup"><span data-stu-id="d1adc-128">To set the total number of stages to three, you'd use the following command line:</span></span>  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 <span data-ttu-id="d1adc-129">由于解决方案会缓存配置值，你必须等待，直到刷新间隔过后才会生效的新值。</span><span class="sxs-lookup"><span data-stu-id="d1adc-129">Because the solution caches the configuration values, you must wait until the  refresh interval passes for the new value to take effect.</span></span>  
  
## <a name="versioning-schemas"></a><span data-ttu-id="d1adc-130">架构版本控制</span><span class="sxs-lookup"><span data-stu-id="d1adc-130">Versioning Schemas</span></span>  
 <span data-ttu-id="d1adc-131">BizTalk 需要来自包含它的程序集的最新版本的架构。</span><span class="sxs-lookup"><span data-stu-id="d1adc-131">BizTalk takes a schema from the most recent version of the assembly containing it.</span></span> <span data-ttu-id="d1adc-132">这意味着，如果创建新架构版本完全替换所有以前版本的架构。</span><span class="sxs-lookup"><span data-stu-id="d1adc-132">This means that if you create a new version of a schema it completely replaces all previous versions of the schema.</span></span> <span data-ttu-id="d1adc-133">这适用于事务的生存期较短。</span><span class="sxs-lookup"><span data-stu-id="d1adc-133">This works well when transactions are short-lived.</span></span> <span data-ttu-id="d1adc-134">但是，业务流程管理解决方案中的事务寿命很长： 订单可能需要一年时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="d1adc-134">However, transactions in the Business Process Management solution are long-lived: an order may take up to a year to complete.</span></span>  
  
 <span data-ttu-id="d1adc-135">若要允许使用正在使用的架构的多个版本的可能性，解决方案中的每个架构包括其命名空间中的版本号。</span><span class="sxs-lookup"><span data-stu-id="d1adc-135">To allow for the possibility of using multiple versions of a schema being in use, each schema in the solution includes a version number in its namespace.</span></span> <span data-ttu-id="d1adc-136">例如，订单架构的命名空间是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1adc-136">For example, the namespace for the Order schema is as follows:</span></span>  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 <span data-ttu-id="d1adc-137">命名空间标识架构和版本号使包含唯一的架构的命名空间，因为新的架构将是不同于较旧版本。</span><span class="sxs-lookup"><span data-stu-id="d1adc-137">Because the namespace identifies the schema and inclusion of the version number makes the namespace unique to the schema, the new schema will be distinct from the older version.</span></span> <span data-ttu-id="d1adc-138">因此，新的架构可以使用而无需取代旧架构。</span><span class="sxs-lookup"><span data-stu-id="d1adc-138">Thus, a new schema can be used without supplanting the old schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1adc-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1adc-139">See Also</span></span>  
 [<span data-ttu-id="d1adc-140">开发业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="d1adc-140">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)