---
title: 方案：更新应用程序项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c144fcafd0800f5ac41fe1b0572f60ac895ff536
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308107"
---
# <a name="scenario-updating-application-artifacts"></a><span data-ttu-id="cf1d4-102">方案：更新应用程序项目</span><span class="sxs-lookup"><span data-stu-id="cf1d4-102">Scenario: Updating Application Artifacts</span></span>
<span data-ttu-id="cf1d4-103">有更新的应用程序部署到生产环境中项目的两种基本方案：</span><span class="sxs-lookup"><span data-stu-id="cf1d4-103">There are two basic scenarios for updating the artifacts in an application that has been deployed into a production environment:</span></span>  
  
- <span data-ttu-id="cf1d4-104">当业务流程处理长期事务或正在等待来自要求-响应端口的响应时使用新版本更新业务流程。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-104">Updating an orchestration with a new version when the orchestration handles long-running transactions or is waiting for a response from a solicit-response port.</span></span>  
  
- <span data-ttu-id="cf1d4-105">更多常规更新的情况下，当您不关心完成消息处理，如更新架构或映射使用新版本。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-105">The more general update case, when you are not concerned with completing message processing, such as updating a schema or map with a new version.</span></span>  
  
  <span data-ttu-id="cf1d4-106">在一般性的更新情况下，你可能正在更新项目使用新版本，例如为了满足业务要求的更改。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-106">In the general update case, you may be updating an artifact with a new version, for example to address a change in business requirements.</span></span> <span data-ttu-id="cf1d4-107">相对简单，这种情况下，您可以用更新后项目覆盖原始项目。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-107">This scenario is relatively straightforward, and you can overwrite the original artifact with the updated one.</span></span> <span data-ttu-id="cf1d4-108">有关所涉及的步骤的列表，请参阅[核对清单：更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-108">For a list of the steps involved, see [Checklist: Update the Artifacts in a BizTalk Application](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="cf1d4-109">第二个方案是更复杂。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-109">The second scenario is more complex.</span></span> <span data-ttu-id="cf1d4-110">在这种情况下，必须允许现有业务流程完成处理消息。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-110">In this case, you must allow the existing orchestration to finish processing the messages.</span></span> <span data-ttu-id="cf1d4-111">在同一时间，则必须防止现有的业务流程处理任何新消息。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-111">At the same time, you must prevent the existing orchestration from processing any new messages.</span></span> <span data-ttu-id="cf1d4-112">相反，您希望的更新的版本的业务流程进行处理。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-112">Instead, you want the updated version of the orchestration to take over.</span></span> <span data-ttu-id="cf1d4-113">若要实现此目的，您部署包含到与原始版本相同的 BizTalk 应用程序已更新的业务流程的程序集，然后同时运行这两个业务流程。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-113">To accomplish this, you deploy the assembly containing the updated orchestration into the same BizTalk application as the original version, and then run both orchestrations simultaneously.</span></span> <span data-ttu-id="cf1d4-114">（新的程序集必须具有不同的版本号比包含原始业务流程的程序集或你将无法再将它部署到同一个 BizTalk 组。）然后，停止原始业务流程，以便没有新消息路由到它，并启动更新的版本中，以便所有新消息发送给它。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-114">(The new assembly must have a different version number than the assembly containing the original orchestration, or you will not be able to deploy it into the same BizTalk group.) You then stop the original orchestration, so that no new messages are routed to it, and start the updated version, so that all new messages are sent to it.</span></span> <span data-ttu-id="cf1d4-115">原始版本完成其所有消息的处理后，你可以然后取消部署它。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-115">After the original version has finished processing all of its messages, you can then undeploy it.</span></span> <span data-ttu-id="cf1d4-116">有关执行这些任务的说明，请参阅[如何升级业务流程](../core/how-to-upgrade-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-116">For instructions on performing these tasks, see [How to Upgrade an Orchestration](../core/how-to-upgrade-an-orchestration.md).</span></span>  
  
  <span data-ttu-id="cf1d4-117">下图显示了典型的并行业务流程部署。</span><span class="sxs-lookup"><span data-stu-id="cf1d4-117">The following diagram shows a typical side-by-side orchestration deployment.</span></span>  
  
  <span data-ttu-id="cf1d4-118">![并排部署方案](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span><span class="sxs-lookup"><span data-stu-id="cf1d4-118">![Side by Side Deployment Scenario](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1d4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf1d4-119">See Also</span></span>  
 <span data-ttu-id="cf1d4-120">[应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="cf1d4-120">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="cf1d4-121">更新应用程序的重要注意事项</span><span class="sxs-lookup"><span data-stu-id="cf1d4-121">Important Considerations for Updating Applications</span></span>](../core/important-considerations-for-updating-applications.md)