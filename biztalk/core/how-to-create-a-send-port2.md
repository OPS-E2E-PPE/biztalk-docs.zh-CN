---
title: 如何创建发送端口 2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createsendport
helpviewer_keywords:
- managing [send ports], creating
- creating, send ports
- send ports, creating
ms.assetid: 7f0d07b8-1ac5-4032-bb08-2f7e05185f86
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796ba5da53257d0f198e4b8bf13ee81835efcf4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="f4614-102">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="f4614-102">How to Create a Send Port</span></span>
<span data-ttu-id="f4614-103">本主题将介绍如何使用 BizTalk Server 管理控制台来创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="f4614-103">This topic describes how to use the BizTalk Server Administration console to create a send port.</span></span> <span data-ttu-id="f4614-104">创建发送端口时，必须选择要创建的发送端口的类型，各类型如下：</span><span class="sxs-lookup"><span data-stu-id="f4614-104">When creating a send port, you must select the type of send port to create, as follows:</span></span>  
  
-   <span data-ttu-id="f4614-105">静态单向 — 仅发送端口 。</span><span class="sxs-lookup"><span data-stu-id="f4614-105">Static one-way — a send-only port.</span></span>  
  
-   <span data-ttu-id="f4614-106">静态要求响应 — 等待目标回复的发送端口 。</span><span class="sxs-lookup"><span data-stu-id="f4614-106">Static solicit-response — a send port that waits for a reply from the destination.</span></span>  
  
-   <span data-ttu-id="f4614-107">动态单向 — 仅发送端口 ， 运行时可基于消息属性绑定到协议和位置 。</span><span class="sxs-lookup"><span data-stu-id="f4614-107">Dynamic one-way — a send-only port that can be bound to a protocol and location at runtime based on message properties.</span></span>  
  
-   <span data-ttu-id="f4614-108">动态要求响应 — 等待回复的发送端口 ， 运行时可基于消息属性绑定到协议和位置 。</span><span class="sxs-lookup"><span data-stu-id="f4614-108">Dynamic solicit-response — a send port that waits for a reply and can be bound to a protocol and location at runtime based on message properties.</span></span>  
  
 <span data-ttu-id="f4614-109">创建发送端口后，您可以执行以下其他步骤来完成该配置：</span><span class="sxs-lookup"><span data-stu-id="f4614-109">After you create a send port, you can perform the following additional steps to complete the configuration:</span></span>  
  
-   <span data-ttu-id="f4614-110">配置高级传输选项，如的次数重试发送消息失败和对于端口的服务窗口计划上的消息中所述[如何配置传输高级选项发送端口](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-110">Configure advanced transport options, such as the number of times to retry sending messages on message failure and the service window schedule for the port, as described in [How to Configure Transport Advanced Options for a Send Port](../core/how-to-configure-transport-advanced-options-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="f4614-111">事件的主要传输无法正常工作中, 所述配置备份传输协议、[如何发送端口配置备份传输选项](../core/how-to-configure-backup-transport-options-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-111">Configure a backup transport, in the event the primary transport fails to function, as described in [How to Configure Backup Transport Options for a Send Port](../core/how-to-configure-backup-transport-options-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="f4614-112">配置筛选器，以确定消息框中，从哪些消息路由到此发送端口中所述[如何将筛选器配置为发送端口](../core/how-to-configure-filters-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-112">Configure filters to determine which messages are routed to this send port from the message box, as described in [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="f4614-113">将一个安全证书分配给要加密或签名由发送端口中，处理的文档中所述的发送端口[如何将证书分配给发送端口](../core/how-to-assign-a-certificate-to-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-113">Assign a security certificate to the send port to encrypt or sign documents handled by the send port, as described in [How to Assign a Certificate to a Send Port](../core/how-to-assign-a-certificate-to-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="f4614-114">中所述配置由发送端口中，处理消息的跟踪选项[如何配置跟踪发送端口](../core/how-to-configure-tracking-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-114">Configure tracking options for messages handled by the send port, as described in [How to Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4614-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="f4614-115">Prerequisites</span></span>  
 <span data-ttu-id="f4614-116">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f4614-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f4614-117">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-117">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span> <span data-ttu-id="f4614-118">此外，还需有企业单一登录 (SSO) 数据库的 SSO 关联管理员权限。</span><span class="sxs-lookup"><span data-stu-id="f4614-118">In addition, you need to have SSO affiliate administrator permissions on the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="f4614-119">有关详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="f4614-119">For more information, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="f4614-120">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="f4614-120">To create a send port</span></span>  
  
1.  <span data-ttu-id="f4614-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f4614-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f4614-122">在控制台树中，展开要为其创建发送端口的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4614-122">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="f4614-123">右键单击**发送端口**，指向**新建**，然后单击要创建的端口类型。</span><span class="sxs-lookup"><span data-stu-id="f4614-123">Right-click **Send Ports**, point to **New**, and then click the type of port to create.</span></span>  
  
4.  <span data-ttu-id="f4614-124">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f4614-124">In the **Send Ports Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="f4614-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f4614-125">Use this</span></span>|<span data-ttu-id="f4614-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f4614-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4614-127">**名称**</span><span class="sxs-lookup"><span data-stu-id="f4614-127">**Name**</span></span>|<span data-ttu-id="f4614-128">键入新发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="f4614-128">Type the name of the new send port.</span></span> <span data-ttu-id="f4614-129">此名称在 BizTalk 组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f4614-129">This name must be unique in the BizTalk group.</span></span>|  
    |<span data-ttu-id="f4614-130">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="f4614-130">**Transport Type**</span></span>|<span data-ttu-id="f4614-131">从下拉列表中，选择适当的传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="f4614-131">From the drop-down list, select the appropriate transport type, or transport protocol.</span></span> <span data-ttu-id="f4614-132">如果端口是要求响应端口，则该列表中只显示支持要求响应的传输类型。</span><span class="sxs-lookup"><span data-stu-id="f4614-132">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span> <span data-ttu-id="f4614-133">此属性仅对静态端口可见。</span><span class="sxs-lookup"><span data-stu-id="f4614-133">This property is visible only for static ports.</span></span>|  
    |<span data-ttu-id="f4614-134">**配置**</span><span class="sxs-lookup"><span data-stu-id="f4614-134">**Configure**</span></span>|<span data-ttu-id="f4614-135">选择传输类型后，单击**配置**以显示**传输属性**对话框中，提供特定于传输的配置选项。</span><span class="sxs-lookup"><span data-stu-id="f4614-135">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box, which provides transport-specific configuration options.</span></span> <span data-ttu-id="f4614-136">此属性仅对静态端口可见。</span><span class="sxs-lookup"><span data-stu-id="f4614-136">This property is visible only for static ports.</span></span> <span data-ttu-id="f4614-137">单击**帮助**对话框中的配置说明。</span><span class="sxs-lookup"><span data-stu-id="f4614-137">Click **Help** in the dialog box for configuration instructions.</span></span>|  
    |<span data-ttu-id="f4614-138">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="f4614-138">**Send handler**</span></span>|<span data-ttu-id="f4614-139">从下拉列表中选择运行发送适配器的主机实例。</span><span class="sxs-lookup"><span data-stu-id="f4614-139">From the drop-down list, select the host instance on which the send adapter is running.</span></span> <span data-ttu-id="f4614-140">此属性仅对静态端口可见。</span><span class="sxs-lookup"><span data-stu-id="f4614-140">This property is visible only for static ports.</span></span>|  
    |<span data-ttu-id="f4614-141">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="f4614-141">**Send pipeline**</span></span>|<span data-ttu-id="f4614-142">从下拉列表中选择处理通过此端口发送的消息的管道。</span><span class="sxs-lookup"><span data-stu-id="f4614-142">From the drop-down list, select the pipeline that processes the messages sent through this port.</span></span> <span data-ttu-id="f4614-143">选择管道后，你可以单击旁边的省略号 (**...**) 按钮以显示**配置管道**对话框中，你在其中配置为此特定端口的每个实例管道属性。</span><span class="sxs-lookup"><span data-stu-id="f4614-143">After you select the pipeline, you can click the adjacent ellipsis (**…**) button to display the **Configure Pipeline** dialog box, where you configure per-instance pipeline properties for this specific port.</span></span> <span data-ttu-id="f4614-144">单击**帮助**对话框中的配置说明。</span><span class="sxs-lookup"><span data-stu-id="f4614-144">Click **Help** in the dialog box for configuration instructions.</span></span>|  
    |<span data-ttu-id="f4614-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="f4614-145">**Receive pipeline**</span></span>|<span data-ttu-id="f4614-146">从下拉列表中选择处理通过此端口接收的消息的管道。</span><span class="sxs-lookup"><span data-stu-id="f4614-146">From the drop-down list, select the pipeline that processes messages received through this port.</span></span> <span data-ttu-id="f4614-147">对通过此管道接收的消息的响应也将通过此管道发送。</span><span class="sxs-lookup"><span data-stu-id="f4614-147">Responses to messages received through this pipeline will also be sent through this pipeline.</span></span> <span data-ttu-id="f4614-148">选择管道后，你可以单击旁边的省略号 (**...**) 按钮以显示**配置管道**对话框中，你在其中配置为此特定端口的每个实例管道属性。</span><span class="sxs-lookup"><span data-stu-id="f4614-148">After you select the pipeline, you can click the adjacent ellipsis (**…**) button to display the **Configure Pipeline** dialog box, where you configure per-instance pipeline properties for this specific port.</span></span> <span data-ttu-id="f4614-149">此属性仅对要求响应端口可见。</span><span class="sxs-lookup"><span data-stu-id="f4614-149">This property is visible only for Solicit-Response ports.</span></span>|  
  
5.  <span data-ttu-id="f4614-150">如果您创建请求-响应发送端口，在左窗格中，单击**入站映射**并执行以下操作，根据需要重复如果你想要添加多个映射：</span><span class="sxs-lookup"><span data-stu-id="f4614-150">If you are creating a solicit-response send port, in the left pane, click **Inbound Maps** and do the following, repeating as necessary if you want to add multiple maps:</span></span>  
  
    |<span data-ttu-id="f4614-151">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f4614-151">Use this</span></span>|<span data-ttu-id="f4614-152">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f4614-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4614-153">**源文档**</span><span class="sxs-lookup"><span data-stu-id="f4614-153">**Source Document**</span></span>|<span data-ttu-id="f4614-154">从下拉列表中选择入站映射的源文档。</span><span class="sxs-lookup"><span data-stu-id="f4614-154">From the drop-down list, select the source document for the inbound map.</span></span> <span data-ttu-id="f4614-155">一个发送端口可以具有多个映射，但是每个映射应具有唯一的源文档。</span><span class="sxs-lookup"><span data-stu-id="f4614-155">A send port may have more than one map, but each map should have a unique source document.</span></span>|  
    |<span data-ttu-id="f4614-156">**地图**</span><span class="sxs-lookup"><span data-stu-id="f4614-156">**Map**</span></span>|<span data-ttu-id="f4614-157">从下拉列表中选择与源文档和目标文档关联的映射。</span><span class="sxs-lookup"><span data-stu-id="f4614-157">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
    |<span data-ttu-id="f4614-158">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="f4614-158">**Target Document**</span></span>|<span data-ttu-id="f4614-159">从下拉列表中选择入站映射的目标文档。</span><span class="sxs-lookup"><span data-stu-id="f4614-159">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
6.  <span data-ttu-id="f4614-160">在左窗格中，单击**出站映射**并执行以下操作，根据需要重复如果你想要添加多个映射：</span><span class="sxs-lookup"><span data-stu-id="f4614-160">In the left pane, click **Outbound Maps** and do the following, repeating as necessary if you want to add multiple maps:</span></span>  
  
    |<span data-ttu-id="f4614-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f4614-161">Use this</span></span>|<span data-ttu-id="f4614-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f4614-162">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4614-163">**源文档**</span><span class="sxs-lookup"><span data-stu-id="f4614-163">**Source Document**</span></span>|<span data-ttu-id="f4614-164">从下拉列表中选择出站映射的源文档。</span><span class="sxs-lookup"><span data-stu-id="f4614-164">From the drop-down list, select the source document for the outbound map.</span></span>|  
    |<span data-ttu-id="f4614-165">**地图**</span><span class="sxs-lookup"><span data-stu-id="f4614-165">**Map**</span></span>|<span data-ttu-id="f4614-166">从下拉列表中选择与源文档和目标文档关联的映射。</span><span class="sxs-lookup"><span data-stu-id="f4614-166">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
    |<span data-ttu-id="f4614-167">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="f4614-167">**Target Document**</span></span>|<span data-ttu-id="f4614-168">从下拉列表中选择出站映射的目标文档。</span><span class="sxs-lookup"><span data-stu-id="f4614-168">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
7.  <span data-ttu-id="f4614-169">完成配置发送端口，则单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4614-169">When finished configuring the send port, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4614-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4614-170">See Also</span></span>  
 <span data-ttu-id="f4614-171">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="f4614-171">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="f4614-172">[管理管道](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="f4614-172">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 [<span data-ttu-id="f4614-173">管理映射</span><span class="sxs-lookup"><span data-stu-id="f4614-173">Managing Maps</span></span>](../core/managing-maps.md)