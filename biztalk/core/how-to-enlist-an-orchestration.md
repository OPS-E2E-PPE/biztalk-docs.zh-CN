---
title: 如何登记业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966286"
---
# <a name="how-to-enlist-an-orchestration"></a><span data-ttu-id="c176c-102">如何登记业务流程</span><span class="sxs-lookup"><span data-stu-id="c176c-102">How to Enlist an Orchestration</span></span>
<span data-ttu-id="c176c-103">本主题介绍如何使用 BizTalk Server 管理控制台来登记到主机的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c176c-103">This topic describes how to use the BizTalk Server Administration console to enlist an orchestration into a host.</span></span> <span data-ttu-id="c176c-104">必须登记业务流程，然后才能开始。</span><span class="sxs-lookup"><span data-stu-id="c176c-104">The orchestration must be enlisted before you can start it.</span></span>  
  
 <span data-ttu-id="c176c-105">当登记业务流程，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="c176c-105">When enlisting an orchestration, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="c176c-106">**必须先才能将其登记绑定业务流程。**</span><span class="sxs-lookup"><span data-stu-id="c176c-106">**The orchestration must be bound before you can enlist it.**</span></span> <span data-ttu-id="c176c-107">配置业务流程绑定的说明，请参阅[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="c176c-107">For instructions on configuring bindings for orchestrations, see [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="c176c-108">**自动创建订阅。**</span><span class="sxs-lookup"><span data-stu-id="c176c-108">**Subscriptions are automatically created.**</span></span> <span data-ttu-id="c176c-109">业务流程登记进程 MessageBox 数据库中创建必需的订阅。</span><span class="sxs-lookup"><span data-stu-id="c176c-109">The orchestration enlistment process creates the necessary subscriptions in the MessageBox database.</span></span>  
  
-   <span data-ttu-id="c176c-110">**必须安装该应用程序。**</span><span class="sxs-lookup"><span data-stu-id="c176c-110">**You must install the application.**</span></span> <span data-ttu-id="c176c-111">必须安装包含所有业务流程将在其中运行的计算机上的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c176c-111">You must install the application containing the orchestration on all of computers where the orchestration will run.</span></span> <span data-ttu-id="c176c-112">有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c176c-112">For more information, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="c176c-113">**调用业务流程必须绑定到调用的业务流程所在的主机。**</span><span class="sxs-lookup"><span data-stu-id="c176c-113">**A calling orchestration must be bound to the same host as the called orchestration.**</span></span> <span data-ttu-id="c176c-114">任何其他业务流程调用的业务流程必须绑定到调用业务流程所在的主机。</span><span class="sxs-lookup"><span data-stu-id="c176c-114">Any orchestration that is called by another orchestration must be bound to the same host as the calling orchestration.</span></span>  
  
-   <span data-ttu-id="c176c-115">**您还应登记从属业务流程。**</span><span class="sxs-lookup"><span data-stu-id="c176c-115">**You should also enlist dependent orchestrations.**</span></span> <span data-ttu-id="c176c-116">如果登记业务流程，但未登记任何从属业务流程，从属业务流程将不具有任何订阅。</span><span class="sxs-lookup"><span data-stu-id="c176c-116">If you enlist an orchestration but do not enlist any dependent orchestrations, the dependent orchestrations will not have any subscriptions.</span></span> <span data-ttu-id="c176c-117">没有订阅的相关业务流程可能会删除或挂起消息，因为没有要匹配的消息的订阅。</span><span class="sxs-lookup"><span data-stu-id="c176c-117">A dependent orchestration without subscriptions may drop or suspend messages because there is no subscription for the messages to match.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c176c-118">应用程序开发人员可以通过在开发过程中使用本主题中的过程来登记业务流程以测试其功能。</span><span class="sxs-lookup"><span data-stu-id="c176c-118">The application developer can enlist an orchestration to test its functionality during the development process  by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c176c-119">必要條件</span><span class="sxs-lookup"><span data-stu-id="c176c-119">Prerequisites</span></span>  
 <span data-ttu-id="c176c-120">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c176c-120">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c176c-121">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c176c-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-an-orchestration"></a><span data-ttu-id="c176c-122">若要登记业务流程</span><span class="sxs-lookup"><span data-stu-id="c176c-122">To enlist an orchestration</span></span>  
  
1. <span data-ttu-id="c176c-123">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c176c-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c176c-124">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含要登记的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c176c-124">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to enlist.</span></span>  
  
3. <span data-ttu-id="c176c-125">单击**业务流程**，右键单击业务流程以登记，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="c176c-125">Click **Orchestrations**, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c176c-126">要在一次登记多个业务流程，按住 shift 键并选择要登记的每个业务流程，右键单击业务流程，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="c176c-126">To enlist multiple orchestrations at once, hold down the shift key and select each orchestration to enlist, right-click an orchestration, and then click **Enlist**.</span></span>  
  
    <span data-ttu-id="c176c-127">登记业务流程并创建了相应的订阅。</span><span class="sxs-lookup"><span data-stu-id="c176c-127">The orchestration is enlisted and the appropriate subscriptions are created.</span></span> <span data-ttu-id="c176c-128">业务流程处于停止状态。</span><span class="sxs-lookup"><span data-stu-id="c176c-128">The orchestration is in the stopped state.</span></span> <span data-ttu-id="c176c-129">若要开始处理传入消息，您必须显式启动业务流程通过右键单击它并单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="c176c-129">To start processing incoming messages, you must explicitly start the orchestration by right-clicking it and clicking **Start**.</span></span> <span data-ttu-id="c176c-130">有关详细信息，请参阅[如何启动业务流程](../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="c176c-130">For more information, see [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c176c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c176c-131">See Also</span></span>  
 <span data-ttu-id="c176c-132">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="c176c-132">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="c176c-133">如何取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="c176c-133">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)