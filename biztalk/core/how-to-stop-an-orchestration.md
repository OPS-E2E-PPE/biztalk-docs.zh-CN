---
title: 如何停止业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], stopping
- orchestrations, stopping
ms.assetid: a8009c23-ca83-4d2f-97dd-df660adbc279
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c830b2098a3a6f343999baac95241033892bfa75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017790"
---
# <a name="how-to-stop-an-orchestration"></a><span data-ttu-id="92020-102">如何停止业务流程</span><span class="sxs-lookup"><span data-stu-id="92020-102">How to Stop an Orchestration</span></span>
<span data-ttu-id="92020-103">本主题将介绍如何使用 BizTalk Server 管理控制台停止业务流程。</span><span class="sxs-lookup"><span data-stu-id="92020-103">This topic describes how to use the BizTalk Server Administration console to stop an orchestration.</span></span> <span data-ttu-id="92020-104">停止业务流程将停用并挂起所有到达的激活消息。</span><span class="sxs-lookup"><span data-stu-id="92020-104">Stopping an orchestration deactivates and suspends all of the arriving activation messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92020-105">应用程序开发人员可以通过在开发过程中使用本主题中的过程来停止业务流程。</span><span class="sxs-lookup"><span data-stu-id="92020-105">The application developer stop an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92020-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="92020-106">Prerequisites</span></span>  
 <span data-ttu-id="92020-107">若要执行本主题中描述的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="92020-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="92020-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="92020-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-an-orchestration"></a><span data-ttu-id="92020-109">若要停止业务流程</span><span class="sxs-lookup"><span data-stu-id="92020-109">To stop an orchestration</span></span>  
  
1. <span data-ttu-id="92020-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="92020-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="92020-111">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要停止的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="92020-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to stop.</span></span>  
  
3. <span data-ttu-id="92020-112">单击**业务流程**，右键单击该业务流程，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="92020-112">Click **Orchestrations**, right-click the orchestration, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92020-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="92020-113">See Also</span></span>  
 <span data-ttu-id="92020-114">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="92020-114">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="92020-115">[如何启动业务流程](../core/how-to-start-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="92020-115">[How to Start an Orchestration](../core/how-to-start-an-orchestration.md) </span></span>  
 [<span data-ttu-id="92020-116">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="92020-116">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)