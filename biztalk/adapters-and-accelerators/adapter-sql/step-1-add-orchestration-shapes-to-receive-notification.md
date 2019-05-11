---
title: 第 1 步：添加业务流程形状以接收通知 |Microsoft Docs
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
ms.openlocfilehash: 981ab324745840a4ba15e7d552af3f9ff965e3fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367798"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a><span data-ttu-id="3547e-102">第 1 步：添加业务流程形状以接收通知</span><span class="sxs-lookup"><span data-stu-id="3547e-102">Step 1: Add Orchestration Shapes to Receive Notification</span></span>
<span data-ttu-id="3547e-103">![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="3547e-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="3547e-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="3547e-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="3547e-105">**目标：** 在此步骤中，添加业务流程形状可以接收的更改通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="3547e-105">**Objective:** In this step, you add orchestration shapes to receive notification for changes to the **Employee** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3547e-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="3547e-106">Prerequisites</span></span>  
 <span data-ttu-id="3547e-107">你必须完成中的步骤[第 1 课：生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3547e-107">You must have completed the steps in [Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).</span></span>  
  
### <a name="to-receive-notification-messages"></a><span data-ttu-id="3547e-108">若要接收通知消息</span><span class="sxs-lookup"><span data-stu-id="3547e-108">To receive notification messages</span></span>  
  
1.  <span data-ttu-id="3547e-109">打开 BizTalk 业务流程， **EmployeeOrch.odx**，你在中添加[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="3547e-109">Open the BizTalk orchestration, **EmployeeOrch.odx**, you added in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
2.  <span data-ttu-id="3547e-110">添加**接收**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="3547e-110">Add a **Receive** shape to the orchestration.</span></span> <span data-ttu-id="3547e-111">从业务流程工具箱中拖动**接收**形状变为业务流程设计图面上，并将其放入之间指示空间**开始**（绿色圆形） 和**最终**（红色八边形） 形状。</span><span class="sxs-lookup"><span data-stu-id="3547e-111">From the orchestration Toolbox, drag the **Receive** shape to the orchestration design surface, and drop it into the space indicated between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
    |<span data-ttu-id="3547e-112">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="3547e-112">Set this property</span></span>|<span data-ttu-id="3547e-113">为此值</span><span class="sxs-lookup"><span data-stu-id="3547e-113">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="3547e-114">**Activate**</span><span class="sxs-lookup"><span data-stu-id="3547e-114">**Activate**</span></span>|<span data-ttu-id="3547e-115">True</span><span class="sxs-lookup"><span data-stu-id="3547e-115">True</span></span>|  
    |<span data-ttu-id="3547e-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="3547e-116">**Message**</span></span>|<span data-ttu-id="3547e-117">NotifyReceive</span><span class="sxs-lookup"><span data-stu-id="3547e-117">NotifyReceive</span></span>|  
    |<span data-ttu-id="3547e-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="3547e-118">**Name**</span></span>|<span data-ttu-id="3547e-119">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="3547e-119">ReceiveNotification</span></span>|  
  
3.  <span data-ttu-id="3547e-120">添加一个单向接收端口与业务流程。</span><span class="sxs-lookup"><span data-stu-id="3547e-120">Add a one-way receive port to the orchestration.</span></span> <span data-ttu-id="3547e-121">此端口将用于从 SQL Server 数据库中接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="3547e-121">You will use this port to receive notification messages from the SQL Server database.</span></span> <span data-ttu-id="3547e-122">设置端口的以下属性。</span><span class="sxs-lookup"><span data-stu-id="3547e-122">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="3547e-123">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="3547e-123">Set this property</span></span>|<span data-ttu-id="3547e-124">为此值</span><span class="sxs-lookup"><span data-stu-id="3547e-124">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="3547e-125">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="3547e-125">**Communication Direction**</span></span>|<span data-ttu-id="3547e-126">Receive</span><span class="sxs-lookup"><span data-stu-id="3547e-126">Receive</span></span>|  
    |<span data-ttu-id="3547e-127">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="3547e-127">**Communication Pattern**</span></span>|<span data-ttu-id="3547e-128">单向</span><span class="sxs-lookup"><span data-stu-id="3547e-128">One-Way</span></span>|  
    |<span data-ttu-id="3547e-129">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="3547e-129">**Identifier**</span></span>|<span data-ttu-id="3547e-130">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="3547e-130">ReceiveNotification</span></span>|  
  
     <span data-ttu-id="3547e-131">此外，更改操作名称从为 Operation_1**通知**。</span><span class="sxs-lookup"><span data-stu-id="3547e-131">Also, change the operation name from Operation_1 to **Notification**.</span></span>  
  
4.  <span data-ttu-id="3547e-132">连接**ReceiveNotification**到端口**ReceiveNotification**操作形状。</span><span class="sxs-lookup"><span data-stu-id="3547e-132">Connect the **ReceiveNotification** port to the **ReceiveNotification** action shape.</span></span> <span data-ttu-id="3547e-133">在业务流程设计器中，在设计图面上，将的操作形状的端口到相应的绿色句柄的绿色箭头状手柄。</span><span class="sxs-lookup"><span data-stu-id="3547e-133">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3547e-134">在此步骤中，使用拖放方法将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="3547e-134">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="3547e-135">您可以改用操作形状的操作属性来操作形状连接到端口。</span><span class="sxs-lookup"><span data-stu-id="3547e-135">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
5.  <span data-ttu-id="3547e-136">下图显示了正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="3547e-136">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="3547e-137">![接收通知消息的业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span><span class="sxs-lookup"><span data-stu-id="3547e-137">![Orchestration to receive notification messages](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="3547e-138">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="3547e-138">What did I just do?</span></span>  
 <span data-ttu-id="3547e-139">在此步骤中，添加业务流程形状和接收端口以从 SQL Server 数据库中接收通知。</span><span class="sxs-lookup"><span data-stu-id="3547e-139">In this step, you added orchestration shapes and receive port to receive notification from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3547e-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3547e-140">Next Steps</span></span>  
 <span data-ttu-id="3547e-141">将表达式形状添加到业务流程，以提取 SQL Server 数据库中，从收到的通知的类型，如中所述[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。</span><span class="sxs-lookup"><span data-stu-id="3547e-141">You add an expression shape to the orchestration to extract the type of notification received from the SQL Server database, as described in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3547e-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="3547e-142">See Also</span></span>  
 <span data-ttu-id="3547e-143">[步骤 2：从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="3547e-143">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="3547e-144">第 2 课：接收和筛选通知</span><span class="sxs-lookup"><span data-stu-id="3547e-144">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)