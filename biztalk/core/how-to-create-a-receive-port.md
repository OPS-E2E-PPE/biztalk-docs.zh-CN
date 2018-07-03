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
ms.openlocfilehash: 194645d9f6f04db6d8005d4ea288a73271260252
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983102"
---
# <a name="how-to-create-a-receive-port"></a><span data-ttu-id="be345-102">如何创建接收端口</span><span class="sxs-lookup"><span data-stu-id="be345-102">How to Create a Receive Port</span></span>
<span data-ttu-id="be345-103">本主题将介绍如何使用 BizTalk Server 管理控制台来创建接收端口。</span><span class="sxs-lookup"><span data-stu-id="be345-103">This topic describes how to use the BizTalk Server Administration console to create a receive port.</span></span> <span data-ttu-id="be345-104">接收端口是相似接收位置的一个逻辑分组，使用该端口，服务可通过接收数据与外部合作伙伴进行交互。</span><span class="sxs-lookup"><span data-stu-id="be345-104">A receive port is a logical grouping of similar receive locations through which services interact with external partners by receiving data.</span></span>  

 <span data-ttu-id="be345-105">您可以创建以下类型的接收端口：</span><span class="sxs-lookup"><span data-stu-id="be345-105">You can create the following types of receive ports:</span></span>  

- <span data-ttu-id="be345-106">单向端口 — 用于丢弃消息并且不等待同步回复的应用程序</span><span class="sxs-lookup"><span data-stu-id="be345-106">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  

- <span data-ttu-id="be345-107">请求-响应 — 用于请求消息响应的应用程序</span><span class="sxs-lookup"><span data-stu-id="be345-107">Request-response — used with applications that require a response to a message</span></span>  

  <span data-ttu-id="be345-108">除了本主题中所述的配置，您还可以指定接收端口，处理的消息的跟踪选项中所述[如何为接收端口配置跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="be345-108">In addition to the configuration described in this topic, you can also specify tracking options for the messages handled by a receive port, as described in [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="be345-109">如果您正在远程计算机上创建某一接收端口，并且该计算机未启用网络 DTC，则您必须在创建该接收端口后重新启动远程计算机。</span><span class="sxs-lookup"><span data-stu-id="be345-109">If you are creating a receive port on a remote computer and that computer does not have network DTC enabled, you will have to reboot the remote computer after creating the receive port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="be345-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="be345-110">Prerequisites</span></span>  
 <span data-ttu-id="be345-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="be345-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="be345-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="be345-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

### <a name="to-create-a-receive-port"></a><span data-ttu-id="be345-113">若要创建的接收端口</span><span class="sxs-lookup"><span data-stu-id="be345-113">To create a receive port</span></span>  

1. <span data-ttu-id="be345-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="be345-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="be345-115">在控制台树中，展开要为其创建接收端口的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="be345-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive port.</span></span>  

3. <span data-ttu-id="be345-116">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**根据要向端口类型创建。</span><span class="sxs-lookup"><span data-stu-id="be345-116">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port** or **Request Response Receive Port**, according to the type of port you want to create.</span></span>  

4. <span data-ttu-id="be345-117">在中**接收端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be345-117">In the **Receive Port Properties** window, do the following:</span></span>  


   |                 <span data-ttu-id="be345-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be345-118">Use this</span></span>                  |                                                                                                                                                                                                                            <span data-ttu-id="be345-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be345-119">To do this</span></span>                                                                                                                                                                                                                             |
   |-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 <span data-ttu-id="be345-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="be345-120">**Name**</span></span>                  |                                                                                                                                                                                                                    <span data-ttu-id="be345-121">键入端口的名称。</span><span class="sxs-lookup"><span data-stu-id="be345-121">Type the name of the port.</span></span>                                                                                                                                                                                                                     |
   |           <span data-ttu-id="be345-122">**无身份验证**</span><span class="sxs-lookup"><span data-stu-id="be345-122">**No authentication**</span></span>           |                                                                                                                                                                                                 <span data-ttu-id="be345-123">单击此选项可禁用验证。</span><span class="sxs-lookup"><span data-stu-id="be345-123">Click this option to disable authentication.</span></span> <span data-ttu-id="be345-124">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="be345-124">This is the default.</span></span>                                                                                                                                                                                                 |
   | <span data-ttu-id="be345-125">**身份验证失败时删除消息**</span><span class="sxs-lookup"><span data-stu-id="be345-125">**Drop messages if authentication fails**</span></span> |                                                                                                                                                                                         <span data-ttu-id="be345-126">单击此选项可启用验证，但将删除未通过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="be345-126">Click this option to enable authentication but to drop unauthenticated messages.</span></span>                                                                                                                                                                                          |
   | <span data-ttu-id="be345-127">**身份验证失败时保留消息**</span><span class="sxs-lookup"><span data-stu-id="be345-127">**Keep messages if authentication fails**</span></span> |                                                                                                                                                                                           <span data-ttu-id="be345-128">单击此选项可启用验证，并保留未通过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="be345-128">Click this option to enable authentication and keep unauthenticated messages.</span></span>                                                                                                                                                                                           |
   |  <span data-ttu-id="be345-129">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="be345-129">**Enable routing for failed messages**</span></span>   | <span data-ttu-id="be345-130">选中此复选框可尝试将失败的所有消息路由至某个订阅应用程序（例如另一个接收端口或业务流程计划）。</span><span class="sxs-lookup"><span data-stu-id="be345-130">Select this check box to attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="be345-131">清除此复选框可挂起失败的消息，并生成一个否定确认 (NACK)。</span><span class="sxs-lookup"><span data-stu-id="be345-131">Clear the check box to suspend failed messages and generate a negative acknowledgment (NACK).</span></span> <span data-ttu-id="be345-132">默认值为清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="be345-132">The default value is cleared.</span></span> <span data-ttu-id="be345-133">有关详细信息，请参阅[如何为接收端口的失败消息启用路由](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="be345-133">For more information, see [How to Enable Routing for Failed Messages for a Receive Port](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).</span></span> |


5. <span data-ttu-id="be345-134">在左窗格中，单击**接收位置**，并创建新的接收位置，为此接收端口。</span><span class="sxs-lookup"><span data-stu-id="be345-134">In the left pane, click **Receive Locations**, and create a new receive location for this receive port.</span></span> <span data-ttu-id="be345-135">有关说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="be345-135">For instructions, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

6. <span data-ttu-id="be345-136">在左窗格中，单击**入站映射**，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be345-136">In the left pane, click **Inbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="be345-137">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be345-137">Use this</span></span>       |                                  <span data-ttu-id="be345-138">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be345-138">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="be345-139">**源文档**</span><span class="sxs-lookup"><span data-stu-id="be345-139">**Source Document**</span></span> |   <span data-ttu-id="be345-140">从下拉列表中，选择要与此端口一起使用的源架构。</span><span class="sxs-lookup"><span data-stu-id="be345-140">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="be345-141">**地图**</span><span class="sxs-lookup"><span data-stu-id="be345-141">**Map**</span></span>       | <span data-ttu-id="be345-142">从下拉列表中，选择要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="be345-142">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="be345-143">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="be345-143">**Target Document**</span></span> | <span data-ttu-id="be345-144">从下拉列表中，选择要与此端口一起使用的目标架构。</span><span class="sxs-lookup"><span data-stu-id="be345-144">From the drop-down list, select the destination schema to use with this port.</span></span> |


7. <span data-ttu-id="be345-145">如果要创建请求-响应接收端口，请在左窗格中，单击**出站映射**，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be345-145">If you are creating a request-response receive port, then in the left pane, click **Outbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="be345-146">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be345-146">Use this</span></span>       |                                  <span data-ttu-id="be345-147">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be345-147">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="be345-148">**源文档**</span><span class="sxs-lookup"><span data-stu-id="be345-148">**Source Document**</span></span> |   <span data-ttu-id="be345-149">从下拉列表中，选择要与此端口一起使用的源架构。</span><span class="sxs-lookup"><span data-stu-id="be345-149">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="be345-150">**地图**</span><span class="sxs-lookup"><span data-stu-id="be345-150">**Map**</span></span>       | <span data-ttu-id="be345-151">从下拉列表中，选择要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="be345-151">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="be345-152">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="be345-152">**Target Document**</span></span> | <span data-ttu-id="be345-153">从下拉列表中，选择要与此端口一起使用的目标架构。</span><span class="sxs-lookup"><span data-stu-id="be345-153">From the drop-down list, select the destination schema to use with this port.</span></span> |


8. <span data-ttu-id="be345-154">完成配置接收端口，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="be345-154">When finished configuring the receive port, click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="be345-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="be345-155">See Also</span></span>  
 [<span data-ttu-id="be345-156">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="be345-156">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)