---
title: 第 2 步：从通知消息中提取通知类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cca1b44daa45f5502957fa783cdf5e4e2ebca1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367785"
---
# <a name="step-2-extract-notification-type-from-notification-message"></a><span data-ttu-id="940c3-102">第 2 步：从通知消息中提取通知类型</span><span class="sxs-lookup"><span data-stu-id="940c3-102">Step 2: Extract Notification Type from Notification Message</span></span>
<span data-ttu-id="940c3-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="940c3-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="940c3-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="940c3-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="940c3-105">**目标：** 在此步骤中，添加表达式形状中提取的 SQL Server 数据库从收到的通知类型。</span><span class="sxs-lookup"><span data-stu-id="940c3-105">**Objective:** In this step, you add an expression shape to extract the type of notification received from the SQL Server database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="940c3-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="940c3-106">Prerequisites</span></span>  
 <span data-ttu-id="940c3-107">你必须已完成[步骤 1:添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="940c3-107">You must have completed [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a><span data-ttu-id="940c3-108">若要从通知消息中提取通知类型</span><span class="sxs-lookup"><span data-stu-id="940c3-108">To extract the notification type from the notification message</span></span>  
  
1.  <span data-ttu-id="940c3-109">将变量添加到 BizTalk 业务流程中创建[步骤 1:添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="940c3-109">Add a variable to the BizTalk orchestration you created in [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
    1.  <span data-ttu-id="940c3-110">从业务流程视图中，右键单击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="940c3-110">From the Orchestration View, right-click **Variables**, and then click **New Variable**.</span></span>  
  
    2.  <span data-ttu-id="940c3-111">右键单击该新变量**Variable_1**，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="940c3-111">Right-click the new variable, **Variable_1**, and click **Properties Window**.</span></span> <span data-ttu-id="940c3-112">设置变量的以下属性。</span><span class="sxs-lookup"><span data-stu-id="940c3-112">Set the following properties for the variable.</span></span>  
  
        |<span data-ttu-id="940c3-113">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="940c3-113">Set this property</span></span>|<span data-ttu-id="940c3-114">为此值</span><span class="sxs-lookup"><span data-stu-id="940c3-114">To this value</span></span>|  
        |-----------------------|-------------------|  
        |<span data-ttu-id="940c3-115">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="940c3-115">**Identifier**</span></span>|<span data-ttu-id="940c3-116">NotificationType</span><span class="sxs-lookup"><span data-stu-id="940c3-116">NotificationType</span></span>|  
        |<span data-ttu-id="940c3-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="940c3-117">**Type**</span></span>|<span data-ttu-id="940c3-118">System.String</span><span class="sxs-lookup"><span data-stu-id="940c3-118">System.String</span></span>|  
  
2.  <span data-ttu-id="940c3-119">添加**表达式**到 BizTalk 业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="940c3-119">Add an **Expression** shape to the BizTalk orchestration.</span></span> <span data-ttu-id="940c3-120">从业务流程工具箱中拖动**表达式**形状变为业务流程设计图面上，然后将其放置**接收**形状</span><span class="sxs-lookup"><span data-stu-id="940c3-120">From the orchestration Toolbox, drag the **Expression** shape to the orchestration design surface, and drop it after the **Receive** shape</span></span>  
  
     <span data-ttu-id="940c3-121">内**表达式**形状，您将添加 xpath 查询来提取从 SQL Server 收到的通知消息的类型。</span><span class="sxs-lookup"><span data-stu-id="940c3-121">Within the **Expression** shape, you will add an xpath query to extract the type of notification message received from SQL Server.</span></span> <span data-ttu-id="940c3-122">然后再创建 xpath 查询，让我们看一下通知消息的格式。</span><span class="sxs-lookup"><span data-stu-id="940c3-122">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="940c3-123">典型的通知消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="940c3-123">A typical notification message resembles the following:</span></span>  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  <span data-ttu-id="940c3-124">正如您看到的通知类型有关的信息中有可用`<info>`标记，在父级内的`<Notification>`标记。</span><span class="sxs-lookup"><span data-stu-id="940c3-124">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="940c3-125">因此，添加以下 xpath 查询中的**表达式**形状：</span><span class="sxs-lookup"><span data-stu-id="940c3-125">So, add the following xpath query within the **Expression** shape:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="940c3-126">在这里， **NotificationType**是你创建用于存储提取由 xpath 查询的值的变量。</span><span class="sxs-lookup"><span data-stu-id="940c3-126">Here, **NotificationType** is the variable you created to store the value extracted by the xpath query.</span></span> <span data-ttu-id="940c3-127">**NotifyReceive**是你在中创建的消息[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="940c3-127">**NotifyReceive** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) to receive notification messages.</span></span>  
  
4.  <span data-ttu-id="940c3-128">下图显示了与正在进行中业务流程**表达式**包含的形状。</span><span class="sxs-lookup"><span data-stu-id="940c3-128">The following figure shows the in-progress orchestration with the **Expression** shape included.</span></span>  
  
     <span data-ttu-id="940c3-129">![将表达式形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span><span class="sxs-lookup"><span data-stu-id="940c3-129">![Add an Expression shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="940c3-130">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="940c3-130">What did I just do?</span></span>  
 <span data-ttu-id="940c3-131">在此步骤中，您添加了**表达式**形状以提取 SQL Server 数据库从收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="940c3-131">In this step, you added an **Expression** shape to extract the kind of notification received from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="940c3-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="940c3-132">Next Steps</span></span>  
 <span data-ttu-id="940c3-133">如中所述添加判定形状来为插入通知筛选[步骤 3:为插入通知添加筛选器](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="940c3-133">You add a Decide shape to filter for Insert notifications, as described in [Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940c3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="940c3-134">See Also</span></span>  
 <span data-ttu-id="940c3-135">[步骤 1：添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span><span class="sxs-lookup"><span data-stu-id="940c3-135">[Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span></span>  
 <span data-ttu-id="940c3-136">[步骤 3：为插入通知添加筛选器](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="940c3-136">[Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span></span>  
 [<span data-ttu-id="940c3-137">第 2 课：接收和筛选通知</span><span class="sxs-lookup"><span data-stu-id="940c3-137">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)