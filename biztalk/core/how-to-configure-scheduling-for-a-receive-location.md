---
title: 如何配置计划的接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, receive locations
- managing [receive locations], scheduling
- scheduling, receive locations
- managing [receive locations], configuring
ms.assetid: 2653e1c3-ddbd-4d3f-be64-2a5fcd7cf267
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 598d26b47e954cf4299aabc0d0e77ecb4598c984
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386183"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a><span data-ttu-id="4632e-102">如何配置计划的接收位置</span><span class="sxs-lookup"><span data-stu-id="4632e-102">How to Configure Scheduling for a Receive Location</span></span>
<span data-ttu-id="4632e-103">本主题介绍如何使用 BizTalk Server 管理控制台配置接收位置的计划属性。</span><span class="sxs-lookup"><span data-stu-id="4632e-103">This topic describes how to use the BizTalk Server Administration console to configure scheduling properties for a receive location.</span></span> <span data-ttu-id="4632e-104">可以指定当你想要启动和停止处理消息的接收位置的日期。</span><span class="sxs-lookup"><span data-stu-id="4632e-104">You can specify the dates when you want the receive location to start and stop processing messages.</span></span> <span data-ttu-id="4632e-105">此外可以指定要处理的消息的接收位置在一天的特定时间。</span><span class="sxs-lookup"><span data-stu-id="4632e-105">You can also specify certain times of the day during which you want the receive location to process messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4632e-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="4632e-106">Prerequisites</span></span>  
 <span data-ttu-id="4632e-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4632e-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4632e-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4632e-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a><span data-ttu-id="4632e-109">若要配置的接收位置计划</span><span class="sxs-lookup"><span data-stu-id="4632e-109">To configure scheduling for a receive location</span></span>  
  
1. <span data-ttu-id="4632e-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4632e-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4632e-111">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置为接收位置计划。</span><span class="sxs-lookup"><span data-stu-id="4632e-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure scheduling for a receive location.</span></span>  
  
3. <span data-ttu-id="4632e-112">单击**接收位置**，右键单击该接收位置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4632e-112">Click **Receive Locations**, right-click the receive location, and click **Properties**.</span></span>  
  
4. <span data-ttu-id="4632e-113">在左窗格中，单击**计划**，按下表中所述配置计划属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4632e-113">In the left pane, click **Schedule**, configure scheduling properties as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="4632e-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4632e-114">Use this</span></span>|<span data-ttu-id="4632e-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4632e-115">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="4632e-116">**开始日期**</span><span class="sxs-lookup"><span data-stu-id="4632e-116">**Start date**</span></span>|<span data-ttu-id="4632e-117">选择此复选框，并从下拉日历中，选择接收位置开始处理消息的日期。</span><span class="sxs-lookup"><span data-stu-id="4632e-117">Select this check box, and then from the pull-down calendar, select the date on which the receive location starts processing messages.</span></span> <span data-ttu-id="4632e-118">若要更改年份，请单击所显示的年份。</span><span class="sxs-lookup"><span data-stu-id="4632e-118">To change the year, click the displayed year.</span></span>|  
   |<span data-ttu-id="4632e-119">**停止日期**</span><span class="sxs-lookup"><span data-stu-id="4632e-119">**Stop date**</span></span>|<span data-ttu-id="4632e-120">选择此复选框，并从下拉日历中，选择接收位置停止处理消息的日期。</span><span class="sxs-lookup"><span data-stu-id="4632e-120">Select this check box, and then from the pull-down calendar, select the date on which the receive location stops processing messages.</span></span> <span data-ttu-id="4632e-121">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="4632e-121">This property is optional.</span></span> <span data-ttu-id="4632e-122">如果不指定停止日期，则接收位置保持活动状态，直到它处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4632e-122">If you do not specify a stop date, the receive location remains active until it is disabled.</span></span>|  
   |<span data-ttu-id="4632e-123">**启用服务时段**</span><span class="sxs-lookup"><span data-stu-id="4632e-123">**Enable service window**</span></span>|<span data-ttu-id="4632e-124">选中此复选框以配置接收消息的接收位置，仅在指定时间的日期，则指定的时间**开始时间和停止时间**框。</span><span class="sxs-lookup"><span data-stu-id="4632e-124">Select this check box to configure the receive location to receive messages only at specified times of the day, then specify the times in the **Start time and Stop time** boxes.</span></span> <span data-ttu-id="4632e-125">如果清除该复选框，则接收位置在任何时间接收消息。</span><span class="sxs-lookup"><span data-stu-id="4632e-125">If the check box is cleared, the receive location receives messages at any time.</span></span> <span data-ttu-id="4632e-126">默认值为 false （清除）。</span><span class="sxs-lookup"><span data-stu-id="4632e-126">The default value is false (cleared).</span></span>|  
   |<span data-ttu-id="4632e-127">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="4632e-127">**Start time**</span></span>|<span data-ttu-id="4632e-128">指定接收位置应开始接收消息的时间。</span><span class="sxs-lookup"><span data-stu-id="4632e-128">Specify the time when the receive location should begin to receive messages.</span></span> <span data-ttu-id="4632e-129">此框是时才可用**启用服务时段**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="4632e-129">This box is available only when the **Enable service window** check box is selected.</span></span>|  
   |<span data-ttu-id="4632e-130">**停止时间**</span><span class="sxs-lookup"><span data-stu-id="4632e-130">**Stop time**</span></span>|<span data-ttu-id="4632e-131">指定接收位置应停止接收消息的时间。</span><span class="sxs-lookup"><span data-stu-id="4632e-131">Specify the time when the receive location should cease to receive messages.</span></span> <span data-ttu-id="4632e-132">此框是时才可用**启用服务时段**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="4632e-132">This box is available only when the **Enable service window** check box is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4632e-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4632e-133">See Also</span></span>  
 [<span data-ttu-id="4632e-134">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="4632e-134">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)