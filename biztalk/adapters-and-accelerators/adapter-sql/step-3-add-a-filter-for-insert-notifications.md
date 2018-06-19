---
title: 步骤 3： 添加筛选器插入通知 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223261"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a><span data-ttu-id="dac40-102">步骤 3： 添加筛选器插入通知</span><span class="sxs-lookup"><span data-stu-id="dac40-102">Step 3: Add a Filter for Insert Notifications</span></span>
<span data-ttu-id="dac40-103">![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="dac40-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="dac40-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="dac40-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="dac40-105">**目标：** 在此步骤中，你可以将确定形状添加到要用于插入操作的通知消息的筛选器业务流程。</span><span class="sxs-lookup"><span data-stu-id="dac40-105">**Objective:** In this step, you add a Decide shape to the orchestration to filter for notification messages for Insert operation.</span></span> <span data-ttu-id="dac40-106">仅当所接收的通知属于插入类型执行业务流程中的后续操作。</span><span class="sxs-lookup"><span data-stu-id="dac40-106">Subsequent operations in the orchestration are performed only if the notification received is of Insert type.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dac40-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="dac40-107">Prerequisites</span></span>  
 <span data-ttu-id="dac40-108">你必须已完成[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。</span><span class="sxs-lookup"><span data-stu-id="dac40-108">You must have completed [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
### <a name="to-filter-for-notification-messages"></a><span data-ttu-id="dac40-109">若要筛选的通知消息</span><span class="sxs-lookup"><span data-stu-id="dac40-109">To filter for notification messages</span></span>  
  
1.  <span data-ttu-id="dac40-110">添加**确定**形状变为业务流程之后,**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="dac40-110">Add a **Decide** shape to the orchestration, after the **Expression** shape.</span></span> <span data-ttu-id="dac40-111">从工具箱中，拖动**确定**形状拖到所连接的正下方线**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="dac40-111">From the Toolbox, drag the **Decide** shape onto the connecting line directly below the **Expression** shape.</span></span>  
  
     <span data-ttu-id="dac40-112">**确定**形状展开以显示有关分支**如果**语句 **(Rule_1)** 和有关分支**Else**语句。</span><span class="sxs-lookup"><span data-stu-id="dac40-112">The **Decide** shape expands to show a branch for the **If** statement **(Rule_1)** and a branch for the **Else** statement.</span></span>  
  
2.  <span data-ttu-id="dac40-113">在设计图面上，右键单击**确定**形状，并依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="dac40-113">On the design surface, right-click the **Decide** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="dac40-114">在**属性**窗格**确定**形状，在**名称**属性中，键入`CheckNotification`。</span><span class="sxs-lookup"><span data-stu-id="dac40-114">In the **Properties** pane for the **Decide** shape, in the **Name** property, type `CheckNotification`.</span></span>  
  
4.  <span data-ttu-id="dac40-115">在设计图面上，右键单击**Rule_1**形状 (内**确定**形状)，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="dac40-115">On the design surface, right-click the **Rule_1** shape (inside of the **Decide** shape), and then click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="dac40-116">在**属性**窗格**Rule_1**中**名称**属性中，键入**插入**。</span><span class="sxs-lookup"><span data-stu-id="dac40-116">In the **Properties** pane for **Rule_1**, in the **Name** property, type **Insert**.</span></span>  
  
6.  <span data-ttu-id="dac40-117">右键单击**插入**形状，并依次**编辑布尔表达式**。</span><span class="sxs-lookup"><span data-stu-id="dac40-117">Right-click the **Insert** shape, and then click **Edit Boolean Expression**.</span></span>  
  
7.  <span data-ttu-id="dac40-118">在 BizTalk 表达式编辑器中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="dac40-118">In the BizTalk Expression Editor, type the following:</span></span>  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     <span data-ttu-id="dac40-119">这种情况告诉业务流程，以便才执行后续操作中的值**NotificationType**变量是**插入**。</span><span class="sxs-lookup"><span data-stu-id="dac40-119">This condition tells the orchestration to perform subsequent operations only if the value in the **NotificationType** variable is **Insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dac40-120">添加此变量在[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)从 SQL Server 数据库从收到的通知消息中提取通知的类型。</span><span class="sxs-lookup"><span data-stu-id="dac40-120">You added this variable in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) to extract the type of notification from the notification message received from the SQL Server database.</span></span>  
  
8.  <span data-ttu-id="dac40-121">下图显示与正在进行中业务流程**确定**包含的形状。</span><span class="sxs-lookup"><span data-stu-id="dac40-121">The following figure shows the in-progress orchestration with the **Decide** shape included.</span></span>  
  
     <span data-ttu-id="dac40-122">![将确定形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span><span class="sxs-lookup"><span data-stu-id="dac40-122">![Add a Decide shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="dac40-123">内容回顾</span><span class="sxs-lookup"><span data-stu-id="dac40-123">What did I just do?</span></span>  
 <span data-ttu-id="dac40-124">在此步骤中，您将添加**确定**形状来筛选要对于 Insert 操作是在收到通知时，才执行后续操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="dac40-124">In this step, you added a **Decide** shape to filter the notification messages to perform subsequent operations only if the notification received is for Insert operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dac40-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dac40-125">Next Steps</span></span>  
 <span data-ttu-id="dac40-126">在下一步，你添加业务流程形状来调用 UPDATE_EMPLOYE 员工表中，存储过程中所述[第 3 课： 执行存储过程向选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。</span><span class="sxs-lookup"><span data-stu-id="dac40-126">In the next step, you add orchestration shapes to invoke the UPDATE_EMPLOYE stored procedure on the Employee table, as described in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac40-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dac40-127">See Also</span></span>  
 <span data-ttu-id="dac40-128">[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="dac40-128">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="dac40-129">第 2 课： 接收和筛选器通知</span><span class="sxs-lookup"><span data-stu-id="dac40-129">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)