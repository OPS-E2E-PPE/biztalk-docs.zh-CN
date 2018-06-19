---
title: 步骤 1： 添加业务流程形状可以接收通知 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a33693a09d89acc5d1ad9e4514c7907b789cc75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223125"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a><span data-ttu-id="6b22d-102">步骤 1： 添加业务流程形状可以接收通知</span><span class="sxs-lookup"><span data-stu-id="6b22d-102">Step 1: Add Orchestration Shapes to Receive Notification</span></span>
<span data-ttu-id="6b22d-103">![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="6b22d-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="6b22d-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="6b22d-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="6b22d-105">**目标：** 在此步骤中，添加业务流程形状可以接收的更改通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="6b22d-105">**Objective:** In this step, you add orchestration shapes to receive notification for changes to the **Employee** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b22d-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="6b22d-106">Prerequisites</span></span>  
 <span data-ttu-id="6b22d-107">你必须已完成中的步骤[第 1 课： 生成架构和创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="6b22d-107">You must have completed the steps in [Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).</span></span>  
  
### <a name="to-receive-notification-messages"></a><span data-ttu-id="6b22d-108">若要接收通知消息</span><span class="sxs-lookup"><span data-stu-id="6b22d-108">To receive notification messages</span></span>  
  
1.  <span data-ttu-id="6b22d-109">打开 BizTalk 业务流程， **EmployeeOrch.odx**，你在中添加[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="6b22d-109">Open the BizTalk orchestration, **EmployeeOrch.odx**, you added in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
2.  <span data-ttu-id="6b22d-110">添加**接收**形状上的与业务流程。</span><span class="sxs-lookup"><span data-stu-id="6b22d-110">Add a **Receive** shape to the orchestration.</span></span> <span data-ttu-id="6b22d-111">从工具箱的业务流程，将拖动**接收**形状变为业务流程设计图面，并将其放到指示之间的空间**开始**（绿色圆圈） 和**结束**（红色八边形） 形状。</span><span class="sxs-lookup"><span data-stu-id="6b22d-111">From the orchestration Toolbox, drag the **Receive** shape to the orchestration design surface, and drop it into the space indicated between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
    |<span data-ttu-id="6b22d-112">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="6b22d-112">Set this property</span></span>|<span data-ttu-id="6b22d-113">为此值</span><span class="sxs-lookup"><span data-stu-id="6b22d-113">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="6b22d-114">**Activate**</span><span class="sxs-lookup"><span data-stu-id="6b22d-114">**Activate**</span></span>|<span data-ttu-id="6b22d-115">True</span><span class="sxs-lookup"><span data-stu-id="6b22d-115">True</span></span>|  
    |<span data-ttu-id="6b22d-116">**消息**</span><span class="sxs-lookup"><span data-stu-id="6b22d-116">**Message**</span></span>|<span data-ttu-id="6b22d-117">NotifyReceive</span><span class="sxs-lookup"><span data-stu-id="6b22d-117">NotifyReceive</span></span>|  
    |<span data-ttu-id="6b22d-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="6b22d-118">**Name**</span></span>|<span data-ttu-id="6b22d-119">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="6b22d-119">ReceiveNotification</span></span>|  
  
3.  <span data-ttu-id="6b22d-120">添加单向接收端口与业务流程。</span><span class="sxs-lookup"><span data-stu-id="6b22d-120">Add a one-way receive port to the orchestration.</span></span> <span data-ttu-id="6b22d-121">将使用此端口以接收通知消息从 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="6b22d-121">You will use this port to receive notification messages from the SQL Server database.</span></span> <span data-ttu-id="6b22d-122">设置以下属性的端口。</span><span class="sxs-lookup"><span data-stu-id="6b22d-122">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="6b22d-123">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="6b22d-123">Set this property</span></span>|<span data-ttu-id="6b22d-124">为此值</span><span class="sxs-lookup"><span data-stu-id="6b22d-124">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="6b22d-125">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="6b22d-125">**Communication Direction**</span></span>|<span data-ttu-id="6b22d-126">Receive</span><span class="sxs-lookup"><span data-stu-id="6b22d-126">Receive</span></span>|  
    |<span data-ttu-id="6b22d-127">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="6b22d-127">**Communication Pattern**</span></span>|<span data-ttu-id="6b22d-128">单向</span><span class="sxs-lookup"><span data-stu-id="6b22d-128">One-Way</span></span>|  
    |<span data-ttu-id="6b22d-129">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="6b22d-129">**Identifier**</span></span>|<span data-ttu-id="6b22d-130">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="6b22d-130">ReceiveNotification</span></span>|  
  
     <span data-ttu-id="6b22d-131">此外，从到 Operation_1 更改操作名称**通知**。</span><span class="sxs-lookup"><span data-stu-id="6b22d-131">Also, change the operation name from Operation_1 to **Notification**.</span></span>  
  
4.  <span data-ttu-id="6b22d-132">连接**ReceiveNotification**端口到**ReceiveNotification**操作形状。</span><span class="sxs-lookup"><span data-stu-id="6b22d-132">Connect the **ReceiveNotification** port to the **ReceiveNotification** action shape.</span></span> <span data-ttu-id="6b22d-133">业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。</span><span class="sxs-lookup"><span data-stu-id="6b22d-133">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b22d-134">在此步骤中，使用拖放方法将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="6b22d-134">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="6b22d-135">您可以改用操作形状的操作属性，将操作形状连接到端口。</span><span class="sxs-lookup"><span data-stu-id="6b22d-135">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
5.  <span data-ttu-id="6b22d-136">下图显示正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="6b22d-136">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="6b22d-137">![业务流程以接收通知消息](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span><span class="sxs-lookup"><span data-stu-id="6b22d-137">![Orchestration to receive notification messages](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="6b22d-138">内容回顾</span><span class="sxs-lookup"><span data-stu-id="6b22d-138">What did I just do?</span></span>  
 <span data-ttu-id="6b22d-139">在此步骤中，你将添加业务流程形状，并接收端口从 SQL Server 数据库中接收通知。</span><span class="sxs-lookup"><span data-stu-id="6b22d-139">In this step, you added orchestration shapes and receive port to receive notification from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6b22d-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b22d-140">Next Steps</span></span>  
 <span data-ttu-id="6b22d-141">将表达式形状添加到业务流程中所述提取的一种从 SQL Server 数据库中，接收的通知[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。</span><span class="sxs-lookup"><span data-stu-id="6b22d-141">You add an expression shape to the orchestration to extract the type of notification received from the SQL Server database, as described in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b22d-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b22d-142">See Also</span></span>  
 <span data-ttu-id="6b22d-143">[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="6b22d-143">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="6b22d-144">第 2 课： 接收和筛选器通知</span><span class="sxs-lookup"><span data-stu-id="6b22d-144">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)