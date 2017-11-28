---
title: "处理通知消息，以完成特定任务在 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bddeb5a-3819-40cc-aae0-c49963f0beb1
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b3cf9f99a4a7a2151b9b4f07d076ffb4bc1ec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-e-business-suite"></a><span data-ttu-id="7e945-102">处理通知邮件完成 Oracle E-business Suite 中的特定任务</span><span class="sxs-lookup"><span data-stu-id="7e945-102">Process notification messages to complete specific tasks in Oracle E-Business Suite</span></span>
<span data-ttu-id="7e945-103">你可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收对 Oracle 数据库表的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-103">You can use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications for changes to the Oracle database tables.</span></span> <span data-ttu-id="7e945-104">但是，该适配器仅向你发送通知某些记录已插入、 更新或删除某些数据库表中。</span><span class="sxs-lookup"><span data-stu-id="7e945-104">However, the adapter only sends you a notification that some records were inserted, updated, or deleted in a certain database table.</span></span> <span data-ttu-id="7e945-105">这些记录的任何后续处理必须由客户端应用程序本身进行处理。</span><span class="sxs-lookup"><span data-stu-id="7e945-105">Any post-processing on those records must be handled by the client applications themselves.</span></span> <span data-ttu-id="7e945-106">本主题提供有关如何处理表根据从 Oracle 数据库接收的通知的类型中记录的基于方案的说明。</span><span class="sxs-lookup"><span data-stu-id="7e945-106">This topic presents a scenario-based description on how to process the records in the table based on the kind of notification received from the Oracle database.</span></span>  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a><span data-ttu-id="7e945-107">收到通知后执行后续操作的方案</span><span class="sxs-lookup"><span data-stu-id="7e945-107">Scenarios for Performing Subsequent Actions After Receiving Notification</span></span>  
 <span data-ttu-id="7e945-108">以下是几个适配器客户端必须在其中执行某些后通知任务的场景。</span><span class="sxs-lookup"><span data-stu-id="7e945-108">Following are a couple of scenarios in which the adapter clients must perform certain post-notification tasks.</span></span>  
  
-   <span data-ttu-id="7e945-109">**方案 1。**</span><span class="sxs-lookup"><span data-stu-id="7e945-109">**Scenario 1.**</span></span> <span data-ttu-id="7e945-110">请考虑适配器客户端必须执行某些任务根据从 Oracle 数据库接收的通知的类型的位置的方案。</span><span class="sxs-lookup"><span data-stu-id="7e945-110">Consider a scenario where the adapter client must perform certain tasks based on the kind of notification you receive from the Oracle database.</span></span> <span data-ttu-id="7e945-111">例如，如果在表"B"中插入记录客户端应用程序，就必须更新表"A"中的记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-111">For example, the client application must update the records in table “A” if records are inserted in table “B”.</span></span> <span data-ttu-id="7e945-112">同样，客户端应用程序必须从表"B"中删除记录如果从表"A"中删除记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-112">Similarly, the client application must delete records from table “A” if records are deleted from table “B”.</span></span>  
  
     <span data-ttu-id="7e945-113">收到的通知消息在此方案中，适配器客户端必须提取要决定是否通知已为插入操作或删除操作的通知类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-113">In this scenario, from the notification message received, the adapter clients must extract the type of notification to decide whether the notification was for an insert operation or a delete operation.</span></span> <span data-ttu-id="7e945-114">一旦查明通知类型是适配器客户端必须执行后续操作来插入或更新相关的表。</span><span class="sxs-lookup"><span data-stu-id="7e945-114">Once the notification type is ascertained, the adapter clients must perform subsequent actions to insert or update the relevant tables.</span></span>  
  
-   <span data-ttu-id="7e945-115">**方案 2。**</span><span class="sxs-lookup"><span data-stu-id="7e945-115">**Scenario 2.**</span></span> <span data-ttu-id="7e945-116">请考虑接收到的表的更改的通知消息的接收位置出现故障的方案。</span><span class="sxs-lookup"><span data-stu-id="7e945-116">Consider a scenario where the receive location that receives notification messages for changes to a table goes down.</span></span> <span data-ttu-id="7e945-117">接收位置停机时，某些记录会添加到表中。</span><span class="sxs-lookup"><span data-stu-id="7e945-117">While the receive location is down, some records are added to the table.</span></span> <span data-ttu-id="7e945-118">但是，这些记录的适配器客户端不接收任何通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-118">However, for these records the adapter client does not receive any notification.</span></span> <span data-ttu-id="7e945-119">备份接收位置时，该适配器将通过发送特定消息来通知客户端，然后客户端应用程序必须查找接收位置已关闭时插入数据库表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-119">When the receive location is back up, the adapter notifies the client by sending a specific message, and then the client application must look for all the records that were inserted in the database table while the receive location was down.</span></span>  
  
     <span data-ttu-id="7e945-120">收到的通知消息在此方案中，适配器客户端必须提取通知是到数据库表的更改或用于接收位置启动有关的信息。</span><span class="sxs-lookup"><span data-stu-id="7e945-120">In this scenario, from the notification message received, the adapter clients must extract the information regarding whether the notification is for a change to a database table or for the receive location starting.</span></span> <span data-ttu-id="7e945-121">如果通知所针对的接收位置开始，适配器客户端必须实现的逻辑来处理可能已插入、 更新，或接收位置已关闭时删除的记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-121">If the notification is for the receive location starting, the adapter clients must implement the logic to process the records that might have been inserted, updated, or deleted while the receive location was down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e945-122">这些是只为某些更好地了解如何使用通知功能中的列出的示例方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7e945-122">These are just some example scenarios that are listed for a better understanding of how to use the notification feature in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="7e945-123">但是，提取收到的通知的类型所需的任务的一组基本将为所有应用场景类似。</span><span class="sxs-lookup"><span data-stu-id="7e945-123">However, the basic set of tasks required to extract the type of notification received will be similar for all scenarios.</span></span> <span data-ttu-id="7e945-124">本主题将说明了如何从一条通知消息中提取通知的类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-124">This topic provides instructions on how to extract the type of notification from a notification message.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="7e945-125">本主题演示接收通知消息的方式</span><span class="sxs-lookup"><span data-stu-id="7e945-125">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="7e945-126">在本主题中，来演示如何处理通知消息，以执行后续任务中，我们假设一个基本方案适配器客户端其中使用 BizTalk 应用程序以接收对 ACCOUNTACTIVITY 表的更改的通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-126">In this topic, to demonstrate how to process notification messages to perform subsequent tasks, we consider a basic scenario where an adapter client uses BizTalk application to receive notification messages for changes to the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7e945-127">收到通知后，客户端将筛选器收到的通知的类型，并执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-127">After the notification is received, the client filters the type of notification received and performs subsequent action.</span></span> <span data-ttu-id="7e945-128">为了演示非常基本的方案，让我们考虑适配器客户端将通知消息复制到不同的文件夹，根据收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-128">To demonstrate a very basic scenario, let us consider that the adapter client copies the notification messages to different folders based on the kind of notification received.</span></span> <span data-ttu-id="7e945-129">因此：</span><span class="sxs-lookup"><span data-stu-id="7e945-129">Therefore:</span></span>  
  
-   <span data-ttu-id="7e945-130">如果通知消息是针对插入或更新操作，适配器客户端会将该邮件复制到 C:\TestLocation\UpsertNotification 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7e945-130">If the notification message is for an Insert or Update operation, the adapter client copies the message to C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="7e945-131">如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e945-131">If the notification message is for any other operation, for example Delete, the adapter client copies the message to C:\TestLocation\OtherNotificaiton folder.</span></span>  
  
 <span data-ttu-id="7e945-132">若要实现此方法作为 BizTalk 应用程序的一部分，业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="7e945-132">To achieve this as part of a BizTalk application, the orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="7e945-133">单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-133">A one-way receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="7e945-134">表达式形状包含 xpath 查询来提取有关收到的通知消息的类型的信息。</span><span class="sxs-lookup"><span data-stu-id="7e945-134">An Expression shape that contains an xpath query to extract the information about the kind of notification message received.</span></span>  
  
-   <span data-ttu-id="7e945-135">要包含在业务流程中的决策块判定形状。</span><span class="sxs-lookup"><span data-stu-id="7e945-135">A Decide shape to include a decision block in the orchestration.</span></span> <span data-ttu-id="7e945-136">在此决策块中，应用程序决定要执行的后续操作基于收到的通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-136">In this decision block, the application decides on what subsequent operations to perform based on the notification message received.</span></span>  
  
-   <span data-ttu-id="7e945-137">两个单向发送最后接收通知消息的端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-137">Two one-way send ports that finally receive the notification messages.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="7e945-138">与 Oracle E-business 适配器绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="7e945-138">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="7e945-139">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于配置从 Oracle E-business Suite 接收通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-139">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="7e945-140">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7e945-140">You must specify these binding properties when configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e945-141">你可以选择在生成的架构时指定这些绑定属性**通知**操作，即使它不是强制性。</span><span class="sxs-lookup"><span data-stu-id="7e945-141">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="7e945-142">如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="7e945-142">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="7e945-143">你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF OracleEBS 接收属性已设置对绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-143">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-OracleEBS receive port with the binding properties already set.</span></span> <span data-ttu-id="7e945-144">有关创建使用绑定文件的 WCF 自定义或 WCF OracleEBS 端口的详细信息，请参阅[物理端口绑定使用端口绑定文件到 Oracle E-business Suite 配置](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-144">For more information about creating a WCF-custom or WCF-OracleEBS port using the binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
|<span data-ttu-id="7e945-145">绑定属性</span><span class="sxs-lookup"><span data-stu-id="7e945-145">Binding Property</span></span>|<span data-ttu-id="7e945-146">Description</span><span class="sxs-lookup"><span data-stu-id="7e945-146">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="7e945-147">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="7e945-147">**InboundOperationType**</span></span>|<span data-ttu-id="7e945-148">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-148">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="7e945-149">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="7e945-149">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="7e945-150">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="7e945-150">**NotificationPort**</span></span>|<span data-ttu-id="7e945-151">指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。</span><span class="sxs-lookup"><span data-stu-id="7e945-151">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="7e945-152">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="7e945-152">**NotificationStatement**</span></span>|<span data-ttu-id="7e945-153">指定用来注册查询通知的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="7e945-153">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="7e945-154">仅当指定的 SELECT 语句更改的结果集时，适配器获取一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-154">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="7e945-155">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="7e945-155">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="7e945-156">指定启动侦听器时，适配器是否发送到适配器客户端通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-156">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="7e945-157">有关这些属性的更完整说明，请参阅 [[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-157">For a more complete description of these properties, see [[Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="7e945-158">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="7e945-158">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read further.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a><span data-ttu-id="7e945-159">如何从 Oracle E-business Suite 接收通知消息</span><span class="sxs-lookup"><span data-stu-id="7e945-159">How to Receive Notification Messages from Oracle E-Business Suite</span></span>  
 <span data-ttu-id="7e945-160">执行对 Oracle E-business Suite 使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-160">Performing an operation on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to create Oracle E-Business Suite applications](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md).</span></span> <span data-ttu-id="7e945-161">若要配置的适配器以接收通知消息，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="7e945-161">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="7e945-162">创建 BizTalk 项目，然后生成架构**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-162">Create a BizTalk project, and then generate schema for the **Notification** inbound operation.</span></span> <span data-ttu-id="7e945-163">（可选） 你可以为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-163">Optionally, you can specify values for the **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="7e945-164">在从 Oracle E-business Suite 接收通知的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-164">Create a message in the BizTalk project for receiving notification from Oracle E-Business Suite.</span></span>  
  
3.  <span data-ttu-id="7e945-165">在前面部分所述创建一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="7e945-165">Create an orchestration as described in the preceding section.</span></span>  
  
4.  <span data-ttu-id="7e945-166">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7e945-166">Build and deploy the BizTalk project.</span></span>  
  
5.  <span data-ttu-id="7e945-167">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-167">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e945-168">对于入站操作，如接收通知消息，你必须仅配置单向的 WCF 自定义或 WCF OracleEBS 接收端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-168">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="7e945-169">双向接收入站操作不支持端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-169">Two-way receive ports are not supported for inbound operations.</span></span>  
  
6.  <span data-ttu-id="7e945-170">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e945-170">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="7e945-171">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="7e945-171">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="7e945-172">生成架构</span><span class="sxs-lookup"><span data-stu-id="7e945-172">Generating Schema</span></span>  
 <span data-ttu-id="7e945-173">必须生成的架构**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-173">You must generate the schema for the **Notification** inbound operation.</span></span> <span data-ttu-id="7e945-174">有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-174">For more information about how to generate the schema, see [Retrieving Metadata for Oracle E-Business Suite Operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span></span> <span data-ttu-id="7e945-175">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="7e945-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="7e945-176">如果你不想要指定的绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="7e945-176">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
 <span data-ttu-id="7e945-177">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="7e945-177">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="7e945-178">如果你不想要指定的绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="7e945-178">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="7e945-179">为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-179">Specify a value for **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="7e945-180">有关此绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-180">For more information about this binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="7e945-181">有关如何指定绑定属性的说明，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-181">For instructions on how to specify binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
2.  <span data-ttu-id="7e945-182">选择与具有协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="7e945-182">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="7e945-183">生成架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-183">Generate schema for the **Notification** operation.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="7e945-184">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="7e945-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="7e945-185">你在上一节中生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="7e945-185">The schema that you generated in the previous section describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="7e945-186">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="7e945-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="7e945-187">生成架构后，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。</span><span class="sxs-lookup"><span data-stu-id="7e945-187">After the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="7e945-188">对于本主题中，你必须创建一条消息从 Oracle 数据库接收通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-188">For this topic, you must create one message to receive notifications from the Oracle database.</span></span>  
  
 <span data-ttu-id="7e945-189">执行以下步骤以创建消息并将它们链接到架构。</span><span class="sxs-lookup"><span data-stu-id="7e945-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="7e945-190">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="7e945-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="7e945-191">BizTalk 项目中添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="7e945-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="7e945-192">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="7e945-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="7e945-193">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7e945-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="7e945-194">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="7e945-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="7e945-195">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="7e945-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="7e945-196">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="7e945-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="7e945-197">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="7e945-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="7e945-198">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7e945-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="7e945-199">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7e945-199">Use this</span></span>|<span data-ttu-id="7e945-200">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7e945-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7e945-201">Identifier</span><span class="sxs-lookup"><span data-stu-id="7e945-201">Identifier</span></span>|<span data-ttu-id="7e945-202">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="7e945-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="7e945-203">消息类型</span><span class="sxs-lookup"><span data-stu-id="7e945-203">Message Type</span></span>|<span data-ttu-id="7e945-204">从下拉列表中，展开**架构**，然后选择*Process_Notification.OracleEBSBinding.Notification*，其中*Process_Notification*是的名称你BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7e945-204">From the drop-down list, expand **Schemas**, and select *Process_Notification.OracleEBSBinding.Notification*, where *Process_Notification* is the name of your BizTalk project.</span></span> <span data-ttu-id="7e945-205">*OracleEBSBinding*是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-205">*OracleEBSBinding* is the schema generated for the **Notification** operation.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="7e945-206">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="7e945-206">Setting up the Orchestration</span></span>  
 <span data-ttu-id="7e945-207">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为从 Oracle 数据库接收通知消息，然后执行基于收到的通知的类型的任务。</span><span class="sxs-lookup"><span data-stu-id="7e945-207">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the Oracle database and then performing tasks based on the type of notification received.</span></span> <span data-ttu-id="7e945-208">在此业务流程，适配器接收基于 SELECT 语句为指定的通知消息**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-208">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="7e945-209">表达式形状中指定的 xpath 查询提取到变量中，通知的类型假设**NotificationType**。</span><span class="sxs-lookup"><span data-stu-id="7e945-209">The xpath query specified within the Expression shape extracts the type of notification into a variable, say **NotificationType**.</span></span> <span data-ttu-id="7e945-210">确定形状使用此变量中的值来确定接收通知的类型和采用的相应"路径"执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-210">The Decide shape uses the value in this variable to decide on the kind of notification received and takes the appropriate “path” to perform subsequent operations.</span></span> <span data-ttu-id="7e945-211">如前一部分所述，业务流程将执行以下操作，根据收到的通知消息的类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-211">As mentioned in the preceding section, the orchestration will perform the following operations based on the kind of notification message received.</span></span>  
  
-   <span data-ttu-id="7e945-212">如果通知消息是针对插入或更新操作，适配器客户端会将该邮件复制到 C:\TestLocation\UpsertNotification 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7e945-212">If the notification message is for an Insert or Update operation, the adapter client copies the message to C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="7e945-213">如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e945-213">If the notification message is for any other operation, for example Delete, the adapter client copies the message to C:\TestLocation\OtherNotificaiton folder.</span></span>  
  
 <span data-ttu-id="7e945-214">因此，您的业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="7e945-214">So, your orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="7e945-215">单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-215">A one-way receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="7e945-216">包含要提取的收到的通知类型 xpath 查询是表达式形状。</span><span class="sxs-lookup"><span data-stu-id="7e945-216">An Expression shape that contains an xpath query to extract the kind of notification received.</span></span>  
  
-   <span data-ttu-id="7e945-217">要包含在业务流程中的决策块判定形状。</span><span class="sxs-lookup"><span data-stu-id="7e945-217">A Decide shape to include a decision block in the orchestration.</span></span> <span data-ttu-id="7e945-218">在此决策块中，应用程序决定要执行的后续操作基于收到的通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-218">In this decision block, the application decides on what subsequent operations to perform based on the notification message received.</span></span>  
  
-   <span data-ttu-id="7e945-219">两个单向发送最后接收通知消息的端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-219">Two one-way send ports that finally receive the notification messages.</span></span>  
  
-   <span data-ttu-id="7e945-220">接收形状。</span><span class="sxs-lookup"><span data-stu-id="7e945-220">Receive shape.</span></span>  
  
 <span data-ttu-id="7e945-221">示例业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e945-221">A sample orchestration resembles the following:</span></span>  
  
 <span data-ttu-id="7e945-222">![业务流程执行 post &#45; 通知任务](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")</span><span class="sxs-lookup"><span data-stu-id="7e945-222">![Orchestration to perform post&#45;notification task](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="7e945-223">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="7e945-223">Adding Message Shapes</span></span>  
 <span data-ttu-id="7e945-224">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-224">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="7e945-225">中列出的名称**形状**列是在业务流程关系图中显示消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="7e945-225">The names listed in the **Shape** column are the names of the message shapes as displayed in the orchestration diagram.</span></span>  
  
|<span data-ttu-id="7e945-226">形状</span><span class="sxs-lookup"><span data-stu-id="7e945-226">Shape</span></span>|<span data-ttu-id="7e945-227">形状类型</span><span class="sxs-lookup"><span data-stu-id="7e945-227">Shape Type</span></span>|<span data-ttu-id="7e945-228">属性</span><span class="sxs-lookup"><span data-stu-id="7e945-228">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="7e945-229">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="7e945-229">ReceiveNotification</span></span>|<span data-ttu-id="7e945-230">Receive</span><span class="sxs-lookup"><span data-stu-id="7e945-230">Receive</span></span>|<span data-ttu-id="7e945-231">-将设置**名称**到*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="7e945-231">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="7e945-232">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="7e945-232">- Set **Activate** to *True*</span></span>|  
  
### <a name="adding-an-expression-shape"></a><span data-ttu-id="7e945-233">添加表达式形状</span><span class="sxs-lookup"><span data-stu-id="7e945-233">Adding an Expression Shape</span></span>  
 <span data-ttu-id="7e945-234">包括表达式形状中业务流程的用途是具有要提取的收到的通知消息的种类的 xpath 查询。</span><span class="sxs-lookup"><span data-stu-id="7e945-234">The purpose of including an Expression shape in the orchestration is to have an xpath query to extract the kind of notification message received.</span></span> <span data-ttu-id="7e945-235">在创建之前 xpath 查询，让我们看一下通知消息的格式。</span><span class="sxs-lookup"><span data-stu-id="7e945-235">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="7e945-236">典型的通知消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e945-236">A typical notification message resembles the following:</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
 <span data-ttu-id="7e945-237">正如您看到的通知类型有关的信息中有可用`<info>`标记，父项中的`<Notification>`标记。</span><span class="sxs-lookup"><span data-stu-id="7e945-237">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="7e945-238">因此，在此表达式形状的你必须：</span><span class="sxs-lookup"><span data-stu-id="7e945-238">So, as part of this expression shape you must:</span></span>  
  
-   <span data-ttu-id="7e945-239">创建包含中的值的变量`<Info>`标记并将其类型设置为 System.String。</span><span class="sxs-lookup"><span data-stu-id="7e945-239">Create a variable that contains the value within the `<Info>` tag and set its type to System.String.</span></span> <span data-ttu-id="7e945-240">有关创建变量的详细信息，请参阅[在业务流程中使用变量](../../core/using-variables-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-240">For more information about creating variables, see [Using Variables in Orchestrations](../../core/using-variables-in-orchestrations.md).</span></span>  
  
     <span data-ttu-id="7e945-241">本主题中，将命名为变量**NotificationType**。</span><span class="sxs-lookup"><span data-stu-id="7e945-241">For this topic, name the variable as **NotificationType**.</span></span>  
  
-   <span data-ttu-id="7e945-242">创建要提取的值的 xpath 查询\<信息 > 标记。</span><span class="sxs-lookup"><span data-stu-id="7e945-242">Create an xpath query to extract the value from the \<Info> tag.</span></span> <span data-ttu-id="7e945-243">Xpath 查询将如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e945-243">The xpath query will resemble the following:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="7e945-244">在此 xpath 查询**NotifyReceive**是创建用于接收通知消息的消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-244">In this xpath query, **NotifyReceive** is the message you created for receiving notification messages.</span></span> <span data-ttu-id="7e945-245">中的摘录`string`函数指示查询必须提取的值在`<Info>`标记，又是内`<Notification>`标记。</span><span class="sxs-lookup"><span data-stu-id="7e945-245">The excerpt within the `string` function indicates that the query must extract the value within the `<Info>` tag, which in turn is within the `<Notification>` tag.</span></span> <span data-ttu-id="7e945-246">最后，该查询所提取的值分配给**NotificaitonType**变量。</span><span class="sxs-lookup"><span data-stu-id="7e945-246">Finally, the value extracted by the query is assigned to the **NotificaitonType** variable.</span></span>  
  
### <a name="adding-a-decide-shape"></a><span data-ttu-id="7e945-247">添加判定形状</span><span class="sxs-lookup"><span data-stu-id="7e945-247">Adding a Decide Shape</span></span>  
 <span data-ttu-id="7e945-248">添加判定形状的目的是要包含在业务流程来决定要执行的后续操作根据收到的通知消息的类型中的决策块。</span><span class="sxs-lookup"><span data-stu-id="7e945-248">The purpose of adding a Decide shape is to include a decision block in the orchestration to decide what subsequent operations to perform based on the kind of notification message received.</span></span> <span data-ttu-id="7e945-249">默认情况下，决定的值根据**NotificationType**变量。</span><span class="sxs-lookup"><span data-stu-id="7e945-249">The decision is made on the basis of the value of the **NotificationType** variable.</span></span> <span data-ttu-id="7e945-250">在本主题中，业务流程做出决策基于收到的通知消息的种类。</span><span class="sxs-lookup"><span data-stu-id="7e945-250">In this topic, the orchestration makes a decision based on the kind of notification message received.</span></span> <span data-ttu-id="7e945-251">因此，规则形状中的条件，如下所示指定：</span><span class="sxs-lookup"><span data-stu-id="7e945-251">So, the condition in the Rule shape is specified as follows:</span></span>  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 <span data-ttu-id="7e945-252">此条件提供的建议，如果值**NotificaitonType**变量是 Insert 或 Update，业务流程将执行一组任务。</span><span class="sxs-lookup"><span data-stu-id="7e945-252">This condition suggests that if the value for **NotificaitonType** variable is Insert or Update, the orchestration will perform one set of tasks.</span></span> <span data-ttu-id="7e945-253">如果值**NotificationType**变量是任何其他操作，业务流程将执行另一组任务。</span><span class="sxs-lookup"><span data-stu-id="7e945-253">If the value of **NotificationType** variable is anything else, the orchestration will perform other set of tasks.</span></span>  
  
 <span data-ttu-id="7e945-254">如前面几节中所述，来演示一种简单方法，业务流程将将消息复制到不同的文件夹，基于通知消息类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-254">As mentioned in the preceding sections, to demonstrate a simple approach, the orchestration will copy messages to different folders based on the notification message type.</span></span> <span data-ttu-id="7e945-255">这样，在规则中和 Else 块，您必须添加发送形状以将消息发送到不同的端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-255">So, within the Rule and Else blocks, you must add Send shapes to send the messages to different ports.</span></span> <span data-ttu-id="7e945-256">本主题中，将命名为规则块中的发送形状**SendUpsertNotification**和作为 Else 块中的发送形状**SendOtherNotification**。</span><span class="sxs-lookup"><span data-stu-id="7e945-256">For this topic, name the Send shape in the Rule block as **SendUpsertNotification** and the Send shape in the Else block as **SendOtherNotification**.</span></span>  
  
### <a name="adding-ports"></a><span data-ttu-id="7e945-257">添加端口</span><span class="sxs-lookup"><span data-stu-id="7e945-257">Adding Ports</span></span>  
 <span data-ttu-id="7e945-258">现在，你必须将以下逻辑端口添加到业务流程：</span><span class="sxs-lookup"><span data-stu-id="7e945-258">You must now add the following logical ports to the orchestration:</span></span>  
  
-   <span data-ttu-id="7e945-259">单向接收端口从 Oracle 数据库接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-259">One-way receive port to receive notification messages from the Oracle database.</span></span>  
  
-   <span data-ttu-id="7e945-260">将 Insert 和 Update 操作的通知消息发送到特定文件夹的单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-260">One-way send port to send notification messages for Insert and Update operations to a specific folder.</span></span>  
  
-   <span data-ttu-id="7e945-261">要将任何其他操作的通知消息发送到特定文件夹的单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-261">One-way send port to send notification messages for any other operations to a specific folder.</span></span>  
  
 <span data-ttu-id="7e945-262">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-262">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="7e945-263">中列出的名称**端口**列是本主题中前面所示的业务流程图表中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="7e945-263">The names listed in the **Port** column are the names of the ports as displayed in the orchestration diagram shown earlier in this topic.</span></span>  
  
|<span data-ttu-id="7e945-264">端口</span><span class="sxs-lookup"><span data-stu-id="7e945-264">Port</span></span>|<span data-ttu-id="7e945-265">属性</span><span class="sxs-lookup"><span data-stu-id="7e945-265">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7e945-266">OracleNotifyPort</span><span class="sxs-lookup"><span data-stu-id="7e945-266">OracleNotifyPort</span></span>|<span data-ttu-id="7e945-267">-将设置**标识符**到*OracleNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="7e945-267">- Set **Identifier** to *OracleNotifyPort*</span></span><br /><br /> <span data-ttu-id="7e945-268">-将设置**类型**到*OracleNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="7e945-268">- Set **Type** to *OracleNotifyPortType*</span></span><br /><br /> <span data-ttu-id="7e945-269">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="7e945-269">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="7e945-270">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="7e945-270">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="7e945-271">NotificationUpsertPort</span><span class="sxs-lookup"><span data-stu-id="7e945-271">NotificationUpsertPort</span></span>|<span data-ttu-id="7e945-272">-将设置**标识符**到*NotificationUpsertPort*</span><span class="sxs-lookup"><span data-stu-id="7e945-272">- Set **Identifier** to *NotificationUpsertPort*</span></span><br /><br /> <span data-ttu-id="7e945-273">-将设置**类型**到*NotificationUpsertPortType*</span><span class="sxs-lookup"><span data-stu-id="7e945-273">- Set **Type** to *NotificationUpsertPortType*</span></span><br /><br /> <span data-ttu-id="7e945-274">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="7e945-274">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="7e945-275">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="7e945-275">- Set **Communication Direction** to *Send*</span></span>|  
|<span data-ttu-id="7e945-276">OtherNotificationPort</span><span class="sxs-lookup"><span data-stu-id="7e945-276">OtherNotificationPort</span></span>|<span data-ttu-id="7e945-277">-将设置**标识符**到*OtherNotificationPort*</span><span class="sxs-lookup"><span data-stu-id="7e945-277">- Set **Identifier** to *OtherNotificationPort*</span></span><br /><br /> <span data-ttu-id="7e945-278">-将设置**类型**到*OtherNotificationPortType*</span><span class="sxs-lookup"><span data-stu-id="7e945-278">- Set **Type** to *OtherNotificationPortType*</span></span><br /><br /> <span data-ttu-id="7e945-279">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="7e945-279">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="7e945-280">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="7e945-280">- Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="7e945-281">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="7e945-281">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="7e945-282">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="7e945-282">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="7e945-283">中列出的名称**形状**列是消息形状的名称，如本主题中前面所示的业务流程图表中显示。</span><span class="sxs-lookup"><span data-stu-id="7e945-283">The names listed in the **Shape** column are the names of the message shapes as displayed in the orchestration diagram shown earlier in this topic.</span></span>  
  
|<span data-ttu-id="7e945-284">形状</span><span class="sxs-lookup"><span data-stu-id="7e945-284">Shape</span></span>|<span data-ttu-id="7e945-285">属性</span><span class="sxs-lookup"><span data-stu-id="7e945-285">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="7e945-286">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="7e945-286">ReceiveNotification</span></span>|<span data-ttu-id="7e945-287">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="7e945-287">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="7e945-288">-将设置**操作**到*OracleNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="7e945-288">- Set **Operation** to *OracleNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="7e945-289">SendUpsertNotification</span><span class="sxs-lookup"><span data-stu-id="7e945-289">SendUpsertNotification</span></span>|<span data-ttu-id="7e945-290">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="7e945-290">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="7e945-291">-将设置**操作**到*NotificationUpsertPort.Upsert.Request*</span><span class="sxs-lookup"><span data-stu-id="7e945-291">- Set **Operation** to *NotificationUpsertPort.Upsert.Request*</span></span>|  
|<span data-ttu-id="7e945-292">SendOtherNotification</span><span class="sxs-lookup"><span data-stu-id="7e945-292">SendOtherNotification</span></span>|<span data-ttu-id="7e945-293">-将设置**消息**到*选择*</span><span class="sxs-lookup"><span data-stu-id="7e945-293">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="7e945-294">-将设置**操作**到*OtherNotificationPort.Other.Request*</span><span class="sxs-lookup"><span data-stu-id="7e945-294">- Set **Operation** to *OtherNotificationPort.Other.Request*</span></span>|  
  
 <span data-ttu-id="7e945-295">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="7e945-295">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="7e945-296">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7e945-296">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7e945-297">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-297">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="7e945-298">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7e945-298">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="7e945-299">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7e945-299">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7e945-300">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e945-300">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="7e945-301">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-301">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>  
  
 <span data-ttu-id="7e945-302">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="7e945-302">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="7e945-303">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="7e945-303">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="7e945-304">映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7e945-304">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7e945-305">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="7e945-305">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="7e945-306">定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-306">Define a physical WCF-Custom or WCF-OracleEBS one-way receive port.</span></span> <span data-ttu-id="7e945-307">此端口侦听来自 Oracle E-business Suite 的通知。</span><span class="sxs-lookup"><span data-stu-id="7e945-307">This port listens for notifications coming from Oracle E-Business Suite.</span></span> <span data-ttu-id="7e945-308">有关如何创建接收端口，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-308">For information about how to create receive ports, see [Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).</span></span> <span data-ttu-id="7e945-309">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-309">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7e945-310">不需要执行此步骤中，如果指定在设计时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7e945-310">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="7e945-311">在这种情况下，你可以创建 WCF 自定义或 WCF OracleEBS 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7e945-311">In such a case, you can create a WCF-custom or WCF-OracleEBS receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="7e945-312">有关详细信息请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-312">For more information see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
        |<span data-ttu-id="7e945-313">绑定属性</span><span class="sxs-lookup"><span data-stu-id="7e945-313">Binding Property</span></span>|<span data-ttu-id="7e945-314">值</span><span class="sxs-lookup"><span data-stu-id="7e945-314">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="7e945-315">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="7e945-315">**InboundOperationType**</span></span>|<span data-ttu-id="7e945-316">将其设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="7e945-316">Set this to **Notification**.</span></span>|  
        |<span data-ttu-id="7e945-317">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="7e945-317">**NotificationPort**</span></span>|<span data-ttu-id="7e945-318">指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。</span><span class="sxs-lookup"><span data-stu-id="7e945-318">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span> <span data-ttu-id="7e945-319">将其设置为相同的端口号必须已添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="7e945-319">Set this to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="7e945-320">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="7e945-320">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span><br /><br /> <span data-ttu-id="7e945-321">**重要**如果设置为默认值为-1，则你将需要完全禁用 Windows 防火墙，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-321">**Important** If you set this to the default value of -1, you will have to completely disable Windows Firewall to receive notification messages.</span></span>|  
        |<span data-ttu-id="7e945-322">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="7e945-322">**NotificationStatement**</span></span>|<span data-ttu-id="7e945-323">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="7e945-323">Set this to:</span></span><br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> <span data-ttu-id="7e945-324">**请注意**必须指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="7e945-324">**Note** You must specify the table name along with the schema name.</span></span> <span data-ttu-id="7e945-325">例如， `SCOTT.ACCOUNTACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="7e945-325">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>|  
        |<span data-ttu-id="7e945-326">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="7e945-326">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="7e945-327">将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="7e945-327">Set this to **True**.</span></span>|  
  
         <span data-ttu-id="7e945-328">有关不同的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-328">For more information about the different binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7e945-329">如果你要配置为接口表的通知，您必须通过指定所需的绑定属性中设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="7e945-329">If you are configuring notifications for an interface table, you must set the application context by specifying the requisite binding properties.</span></span> <span data-ttu-id="7e945-330">有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-330">For more information about setting the application context see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7e945-331">我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7e945-331">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="7e945-332">你可以通过配置 WCF 自定义时添加的服务行为来实现或 WCF OracleEBS 接收端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-332">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="7e945-333">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 Oracle E-business Suite 的事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-333">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
    -   <span data-ttu-id="7e945-334">硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Oracle 数据库 Insert 和 Update 操作的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="7e945-334">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the notification messages from the Oracle database for Insert and Update operations.</span></span> <span data-ttu-id="7e945-335">配置此端口，以将通知消息放置到 C:\TestLocation\UpsertNotification 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e945-335">Configure this port to drop notification messages to the folder C:\TestLocation\UpsertNotification.</span></span>  
  
    -   <span data-ttu-id="7e945-336">硬盘和 BizTalk 业务流程将放置的位置的通知消息从所有其他操作的 Oracle 数据库的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="7e945-336">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the notification messages from the Oracle database for all other operations.</span></span> <span data-ttu-id="7e945-337">配置此端口，以将通知消息放置到 C:\TestLocation\OtherNotification 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e945-337">Configure this port to drop notification messages to the folder C:\TestLocation\OtherNotification.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="7e945-338">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="7e945-338">Starting the Application</span></span>  
 <span data-ttu-id="7e945-339">你必须启动 BizTalk 应用程序接收通知消息从 Oracle 数据库并执行后续的选择和更新操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-339">You must start the BizTalk application for receiving notification messages from the Oracle database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="7e945-340">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-340">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="7e945-341">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="7e945-341">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="7e945-342">WCF 自定义或 WCF OracleEBS 单向接收端口，从而从 Oracle 数据库运行时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-342">The WCF-Custom or WCF-OracleEBS one-way receive port, which receives the notification messages from the Oracle database is running.</span></span>  
  
-   <span data-ttu-id="7e945-343">正在从 Oracle 数据库中接收消息，两个文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-343">The two FILE send ports, which receive messages from Oracle database, are running.</span></span>  
  
-   <span data-ttu-id="7e945-344">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="7e945-344">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="7e945-345">执行该操作</span><span class="sxs-lookup"><span data-stu-id="7e945-345">Executing the Operation</span></span>  
 <span data-ttu-id="7e945-346">启动 BizTalk 业务流程后，下面的一组操作发生：</span><span class="sxs-lookup"><span data-stu-id="7e945-346">After you start the BizTalk orchestration, the following set of actions take place:</span></span>  
  
-   <span data-ttu-id="7e945-347">因为**NotifyOnListenerStart**绑定属性设置为**True**，收到以下消息：</span><span class="sxs-lookup"><span data-stu-id="7e945-347">Because the **NotifyOnListenerStart** binding property is set to **True**, you receive the following message:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="7e945-348">请注意，中的值`<Info>`标记为"ListnerStarted"。</span><span class="sxs-lookup"><span data-stu-id="7e945-348">Note that the value in the `<Info>` tag is “ListnerStarted”.</span></span> <span data-ttu-id="7e945-349">因此，在 C:\TestLocation\OtherNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-349">Hence, this message is received in C:\TestLocation\OtherNotification folder.</span></span>  
  
-   <span data-ttu-id="7e945-350">ACCOUNTACTIVITY 表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-350">Insert a record in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7e945-351">你将收到类似于以下通知消息：</span><span class="sxs-lookup"><span data-stu-id="7e945-351">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     <span data-ttu-id="7e945-352">请注意，中的值`<Info>`标记为"插入"。</span><span class="sxs-lookup"><span data-stu-id="7e945-352">Note that the value in the `<Info>` tag is “Insert”.</span></span> <span data-ttu-id="7e945-353">因此，在 C:\TestLocation\UpsertNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-353">Hence, this message is received in C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="7e945-354">更新 ACCOUNTACTIVITY 表中的记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-354">Update a record in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7e945-355">你将收到类似于以下通知消息：</span><span class="sxs-lookup"><span data-stu-id="7e945-355">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="7e945-356">请注意，中的值`<Info>`标记为"更新"。</span><span class="sxs-lookup"><span data-stu-id="7e945-356">Note that the value in the `<Info>` tag is “Update”.</span></span> <span data-ttu-id="7e945-357">因此，在 C:\TestLocation\UpsertNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-357">Hence, this message is received in C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="7e945-358">从 ACCOUNTACTIVITY 表中删除一条记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-358">Delete a record from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7e945-359">你将收到类似于以下通知消息：</span><span class="sxs-lookup"><span data-stu-id="7e945-359">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>16</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Delete</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="7e945-360">请注意，中的值`<Info>`标记为"Delete"。</span><span class="sxs-lookup"><span data-stu-id="7e945-360">Note that the value in the `<Info>` tag is “Delete”.</span></span> <span data-ttu-id="7e945-361">因此，在 C:\TestLocation\OtherNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="7e945-361">Hence, this message is received in C:\TestLocation\OtherNotification folder.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="7e945-362">最佳实践</span><span class="sxs-lookup"><span data-stu-id="7e945-362">Best Practices</span></span>  
 <span data-ttu-id="7e945-363">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7e945-363">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="7e945-364">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="7e945-364">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="7e945-365">有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7e945-365">For more information about binding files, see [Reuse Adapter Bindings with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).</span></span>  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a><span data-ttu-id="7e945-366">接收通知消息之后执行复杂的操作</span><span class="sxs-lookup"><span data-stu-id="7e945-366">Performing Complex Operations After Receiving Notification Messages</span></span>  
 <span data-ttu-id="7e945-367">为简单和更好地了解，本主题中的业务流程将消息复制到不同的文件夹，基于通知类型。</span><span class="sxs-lookup"><span data-stu-id="7e945-367">For simplicity and better understanding, the orchestration in this topic copies messages to different folders based on the notification type.</span></span> <span data-ttu-id="7e945-368">但是，在实际方案中你可能想要执行更复杂的操作。</span><span class="sxs-lookup"><span data-stu-id="7e945-368">However, in real-world scenarios you might want to perform more complex operations.</span></span> <span data-ttu-id="7e945-369">对其执行操作要生成此主题中所述，你可以执行类似的过程。</span><span class="sxs-lookup"><span data-stu-id="7e945-369">You can perform similar procedures as provided in this topic and build on them to perform the operations you wish.</span></span> <span data-ttu-id="7e945-370">例如，你可以更改业务流程如果 ACCOUNTACTIVITY 表上的插入操作获取一条通知消息，另一个表中插入记录。</span><span class="sxs-lookup"><span data-stu-id="7e945-370">For example, you can change the orchestration to insert records in another table if you get a notification message for an Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7e945-371">在这种情况下，你可以确定形状中的相应更改。</span><span class="sxs-lookup"><span data-stu-id="7e945-371">In such a case, you can make appropriate changes within the Decide shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e945-372">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e945-372">See Also</span></span>  
 [<span data-ttu-id="7e945-373">接收使用 BizTalk Server 的 Oracle E-business Suite 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="7e945-373">Receive Oracle E-Business Suite Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)