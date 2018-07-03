---
title: 如何暂停、 恢复和终止业务流程实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ad7a5b278f8f972a518af40d527ff312d0d237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980390"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a><span data-ttu-id="96a8f-102">如何暂停、恢复和终止业务流程实例</span><span class="sxs-lookup"><span data-stu-id="96a8f-102">How to Suspend, Resume, and Terminate Orchestration Instances</span></span>
<span data-ttu-id="96a8f-103">本主题介绍如何使用 BizTalk Server 管理控制台来暂停、恢复和终止业务流程的一个或多个正在运行的服务实例。</span><span class="sxs-lookup"><span data-stu-id="96a8f-103">This topic describes how to suspend, resume, and terminate one or more running service instances of an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="96a8f-104">服务实例是实例的 BizTalk server 业务流程处理或的已序列化到 MessageBox 中以便进一步处理或跟踪。</span><span class="sxs-lookup"><span data-stu-id="96a8f-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or that has been serialized into the MessageBox for further processing or tracking.</span></span>  
  
 <span data-ttu-id="96a8f-105">下面描述了这三个操作的影响：</span><span class="sxs-lookup"><span data-stu-id="96a8f-105">The following describes the effects of these three operations:</span></span>  
  
-   <span data-ttu-id="96a8f-106">**挂起。**</span><span class="sxs-lookup"><span data-stu-id="96a8f-106">**Suspend.**</span></span> <span data-ttu-id="96a8f-107">这将暂停服务实例的运行。</span><span class="sxs-lookup"><span data-stu-id="96a8f-107">This pauses the service instance.</span></span> <span data-ttu-id="96a8f-108">进程内消息将运行到结束。</span><span class="sxs-lookup"><span data-stu-id="96a8f-108">In-process messages run to completion.</span></span> <span data-ttu-id="96a8f-109">消息仍传送到服务实例，但不会予以处理。</span><span class="sxs-lookup"><span data-stu-id="96a8f-109">Messages are still routed to service instances, but are not processed.</span></span>  
  
-   <span data-ttu-id="96a8f-110">**恢复。**</span><span class="sxs-lookup"><span data-stu-id="96a8f-110">**Resume.**</span></span> <span data-ttu-id="96a8f-111">这将恢复挂起的实例的处理。</span><span class="sxs-lookup"><span data-stu-id="96a8f-111">This resumes processing of suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96a8f-112">不能从断点状态恢复某一实例。</span><span class="sxs-lookup"><span data-stu-id="96a8f-112">You cannot resume an instance from a breakpoint state.</span></span> <span data-ttu-id="96a8f-113">恢复此类实例可能会显示“挂起”状态，但该实例最终将失败。</span><span class="sxs-lookup"><span data-stu-id="96a8f-113">Resuming such an instance may show a status of "Pending," but the instance will eventually fail.</span></span>  
  
-   <span data-ttu-id="96a8f-114">**终止。**</span><span class="sxs-lookup"><span data-stu-id="96a8f-114">**Terminate.**</span></span> <span data-ttu-id="96a8f-115">这将终止所有消息处理。</span><span class="sxs-lookup"><span data-stu-id="96a8f-115">This terminates all message processing.</span></span> <span data-ttu-id="96a8f-116">该服务实例将从 BizTalk Server 数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="96a8f-116">The service instance is deleted from the BizTalk Server databases.</span></span> <span data-ttu-id="96a8f-117">服务实例正在处理的消息也被删除，但未终止的服务实例引用的消息除外。</span><span class="sxs-lookup"><span data-stu-id="96a8f-117">Messages that the service instance is processing are also deleted, except for any messages that are also referenced by a service instance that is not being terminated.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96a8f-118">必要條件</span><span class="sxs-lookup"><span data-stu-id="96a8f-118">Prerequisites</span></span>  
 <span data-ttu-id="96a8f-119">若要执行本主题中的过程，则必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="96a8f-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="96a8f-120">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="96a8f-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a><span data-ttu-id="96a8f-121">查看业务流程实例的启动、停止或终止</span><span class="sxs-lookup"><span data-stu-id="96a8f-121">To view start, stop, or terminate an instance of an orchestration</span></span>  
  
1. <span data-ttu-id="96a8f-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="96a8f-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="96a8f-123">选择“BizTalk 组”以显示“组中心”页。</span><span class="sxs-lookup"><span data-stu-id="96a8f-123">Select the BizTalk Group to display the Group Hub page.</span></span>  
  
3. <span data-ttu-id="96a8f-124">下**正在进行的工作**，单击**正在运行的服务实例**。</span><span class="sxs-lookup"><span data-stu-id="96a8f-124">Under **Work in Progress**, click **Running service instances**.</span></span>  
  
    <span data-ttu-id="96a8f-125">此页下半部分的“查询结果”面板将显示该业务流程的所有实例。</span><span class="sxs-lookup"><span data-stu-id="96a8f-125">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
4. <span data-ttu-id="96a8f-126">若要修改查询和查看业务流程的不同实例，请单击下面的框**值**有关**搜索**字段中，选择要查看，然后单击实例类型**运行查询**.</span><span class="sxs-lookup"><span data-stu-id="96a8f-126">To refine the query and view different instances for the orchestration, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="96a8f-127">有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="96a8f-127">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
5. <span data-ttu-id="96a8f-128">右键单击的实例，单击**挂起**，**恢复**，或**终止**。</span><span class="sxs-lookup"><span data-stu-id="96a8f-128">Right-click the instance you want and click **Suspend**, **Resume**, or **Terminate**.</span></span> <span data-ttu-id="96a8f-129">使用此功能可以选择要恢复哪些实例。</span><span class="sxs-lookup"><span data-stu-id="96a8f-129">This functionality allows you to select which instances to resume.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="96a8f-130">若要对多个实例执行该操作，请在按住 CTRL 键的同时单击所需实例。</span><span class="sxs-lookup"><span data-stu-id="96a8f-130">To perform the operation on multiple instances, hold down the CTRL key and click the instances you want.</span></span> <span data-ttu-id="96a8f-131">右键单击实例，然后单击**挂起**，**恢复**，或**终止**。</span><span class="sxs-lookup"><span data-stu-id="96a8f-131">Then right-click an instance and click **Suspend**, **Resume**, or **Terminate**.</span></span>  
  
    <span data-ttu-id="96a8f-132">[服务实例状态](../core/service-instance-states.md)提供了有关挂起状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96a8f-132">[Service Instance States](../core/service-instance-states.md) provides more information on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a8f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="96a8f-133">See Also</span></span>  
 <span data-ttu-id="96a8f-134">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="96a8f-134">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="96a8f-135">[如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="96a8f-135">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 [<span data-ttu-id="96a8f-136">如何搜索挂起的服务实例</span><span class="sxs-lookup"><span data-stu-id="96a8f-136">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)