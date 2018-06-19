---
title: 如何启动 Orchestration |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e277c078a36129a125937114ee9287a1e97999b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255421"
---
# <a name="how-to-start-an-orchestration"></a><span data-ttu-id="7882b-102">如何启动业务流程</span><span class="sxs-lookup"><span data-stu-id="7882b-102">How to Start an Orchestration</span></span>
<span data-ttu-id="7882b-103">本主题将介绍如何使用 BizTalk Server 管理控制台启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="7882b-103">This topic describes how to use the BizTalk Server Administration console to start an orchestration.</span></span> <span data-ttu-id="7882b-104">启动业务流程后，业务流程将开始处理传入的消息。</span><span class="sxs-lookup"><span data-stu-id="7882b-104">When you start an orchestration, it begins processing incoming messages.</span></span>  
  
 <span data-ttu-id="7882b-105">启动业务流程时，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="7882b-105">When starting and orchestration, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="7882b-106">必须先登记业务流程以及与该业务流程相关联的所有发送端口和发送端口组，然后才可以启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="7882b-106">Before you can start the orchestration, it must be enlisted, along with all of the send ports and send port groups associated with it.</span></span> <span data-ttu-id="7882b-107">有关说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)和[如何登记发送端口或发送端口组](../core/how-to-enlist-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="7882b-107">For instructions, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Enlist a Send Port or Send Port Group](../core/how-to-enlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="7882b-108">启动业务流程并不会自动启动任何相关的发送端口。</span><span class="sxs-lookup"><span data-stu-id="7882b-108">Starting an orchestration does not automatically start any associated send ports.</span></span> <span data-ttu-id="7882b-109">你必须单独中所述启动它们[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="7882b-109">You must start them separately, as described in [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="7882b-110">如果登记了与此业务流程相关联的发送端口和/或发送端口组，但没有启动它们，则 BizTalk Server 会将发送到此发送端口或发送端口组的任何消息放入已登记发送端口或发送端口组的主机的挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="7882b-110">If you enlist the send ports and/or send port groups associated with this orchestration, but do not start them, BizTalk Server places any messages sent to this send port or send port group in the suspended queue of the host where you enlisted the send port or send port group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7882b-111">应用程序开发人员可以启动业务流程，以在开发过程中测试其功能，通过使用本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="7882b-111">The application developer can start an orchestration to test its functionality during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7882b-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="7882b-112">Prerequisites</span></span>  
 <span data-ttu-id="7882b-113">若要执行本主题中的过程，则必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="7882b-113">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="7882b-114">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7882b-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-an-orchestration"></a><span data-ttu-id="7882b-115">若要启动业务流程</span><span class="sxs-lookup"><span data-stu-id="7882b-115">To start an orchestration</span></span>  
  
1.  <span data-ttu-id="7882b-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7882b-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7882b-117">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要启动的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7882b-117">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to start.</span></span>  
  
3.  <span data-ttu-id="7882b-118">单击**业务流程**，业务流程中，右键单击，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7882b-118">Click **Orchestrations**, right-click the orchestration, and then click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7882b-119">如果在启动业务流程前没有先登记相关的发送端口和发送端口组，则将看到错误消息。</span><span class="sxs-lookup"><span data-stu-id="7882b-119">If you did not first enlist the associated send port and send port groups before starting the orchestration, you will see an error message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7882b-120">若要同时启动多个业务流程，请按住 shift 键并选择每个业务流程，右键单击业务流程，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7882b-120">To start multiple orchestrations at once, hold down the shift key and select each orchestration, right-click an orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7882b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7882b-121">See Also</span></span>  
 <span data-ttu-id="7882b-122">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="7882b-122">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="7882b-123">[如何停止业务流程](../core/how-to-stop-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="7882b-123">[How to Stop an Orchestration](../core/how-to-stop-an-orchestration.md) </span></span>  
 [<span data-ttu-id="7882b-124">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7882b-124">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)