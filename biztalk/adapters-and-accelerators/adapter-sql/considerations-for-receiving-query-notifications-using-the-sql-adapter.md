---
title: "使用 SQL 适配器接收查询通知的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d7aa9eadc5e639e56cc526bfd5763abc432a4f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a><span data-ttu-id="a5fa7-102">使用 SQL 适配器接收查询通知的注意事项</span><span class="sxs-lookup"><span data-stu-id="a5fa7-102">Considerations for Receiving Query Notifications Using the SQL adapter</span></span>
<span data-ttu-id="a5fa7-103">本主题提供一些注意事项和最佳实践，在使用时需要牢记[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 数据库接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-103">This topic provides some considerations and best practices to keep in mind while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notifications from a SQL Server database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="a5fa7-104">使用该适配器可在收到通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="a5fa7-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="a5fa7-105">你必须考虑以下方法时使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收查询通知：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-105">You must consider the following while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notifications:</span></span>  
  
-   <span data-ttu-id="a5fa7-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收查询通知，然后只需将交给通知适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] receives the query notification from SQL Server, and then simply passes on the notification to the adapter clients.</span></span> <span data-ttu-id="a5fa7-107">适配器不区分不同的操作的通知 （即，适配器没有任何信息是用于插入操作或更新操作的一个特定的通知）。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-107">The adapter does not distinguish between the notifications for different operations (i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation).</span></span>  
  
-   <span data-ttu-id="a5fa7-108">该操作所影响的记录数不影响操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="a5fa7-109">例如，无论包含几个记录插入、 更新或删除的 SQL Server 数据库表中，适配器客户端接收只有一个通知消息。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-109">For example, regardless of the number of records inserted, updated, or deleted in a SQL Server database table, the adapter client receives only one notification message.</span></span>  
  
-   <span data-ttu-id="a5fa7-110">我们建议适配器客户端应用程序包含的逻辑来解释收到来自 SQL Server 的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-110">We recommend that the adapter client application contain the logic to interpret the type of notification received from SQL Server.</span></span> <span data-ttu-id="a5fa7-111">可以通过提取的信息，确定通知类型**\<信息\>**收到的通知消息元素。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-111">The notification type can be determined by extracting the information from, the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="a5fa7-112">下面是收到有关插入操作的通知消息示例：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-112">Here’s an example of a notification message received for an Insert operation:</span></span>  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>  
      <Source>Data</Source>  
      <Type>Change</Type>  
    </Notification>  
    ```  
  
     <span data-ttu-id="a5fa7-113">请注意内的值**\<信息\>**元素。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="a5fa7-114">此值提供有关为其接收到通知消息的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="a5fa7-115">你的应用程序应具有用于提取内的值的功能**\<信息\>**元素，然后根据值，执行后续的任务。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="a5fa7-116">主题[过程通知消息，以完成 SQL 使用 BizTalk Server 中的特定任务](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)说明了如何提取的值在**\<信息\>**元素.</span><span class="sxs-lookup"><span data-stu-id="a5fa7-116">The topic [Process Notification Messages to complete Specific Tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span> <span data-ttu-id="a5fa7-117">执行类似任务的详细的教程也是在[教程 2： 员工-采购订单过程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-117">A detailed tutorial that performs similar tasks is also available at [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="a5fa7-118">理想情况下，客户端应用程序收到特定记录的通知后，该记录应更新，以便不会收到其他通知。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-118">Ideally, after the client application receives a notification for a specific record, that record should be updated so that additional notifications are not received.</span></span> <span data-ttu-id="a5fa7-119">例如，考虑**员工**表具有**状态**列。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-119">For example, consider an **Employee** table that has a **Status** column.</span></span> <span data-ttu-id="a5fa7-120">为所有新记录插入到**员工**表中的值**状态**列始终是"0"因此表看起来类似于以下：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-120">For all new records inserted into the **Employee** table, the value in the **Status** column is always “0” so the table will look like the following:</span></span>  
  
    |<span data-ttu-id="a5fa7-121">员工姓名</span><span class="sxs-lookup"><span data-stu-id="a5fa7-121">Employee Name</span></span>|<span data-ttu-id="a5fa7-122">状态</span><span class="sxs-lookup"><span data-stu-id="a5fa7-122">Status</span></span>|  
    |-------------------|------------|  
    |<span data-ttu-id="a5fa7-123">John</span><span class="sxs-lookup"><span data-stu-id="a5fa7-123">John</span></span>|<span data-ttu-id="a5fa7-124">0</span><span class="sxs-lookup"><span data-stu-id="a5fa7-124">0</span></span>|  
  
     <span data-ttu-id="a5fa7-125">若要接收新插入的记录的通知，适配器客户端将设置**NotificatonStatement**绑定属性作为：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-125">To receive notifications for the newly inserted record, the adapter client will set the **NotificatonStatement** binding property as:</span></span>  
  
    ```  
    SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a5fa7-126">具体而言，你必须指定在此所示的语句中的列名称 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-126">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="a5fa7-127">此外，你必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-127">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="a5fa7-128">例如，dbo。员工。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-128">For example, dbo.Employee.</span></span>  
  
     <span data-ttu-id="a5fa7-129">在收到通知，客户端应用程序必须重置的值**状态**为"1"的列，以便通知语句不会再次运行的记录。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-129">After receiving the notification, the client application must reset the value of the **Status** column to “1” so that the notification statement does not operate on the record again.</span></span> <span data-ttu-id="a5fa7-130">若要实现此目的，客户端应用程序必须执行更新操作上**员工**表。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-130">To achieve this, the client application must perform an Update operation on the **Employee** table.</span></span> <span data-ttu-id="a5fa7-131">更新操作后，该记录中**员工**表将如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-131">After the Update operation, the same record in the **Employee** table will look like the following:</span></span>  
  
    |<span data-ttu-id="a5fa7-132">员工姓名</span><span class="sxs-lookup"><span data-stu-id="a5fa7-132">Employee Name</span></span>|<span data-ttu-id="a5fa7-133">状态</span><span class="sxs-lookup"><span data-stu-id="a5fa7-133">Status</span></span>|  
    |-------------------|------------|  
    |<span data-ttu-id="a5fa7-134">John</span><span class="sxs-lookup"><span data-stu-id="a5fa7-134">John</span></span>|<span data-ttu-id="a5fa7-135">1</span><span class="sxs-lookup"><span data-stu-id="a5fa7-135">1</span></span>|  
  
     <span data-ttu-id="a5fa7-136">有趣的是，更新操作会再次发送通知到适配器客户端并将再次重复整个过程，因此，客户端应用程序必须具有所需的逻辑，以放弃此类不需要发送的通知。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-136">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again, therefore, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
-   <span data-ttu-id="a5fa7-137">如果**NotifyOnListenerStart**绑定属性为 true 时，每次接收位置启动时，适配器客户端将收到一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-137">If the **NotifyOnListenerStart** binding property is true, the adapter client will receive a notification message every time the receive location starts.</span></span> <span data-ttu-id="a5fa7-138">有关如何使用绑定属性和解释通知消息的详细信息，请参阅[接收查询通知后接收位置分解 SQL 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-138">For more information on how to use the binding property and interpret the notification message, see [Receive Query Notifications After a Receive Location Breakdown in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="a5fa7-139">典型的业务流程，用于接收通知</span><span class="sxs-lookup"><span data-stu-id="a5fa7-139">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="a5fa7-140">本部分概述了用于接收通知使用的典型的业务流程流[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-140">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="a5fa7-141">必须执行业务流程的第一件事是确定接收通知的类型包括：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-141">The first thing that the orchestration must do is to determine the type of notification received, including:</span></span>  
  
    -   <span data-ttu-id="a5fa7-142">是否接收位置重新启动后收到通知。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-142">Whether the notification was received after a receive location restarts.</span></span>  
  
    -   <span data-ttu-id="a5fa7-143">是否通知已接收到操作数据库表，如 Insert、 Update 或 Delete。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-143">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="a5fa7-144">业务流程必须包括**表达式**形状，并在其中 xpath 查询来确定收到的消息类型。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-144">The orchestration must include an **Expression** shape, and within that, an xpath query to decide what kind of message is received.</span></span>  
  
2.  <span data-ttu-id="a5fa7-145">在通知后类型确定，业务流程必须包括决策块执行基于收到的通知的类型的特定操作。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-145">After the notification type is determined, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="a5fa7-146">若要实现此目的，业务流程必须包括**确定**形状，其中包括**规则**块和**Else**块：</span><span class="sxs-lookup"><span data-stu-id="a5fa7-146">To achieve this, the orchestration must include a **Decide** shape, which includes a **Rule** block and an **Else** block:</span></span>  
  
    -   <span data-ttu-id="a5fa7-147">在**规则**块中，你必须指定条件，并且然后包括业务流程形状，以便执行某些操作，如果满足该条件。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-147">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span>  
  
    -   <span data-ttu-id="a5fa7-148">在**Else**块中，你必须包括业务流程形状，以便执行某些操作，如果条件为*不*满足。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-148">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
 <span data-ttu-id="a5fa7-149">中介绍的上述要求的详细信息[过程通知消息，以完成 SQL 使用 BizTalk Server 中的特定任务](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-149">Details of the preceding requirements are described in [Process Notification Messages to complete Specific Tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span> <span data-ttu-id="a5fa7-150">详细的教程还会显示在[教程 2： 员工-采购订单过程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a5fa7-150">A detailed tutorial is also available in [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>