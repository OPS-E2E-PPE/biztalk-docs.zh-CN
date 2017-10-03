---
title: "状态监视定义 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2c8247-5e25-4624-9f0d-c7fe621ffba2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97007535e67a4c3540278cee7ff82fec18d492c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="state-monitoring-definitions"></a><span data-ttu-id="1697c-102">状态监视定义</span><span class="sxs-lookup"><span data-stu-id="1697c-102">State Monitoring Definitions</span></span>
<span data-ttu-id="1697c-103">状态监视有助于回答问题在给定时间从特定的应用程序的角度监视的计算机是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="1697c-103">State monitoring helps answer the question of whether a monitored computer is healthy at a given time from the perspective of a particular application.</span></span> <span data-ttu-id="1697c-104">System Center Operations Manager (SCOM) 更新不同向用户公开的托管实体的状态，并显示状态的监视视图的状态的一部分。</span><span class="sxs-lookup"><span data-stu-id="1697c-104">System Center Operations Manager (SCOM) updates the status of different managed entities exposed to the user and presents the status as part of the state monitoring view.</span></span>  
  
 <span data-ttu-id="1697c-105">若要了解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状态监视视图，你必须了解的概念 SCOM 状态监视。</span><span class="sxs-lookup"><span data-stu-id="1697c-105">To understand the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] State Monitoring view, you must understand the concepts behind SCOM state monitoring.</span></span> <span data-ttu-id="1697c-106">下面的术语用于描述状态监视的关键元素：</span><span class="sxs-lookup"><span data-stu-id="1697c-106">The following terminology is used to describe the key components of state monitoring:</span></span>  
  
-   <span data-ttu-id="1697c-107">**角色**-由服务发现的环境中执行服务器的角色。</span><span class="sxs-lookup"><span data-stu-id="1697c-107">**Role** - A role that a server is performing in an environment as determined by service discovery.</span></span> <span data-ttu-id="1697c-108">例如，BizTalk 运行时角色封装的运行时项目和 BizTalk Server 中的实例。</span><span class="sxs-lookup"><span data-stu-id="1697c-108">For example, the BizTalk run-time role encapsulates the runtime artifacts and instances in BizTalk Server.</span></span>  
  
-   <span data-ttu-id="1697c-109">**组件**-的运行状况汇总一部分用于测量服务器角色的总体运行状况的子角色。</span><span class="sxs-lookup"><span data-stu-id="1697c-109">**Component** - A sub-role that is used as part of the health roll-up to measure the overall health of the server role.</span></span> <span data-ttu-id="1697c-110">例如，BAM 警报组件用于生成警报，以指示的总体运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="1697c-110">For example, the BAM alert component is used to generate alerts to indicate the status of overall health.</span></span>  
  
-   <span data-ttu-id="1697c-111">**实例**-特定计算机可以托管服务器角色的实例。</span><span class="sxs-lookup"><span data-stu-id="1697c-111">**Instance** - A particular computer may host instance(s) of the server role.</span></span>  
  
 <span data-ttu-id="1697c-112">简言之，以下是 SCOM 状态监控的重要原则：</span><span class="sxs-lookup"><span data-stu-id="1697c-112">In brief, the following are the important principles of SCOM state monitoring:</span></span>  
  
-   <span data-ttu-id="1697c-113">计算机组的运行状况源自计算机组中包含计算机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="1697c-113">Health of a computer group is derived from the health of the computers that are contained in the computer group.</span></span>  
  
-   <span data-ttu-id="1697c-114">计算机的状态显示在计算机上运行的应用程序（称作服务器角色）是否运行正常，并且运行状况从作为宿主的应用程序的运行状况派生。</span><span class="sxs-lookup"><span data-stu-id="1697c-114">The status of the computer shows whether applications (referred as server roles) running on the computer are healthy, and the health is derived from the health of the hosted applications.</span></span>  
  
-   <span data-ttu-id="1697c-115">在应用程序级别（服务器角色），服务器角色的状态是该服务器角色的所有应用程序实例的整体状态。</span><span class="sxs-lookup"><span data-stu-id="1697c-115">At the application level (server role), the status of the server role is the overall status of all application instances of that server role.</span></span> <span data-ttu-id="1697c-116">例如，运行状况的一个或多个项目，如业务流程，接收位置、 接收端口和依此类推会影响的状态和 BizTalk 应用程序的总体运行状况。</span><span class="sxs-lookup"><span data-stu-id="1697c-116">For example, health of one or more artifacts like orchestrations, receives locations, receives ports and so on affects the status and overall health of a BizTalk application.</span></span>  
  
-   <span data-ttu-id="1697c-117">在应用程序实例级别 （服务器角色实例），应用程序实例的运行状况源自的 （称为组件） 的应用程序实例的不同方面的运行状况。</span><span class="sxs-lookup"><span data-stu-id="1697c-117">At the application instance level (server role instance), the health of the application instance is derived from the health of different areas of the application instance (known as components).</span></span>  
  
-   <span data-ttu-id="1697c-118">SCOM 警报与组件的运行状况相关联。</span><span class="sxs-lookup"><span data-stu-id="1697c-118">SCOM alerts are associated with the health of a component.</span></span> <span data-ttu-id="1697c-119">在触发警报以指示整体运行状况时，组件的状态设置为红色、黄色或绿色。</span><span class="sxs-lookup"><span data-stu-id="1697c-119">Status of a component is set to red, yellow, or green when alerts are triggered to indicate overall health.</span></span>  
  
-   <span data-ttu-id="1697c-120">组件的运行状况将影响服务器角色的运行状况。</span><span class="sxs-lookup"><span data-stu-id="1697c-120">Health of a component contributes to the health of the server role.</span></span>  
  
 <span data-ttu-id="1697c-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中：</span><span class="sxs-lookup"><span data-stu-id="1697c-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="1697c-122">每个 BizTalk 服务器将被视为的 BizTalk Server role 的实例。</span><span class="sxs-lookup"><span data-stu-id="1697c-122">Each BizTalk Server is considered an instance of the BizTalk Server role.</span></span>  
  
-   <span data-ttu-id="1697c-123">因此，某一计算机中的 BizTalk Server 角色将被计算为该计算机中所有 BizTalk Server 进程的所有事件/活动的结果。</span><span class="sxs-lookup"><span data-stu-id="1697c-123">The BizTalk Server role in a computer will therefore be computed as a result of all events/activities of all the BizTalk Server processes in that computer.</span></span>  
  
 <span data-ttu-id="1697c-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包可用于 BizTalk Server 项目，其中包括监视状态</span><span class="sxs-lookup"><span data-stu-id="1697c-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack provides state monitoring for BizTalk Server artifacts which includes</span></span>  
  
-   <span data-ttu-id="1697c-125">例如，业务流程的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="1697c-125">Application artifacts such as orchestrations.</span></span> <span data-ttu-id="1697c-126">如消息组件接收端口、 接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="1697c-126">Messaging components such as receive ports, receive locations, and send ports.</span></span>  
  
-   <span data-ttu-id="1697c-127">部署项目，如服务器，承载情况下，SSO，依此类推。</span><span class="sxs-lookup"><span data-stu-id="1697c-127">Deployment artifacts such as servers, host instances, SSO and so on.</span></span>  
  
 <span data-ttu-id="1697c-128">下表列出以可视方式表示所有的 BizTalk Server 平台和应用程序级项目的运行状况状态的三种状态。</span><span class="sxs-lookup"><span data-stu-id="1697c-128">The following table lists the three states that visually represent the health status of all BizTalk Server platform and application level artifacts.</span></span> <span data-ttu-id="1697c-129">因此，SCOM 操作员能够清楚地了解多服务器部署的情况，以便更快地关注重要问题。</span><span class="sxs-lookup"><span data-stu-id="1697c-129">This provides the SCOM operator a high-level view of a multi-server deployment in order to focus on important problems quickly.</span></span>  
  
|<span data-ttu-id="1697c-130">项目</span><span class="sxs-lookup"><span data-stu-id="1697c-130">Artifacts</span></span>|<span data-ttu-id="1697c-131">绿色</span><span class="sxs-lookup"><span data-stu-id="1697c-131">Green</span></span>|<span data-ttu-id="1697c-132">Yellow</span><span class="sxs-lookup"><span data-stu-id="1697c-132">Yellow</span></span>|<span data-ttu-id="1697c-133">Red</span><span class="sxs-lookup"><span data-stu-id="1697c-133">Red</span></span>|  
|---------------|-----------|------------|---------|  
|<span data-ttu-id="1697c-134">应用程序级项目</span><span class="sxs-lookup"><span data-stu-id="1697c-134">Application level artifacts</span></span>|<span data-ttu-id="1697c-135">处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="1697c-135">Are in a running state.</span></span>|<span data-ttu-id="1697c-136">不超过 70%的实例出现故障。</span><span class="sxs-lookup"><span data-stu-id="1697c-136">Less than 70% of the   instances are faulted.</span></span>|<span data-ttu-id="1697c-137">超过 70%的实例出现故障，或导致严重错误。</span><span class="sxs-lookup"><span data-stu-id="1697c-137">More than 70% of the instances are faulted or have resulted in critical errors.</span></span>|  
|<span data-ttu-id="1697c-138">部署级别项目</span><span class="sxs-lookup"><span data-stu-id="1697c-138">Deployment level artifacts</span></span>|<span data-ttu-id="1697c-139">处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="1697c-139">Are in a running state.</span></span>|<span data-ttu-id="1697c-140">不适用</span><span class="sxs-lookup"><span data-stu-id="1697c-140">Not applicable</span></span>|<span data-ttu-id="1697c-141">未处于运行状态或已停止。</span><span class="sxs-lookup"><span data-stu-id="1697c-141">Are not in a running state or have stopped.</span></span>|