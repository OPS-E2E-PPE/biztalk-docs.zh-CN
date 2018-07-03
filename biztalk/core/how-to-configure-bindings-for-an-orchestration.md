---
title: 为业务流程配置绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc4daaf1fec46dea10003d8037003ad894733c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000142"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a><span data-ttu-id="f467a-102">如何为业务流程配置绑定</span><span class="sxs-lookup"><span data-stu-id="f467a-102">How to Configure Bindings for an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="f467a-103">概述</span><span class="sxs-lookup"><span data-stu-id="f467a-103">Overview</span></span>
<span data-ttu-id="f467a-104">本主题将介绍如何使用 BizTalk Server 管理控制台为业务流程配置绑定。</span><span class="sxs-lookup"><span data-stu-id="f467a-104">This topic describes how to use the BizTalk Server Administration console to configure bindings for an orchestration.</span></span> <span data-ttu-id="f467a-105">这包括在过渡环境或生产环境中将为业务流程定义的逻辑端口绑定到物理端口，以及将业务流程绑定到主机。</span><span class="sxs-lookup"><span data-stu-id="f467a-105">This involves binding the logical ports defined for the orchestration to physical ports in the staging or production environment as well as binding the orchestration to a host.</span></span> <span data-ttu-id="f467a-106">如果业务流程已绑定，则使用此过程可以更改这些绑定。</span><span class="sxs-lookup"><span data-stu-id="f467a-106">If the orchestration has already been bound, you can change the bindings by using this procedure.</span></span>  
  
 <span data-ttu-id="f467a-107">配置绑定后，可以登记业务流程，然后启动它，以使该业务流程开始处理消息。</span><span class="sxs-lookup"><span data-stu-id="f467a-107">After configuring bindings, you can enlist the orchestration and then start it so that it begins processing messages.</span></span> <span data-ttu-id="f467a-108">有关执行这些任务的说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)并[如何启动业务流程](../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="f467a-108">For instructions on performing these tasks, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f467a-109">应用程序开发人员可以通过在开发过程中使用本主题中的过程来为业务流程配置绑定。</span><span class="sxs-lookup"><span data-stu-id="f467a-109">The application developer can configure bindings for an orchestration to test its functionality during the development process either by using the procedure in this topic.</span></span> <span data-ttu-id="f467a-110">此外可以使用 Microsoft Windows Management Instrumentation (WMI) 对象模型来创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="f467a-110">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="f467a-111">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="f467a-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="f467a-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="f467a-112">Prerequisites</span></span>  
 <span data-ttu-id="f467a-113">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f467a-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f467a-114">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f467a-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="configure-bindings-for-an-orchestration"></a><span data-ttu-id="f467a-115">为业务流程配置绑定</span><span class="sxs-lookup"><span data-stu-id="f467a-115">Configure bindings for an orchestration</span></span>  
  
1. <span data-ttu-id="f467a-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f467a-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f467a-117">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含所需的业务流程的应用程序配置绑定</span><span class="sxs-lookup"><span data-stu-id="f467a-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure bindings</span></span>  
  
3. <span data-ttu-id="f467a-118">单击**业务流程**，右键单击您要为其配置绑定，然后单击该业务的流程**属性**。</span><span class="sxs-lookup"><span data-stu-id="f467a-118">Click **Orchestrations**, right-click the orchestration for which you want to configure bindings, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="f467a-119">单击**绑定**选项卡上，并从**主机**列表中，选择要登记业务流程的主机。</span><span class="sxs-lookup"><span data-stu-id="f467a-119">Click the **Bindings** tab, and from the **Host** list, select the host on which to enlist an orchestration.</span></span>  
  
5. <span data-ttu-id="f467a-120">从下拉列表中列出了**接收端口**列中的，每个入站逻辑端口旁边，选择你想要将逻辑端口绑定的接收端口。</span><span class="sxs-lookup"><span data-stu-id="f467a-120">From the drop-down lists in the **Receive Ports** column, next to each inbound logical port, select the receive port to which you want to bind the logical port.</span></span>  
  
6. <span data-ttu-id="f467a-121">从下拉列表中**发送端口/发送端口组**列中的，每个入站逻辑端口旁边，选择你想要将逻辑端口绑定，然后单击发送端口**确定**。</span><span class="sxs-lookup"><span data-stu-id="f467a-121">From the drop-down list in the **Send Ports/Send Port Groups** column, next to each inbound logical port, select the send port to which you want to bind the logical port, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f467a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f467a-122">See Also</span></span>  
 <span data-ttu-id="f467a-123">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f467a-123">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="f467a-124">[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="f467a-124">[How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md) </span></span>  
 [<span data-ttu-id="f467a-125">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="f467a-125">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)