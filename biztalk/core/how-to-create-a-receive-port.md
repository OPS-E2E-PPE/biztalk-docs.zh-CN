---
title: 如何创建接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceiveport
helpviewer_keywords:
- receive ports, creating
- managing [receive ports], creating
- creating, receive ports
ms.assetid: 23fae441-be80-4759-b3d6-74787a40e65b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b13b426077d0c768970debab88c52067a9a306
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385585"
---
# <a name="how-to-create-a-receive-port"></a><span data-ttu-id="9b5d2-102">如何创建接收端口</span><span class="sxs-lookup"><span data-stu-id="9b5d2-102">How to Create a Receive Port</span></span>
<span data-ttu-id="9b5d2-103">本主题介绍如何使用 BizTalk Server 管理控制台来创建接收端口。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-103">This topic describes how to use the BizTalk Server Administration console to create a receive port.</span></span> <span data-ttu-id="9b5d2-104">接收端口来接收数据是相似接收位置的服务进行交互与外部合作伙伴的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-104">A receive port is a logical grouping of similar receive locations through which services interact with external partners by receiving data.</span></span>  

 <span data-ttu-id="9b5d2-105">可以创建以下类型的接收端口：</span><span class="sxs-lookup"><span data-stu-id="9b5d2-105">You can create the following types of receive ports:</span></span>  

- <span data-ttu-id="9b5d2-106">单向端口 — 用于丢弃消息并不等待同步回复的应用程序</span><span class="sxs-lookup"><span data-stu-id="9b5d2-106">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  

- <span data-ttu-id="9b5d2-107">请求-响应 — 用于要求对消息的响应的应用程序</span><span class="sxs-lookup"><span data-stu-id="9b5d2-107">Request-response — used with applications that require a response to a message</span></span>  

  <span data-ttu-id="9b5d2-108">除了本主题中所述的配置，您还可以指定接收端口，处理的消息的跟踪选项中所述[如何为接收端口配置跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-108">In addition to the configuration described in this topic, you can also specify tracking options for the messages handled by a receive port, as described in [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="9b5d2-109">如果你要在远程计算机上创建接收端口，并且该计算机没有启用网络 DTC，您将必须创建接收端口后重新启动远程计算机。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-109">If you are creating a receive port on a remote computer and that computer does not have network DTC enabled, you will have to reboot the remote computer after creating the receive port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9b5d2-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="9b5d2-110">Prerequisites</span></span>  
 <span data-ttu-id="9b5d2-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9b5d2-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

### <a name="to-create-a-receive-port"></a><span data-ttu-id="9b5d2-113">若要创建的接收端口</span><span class="sxs-lookup"><span data-stu-id="9b5d2-113">To create a receive port</span></span>  

1. <span data-ttu-id="9b5d2-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="9b5d2-115">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要创建的接收端口。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive port.</span></span>  

3. <span data-ttu-id="9b5d2-116">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**根据要向端口类型创建。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-116">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port** or **Request Response Receive Port**, according to the type of port you want to create.</span></span>  

4. <span data-ttu-id="9b5d2-117">在中**接收端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9b5d2-117">In the **Receive Port Properties** window, do the following:</span></span>  


   |                 <span data-ttu-id="9b5d2-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9b5d2-118">Use this</span></span>                  |                                                                                                                                                                                                                            <span data-ttu-id="9b5d2-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9b5d2-119">To do this</span></span>                                                                                                                                                                                                                             |
   |-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 <span data-ttu-id="9b5d2-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-120">**Name**</span></span>                  |                                                                                                                                                                                                                    <span data-ttu-id="9b5d2-121">键入端口的名称。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-121">Type the name of the port.</span></span>                                                                                                                                                                                                                     |
   |           <span data-ttu-id="9b5d2-122">**无身份验证**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-122">**No authentication**</span></span>           |                                                                                                                                                                                                 <span data-ttu-id="9b5d2-123">单击此选项可禁用身份验证。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-123">Click this option to disable authentication.</span></span> <span data-ttu-id="9b5d2-124">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-124">This is the default.</span></span>                                                                                                                                                                                                 |
   | <span data-ttu-id="9b5d2-125">**身份验证失败时删除消息**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-125">**Drop messages if authentication fails**</span></span> |                                                                                                                                                                                         <span data-ttu-id="9b5d2-126">单击此选项以启用身份验证，但将删除未经验证的消息。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-126">Click this option to enable authentication but to drop unauthenticated messages.</span></span>                                                                                                                                                                                          |
   | <span data-ttu-id="9b5d2-127">**身份验证失败时保留消息**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-127">**Keep messages if authentication fails**</span></span> |                                                                                                                                                                                           <span data-ttu-id="9b5d2-128">单击此选项可启用身份验证并保留未经验证的消息。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-128">Click this option to enable authentication and keep unauthenticated messages.</span></span>                                                                                                                                                                                           |
   |  <span data-ttu-id="9b5d2-129">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-129">**Enable routing for failed messages**</span></span>   | <span data-ttu-id="9b5d2-130">选中此复选框可尝试将路由到某个订阅应用程序的处理失败的任何消息 （例如其他接收端口或业务流程计划）。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-130">Select this check box to attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="9b5d2-131">清除复选框可挂起失败的消息，并生成一个否定确认 (NACK)。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-131">Clear the check box to suspend failed messages and generate a negative acknowledgment (NACK).</span></span> <span data-ttu-id="9b5d2-132">默认值为清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-132">The default value is cleared.</span></span> <span data-ttu-id="9b5d2-133">有关详细信息，请参阅[如何为接收端口的失败消息启用路由](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-133">For more information, see [How to Enable Routing for Failed Messages for a Receive Port](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).</span></span> |


5. <span data-ttu-id="9b5d2-134">在左窗格中，单击**接收位置**，并创建新的接收位置，为此接收端口。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-134">In the left pane, click **Receive Locations**, and create a new receive location for this receive port.</span></span> <span data-ttu-id="9b5d2-135">有关说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-135">For instructions, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

6. <span data-ttu-id="9b5d2-136">在左窗格中，单击**入站映射**，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9b5d2-136">In the left pane, click **Inbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="9b5d2-137">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9b5d2-137">Use this</span></span>       |                                  <span data-ttu-id="9b5d2-138">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9b5d2-138">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="9b5d2-139">**源文档**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-139">**Source Document**</span></span> |   <span data-ttu-id="9b5d2-140">从下拉列表中，选择要使用与此端口的源架构。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-140">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="9b5d2-141">**地图**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-141">**Map**</span></span>       | <span data-ttu-id="9b5d2-142">从下拉列表中，选择你想要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-142">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="9b5d2-143">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-143">**Target Document**</span></span> | <span data-ttu-id="9b5d2-144">从下拉列表中，选择要使用与此端口的目标架构。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-144">From the drop-down list, select the destination schema to use with this port.</span></span> |


7. <span data-ttu-id="9b5d2-145">如果要创建请求-响应接收端口，请在左窗格中，单击**出站映射**，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9b5d2-145">If you are creating a request-response receive port, then in the left pane, click **Outbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="9b5d2-146">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9b5d2-146">Use this</span></span>       |                                  <span data-ttu-id="9b5d2-147">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9b5d2-147">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="9b5d2-148">**源文档**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-148">**Source Document**</span></span> |   <span data-ttu-id="9b5d2-149">从下拉列表中，选择要使用与此端口的源架构。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-149">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="9b5d2-150">**地图**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-150">**Map**</span></span>       | <span data-ttu-id="9b5d2-151">从下拉列表中，选择你想要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-151">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="9b5d2-152">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="9b5d2-152">**Target Document**</span></span> | <span data-ttu-id="9b5d2-153">从下拉列表中，选择要使用与此端口的目标架构。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-153">From the drop-down list, select the destination schema to use with this port.</span></span> |


8. <span data-ttu-id="9b5d2-154">完成配置接收端口，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9b5d2-154">When finished configuring the receive port, click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9b5d2-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b5d2-155">See Also</span></span>  
 [<span data-ttu-id="9b5d2-156">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="9b5d2-156">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)