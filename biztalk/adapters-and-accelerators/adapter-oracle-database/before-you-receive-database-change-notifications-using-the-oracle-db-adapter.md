---
title: 接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 206439b9-0408-4fbb-80e3-cfda2f5a89a5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7237037794168ffb136c95734582b3df95db48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015190"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-database-adapter"></a><span data-ttu-id="e748e-102">接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="e748e-102">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>
<span data-ttu-id="e748e-103">本主题提供的一些注意事项和最佳实践，您在使用时必须牢记于心[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收数据库通知。</span><span class="sxs-lookup"><span data-stu-id="e748e-103">This topic provides some considerations and best practices that you must keep in mind while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive database notifications from an Oracle database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="e748e-104">使用适配器来接收通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="e748e-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="e748e-105">你必须考虑以下方法同时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="e748e-105">You must consider the following while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive query notifications.</span></span>  
  
- <span data-ttu-id="e748e-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]仅传递通知，它接收从 Oracle 数据库时，向适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="e748e-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] simply passes on the notification, which it receives from the Oracle database, to the adapter clients.</span></span> <span data-ttu-id="e748e-107">适配器不会区分不同操作的通知即，一个特定的通知是用于插入操作或更新操作，适配器不具有任何信息。</span><span class="sxs-lookup"><span data-stu-id="e748e-107">The adapter does not distinguish between the notifications for different operations, i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation.</span></span>  
  
- <span data-ttu-id="e748e-108">该操作所影响的记录数不会影响操作的通知消息。</span><span class="sxs-lookup"><span data-stu-id="e748e-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="e748e-109">例如，而不考虑为 Oracle 数据库表中插入的记录数，适配器客户端收到一个通知消息。</span><span class="sxs-lookup"><span data-stu-id="e748e-109">For example, irrespective of the number of records inserted in an Oracle database table, the adapter clients receive only one notification message.</span></span>  
  
- <span data-ttu-id="e748e-110">我们建议适配器客户端应用程序包含的逻辑来解释的类型从 Oracle 数据库接收的通知。</span><span class="sxs-lookup"><span data-stu-id="e748e-110">We recommend that the adapter client application contain the logic to interpret the kind of notification received from the Oracle database.</span></span> <span data-ttu-id="e748e-111">适配器客户端应用程序可以执行操作来提取中的信息**\<信息\>** 收到的通知消息的元素。</span><span class="sxs-lookup"><span data-stu-id="e748e-111">The adapter client applications can do so by extracting the information in the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="e748e-112">下面是收到了插入操作的通知消息的示例。</span><span class="sxs-lookup"><span data-stu-id="e748e-112">Here’s an example of a notification message received for an Insert operation.</span></span>  
  
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
  
   <span data-ttu-id="e748e-113">请注意内的值**\<信息\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="e748e-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="e748e-114">此值提供为其接收通知消息操作的信息。</span><span class="sxs-lookup"><span data-stu-id="e748e-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="e748e-115">你的应用程序应具有的功能中的值中提取**\<信息\>** 元素，然后根据值，执行后续任务。</span><span class="sxs-lookup"><span data-stu-id="e748e-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="e748e-116">本主题[处理通知消息，以完成特定任务在 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)说明了如何在值中提取**\<信息\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="e748e-116">The topic [Processing Notification Messages to complete Specific Tasks in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span>  
  
- <span data-ttu-id="e748e-117">理想情况下，客户端应用程序收到通知后，它应更新为其已收到通知，以便后续通知不能用于同一条记录的记录。</span><span class="sxs-lookup"><span data-stu-id="e748e-117">Ideally, after the client application receives a notification, it should update the record for which the notification is already received so that the subsequent notifications are not for the same record.</span></span> <span data-ttu-id="e748e-118">例如，考虑**ACCOUNTACTIVITY**具有表**处理**列。</span><span class="sxs-lookup"><span data-stu-id="e748e-118">For example, consider an **ACCOUNTACTIVITY** table that has a **Processed** column.</span></span> <span data-ttu-id="e748e-119">对于所有新记录插入到**ACCOUNTACTIVITY**表中的值**处理**列始终是 ' n '。</span><span class="sxs-lookup"><span data-stu-id="e748e-119">For all new records inserted into the **ACCOUNTACTIVITY** table, the value in the **Processed** column is always ‘n’.</span></span> <span data-ttu-id="e748e-120">例如，在插入操作，在中记录**ACCOUNTACTIVITY**表将如下所示：</span><span class="sxs-lookup"><span data-stu-id="e748e-120">For example, after an insert operation, the records in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
  |<span data-ttu-id="e748e-121">帐户事务 ID</span><span class="sxs-lookup"><span data-stu-id="e748e-121">Account Transaction ID</span></span>|<span data-ttu-id="e748e-122">已处理</span><span class="sxs-lookup"><span data-stu-id="e748e-122">Processed</span></span>|  
  |----------------------------|---------------|  
  |<span data-ttu-id="e748e-123">10001</span><span class="sxs-lookup"><span data-stu-id="e748e-123">10001</span></span>|<span data-ttu-id="e748e-124">n</span><span class="sxs-lookup"><span data-stu-id="e748e-124">n</span></span>|  
  
   <span data-ttu-id="e748e-125">若要获取新插入记录的通知，适配器客户端将设置**NotificationStatement**绑定属性设置为：</span><span class="sxs-lookup"><span data-stu-id="e748e-125">To get notifications for the newly inserted record, the adapter client will set the **NotificationStatement** binding property as:</span></span>  
  
  ```  
  SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
  ```  
  
   <span data-ttu-id="e748e-126">之后，接收通知，客户端应用程序必须设置的值**处理**为 y 的列，以便通知语句不会进行的记录的有关已通知的操作。</span><span class="sxs-lookup"><span data-stu-id="e748e-126">After, receiving the notification, the client application must set the value of the **Processed** column to ‘y’ so that the notification statement does not operate on the record that was already notified for.</span></span> <span data-ttu-id="e748e-127">因此，若要实现此目的，客户端应用程序必须执行更新操作上**ACCOUNTACTIVITY**表。</span><span class="sxs-lookup"><span data-stu-id="e748e-127">So, to achieve this, the client application must perform an Update operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="e748e-128">更新操作后，该记录中**ACCOUNTACTIVITY**表将如下所示：</span><span class="sxs-lookup"><span data-stu-id="e748e-128">After the Update operation, the same record in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
  |<span data-ttu-id="e748e-129">帐户事务 ID</span><span class="sxs-lookup"><span data-stu-id="e748e-129">Account Transaction ID</span></span>|<span data-ttu-id="e748e-130">已处理</span><span class="sxs-lookup"><span data-stu-id="e748e-130">Processed</span></span>|  
  |----------------------------|---------------|  
  |<span data-ttu-id="e748e-131">10001</span><span class="sxs-lookup"><span data-stu-id="e748e-131">10001</span></span>|<span data-ttu-id="e748e-132">y</span><span class="sxs-lookup"><span data-stu-id="e748e-132">y</span></span>|  
  
   <span data-ttu-id="e748e-133">有趣的是，更新操作将再次向适配器客户端发送通知，并且将再次重复整个过程。</span><span class="sxs-lookup"><span data-stu-id="e748e-133">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again.</span></span> <span data-ttu-id="e748e-134">因此，客户端应用程序必须具有所需的逻辑，若要放弃此类不需要发送的通知。</span><span class="sxs-lookup"><span data-stu-id="e748e-134">So, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
- <span data-ttu-id="e748e-135">如果**NotifyOnListenerStart**绑定属性为 true 时，每次启动接收位置时适配器会将通知发送到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="e748e-135">If the **NotifyOnListenerStart** binding property is true, the adapter will send a notification to the adapter client every time the receive location starts.</span></span> <span data-ttu-id="e748e-136">有关如何使用绑定属性和解释该通知消息的详细信息，请参阅[接收 Oracle 数据库更改通知后接收位置中断](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)。</span><span class="sxs-lookup"><span data-stu-id="e748e-136">For more information on how to use the binding property and interpret the notification message, see [Receiving Oracle Database Change Notifications After a Receive Location Breakdown](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="e748e-137">典型的业务流程接收通知</span><span class="sxs-lookup"><span data-stu-id="e748e-137">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="e748e-138">本部分概述了用于接收通知使用典型的业务流程流[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e748e-138">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
1. <span data-ttu-id="e748e-139">业务流程必须执行的第一件事是通知的检查收到的类型。</span><span class="sxs-lookup"><span data-stu-id="e748e-139">The first thing that the orchestration must do is to check the kind of notification received.</span></span> <span data-ttu-id="e748e-140">要检查的事项包括：</span><span class="sxs-lookup"><span data-stu-id="e748e-140">The things to check for are:</span></span>  
  
   - <span data-ttu-id="e748e-141">是否收到通知的接收位置重新启动。</span><span class="sxs-lookup"><span data-stu-id="e748e-141">Whether the notification was received for the receive location restart.</span></span>  
  
   - <span data-ttu-id="e748e-142">是否通知已接收到操作数据库表，例如插入、 更新或删除。</span><span class="sxs-lookup"><span data-stu-id="e748e-142">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="e748e-143">业务流程必须包括**表达式**形状，并在其中接收一个 xpath 查询，以确定哪种消息。</span><span class="sxs-lookup"><span data-stu-id="e748e-143">The orchestration must include an **Expression** shape, and within that an xpath query, to decide what kind of message is received.</span></span>  
  
2. <span data-ttu-id="e748e-144">通知类型可用后，业务流程必须包括判定块，以执行特定操作的通知接收到的类型。</span><span class="sxs-lookup"><span data-stu-id="e748e-144">After the notification type is available, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="e748e-145">若要实现此目的，该业务流程必须包括**判定**形状。</span><span class="sxs-lookup"><span data-stu-id="e748e-145">To achieve this, the orchestration must include a **Decide** shape.</span></span> <span data-ttu-id="e748e-146">**判定**形状组成**规则**块和一个**Else**块。</span><span class="sxs-lookup"><span data-stu-id="e748e-146">The **Decide** shape consists of a **Rule** block and an **Else** block.</span></span> <span data-ttu-id="e748e-147">内**规则**块中，必须指定的条件，然后将包含业务流程形状来执行某些操作，如果满足该条件。</span><span class="sxs-lookup"><span data-stu-id="e748e-147">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span> <span data-ttu-id="e748e-148">内**Else**块中，必须包括业务流程形状来执行某些操作，如果条件为*不*满足。</span><span class="sxs-lookup"><span data-stu-id="e748e-148">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
   <span data-ttu-id="e748e-149">中详细介绍之前提出的建议[处理通知消息，以完成特定任务在 Oracle 数据库中使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="e748e-149">The preceding recommendations are described in detail in [Processing Notification Messages to complete Specific Tasks in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e748e-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="e748e-150">See Also</span></span>  
 [<span data-ttu-id="e748e-151">使用 BizTalk Server 的 Oracle 数据库更改通知的接收</span><span class="sxs-lookup"><span data-stu-id="e748e-151">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)