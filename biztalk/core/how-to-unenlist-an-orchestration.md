---
title: 如何取消登记业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a96f0ee3f3de6c4ee64f004366f3e82a923b38aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383671"
---
# <a name="how-to-unenlist-an-orchestration"></a><span data-ttu-id="34ae2-102">如何取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="34ae2-102">How to Unenlist an Orchestration</span></span>
<span data-ttu-id="34ae2-103">本主题介绍如何使用 BizTalk Server 管理控制台取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="34ae2-103">This topic describes how to unenlist an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="34ae2-104">取消登记业务流程从主机中删除它。</span><span class="sxs-lookup"><span data-stu-id="34ae2-104">Unenlisting an orchestration removes it from the host.</span></span> <span data-ttu-id="34ae2-105">这将删除订阅，以便该业务流程不再处理消息。</span><span class="sxs-lookup"><span data-stu-id="34ae2-105">This removes the subscription so that the orchestration no longer processes messages.</span></span> <span data-ttu-id="34ae2-106">然后可以编辑自己的绑定，必须取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="34ae2-106">You must unenlist an orchestration before you can edit its bindings.</span></span>  
  
 <span data-ttu-id="34ae2-107">可以取消登记业务流程之前，必须终止任何正在运行的实例，如中所述[如何挂起、 恢复和终止业务流程实例](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="34ae2-107">Before you can unenlist an orchestration, you must terminate any running instances, as described in [How to Suspend, Resume, and Terminate Orchestration Instances](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34ae2-108">应用程序开发人员可以取消登记业务流程在开发过程中通过使用本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="34ae2-108">The application developer can unenlist an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34ae2-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="34ae2-109">Prerequisites</span></span>  
 <span data-ttu-id="34ae2-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="34ae2-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="34ae2-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="34ae2-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-an-orchestration"></a><span data-ttu-id="34ae2-112">若要取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="34ae2-112">To unenlist an orchestration</span></span>  
  
1. <span data-ttu-id="34ae2-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="34ae2-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="34ae2-114">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要取消登记该业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="34ae2-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="34ae2-115">单击**业务流程**，右键单击业务流程以取消登记，然后单击**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="34ae2-115">Click **Orchestrations**, right-click the orchestration to unenlist, and then click **Unenlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="34ae2-116">若要立即取消登记多个业务流程，请按住 shift 键并选择要取消登记每个业务流程，右键单击业务流程，然后依次**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="34ae2-116">To unenlist multiple orchestrations at once, hold down the shift key and select each orchestration to unenlist, right-click an orchestration, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ae2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="34ae2-117">See Also</span></span>  
 <span data-ttu-id="34ae2-118">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="34ae2-118">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="34ae2-119">[如何登记业务流程](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="34ae2-119">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="34ae2-120">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="34ae2-120">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)