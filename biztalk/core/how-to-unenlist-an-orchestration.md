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
ms.openlocfilehash: 7504551d6cc97f108d6cdee695f241ee983994a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993510"
---
# <a name="how-to-unenlist-an-orchestration"></a><span data-ttu-id="753c5-102">如何取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="753c5-102">How to Unenlist an Orchestration</span></span>
<span data-ttu-id="753c5-103">本主题介绍如何使用 BizTalk Server 管理控制台来取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="753c5-103">This topic describes how to unenlist an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="753c5-104">取消登记业务流程从主机中删除它。</span><span class="sxs-lookup"><span data-stu-id="753c5-104">Unenlisting an orchestration removes it from the host.</span></span> <span data-ttu-id="753c5-105">这将删除订阅，因此该业务流程将不再处理消息。</span><span class="sxs-lookup"><span data-stu-id="753c5-105">This removes the subscription so that the orchestration no longer processes messages.</span></span> <span data-ttu-id="753c5-106">在编辑业务流程的绑定前，必须先对该业务流程进行取消登记。</span><span class="sxs-lookup"><span data-stu-id="753c5-106">You must unenlist an orchestration before you can edit its bindings.</span></span>  
  
 <span data-ttu-id="753c5-107">可以取消登记业务流程之前，必须终止任何正在运行的实例，如中所述[如何挂起、 恢复和终止业务流程实例](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="753c5-107">Before you can unenlist an orchestration, you must terminate any running instances, as described in [How to Suspend, Resume, and Terminate Orchestration Instances](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="753c5-108">应用程序开发人员可以通过在开发过程中使用本主题中的过程来取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="753c5-108">The application developer can unenlist an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="753c5-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="753c5-109">Prerequisites</span></span>  
 <span data-ttu-id="753c5-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="753c5-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="753c5-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="753c5-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-an-orchestration"></a><span data-ttu-id="753c5-112">若要取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="753c5-112">To unenlist an orchestration</span></span>  
  
1. <span data-ttu-id="753c5-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="753c5-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="753c5-114">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要取消登记该业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="753c5-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="753c5-115">单击**业务流程**，右键单击业务流程以取消登记，然后单击**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="753c5-115">Click **Orchestrations**, right-click the orchestration to unenlist, and then click **Unenlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="753c5-116">若要立即取消登记多个业务流程，请按住 shift 键并选择要取消登记每个业务流程，右键单击业务流程，然后依次**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="753c5-116">To unenlist multiple orchestrations at once, hold down the shift key and select each orchestration to unenlist, right-click an orchestration, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753c5-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="753c5-117">See Also</span></span>  
 <span data-ttu-id="753c5-118">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="753c5-118">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="753c5-119">[如何登记业务流程](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="753c5-119">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="753c5-120">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="753c5-120">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)