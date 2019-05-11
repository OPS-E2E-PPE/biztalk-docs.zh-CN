---
title: 步骤 3：为插入通知添加筛选器 |Microsoft Docs
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
ms.openlocfilehash: e49f4f914771a26618dd92126b49143492d627b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367929"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a><span data-ttu-id="1290a-102">步骤 3：为插入通知添加筛选器</span><span class="sxs-lookup"><span data-stu-id="1290a-102">Step 3: Add a Filter for Insert Notifications</span></span>
<span data-ttu-id="1290a-103">![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="1290a-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="1290a-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="1290a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="1290a-105">**目标：** 在此步骤中，您将判定形状添加到业务流程，以筛选用于插入操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="1290a-105">**Objective:** In this step, you add a Decide shape to the orchestration to filter for notification messages for Insert operation.</span></span> <span data-ttu-id="1290a-106">仅当所接收的通知是插入类型，会执行业务流程中的后续操作。</span><span class="sxs-lookup"><span data-stu-id="1290a-106">Subsequent operations in the orchestration are performed only if the notification received is of Insert type.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1290a-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="1290a-107">Prerequisites</span></span>  
 <span data-ttu-id="1290a-108">你必须已完成[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。</span><span class="sxs-lookup"><span data-stu-id="1290a-108">You must have completed [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
### <a name="to-filter-for-notification-messages"></a><span data-ttu-id="1290a-109">若要筛选的通知消息</span><span class="sxs-lookup"><span data-stu-id="1290a-109">To filter for notification messages</span></span>  
  
1.  <span data-ttu-id="1290a-110">添加**判定**到该业务流程形状后面**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="1290a-110">Add a **Decide** shape to the orchestration, after the **Expression** shape.</span></span> <span data-ttu-id="1290a-111">从工具箱拖动**判定**下方的连接线上的形状**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="1290a-111">From the Toolbox, drag the **Decide** shape onto the connecting line directly below the **Expression** shape.</span></span>  
  
     <span data-ttu-id="1290a-112">**判定**形状将展开以显示对应于的分支**如果**语句 **(Rule_1)** 分支和**Else**语句。</span><span class="sxs-lookup"><span data-stu-id="1290a-112">The **Decide** shape expands to show a branch for the **If** statement **(Rule_1)** and a branch for the **Else** statement.</span></span>  
  
2.  <span data-ttu-id="1290a-113">在设计图面上，右键单击**判定**形状，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="1290a-113">On the design surface, right-click the **Decide** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="1290a-114">在中**属性**窗格**判定**形状，在**名称**属性中，键入`CheckNotification`。</span><span class="sxs-lookup"><span data-stu-id="1290a-114">In the **Properties** pane for the **Decide** shape, in the **Name** property, type `CheckNotification`.</span></span>  
  
4.  <span data-ttu-id="1290a-115">在设计图面上，右键单击**Rule_1**形状 (内**判定**形状)，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="1290a-115">On the design surface, right-click the **Rule_1** shape (inside of the **Decide** shape), and then click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="1290a-116">在中**属性**窗格**Rule_1**，在**名称**属性中，键入**插入**。</span><span class="sxs-lookup"><span data-stu-id="1290a-116">In the **Properties** pane for **Rule_1**, in the **Name** property, type **Insert**.</span></span>  
  
6.  <span data-ttu-id="1290a-117">右键单击**插入**形状，然后依次**编辑布尔表达式**。</span><span class="sxs-lookup"><span data-stu-id="1290a-117">Right-click the **Insert** shape, and then click **Edit Boolean Expression**.</span></span>  
  
7.  <span data-ttu-id="1290a-118">在 BizTalk 表达式编辑器中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1290a-118">In the BizTalk Expression Editor, type the following:</span></span>  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     <span data-ttu-id="1290a-119">这种情况告诉业务流程以便才执行后续操作中的值**NotificationType**变量是**插入**。</span><span class="sxs-lookup"><span data-stu-id="1290a-119">This condition tells the orchestration to perform subsequent operations only if the value in the **NotificationType** variable is **Insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1290a-120">添加此变量在[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)从收到从 SQL Server 数据库的通知消息中提取的通知类型。</span><span class="sxs-lookup"><span data-stu-id="1290a-120">You added this variable in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) to extract the type of notification from the notification message received from the SQL Server database.</span></span>  
  
8.  <span data-ttu-id="1290a-121">下图显示了与正在进行中业务流程**判定**包含的形状。</span><span class="sxs-lookup"><span data-stu-id="1290a-121">The following figure shows the in-progress orchestration with the **Decide** shape included.</span></span>  
  
     <span data-ttu-id="1290a-122">![将判定形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span><span class="sxs-lookup"><span data-stu-id="1290a-122">![Add a Decide shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="1290a-123">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="1290a-123">What did I just do?</span></span>  
 <span data-ttu-id="1290a-124">在此步骤中，您添加了**判定**形状来筛选要接收通知所针对的插入操作时，才执行后续操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="1290a-124">In this step, you added a **Decide** shape to filter the notification messages to perform subsequent operations only if the notification received is for Insert operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1290a-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1290a-125">Next Steps</span></span>  
 <span data-ttu-id="1290a-126">在下一步，您添加业务流程形状来调用 UPDATE_EMPLOYE 员工表中，在存储过程中所述[第 3 课：执行存储的过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。</span><span class="sxs-lookup"><span data-stu-id="1290a-126">In the next step, you add orchestration shapes to invoke the UPDATE_EMPLOYE stored procedure on the Employee table, as described in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1290a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1290a-127">See Also</span></span>  
 <span data-ttu-id="1290a-128">[步骤 2：从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="1290a-128">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="1290a-129">第 2 课：接收和筛选通知</span><span class="sxs-lookup"><span data-stu-id="1290a-129">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)