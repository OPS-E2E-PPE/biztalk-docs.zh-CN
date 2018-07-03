---
title: 方案： 更新应用程序项目 |Microsoft Docs
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
ms.openlocfilehash: 0f03e0ac546a638c5eaba9a39b10ba937f3b8d7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018103"
---
# <a name="scenario-updating-application-artifacts"></a><span data-ttu-id="bf007-102">方案： 更新应用程序项目</span><span class="sxs-lookup"><span data-stu-id="bf007-102">Scenario: Updating Application Artifacts</span></span>
<span data-ttu-id="bf007-103">存在以下两个在已部署到生产环境的应用程序中更新项目的基本情况：</span><span class="sxs-lookup"><span data-stu-id="bf007-103">There are two basic scenarios for updating the artifacts in an application that has been deployed into a production environment:</span></span>  
  
- <span data-ttu-id="bf007-104">在某一业务流程处理长期事务或正在等待来自要求-响应端口的响应时，通过新版本更新该业务流程。</span><span class="sxs-lookup"><span data-stu-id="bf007-104">Updating an orchestration with a new version when the orchestration handles long-running transactions or is waiting for a response from a solicit-response port.</span></span>  
  
- <span data-ttu-id="bf007-105">在您并不关心消息处理是否完成时，例如使用新版本更新架构或映射，这是更一般性的更新情况。</span><span class="sxs-lookup"><span data-stu-id="bf007-105">The more general update case, when you are not concerned with completing message processing, such as updating a schema or map with a new version.</span></span>  
  
  <span data-ttu-id="bf007-106">在一般性的更新情况中，您可能在用新版本更新某一项目，例如为了满足业务要求变化。</span><span class="sxs-lookup"><span data-stu-id="bf007-106">In the general update case, you may be updating an artifact with a new version, for example to address a change in business requirements.</span></span> <span data-ttu-id="bf007-107">此情况相对简单，并且您可以用更新后的项目覆盖原始项目。</span><span class="sxs-lookup"><span data-stu-id="bf007-107">This scenario is relatively straightforward, and you can overwrite the original artifact with the updated one.</span></span> <span data-ttu-id="bf007-108">有关所涉及的步骤的列表，请参阅[清单： 更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bf007-108">For a list of the steps involved, see [Checklist: Update the Artifacts in a BizTalk Application](../core/checklist-update-the-artifacts-in-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="bf007-109">第二种情况更为复杂。</span><span class="sxs-lookup"><span data-stu-id="bf007-109">The second scenario is more complex.</span></span> <span data-ttu-id="bf007-110">在此情况中，您必须允许现有业务流程完成对消息的处理。</span><span class="sxs-lookup"><span data-stu-id="bf007-110">In this case, you must allow the existing orchestration to finish processing the messages.</span></span> <span data-ttu-id="bf007-111">同时，您必须避免现有业务流程处理任何新消息。</span><span class="sxs-lookup"><span data-stu-id="bf007-111">At the same time, you must prevent the existing orchestration from processing any new messages.</span></span> <span data-ttu-id="bf007-112">而是应该让业务流程的已更新版本进行处理。</span><span class="sxs-lookup"><span data-stu-id="bf007-112">Instead, you want the updated version of the orchestration to take over.</span></span> <span data-ttu-id="bf007-113">为此，您将包含已更新业务流程的程序集部署到与原始版本相同的 BizTalk 应用程序中，然后同时运行这两个业务流程。</span><span class="sxs-lookup"><span data-stu-id="bf007-113">To accomplish this, you deploy the assembly containing the updated orchestration into the same BizTalk application as the original version, and then run both orchestrations simultaneously.</span></span> <span data-ttu-id="bf007-114">（新的程序集必须与包含原始业务流程的程序集具有不同版本，否则，您将不能将它部署到同一 BizTalk 组中。）然后，您将停止原始业务流程，以便没有新消息传送给该业务流程；再启动更新后的版本，以便将所有新消息都发送给它。</span><span class="sxs-lookup"><span data-stu-id="bf007-114">(The new assembly must have a different version number than the assembly containing the original orchestration, or you will not be able to deploy it into the same BizTalk group.) You then stop the original orchestration, so that no new messages are routed to it, and start the updated version, so that all new messages are sent to it.</span></span> <span data-ttu-id="bf007-115">在原始版本完成其所有消息的处理后，您可以取消对它的部署。</span><span class="sxs-lookup"><span data-stu-id="bf007-115">After the original version has finished processing all of its messages, you can then undeploy it.</span></span> <span data-ttu-id="bf007-116">有关执行这些任务的说明，请参阅[如何升级业务流程](../core/how-to-upgrade-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="bf007-116">For instructions on performing these tasks, see [How to Upgrade an Orchestration](../core/how-to-upgrade-an-orchestration.md).</span></span>  
  
  <span data-ttu-id="bf007-117">下图显示了典型的并行业务流程部署方案。</span><span class="sxs-lookup"><span data-stu-id="bf007-117">The following diagram shows a typical side-by-side orchestration deployment.</span></span>  
  
  <span data-ttu-id="bf007-118">![并排部署方案](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span><span class="sxs-lookup"><span data-stu-id="bf007-118">![Side by Side Deployment Scenario](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf007-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf007-119">See Also</span></span>  
 <span data-ttu-id="bf007-120">[应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="bf007-120">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="bf007-121">更新应用程序的重要注意事项</span><span class="sxs-lookup"><span data-stu-id="bf007-121">Important Considerations for Updating Applications</span></span>](../core/important-considerations-for-updating-applications.md)