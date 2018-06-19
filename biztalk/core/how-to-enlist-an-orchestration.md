---
title: 如何登记业务流程 |Microsoft 文档
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
ms.openlocfilehash: f58cb697e270052f8f42229997b1125e808816b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255837"
---
# <a name="how-to-enlist-an-orchestration"></a><span data-ttu-id="2e971-102">如何登记业务流程</span><span class="sxs-lookup"><span data-stu-id="2e971-102">How to Enlist an Orchestration</span></span>
<span data-ttu-id="2e971-103">本主题介绍如何使用 BizTalk Server 管理控制台来登记到主机业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e971-103">This topic describes how to use the BizTalk Server Administration console to enlist an orchestration into a host.</span></span> <span data-ttu-id="2e971-104">你可以使用它之前，必须登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e971-104">The orchestration must be enlisted before you can start it.</span></span>  
  
 <span data-ttu-id="2e971-105">当登记业务流程，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="2e971-105">When enlisting an orchestration, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="2e971-106">**必须先绑定业务流程，你可以对其进行登记。**</span><span class="sxs-lookup"><span data-stu-id="2e971-106">**The orchestration must be bound before you can enlist it.**</span></span> <span data-ttu-id="2e971-107">有关配置业务流程的绑定的说明，请参阅[如何将绑定配置为业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="2e971-107">For instructions on configuring bindings for orchestrations, see [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="2e971-108">**自动创建订阅。**</span><span class="sxs-lookup"><span data-stu-id="2e971-108">**Subscriptions are automatically created.**</span></span> <span data-ttu-id="2e971-109">业务流程登记过程 MessageBox 数据库中创建必需的订阅。</span><span class="sxs-lookup"><span data-stu-id="2e971-109">The orchestration enlistment process creates the necessary subscriptions in the MessageBox database.</span></span>  
  
-   <span data-ttu-id="2e971-110">**你必须安装应用程序。**</span><span class="sxs-lookup"><span data-stu-id="2e971-110">**You must install the application.**</span></span> <span data-ttu-id="2e971-111">你必须安装包含所有将运行业务流程的位置的计算机上的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e971-111">You must install the application containing the orchestration on all of computers where the orchestration will run.</span></span> <span data-ttu-id="2e971-112">有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2e971-112">For more information, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="2e971-113">**调用的业务流程必须绑定到调用的业务流程的同一主机。**</span><span class="sxs-lookup"><span data-stu-id="2e971-113">**A calling orchestration must be bound to the same host as the called orchestration.**</span></span> <span data-ttu-id="2e971-114">所有业务流程，由另一个业务流程调用必须绑定到调用的业务流程的同一主机。</span><span class="sxs-lookup"><span data-stu-id="2e971-114">Any orchestration that is called by another orchestration must be bound to the same host as the calling orchestration.</span></span>  
  
-   <span data-ttu-id="2e971-115">**你还应登记依赖业务流程。**</span><span class="sxs-lookup"><span data-stu-id="2e971-115">**You should also enlist dependent orchestrations.**</span></span> <span data-ttu-id="2e971-116">如果你的业务流程中登记，但不是登记任何从属的业务流程，依赖业务流程将没有任何订阅。</span><span class="sxs-lookup"><span data-stu-id="2e971-116">If you enlist an orchestration but do not enlist any dependent orchestrations, the dependent orchestrations will not have any subscriptions.</span></span> <span data-ttu-id="2e971-117">没有订阅依赖 orchestration 可能会删除或挂起消息，因为没有要匹配的消息没有订阅。</span><span class="sxs-lookup"><span data-stu-id="2e971-117">A dependent orchestration without subscriptions may drop or suspend messages because there is no subscription for the messages to match.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e971-118">应用程序开发人员可以通过在开发过程中使用本主题中的过程来登记业务流程以测试其功能。</span><span class="sxs-lookup"><span data-stu-id="2e971-118">The application developer can enlist an orchestration to test its functionality during the development process  by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e971-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="2e971-119">Prerequisites</span></span>  
 <span data-ttu-id="2e971-120">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2e971-120">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="2e971-121">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2e971-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-an-orchestration"></a><span data-ttu-id="2e971-122">若要登记业务流程</span><span class="sxs-lookup"><span data-stu-id="2e971-122">To enlist an orchestration</span></span>  
  
1.  <span data-ttu-id="2e971-123">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2e971-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2e971-124">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要登记的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e971-124">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to enlist.</span></span>  
  
3.  <span data-ttu-id="2e971-125">单击**业务流程**，右键单击业务流程，以登记，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="2e971-125">Click **Orchestrations**, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2e971-126">要在一次登记多个业务流程，请按住 shift 键，并选择要登记每个业务流程业务流程，右键单击，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="2e971-126">To enlist multiple orchestrations at once, hold down the shift key and select each orchestration to enlist, right-click an orchestration, and then click **Enlist**.</span></span>  
  
     <span data-ttu-id="2e971-127">业务流程将登记，并创建相应的订阅。</span><span class="sxs-lookup"><span data-stu-id="2e971-127">The orchestration is enlisted and the appropriate subscriptions are created.</span></span> <span data-ttu-id="2e971-128">业务流程处于停止状态。</span><span class="sxs-lookup"><span data-stu-id="2e971-128">The orchestration is in the stopped state.</span></span> <span data-ttu-id="2e971-129">若要开始处理传入消息，你必须显式启动业务流程通过右键单击它并单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="2e971-129">To start processing incoming messages, you must explicitly start the orchestration by right-clicking it and clicking **Start**.</span></span> <span data-ttu-id="2e971-130">有关详细信息，请参阅[如何启动 Orchestration](../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="2e971-130">For more information, see [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e971-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e971-131">See Also</span></span>  
 <span data-ttu-id="2e971-132">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="2e971-132">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="2e971-133">如何取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="2e971-133">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)