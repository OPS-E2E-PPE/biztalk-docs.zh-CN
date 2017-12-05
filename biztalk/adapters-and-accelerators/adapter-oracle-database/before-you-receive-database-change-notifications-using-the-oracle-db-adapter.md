---
title: "接收更改通知使用数据库的 Oracle 数据库适配器注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 206439b9-0408-4fbb-80e3-cfda2f5a89a5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0d6c99de2a24975faef3a10059f4bbb10d28a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-database-adapter"></a><span data-ttu-id="3ca2f-102">接收更改通知使用数据库的 Oracle 数据库适配器的注意事项</span><span class="sxs-lookup"><span data-stu-id="3ca2f-102">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>
<span data-ttu-id="3ca2f-103">本主题提供一些注意事项和最佳做法，你必须使用时应牢记[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以接收从 Oracle 数据库的数据库通知。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-103">This topic provides some considerations and best practices that you must keep in mind while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive database notifications from an Oracle database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="3ca2f-104">使用该适配器可在收到通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="3ca2f-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="3ca2f-105">你必须考虑以下方法时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-105">You must consider the following while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive query notifications.</span></span>  
  
-   <span data-ttu-id="3ca2f-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]只需将传递通知，它从 Oracle 数据库时，接收到适配器客户端上。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] simply passes on the notification, which it receives from the Oracle database, to the adapter clients.</span></span> <span data-ttu-id="3ca2f-107">适配器不区分不同的操作的通知即、 特定通知是用于插入操作或更新操作，该适配器不具有任何信息。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-107">The adapter does not distinguish between the notifications for different operations, i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation.</span></span>  
  
-   <span data-ttu-id="3ca2f-108">该操作所影响的记录数不影响操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="3ca2f-109">例如，而不考虑在 Oracle 数据库表中插入的记录数，适配器客户端收到一个通知消息。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-109">For example, irrespective of the number of records inserted in an Oracle database table, the adapter clients receive only one notification message.</span></span>  
  
-   <span data-ttu-id="3ca2f-110">我们建议适配器客户端应用程序包含的逻辑来解释从 Oracle 数据库接收的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-110">We recommend that the adapter client application contain the logic to interpret the kind of notification received from the Oracle database.</span></span> <span data-ttu-id="3ca2f-111">适配器客户端应用程序可以做到这一点提取中的信息**\<信息\>**收到的通知消息元素。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-111">The adapter client applications can do so by extracting the information in the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="3ca2f-112">下面是收到有关插入操作的通知消息的示例。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-112">Here’s an example of a notification message received for an Insert operation.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
  
    ```  
  
     <span data-ttu-id="3ca2f-113">请注意内的值**\<信息\>**元素。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="3ca2f-114">此值提供有关为其接收到通知消息的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="3ca2f-115">你的应用程序应具有用于提取内的值的功能**\<信息\>**元素，然后根据值，执行后续的任务。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="3ca2f-116">主题[处理通知消息来完成 Oracle 数据库中的特定任务](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)说明了如何提取的值在**\<信息\>**元素。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-116">The topic [Processing Notification Messages to complete Specific Tasks in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span>  
  
-   <span data-ttu-id="3ca2f-117">理想情况下，客户端应用程序接收的通知后，它应更新为其已收到通知，以便后续通知不是针对同一条记录的记录。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-117">Ideally, after the client application receives a notification, it should update the record for which the notification is already received so that the subsequent notifications are not for the same record.</span></span> <span data-ttu-id="3ca2f-118">例如，考虑**ACCOUNTACTIVITY**表具有**处理**列。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-118">For example, consider an **ACCOUNTACTIVITY** table that has a **Processed** column.</span></span> <span data-ttu-id="3ca2f-119">为所有新记录插入到**ACCOUNTACTIVITY**表中的值**处理**列始终是 ' n '。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-119">For all new records inserted into the **ACCOUNTACTIVITY** table, the value in the **Processed** column is always ‘n’.</span></span> <span data-ttu-id="3ca2f-120">例如，在插入操作中的记录之后**ACCOUNTACTIVITY**表将如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ca2f-120">For example, after an insert operation, the records in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
    |<span data-ttu-id="3ca2f-121">帐户事务 ID</span><span class="sxs-lookup"><span data-stu-id="3ca2f-121">Account Transaction ID</span></span>|<span data-ttu-id="3ca2f-122">已处理</span><span class="sxs-lookup"><span data-stu-id="3ca2f-122">Processed</span></span>|  
    |----------------------------|---------------|  
    |<span data-ttu-id="3ca2f-123">10001</span><span class="sxs-lookup"><span data-stu-id="3ca2f-123">10001</span></span>|n|  
  
     <span data-ttu-id="3ca2f-124">若要获取新插入的记录的通知，适配器客户端将设置**NotificationStatement**绑定属性作为：</span><span class="sxs-lookup"><span data-stu-id="3ca2f-124">To get notifications for the newly inserted record, the adapter client will set the **NotificationStatement** binding property as:</span></span>  
  
    ```  
    SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
    ```  
  
     <span data-ttu-id="3ca2f-125">之后，接收通知时，客户端应用程序必须设置的值的**处理**为 y 的列，以便通知语句未以已被告知有关的记录的运行。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-125">After, receiving the notification, the client application must set the value of the **Processed** column to ‘y’ so that the notification statement does not operate on the record that was already notified for.</span></span> <span data-ttu-id="3ca2f-126">因此，若要实现此目的，客户端应用程序必须执行更新操作上**ACCOUNTACTIVITY**表。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-126">So, to achieve this, the client application must perform an Update operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="3ca2f-127">更新操作后，该记录中**ACCOUNTACTIVITY**表将如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ca2f-127">After the Update operation, the same record in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
    |<span data-ttu-id="3ca2f-128">帐户事务 ID</span><span class="sxs-lookup"><span data-stu-id="3ca2f-128">Account Transaction ID</span></span>|<span data-ttu-id="3ca2f-129">已处理</span><span class="sxs-lookup"><span data-stu-id="3ca2f-129">Processed</span></span>|  
    |----------------------------|---------------|  
    |<span data-ttu-id="3ca2f-130">10001</span><span class="sxs-lookup"><span data-stu-id="3ca2f-130">10001</span></span>|<span data-ttu-id="3ca2f-131">y</span><span class="sxs-lookup"><span data-stu-id="3ca2f-131">y</span></span>|  
  
     <span data-ttu-id="3ca2f-132">有趣的是，更新操作将再次向适配器客户端发送通知，并且将再次重复整个过程。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-132">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again.</span></span> <span data-ttu-id="3ca2f-133">因此，客户端应用程序必须具有所需的逻辑，以放弃此类不需要发送的通知。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-133">So, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
-   <span data-ttu-id="3ca2f-134">如果**NotifyOnListenerStart**绑定属性为 true 时，每次接收位置启动时该适配器将将通知发送到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-134">If the **NotifyOnListenerStart** binding property is true, the adapter will send a notification to the adapter client every time the receive location starts.</span></span> <span data-ttu-id="3ca2f-135">有关如何使用绑定属性和解释通知消息的详细信息，请参阅[接收 Oracle 数据库更改通知后接收位置分解](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-135">For more information on how to use the binding property and interpret the notification message, see [Receiving Oracle Database Change Notifications After a Receive Location Breakdown](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="3ca2f-136">典型的业务流程，用于接收通知</span><span class="sxs-lookup"><span data-stu-id="3ca2f-136">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="3ca2f-137">本部分概述了用于接收通知使用的典型的业务流程流[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-137">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
1.  <span data-ttu-id="3ca2f-138">必须执行业务流程的第一个操作是通知的检查收到的类型。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-138">The first thing that the orchestration must do is to check the kind of notification received.</span></span> <span data-ttu-id="3ca2f-139">若要检查的事项为：</span><span class="sxs-lookup"><span data-stu-id="3ca2f-139">The things to check for are:</span></span>  
  
    -   <span data-ttu-id="3ca2f-140">接收位置重新启动是否收到通知。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-140">Whether the notification was received for the receive location restart.</span></span>  
  
    -   <span data-ttu-id="3ca2f-141">是否通知已接收到操作数据库表，如 Insert、 Update 或 Delete。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-141">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="3ca2f-142">业务流程必须包括**表达式**形状，并在其中接收 xpath 查询，以确定哪种类型的消息。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-142">The orchestration must include an **Expression** shape, and within that an xpath query, to decide what kind of message is received.</span></span>  
  
2.  <span data-ttu-id="3ca2f-143">可用的通知类型后，业务流程必须包括决策块执行基于收到的通知的类型的特定操作。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-143">After the notification type is available, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="3ca2f-144">若要实现此目的，业务流程必须包括**确定**形状。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-144">To achieve this, the orchestration must include a **Decide** shape.</span></span> <span data-ttu-id="3ca2f-145">**确定**形状组成**规则**块和**Else**块。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-145">The **Decide** shape consists of a **Rule** block and an **Else** block.</span></span> <span data-ttu-id="3ca2f-146">在**规则**块中，你必须指定条件，并且然后包括业务流程形状，以便执行某些操作，如果满足该条件。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-146">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span> <span data-ttu-id="3ca2f-147">在**Else**块中，你必须包括业务流程形状，以便执行某些操作，如果条件为*不*满足。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-147">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
 <span data-ttu-id="3ca2f-148">中详细描述了上述建议[处理通知消息来完成使用 BizTalk Server 的 Oracle 数据库中的特定任务](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca2f-148">The preceding recommendations are described in detail in [Processing Notification Messages to complete Specific Tasks in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca2f-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ca2f-149">See Also</span></span>  
 [<span data-ttu-id="3ca2f-150">使用 BizTalk Server 的接收 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="3ca2f-150">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)