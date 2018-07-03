---
title: 创建处理孤立或重复消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc4e6e8650f0da1446a48b5da8c8f7c2142af7bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997894"
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a><span data-ttu-id="3c5f5-102">创建处理孤立或重复消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="3c5f5-102">Creating a Send Port to Handle Orphan or Duplicate Messages</span></span>
<span data-ttu-id="3c5f5-103">本主题描述如何设置可用于删除孤立或重复消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-103">This topic describes how to set up a send port that you can use to delete orphan or duplicate messages.</span></span>  
  
 <span data-ttu-id="3c5f5-104">孤立或重复消息可能是个问题，如果 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公用业务流程完成处理该消息的第一个副本后收到一条消息的其他副本。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-104">Orphan or duplicate messages can be a problem if Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receives additional copies of a message after the public-process orchestration has completed processing the first copy of the message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3c5f5-105"> 将标记为重复这些消息并将它们挂起。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-105"> marks those messages as duplicates and suspends them.</span></span> <span data-ttu-id="3c5f5-106">您可以在 BizTalk 管理控制台中查看这些消息。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-106">You can view these messages in the BizTalk Administration Console.</span></span> <span data-ttu-id="3c5f5-107">有关 BizTalk 管理控制台的详细信息，请参阅"使用 BizTalk 管理控制台"中的 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-107">For more information about BizTalk Administration Console, see "Using the BizTalk Administration Console" in the BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="3c5f5-108">在您查看并删除孤立或重复的消息之前，这些消息将一直保存在 BizTalk 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-108">Orphan or duplicate messages remain in the BizTalk Administration Console until you review or delete them.</span></span> <span data-ttu-id="3c5f5-109">删除这些消息最有效的方法是设置具有特定筛选器的发送端口，这些筛选器针对孤立或重复的消息进行设置。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-109">The most effective way of deleting them is to set up a send port with filters set for orphan or duplicate messages.</span></span> <span data-ttu-id="3c5f5-110">您可以移动它们使用任何 BizTalk Server 中可用的运输方式。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-110">You can move them using any transportation means available in BizTalk Server.</span></span> <span data-ttu-id="3c5f5-111">例如，可以通过使用文件传输移动它们。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-111">For example, you can move them by using File transport.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3c5f5-112"> 将孤立或重复消息作为文件发送到硬盘上的位置。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-112"> sends the orphan or duplicate messages as files to a location on a hard disk.</span></span> <span data-ttu-id="3c5f5-113">这可使您轻松删除它们。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-113">This lets you to delete them easily.</span></span> <span data-ttu-id="3c5f5-114">该端口可处于登记并停止的状态，在这种情况下，所有发送到该端口的消息都将显示为在该发送端口下挂起。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-114">The port can be in the enlisted and stopped state, in which case all messages sent to it will show as suspended under that send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c5f5-115">除创建发送端口来处理重复/孤立的消息外，还可以创建特殊的管道组件从 MessageBox 数据库中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-115">Instead of creating a send port to handle duplicate/orphan messages, you can create a special pipeline component to delete these messages from the MessageBox database.</span></span> <span data-ttu-id="3c5f5-116">您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK 中的 FixMsg 组件作为模板，</span><span class="sxs-lookup"><span data-stu-id="3c5f5-116">You can use the FixMsg component in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK as a template.</span></span> <span data-ttu-id="3c5f5-117">您必须修改`IComponent.Execute`方法返回 null。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-117">You have to modify the `IComponent.Execute` method to return null.</span></span> <span data-ttu-id="3c5f5-118">这将导致[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]放弃发送到包含该组件的管道的任何消息。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-118">This causes [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to discard any message sent to a pipeline that contains the component.</span></span> <span data-ttu-id="3c5f5-119">您必须编译此管道组件并将其添加到发送管道，然后编译、部署该发送管道并为接收端口选择该发送管道。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-119">You have to compile this pipeline component and add it to a send pipeline, and then compile, deploy, and select the send pipeline for the sink port.</span></span> <span data-ttu-id="3c5f5-120">有关详细信息，请参阅"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]示例)"BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-120">For more information, see "CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Sample)" in BizTalk Server Help.</span></span>  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a><span data-ttu-id="3c5f5-121">创建处理孤立或重复消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="3c5f5-121">To create a send port to handle orphan or duplicate messages</span></span>  
  
1. <span data-ttu-id="3c5f5-122">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**BizTalk 浏览器**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-122">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
2. <span data-ttu-id="3c5f5-123">在 BizTalk 浏览器中，展开**BizTalk 管理数据库**，然后展开**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-123">In BizTalk Explorer, expand **BizTalk Management Database**, and then expand **Send Ports**.</span></span>  
  
3. <span data-ttu-id="3c5f5-124">右键单击**发送端口**，然后单击**添加发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-124">Right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
4. <span data-ttu-id="3c5f5-125">在创建新发送端口窗口中，选择**静态单向端口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-125">In the Create New Send Port window, select **Static One-Way Port**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="3c5f5-126">在静态单向发送端口属性窗口中**名称**框中，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-126">In the Static One-Way Send Port Properties window, in the **Name** box, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="3c5f5-127">在左窗格中，单击**传输**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-127">In the left pane, click **Transport**.</span></span> <span data-ttu-id="3c5f5-128">在右窗格中，单击**传输类型**，然后选择**文件**传输类型。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-128">In the right pane, click **Transport Type**, and select **FILE** for the transport type.</span></span> <span data-ttu-id="3c5f5-129">单击省略号按钮 （...） 下一步**地址 (URI)**，键入您的硬盘上的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-129">Click the ellipsis button (...) next to **Address (URI)**, type a location on your hard disk, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="3c5f5-130">在左窗格中，单击**发送**，单击**发送管道**，然后选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-130">In the left pane, click **Send**, click **Send Pipeline**, and then select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
8. <span data-ttu-id="3c5f5-131">在左窗格中，单击**筛选器和映射**，然后单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-131">In the left pane, click **Filters and Maps**, and then click **Filters**.</span></span>  
  
9. <span data-ttu-id="3c5f5-132">在右窗格中，在第一行的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**从下拉列表中，将保留**运算符**作为**==**，输入**True**有关**值**，然后选择**或**从下拉列表中为**组**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-132">On the first line in the right pane, for **Property**, select **Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage** from the drop-down list, leave the **Operator** as **==**, enter **True** for **Value**, and then select **Or** from the drop-down list for **Group**.</span></span>  
  
10. <span data-ttu-id="3c5f5-133">在右窗格中，在第二个行上的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**从下拉列表中，将保留**运算符**作为**==**，然后输入**True**有关**值**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-133">On the second line in the right pane, for **Property**, select **Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage** from the drop-down list, leave the **Operator** as **==**, and then enter **True** for **Value**.</span></span>  
  
11. <span data-ttu-id="3c5f5-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="3c5f5-135">在 BizTalk 浏览器中，右键单击该发送端口的名称，单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-135">In BizTalk Explorer, right-click the name of the send port, click **Enlist**.</span></span> <span data-ttu-id="3c5f5-136">登记发送端口后，右键单击该发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="3c5f5-136">After the send port has been enlisted, right-click the send port, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f5-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5f5-137">See Also</span></span>  
 [<span data-ttu-id="3c5f5-138">编程指南</span><span class="sxs-lookup"><span data-stu-id="3c5f5-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)