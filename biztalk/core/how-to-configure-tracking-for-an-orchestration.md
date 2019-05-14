---
title: 如何为业务流程配置跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88d5dd42d26fd3c5ca899059beb87f72beff8dd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340167"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="cf663-102">如何为业务流程配置跟踪</span><span class="sxs-lookup"><span data-stu-id="cf663-102">How to Configure Tracking for an Orchestration</span></span>
<span data-ttu-id="cf663-103">本主题介绍如何使用 BizTalk Server 管理控制台为业务流程配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="cf663-103">This topic describes how to use the BizTalk Server Administration console to configure tracking for an orchestration.</span></span>  
  
 <span data-ttu-id="cf663-104">有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="cf663-104">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="cf663-105">有关跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cf663-105">For more information about the tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf663-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cf663-106">Prerequisites</span></span>  
 <span data-ttu-id="cf663-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="cf663-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="cf663-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="cf663-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-an-orchestration"></a><span data-ttu-id="cf663-109">若要为业务流程配置跟踪</span><span class="sxs-lookup"><span data-stu-id="cf663-109">To configure tracking for an orchestration</span></span>  
  
1. <span data-ttu-id="cf663-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cf663-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cf663-111">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含您要为其配置跟踪的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf663-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure tracking.</span></span>  
  
3. <span data-ttu-id="cf663-112">单击**业务流程**，右键单击您要为其配置跟踪，然后单击该业务的流程**属性**。</span><span class="sxs-lookup"><span data-stu-id="cf663-112">Click **Orchestrations**, right-click the orchestration for which you want to configure tracking, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="cf663-113">单击**跟踪**选项卡上，选择所需的跟踪选项下, 表中所述，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cf663-113">Click the **Tracking** tab, select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="cf663-114">Option</span><span class="sxs-lookup"><span data-stu-id="cf663-114">Option</span></span>|<span data-ttu-id="cf663-115">Description</span><span class="sxs-lookup"><span data-stu-id="cf663-115">Description</span></span>|  
   |------------|-----------------|  
   |<span data-ttu-id="cf663-116">**跟踪事件-业务流程开始和结束**</span><span class="sxs-lookup"><span data-stu-id="cf663-116">**Track Events - Orchestration start and end**</span></span>|<span data-ttu-id="cf663-117">选中此复选框以跟踪业务流程实例之前和之后的整个业务流程处理。</span><span class="sxs-lookup"><span data-stu-id="cf663-117">Select this check box to track the orchestration instance before and after processing of the entire business process.</span></span> <span data-ttu-id="cf663-118">业务流程跟踪，您可以查看跟踪中的实例查询结果视图。</span><span class="sxs-lookup"><span data-stu-id="cf663-118">Orchestration tracking enables you to see the instances in the tracking query result views.</span></span>|  
   |<span data-ttu-id="cf663-119">**跟踪事件-消息发送和接收**</span><span class="sxs-lookup"><span data-stu-id="cf663-119">**Track Events - Message send and receive**</span></span>|<span data-ttu-id="cf663-120">选择此复选框可跟踪消息发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="cf663-120">Select this check box to track message send and receive events.</span></span> <span data-ttu-id="cf663-121">此复选框才可用 匡 **业务流程开始和结束**复选框。</span><span class="sxs-lookup"><span data-stu-id="cf663-121">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
   |<span data-ttu-id="cf663-122">**跟踪事件-形状开始和结束**</span><span class="sxs-lookup"><span data-stu-id="cf663-122">**Track Events - Shape start and end**</span></span>|<span data-ttu-id="cf663-123">当您需要调试业务流程调试器中的业务流程实例时，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="cf663-123">Select this check box when you need to debug orchestration instances in the Orchestration Debugger.</span></span> <span data-ttu-id="cf663-124">选中此复选框后，业务流程调试器中的事件列表填充。</span><span class="sxs-lookup"><span data-stu-id="cf663-124">When this check box is selected, the event list in the Orchestration Debugger is populated.</span></span> <span data-ttu-id="cf663-125">此复选框才可用 匡 **业务流程开始和结束**复选框。</span><span class="sxs-lookup"><span data-stu-id="cf663-125">This check box is available only if you select the **Orchestration start and end** check box.</span></span>|  
   |<span data-ttu-id="cf663-126">**跟踪消息正文-业务流程处理前**</span><span class="sxs-lookup"><span data-stu-id="cf663-126">**Track Message Bodies - Before orchestration processing**</span></span>|<span data-ttu-id="cf663-127">选中此复选框可以保存和跟踪业务流程实例在处理之前的实际消息内容。</span><span class="sxs-lookup"><span data-stu-id="cf663-127">Select this check box to save and track the actual message content prior to processing by the orchestration instance.</span></span> <span data-ttu-id="cf663-128">此复选框才可用 匡 **消息发送和接收**复选框。</span><span class="sxs-lookup"><span data-stu-id="cf663-128">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
   |<span data-ttu-id="cf663-129">**跟踪消息正文-业务流程处理之后**</span><span class="sxs-lookup"><span data-stu-id="cf663-129">**Track Message Bodies - After orchestration processing**</span></span>|<span data-ttu-id="cf663-130">选中此复选框可以保存和跟踪业务流程实例在处理后的实际消息内容。</span><span class="sxs-lookup"><span data-stu-id="cf663-130">Select this check box to save and track the actual message content after processing by the orchestration instance.</span></span> <span data-ttu-id="cf663-131">此复选框才可用 匡 **消息发送和接收**复选框。</span><span class="sxs-lookup"><span data-stu-id="cf663-131">This check box is available only if you select the **Message send and receive** check box.</span></span>|  
   |<span data-ttu-id="cf663-132">**跟踪消息属性-传入的消息**</span><span class="sxs-lookup"><span data-stu-id="cf663-132">**Track Message Properties - Incoming messages**</span></span>|<span data-ttu-id="cf663-133">选择此复选框可跟踪入站消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="cf663-133">Select this check box to track the promoted properties of an inbound message.</span></span>|  
   |<span data-ttu-id="cf663-134">**跟踪消息属性-传出消息**</span><span class="sxs-lookup"><span data-stu-id="cf663-134">**Track Message Properties - Outgoing messages**</span></span>|<span data-ttu-id="cf663-135">选择此复选框可跟踪出站消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="cf663-135">Select this check box to track the promoted properties of an outbound message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf663-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf663-136">See Also</span></span>  
 [<span data-ttu-id="cf663-137">管理业务流程</span><span class="sxs-lookup"><span data-stu-id="cf663-137">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)