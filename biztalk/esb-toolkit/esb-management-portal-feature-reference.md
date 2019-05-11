---
title: ESB 管理门户功能参考 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8470b3af-8124-401b-b80f-3dc7346fed96
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae048a3a0cbcd12d7ca81dc46eaae9636d94f6b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306141"
---
# <a name="esb-management-portal-feature-reference"></a><span data-ttu-id="2b811-102">ESB 管理门户功能参考</span><span class="sxs-lookup"><span data-stu-id="2b811-102">ESB Management Portal Feature Reference</span></span>
<span data-ttu-id="2b811-103">ESB 管理门户提供了轻松地监视、 管理和调试 ESB 应用程序故障信息的视图。</span><span class="sxs-lookup"><span data-stu-id="2b811-103">The ESB Management Portal provides views of fault information that make it easy to monitor, manage, and debug ESB applications.</span></span> <span data-ttu-id="2b811-104">它还提供可用于管理警报、 将 UDDI 信息发布和管理门户的功能。</span><span class="sxs-lookup"><span data-stu-id="2b811-104">It also provides features that you can use to manage alerts, publish UDDI information, and administer the portal.</span></span> <span data-ttu-id="2b811-105">若要打开门户，请转到 http://localhost/ESB.Portal/。</span><span class="sxs-lookup"><span data-stu-id="2b811-105">To open the portal, go to http://localhost/ESB.Portal/.</span></span>  
  
 <span data-ttu-id="2b811-106">在门户中提供了以下视图：</span><span class="sxs-lookup"><span data-stu-id="2b811-106">The following views are available in the portal:</span></span>  
  
-   <span data-ttu-id="2b811-107">[门户主页上](../esb-toolkit/portal-home-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-107">[Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="2b811-108">此页显示的应用程序的总体状态、 错误的摘要、 UDDI 注册和显示的错误类型和应用程序细分的图表的最近的请求。</span><span class="sxs-lookup"><span data-stu-id="2b811-108">This page displays the overall application state, a summary of faults, recent requests for UDDI registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
-   <span data-ttu-id="2b811-109">[门户故障页](../esb-toolkit/portal-faults-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-109">[Portal Faults Page](../esb-toolkit/portal-faults-page.md).</span></span> <span data-ttu-id="2b811-110">此页显示被截断为每个错误; 属性的列表它由一系列条件支持的错误进行的分析。</span><span class="sxs-lookup"><span data-stu-id="2b811-110">This page displays a truncated list of properties for each fault; it supports analysis of faults by a range of criteria.</span></span>  
  
-   <span data-ttu-id="2b811-111">[门户故障消息查看器](../esb-toolkit/portal-fault-message-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-111">[Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md).</span></span> <span data-ttu-id="2b811-112">此页才可访问但门户错误页。</span><span class="sxs-lookup"><span data-stu-id="2b811-112">This page is accessible only though the Portal Faults page.</span></span> <span data-ttu-id="2b811-113">它显示的单个错误消息的详细信息，并允许您修复并重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="2b811-113">It displays details of individual fault messages and allows you to repair and resubmit messages.</span></span>  
  
-   <span data-ttu-id="2b811-114">[门户警报页](../esb-toolkit/portal-alerts-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-114">[Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span> <span data-ttu-id="2b811-115">此页面允许用户创建和修改警报，并配置警报的电子邮件设置。</span><span class="sxs-lookup"><span data-stu-id="2b811-115">This page allows users to create and modify alerts and to configure alert email settings.</span></span> <span data-ttu-id="2b811-116">在门户可以发送警报电子邮件消息特定类型的错误或任何错误时，会发生。</span><span class="sxs-lookup"><span data-stu-id="2b811-116">The portal can send an alert email message when a specific type of fault, or any fault, occurs.</span></span>  
  
-   <span data-ttu-id="2b811-117">[门户报告页](../esb-toolkit/portal-reports-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-117">[Portal Reports Page](../esb-toolkit/portal-reports-page.md).</span></span> <span data-ttu-id="2b811-118">此页显示图表，该值指示错误、 警报和消息重新提交活动从应用程序的角度看，并支持的应用程序中的各个服务的运行状况分析。</span><span class="sxs-lookup"><span data-stu-id="2b811-118">This page displays charts indicating the fault, alert, and message resubmission activity from an application perspective and supports analysis of the health of the individual services within applications.</span></span>  
  
-   <span data-ttu-id="2b811-119">[门户注册表页](../esb-toolkit/portal-registry-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-119">[Portal Registry Pages](../esb-toolkit/portal-registry-pages.md).</span></span> <span data-ttu-id="2b811-120">此页面到 UDDI 服务，用户可以发布服务终结点 （例如 Microsoft BizTalk Server 接收位置）。</span><span class="sxs-lookup"><span data-stu-id="2b811-120">This page allows users to publish service endpoints (such as Microsoft BizTalk Server receive locations) to the UDDI service.</span></span> <span data-ttu-id="2b811-121">UDDI 服务充当组织内的服务终结点的中央注册表。</span><span class="sxs-lookup"><span data-stu-id="2b811-121">The UDDI service acts as a central registry of service endpoints within an organization.</span></span>  
  
-   <span data-ttu-id="2b811-122">[门户管理员页](../esb-toolkit/portal-admin-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-122">[Portal Admin Pages](../esb-toolkit/portal-admin-pages.md).</span></span> <span data-ttu-id="2b811-123">此页面允许管理员配置门户设置，查看审核日志的已编辑和重新提交消息，并管理用户和组的警报。</span><span class="sxs-lookup"><span data-stu-id="2b811-123">This page allows administrators to configure portal settings, view an audit log of edited and resubmitted messages, and manage alerts for users and groups.</span></span>  
  
-   <span data-ttu-id="2b811-124">[门户我的设置页面](../esb-toolkit/portal-my-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2b811-124">[Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span> <span data-ttu-id="2b811-125">此页面，用户可以选择默认应用程序和门户的时间段筛选器。</span><span class="sxs-lookup"><span data-stu-id="2b811-125">This page allows users to select the default application and time-period filters for the portal.</span></span>