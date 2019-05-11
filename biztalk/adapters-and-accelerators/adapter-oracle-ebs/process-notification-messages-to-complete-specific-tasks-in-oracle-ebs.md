---
title: 处理通知消息，以完成 Oracle E-business Suite 中的特定任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bddeb5a-3819-40cc-aae0-c49963f0beb1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b61cd9ee11a6c8eba778db8fabf0f50552226046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374864"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-e-business-suite"></a><span data-ttu-id="21556-102">处理通知消息来完成 Oracle E-business Suite 中的特定任务</span><span class="sxs-lookup"><span data-stu-id="21556-102">Process notification messages to complete specific tasks in Oracle E-Business Suite</span></span>
<span data-ttu-id="21556-103">可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收到 Oracle 数据库表的更改通知。</span><span class="sxs-lookup"><span data-stu-id="21556-103">You can use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications for changes to the Oracle database tables.</span></span> <span data-ttu-id="21556-104">但是，适配器仅向你发送某些记录已插入、 更新或删除数据库表中的通知。</span><span class="sxs-lookup"><span data-stu-id="21556-104">However, the adapter only sends you a notification that some records were inserted, updated, or deleted in a certain database table.</span></span> <span data-ttu-id="21556-105">这些记录的任何后续处理必须由客户端应用程序本身进行处理。</span><span class="sxs-lookup"><span data-stu-id="21556-105">Any post-processing on those records must be handled by the client applications themselves.</span></span> <span data-ttu-id="21556-106">本主题显示如何处理从 Oracle 数据库接收的通知类型基于在表中的记录上的基于方案的说明。</span><span class="sxs-lookup"><span data-stu-id="21556-106">This topic presents a scenario-based description on how to process the records in the table based on the kind of notification received from the Oracle database.</span></span>  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a><span data-ttu-id="21556-107">收到通知后执行后续操作的方案</span><span class="sxs-lookup"><span data-stu-id="21556-107">Scenarios for Performing Subsequent Actions After Receiving Notification</span></span>  
 <span data-ttu-id="21556-108">以下是几种方案，适配器客户端必须执行某些通知后任务。</span><span class="sxs-lookup"><span data-stu-id="21556-108">Following are a couple of scenarios in which the adapter clients must perform certain post-notification tasks.</span></span>  
  
-   <span data-ttu-id="21556-109">**方案 1。**</span><span class="sxs-lookup"><span data-stu-id="21556-109">**Scenario 1.**</span></span> <span data-ttu-id="21556-110">假设适配器客户端必须在其中执行某些任务基于从 Oracle 数据库接收的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="21556-110">Consider a scenario where the adapter client must perform certain tasks based on the kind of notification you receive from the Oracle database.</span></span> <span data-ttu-id="21556-111">例如，如果在表"B"中插入记录客户端应用程序必须更新表"A"中的记录。</span><span class="sxs-lookup"><span data-stu-id="21556-111">For example, the client application must update the records in table “A” if records are inserted in table “B”.</span></span> <span data-ttu-id="21556-112">同样，客户端应用程序必须从表"B"中删除记录如果从表"A"中删除记录。</span><span class="sxs-lookup"><span data-stu-id="21556-112">Similarly, the client application must delete records from table “A” if records are deleted from table “B”.</span></span>  
  
     <span data-ttu-id="21556-113">从通知消息接收到，在此方案中，适配器客户端必须提取要决定是否通知已为插入操作或删除操作的通知类型。</span><span class="sxs-lookup"><span data-stu-id="21556-113">In this scenario, from the notification message received, the adapter clients must extract the type of notification to decide whether the notification was for an insert operation or a delete operation.</span></span> <span data-ttu-id="21556-114">一旦确定通知类型，适配器客户端必须执行后续操作来插入或更新相关表。</span><span class="sxs-lookup"><span data-stu-id="21556-114">Once the notification type is ascertained, the adapter clients must perform subsequent actions to insert or update the relevant tables.</span></span>  
  
-   <span data-ttu-id="21556-115">**方案 2。**</span><span class="sxs-lookup"><span data-stu-id="21556-115">**Scenario 2.**</span></span> <span data-ttu-id="21556-116">假设接收对表的更改的通知消息的接收位置出现故障。</span><span class="sxs-lookup"><span data-stu-id="21556-116">Consider a scenario where the receive location that receives notification messages for changes to a table goes down.</span></span> <span data-ttu-id="21556-117">关闭接收位置时，某些记录添加到表。</span><span class="sxs-lookup"><span data-stu-id="21556-117">While the receive location is down, some records are added to the table.</span></span> <span data-ttu-id="21556-118">但是，这些记录的适配器客户端不接收任何通知。</span><span class="sxs-lookup"><span data-stu-id="21556-118">However, for these records the adapter client does not receive any notification.</span></span> <span data-ttu-id="21556-119">当接收位置重新启动时，适配器通过发送特定消息，通知客户端，然后客户端应用程序必须查找的接收位置时向下插入数据库表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="21556-119">When the receive location is back up, the adapter notifies the client by sending a specific message, and then the client application must look for all the records that were inserted in the database table while the receive location was down.</span></span>  
  
     <span data-ttu-id="21556-120">从通知消息接收到，在此方案中，适配器客户端必须提取有关该通知是对数据库表的更改或接收位置开始的信息。</span><span class="sxs-lookup"><span data-stu-id="21556-120">In this scenario, from the notification message received, the adapter clients must extract the information regarding whether the notification is for a change to a database table or for the receive location starting.</span></span> <span data-ttu-id="21556-121">通知所针对的接收位置开始，如果适配器客户端必须实现逻辑以处理可能具有已插入、 更新或接收位置已关闭时删除的记录。</span><span class="sxs-lookup"><span data-stu-id="21556-121">If the notification is for the receive location starting, the adapter clients must implement the logic to process the records that might have been inserted, updated, or deleted while the receive location was down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21556-122">这些是为更好地了解如何使用通知功能中的列出的只是一些示例方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21556-122">These are just some example scenarios that are listed for a better understanding of how to use the notification feature in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="21556-123">但是，一组基本的通知接收到的类型中提取所需的任务将适用于所有方案类似。</span><span class="sxs-lookup"><span data-stu-id="21556-123">However, the basic set of tasks required to extract the type of notification received will be similar for all scenarios.</span></span> <span data-ttu-id="21556-124">本主题将说明了如何从通知消息中提取的通知类型。</span><span class="sxs-lookup"><span data-stu-id="21556-124">This topic provides instructions on how to extract the type of notification from a notification message.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="21556-125">如何本主题演示如何接收通知消息</span><span class="sxs-lookup"><span data-stu-id="21556-125">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="21556-126">在本主题中，用于演示如何处理通知消息，以执行后续任务中，我们考虑其中适配器客户端使用的 BizTalk 应用程序接收到 ACCOUNTACTIVITY 表更改的通知消息的基本方案。</span><span class="sxs-lookup"><span data-stu-id="21556-126">In this topic, to demonstrate how to process notification messages to perform subsequent tasks, we consider a basic scenario where an adapter client uses BizTalk application to receive notification messages for changes to the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="21556-127">收到通知后，客户端筛选收到的通知的类型，并执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="21556-127">After the notification is received, the client filters the type of notification received and performs subsequent action.</span></span> <span data-ttu-id="21556-128">若要演示最基本方案，让我们设想适配器客户端将通知消息复制到不同的文件夹，根据收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="21556-128">To demonstrate a very basic scenario, let us consider that the adapter client copies the notification messages to different folders based on the kind of notification received.</span></span> <span data-ttu-id="21556-129">因此：</span><span class="sxs-lookup"><span data-stu-id="21556-129">Therefore:</span></span>  
  
- <span data-ttu-id="21556-130">如果通知消息是针对 Insert 或 Update 操作，适配器客户端会将消息复制到 C:\TestLocation\UpsertNotification 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="21556-130">If the notification message is for an Insert or Update operation, the adapter client copies the message to C:\TestLocation\UpsertNotification folder.</span></span>  
  
- <span data-ttu-id="21556-131">如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。</span><span class="sxs-lookup"><span data-stu-id="21556-131">If the notification message is for any other operation, for example Delete, the adapter client copies the message to C:\TestLocation\OtherNotificaiton folder.</span></span>  
  
  <span data-ttu-id="21556-132">为此 BizTalk 应用程序的一部分，该业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="21556-132">To achieve this as part of a BizTalk application, the orchestration must contain the following:</span></span>  
  
- <span data-ttu-id="21556-133">一个单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-133">A one-way receive port to receive notification messages.</span></span>  
  
- <span data-ttu-id="21556-134">表达式形状包含 xpath 查询来提取有关收到通知消息的类型信息。</span><span class="sxs-lookup"><span data-stu-id="21556-134">An Expression shape that contains an xpath query to extract the information about the kind of notification message received.</span></span>  
  
- <span data-ttu-id="21556-135">判定形状在业务流程中包括判定块。</span><span class="sxs-lookup"><span data-stu-id="21556-135">A Decide shape to include a decision block in the orchestration.</span></span> <span data-ttu-id="21556-136">在此决策块中，应用程序确定要执行的后续操作根据收到的通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-136">In this decision block, the application decides on what subsequent operations to perform based on the notification message received.</span></span>  
  
- <span data-ttu-id="21556-137">两个单向发送端口的最后接收的通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-137">Two one-way send ports that finally receive the notification messages.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="21556-138">使用 Oracle E-business 适配器的绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="21556-138">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="21556-139">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置 Oracle E-business Suite 中接收通知的属性。</span><span class="sxs-lookup"><span data-stu-id="21556-139">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="21556-140">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="21556-140">You must specify these binding properties when configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21556-141">您可以选择生成的架构时指定这些绑定属性**通知**操作，即使并不总是这样。</span><span class="sxs-lookup"><span data-stu-id="21556-141">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="21556-142">如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。</span><span class="sxs-lookup"><span data-stu-id="21556-142">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="21556-143">稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF OracleEBS 属性已设置对绑定接收端口。</span><span class="sxs-lookup"><span data-stu-id="21556-143">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-OracleEBS receive port with the binding properties already set.</span></span> <span data-ttu-id="21556-144">有关创建使用绑定文件的 WCF 自定义或 WCF OracleEBS 端口的详细信息，请参阅[配置物理端口绑定使用端口绑定文件到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-144">For more information about creating a WCF-custom or WCF-OracleEBS port using the binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
|<span data-ttu-id="21556-145">绑定属性</span><span class="sxs-lookup"><span data-stu-id="21556-145">Binding Property</span></span>|<span data-ttu-id="21556-146">Description</span><span class="sxs-lookup"><span data-stu-id="21556-146">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="21556-147">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="21556-147">**InboundOperationType**</span></span>|<span data-ttu-id="21556-148">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="21556-148">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="21556-149">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="21556-149">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="21556-150">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="21556-150">**NotificationPort**</span></span>|<span data-ttu-id="21556-151">指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="21556-151">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="21556-152">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="21556-152">**NotificationStatement**</span></span>|<span data-ttu-id="21556-153">指定用于对查询通知注册的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="21556-153">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="21556-154">仅当指定的 SELECT 语句更改的结果集时，适配器将获取一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-154">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="21556-155">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="21556-155">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="21556-156">指定适配器是否启动侦听器时在向适配器客户端发送了通知。</span><span class="sxs-lookup"><span data-stu-id="21556-156">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="21556-157">有关这些属性的更完整说明，请参阅 [[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-157">For a more complete description of these properties, see [[Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="21556-158">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 中接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="21556-158">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read further.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a><span data-ttu-id="21556-159">如何从 Oracle E-business Suite 中接收通知消息</span><span class="sxs-lookup"><span data-stu-id="21556-159">How to Receive Notification Messages from Oracle E-Business Suite</span></span>  
 <span data-ttu-id="21556-160">对 Oracle E-business Suite 使用执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-160">Performing an operation on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to create Oracle E-Business Suite applications](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md).</span></span> <span data-ttu-id="21556-161">若要配置要接收通知消息的适配器，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="21556-161">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1. <span data-ttu-id="21556-162">创建 BizTalk 项目，然后生成的架构**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="21556-162">Create a BizTalk project, and then generate schema for the **Notification** inbound operation.</span></span> <span data-ttu-id="21556-163">或者，您可以指定的值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="21556-163">Optionally, you can specify values for the **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties.</span></span>  
  
2. <span data-ttu-id="21556-164">用于 Oracle E-business Suite 中接收通知的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="21556-164">Create a message in the BizTalk project for receiving notification from Oracle E-Business Suite.</span></span>  
  
3. <span data-ttu-id="21556-165">在上一部分中所述创建一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="21556-165">Create an orchestration as described in the preceding section.</span></span>  
  
4. <span data-ttu-id="21556-166">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="21556-166">Build and deploy the BizTalk project.</span></span>  
  
5. <span data-ttu-id="21556-167">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="21556-167">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21556-168">对于入站操作，如接收通知消息，则必须仅配置一个单向 WCF 自定义或 Wcf-oracleebs 接收端口。</span><span class="sxs-lookup"><span data-stu-id="21556-168">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="21556-169">双向接收端口不支持的入站操作。</span><span class="sxs-lookup"><span data-stu-id="21556-169">Two-way receive ports are not supported for inbound operations.</span></span>  
  
6. <span data-ttu-id="21556-170">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="21556-170">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="21556-171">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="21556-171">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="21556-172">生成架构</span><span class="sxs-lookup"><span data-stu-id="21556-172">Generating Schema</span></span>  
 <span data-ttu-id="21556-173">必须生成的架构**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="21556-173">You must generate the schema for the **Notification** inbound operation.</span></span> <span data-ttu-id="21556-174">有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-174">For more information about how to generate the schema, see [Retrieving Metadata for Oracle E-Business Suite Operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span></span> <span data-ttu-id="21556-175">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="21556-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="21556-176">如果不想指定绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="21556-176">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
 <span data-ttu-id="21556-177">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="21556-177">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="21556-178">如果不想指定绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="21556-178">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="21556-179">为指定值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="21556-179">Specify a value for **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="21556-180">有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-180">For more information about this binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="21556-181">有关如何指定绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-181">For instructions on how to specify binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
2.  <span data-ttu-id="21556-182">选择作为协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="21556-182">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="21556-183">生成架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="21556-183">Generate schema for the **Notification** operation.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="21556-184">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="21556-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="21556-185">你在上一节中生成此架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="21556-185">The schema that you generated in the previous section describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="21556-186">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="21556-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="21556-187">生成架构后，必须直接将其链接到的消息，业务流程视图中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="21556-187">After the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="21556-188">对于本主题中，必须创建一条消息从 Oracle 数据库接收通知。</span><span class="sxs-lookup"><span data-stu-id="21556-188">For this topic, you must create one message to receive notifications from the Oracle database.</span></span>  
  
 <span data-ttu-id="21556-189">执行以下步骤创建消息并将其链接到架构。</span><span class="sxs-lookup"><span data-stu-id="21556-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="21556-190">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="21556-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="21556-191">向 BizTalk 项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="21556-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="21556-192">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="21556-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="21556-193">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="21556-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="21556-194">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="21556-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="21556-195">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="21556-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="21556-196">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="21556-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="21556-197">右键单击新创建的消息，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="21556-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="21556-198">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="21556-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="21556-199">使用此选项</span><span class="sxs-lookup"><span data-stu-id="21556-199">Use this</span></span>|<span data-ttu-id="21556-200">执行的操作</span><span class="sxs-lookup"><span data-stu-id="21556-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="21556-201">Identifier</span><span class="sxs-lookup"><span data-stu-id="21556-201">Identifier</span></span>|<span data-ttu-id="21556-202">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="21556-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="21556-203">消息类型</span><span class="sxs-lookup"><span data-stu-id="21556-203">Message Type</span></span>|<span data-ttu-id="21556-204">从下拉列表中，展开**架构**，然后选择*Process_Notification.OracleEBSBinding.Notification*，其中*Process_Notification*的名称在BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="21556-204">From the drop-down list, expand **Schemas**, and select *Process_Notification.OracleEBSBinding.Notification*, where *Process_Notification* is the name of your BizTalk project.</span></span> <span data-ttu-id="21556-205">*OracleEBSBinding*是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="21556-205">*OracleEBSBinding* is the schema generated for the **Notification** operation.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="21556-206">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="21556-206">Setting up the Orchestration</span></span>  
 <span data-ttu-id="21556-207">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]有关从 Oracle 数据库接收通知消息，然后执行任务根据收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="21556-207">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the Oracle database and then performing tasks based on the type of notification received.</span></span> <span data-ttu-id="21556-208">在此业务流程，适配器将接收通知消息根据 SELECT 语句为指定**NotificationStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="21556-208">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="21556-209">表达式形状中指定的 xpath 查询中提取到变量中，通知的类型说**NotificationType**。</span><span class="sxs-lookup"><span data-stu-id="21556-209">The xpath query specified within the Expression shape extracts the type of notification into a variable, say **NotificationType**.</span></span> <span data-ttu-id="21556-210">判定形状使用此变量中的值来确定接收通知的类型和使用的相应"路径"以执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="21556-210">The Decide shape uses the value in this variable to decide on the kind of notification received and takes the appropriate “path” to perform subsequent operations.</span></span> <span data-ttu-id="21556-211">如前面部分中所述，业务流程将执行以下操作，根据收到的通知消息类型。</span><span class="sxs-lookup"><span data-stu-id="21556-211">As mentioned in the preceding section, the orchestration will perform the following operations based on the kind of notification message received.</span></span>  
  
- <span data-ttu-id="21556-212">如果通知消息是针对 Insert 或 Update 操作，适配器客户端会将消息复制到 C:\TestLocation\UpsertNotification 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="21556-212">If the notification message is for an Insert or Update operation, the adapter client copies the message to C:\TestLocation\UpsertNotification folder.</span></span>  
  
- <span data-ttu-id="21556-213">如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。</span><span class="sxs-lookup"><span data-stu-id="21556-213">If the notification message is for any other operation, for example Delete, the adapter client copies the message to C:\TestLocation\OtherNotificaiton folder.</span></span>  
  
  <span data-ttu-id="21556-214">因此，您的业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="21556-214">So, your orchestration must contain the following:</span></span>  
  
- <span data-ttu-id="21556-215">一个单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-215">A one-way receive port to receive notification messages.</span></span>  
  
- <span data-ttu-id="21556-216">表达式形状包含 xpath 查询来提取通知接收到的类型。</span><span class="sxs-lookup"><span data-stu-id="21556-216">An Expression shape that contains an xpath query to extract the kind of notification received.</span></span>  
  
- <span data-ttu-id="21556-217">判定形状在业务流程中包括判定块。</span><span class="sxs-lookup"><span data-stu-id="21556-217">A Decide shape to include a decision block in the orchestration.</span></span> <span data-ttu-id="21556-218">在此决策块中，应用程序确定要执行的后续操作根据收到的通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-218">In this decision block, the application decides on what subsequent operations to perform based on the notification message received.</span></span>  
  
- <span data-ttu-id="21556-219">两个单向发送端口的最后接收的通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-219">Two one-way send ports that finally receive the notification messages.</span></span>  
  
- <span data-ttu-id="21556-220">接收形状。</span><span class="sxs-lookup"><span data-stu-id="21556-220">Receive shape.</span></span>  
  
  <span data-ttu-id="21556-221">示例业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="21556-221">A sample orchestration resembles the following:</span></span>  
  
  <span data-ttu-id="21556-222">![业务流程，以执行 post&#45;通知任务](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")</span><span class="sxs-lookup"><span data-stu-id="21556-222">![Orchestration to perform post&#45;notification task](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="21556-223">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="21556-223">Adding Message Shapes</span></span>  
 <span data-ttu-id="21556-224">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="21556-224">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="21556-225">中列出的名称**形状**列是在业务流程关系图中显示消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="21556-225">The names listed in the **Shape** column are the names of the message shapes as displayed in the orchestration diagram.</span></span>  
  
|<span data-ttu-id="21556-226">形状</span><span class="sxs-lookup"><span data-stu-id="21556-226">Shape</span></span>|<span data-ttu-id="21556-227">形状类型</span><span class="sxs-lookup"><span data-stu-id="21556-227">Shape Type</span></span>|<span data-ttu-id="21556-228">属性</span><span class="sxs-lookup"><span data-stu-id="21556-228">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="21556-229">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="21556-229">ReceiveNotification</span></span>|<span data-ttu-id="21556-230">Receive</span><span class="sxs-lookup"><span data-stu-id="21556-230">Receive</span></span>|<span data-ttu-id="21556-231">-设置**名称**到*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="21556-231">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="21556-232">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="21556-232">- Set **Activate** to *True*</span></span>|  
  
### <a name="adding-an-expression-shape"></a><span data-ttu-id="21556-233">添加表达式形状</span><span class="sxs-lookup"><span data-stu-id="21556-233">Adding an Expression Shape</span></span>  
 <span data-ttu-id="21556-234">在业务流程中包括的表达式形状的用途是收到通知消息的类型中提取的 xpath 查询。</span><span class="sxs-lookup"><span data-stu-id="21556-234">The purpose of including an Expression shape in the orchestration is to have an xpath query to extract the kind of notification message received.</span></span> <span data-ttu-id="21556-235">然后再创建 xpath 查询，让我们看一下通知消息的格式。</span><span class="sxs-lookup"><span data-stu-id="21556-235">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="21556-236">典型的通知消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="21556-236">A typical notification message resembles the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
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
  
 <span data-ttu-id="21556-237">正如您看到的通知类型有关的信息中有可用`<info>`标记，在父级内的`<Notification>`标记。</span><span class="sxs-lookup"><span data-stu-id="21556-237">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="21556-238">因此，在此表达式形状，你必须：</span><span class="sxs-lookup"><span data-stu-id="21556-238">So, as part of this expression shape you must:</span></span>  
  
-   <span data-ttu-id="21556-239">创建包含中的值的变量`<Info>`标记并将其类型设置为 System.String。</span><span class="sxs-lookup"><span data-stu-id="21556-239">Create a variable that contains the value within the `<Info>` tag and set its type to System.String.</span></span> <span data-ttu-id="21556-240">有关创建变量的详细信息，请参阅[业务流程中使用变量](../../core/using-variables-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-240">For more information about creating variables, see [Using Variables in Orchestrations](../../core/using-variables-in-orchestrations.md).</span></span>  
  
     <span data-ttu-id="21556-241">有关本主题中，将变量命名为**NotificationType**。</span><span class="sxs-lookup"><span data-stu-id="21556-241">For this topic, name the variable as **NotificationType**.</span></span>  
  
-   <span data-ttu-id="21556-242">创建 xpath 查询中的值中提取\<信息\>标记。</span><span class="sxs-lookup"><span data-stu-id="21556-242">Create an xpath query to extract the value from the \<Info\> tag.</span></span> <span data-ttu-id="21556-243">Xpath 查询将如下所示：</span><span class="sxs-lookup"><span data-stu-id="21556-243">The xpath query will resemble the following:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="21556-244">在此 xpath 查询中， **NotifyReceive**是创建用于接收通知消息的消息。</span><span class="sxs-lookup"><span data-stu-id="21556-244">In this xpath query, **NotifyReceive** is the message you created for receiving notification messages.</span></span> <span data-ttu-id="21556-245">中的摘录`string`函数指明查询必须在值中提取`<Info>`标记，它又是内`<Notification>`标记。</span><span class="sxs-lookup"><span data-stu-id="21556-245">The excerpt within the `string` function indicates that the query must extract the value within the `<Info>` tag, which in turn is within the `<Notification>` tag.</span></span> <span data-ttu-id="21556-246">最后，在查询中提取的值分配给**NotificaitonType**变量。</span><span class="sxs-lookup"><span data-stu-id="21556-246">Finally, the value extracted by the query is assigned to the **NotificaitonType** variable.</span></span>  
  
### <a name="adding-a-decide-shape"></a><span data-ttu-id="21556-247">添加判定形状</span><span class="sxs-lookup"><span data-stu-id="21556-247">Adding a Decide Shape</span></span>  
 <span data-ttu-id="21556-248">添加判定形状的目的是要包含在业务流程，以决定要执行的后续操作根据收到的通知消息类型中的判定块。</span><span class="sxs-lookup"><span data-stu-id="21556-248">The purpose of adding a Decide shape is to include a decision block in the orchestration to decide what subsequent operations to perform based on the kind of notification message received.</span></span> <span data-ttu-id="21556-249">基于的值做出的决定**NotificationType**变量。</span><span class="sxs-lookup"><span data-stu-id="21556-249">The decision is made on the basis of the value of the **NotificationType** variable.</span></span> <span data-ttu-id="21556-250">在本主题中，业务流程可以根据收到的通知消息类型的决策。</span><span class="sxs-lookup"><span data-stu-id="21556-250">In this topic, the orchestration makes a decision based on the kind of notification message received.</span></span> <span data-ttu-id="21556-251">因此，规则形状中的条件，如下所示指定：</span><span class="sxs-lookup"><span data-stu-id="21556-251">So, the condition in the Rule shape is specified as follows:</span></span>  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 <span data-ttu-id="21556-252">这种情况表明，如果的值**NotificaitonType**变量是插入或更新，该业务流程将执行的一组任务。</span><span class="sxs-lookup"><span data-stu-id="21556-252">This condition suggests that if the value for **NotificaitonType** variable is Insert or Update, the orchestration will perform one set of tasks.</span></span> <span data-ttu-id="21556-253">如果的值**NotificationType**变量是任何其他操作，业务流程将执行另一组任务。</span><span class="sxs-lookup"><span data-stu-id="21556-253">If the value of **NotificationType** variable is anything else, the orchestration will perform other set of tasks.</span></span>  
  
 <span data-ttu-id="21556-254">如前面部分中所述，来演示一种简单方法，该业务流程会将消息复制到不同的文件夹的通知消息类型。</span><span class="sxs-lookup"><span data-stu-id="21556-254">As mentioned in the preceding sections, to demonstrate a simple approach, the orchestration will copy messages to different folders based on the notification message type.</span></span> <span data-ttu-id="21556-255">因此，规则中，Else 块，必须添加发送形状将消息发送到不同的端口。</span><span class="sxs-lookup"><span data-stu-id="21556-255">So, within the Rule and Else blocks, you must add Send shapes to send the messages to different ports.</span></span> <span data-ttu-id="21556-256">本主题中，命名为规则块中的发送形状**SendUpsertNotification**和 Else 块作为中的发送形状**SendOtherNotification**。</span><span class="sxs-lookup"><span data-stu-id="21556-256">For this topic, name the Send shape in the Rule block as **SendUpsertNotification** and the Send shape in the Else block as **SendOtherNotification**.</span></span>  
  
### <a name="adding-ports"></a><span data-ttu-id="21556-257">添加端口</span><span class="sxs-lookup"><span data-stu-id="21556-257">Adding Ports</span></span>  
 <span data-ttu-id="21556-258">您现在必须将以下逻辑端口添加到业务流程：</span><span class="sxs-lookup"><span data-stu-id="21556-258">You must now add the following logical ports to the orchestration:</span></span>  
  
- <span data-ttu-id="21556-259">单向接收端口以从 Oracle 数据库接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-259">One-way receive port to receive notification messages from the Oracle database.</span></span>  
  
- <span data-ttu-id="21556-260">单向发送端口以将 Insert 和 Update 操作的通知消息发送到特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="21556-260">One-way send port to send notification messages for Insert and Update operations to a specific folder.</span></span>  
  
- <span data-ttu-id="21556-261">若要将任何其他操作的通知消息发送到特定文件夹的单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="21556-261">One-way send port to send notification messages for any other operations to a specific folder.</span></span>  
  
  <span data-ttu-id="21556-262">请确保为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="21556-262">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="21556-263">中列出的名称**端口**列是本主题前面所述的业务流程关系图中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="21556-263">The names listed in the **Port** column are the names of the ports as displayed in the orchestration diagram shown earlier in this topic.</span></span>  
  
|<span data-ttu-id="21556-264">Port</span><span class="sxs-lookup"><span data-stu-id="21556-264">Port</span></span>|<span data-ttu-id="21556-265">属性</span><span class="sxs-lookup"><span data-stu-id="21556-265">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="21556-266">OracleNotifyPort</span><span class="sxs-lookup"><span data-stu-id="21556-266">OracleNotifyPort</span></span>|<span data-ttu-id="21556-267">-设置**标识符**到*OracleNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="21556-267">- Set **Identifier** to *OracleNotifyPort*</span></span><br /><br /> <span data-ttu-id="21556-268">-设置**类型**到*OracleNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="21556-268">- Set **Type** to *OracleNotifyPortType*</span></span><br /><br /> <span data-ttu-id="21556-269">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="21556-269">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="21556-270">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="21556-270">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="21556-271">NotificationUpsertPort</span><span class="sxs-lookup"><span data-stu-id="21556-271">NotificationUpsertPort</span></span>|<span data-ttu-id="21556-272">-设置**标识符**到*NotificationUpsertPort*</span><span class="sxs-lookup"><span data-stu-id="21556-272">- Set **Identifier** to *NotificationUpsertPort*</span></span><br /><br /> <span data-ttu-id="21556-273">-设置**类型**到*NotificationUpsertPortType*</span><span class="sxs-lookup"><span data-stu-id="21556-273">- Set **Type** to *NotificationUpsertPortType*</span></span><br /><br /> <span data-ttu-id="21556-274">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="21556-274">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="21556-275">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="21556-275">- Set **Communication Direction** to *Send*</span></span>|  
|<span data-ttu-id="21556-276">OtherNotificationPort</span><span class="sxs-lookup"><span data-stu-id="21556-276">OtherNotificationPort</span></span>|<span data-ttu-id="21556-277">-设置**标识符**到*OtherNotificationPort*</span><span class="sxs-lookup"><span data-stu-id="21556-277">- Set **Identifier** to *OtherNotificationPort*</span></span><br /><br /> <span data-ttu-id="21556-278">-设置**类型**到*OtherNotificationPortType*</span><span class="sxs-lookup"><span data-stu-id="21556-278">- Set **Type** to *OtherNotificationPortType*</span></span><br /><br /> <span data-ttu-id="21556-279">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="21556-279">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="21556-280">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="21556-280">- Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="21556-281">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="21556-281">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="21556-282">下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。</span><span class="sxs-lookup"><span data-stu-id="21556-282">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="21556-283">中列出的名称**形状**列是消息形状的名称，如本主题前面所述的业务流程关系图中显示。</span><span class="sxs-lookup"><span data-stu-id="21556-283">The names listed in the **Shape** column are the names of the message shapes as displayed in the orchestration diagram shown earlier in this topic.</span></span>  
  
|<span data-ttu-id="21556-284">形状</span><span class="sxs-lookup"><span data-stu-id="21556-284">Shape</span></span>|<span data-ttu-id="21556-285">属性</span><span class="sxs-lookup"><span data-stu-id="21556-285">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="21556-286">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="21556-286">ReceiveNotification</span></span>|<span data-ttu-id="21556-287">-设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="21556-287">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="21556-288">-设置**操作**到*OracleNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="21556-288">- Set **Operation** to *OracleNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="21556-289">SendUpsertNotification</span><span class="sxs-lookup"><span data-stu-id="21556-289">SendUpsertNotification</span></span>|<span data-ttu-id="21556-290">-设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="21556-290">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="21556-291">-设置**操作**到*NotificationUpsertPort.Upsert.Request*</span><span class="sxs-lookup"><span data-stu-id="21556-291">- Set **Operation** to *NotificationUpsertPort.Upsert.Request*</span></span>|  
|<span data-ttu-id="21556-292">SendOtherNotification</span><span class="sxs-lookup"><span data-stu-id="21556-292">SendOtherNotification</span></span>|<span data-ttu-id="21556-293">-设置**消息**到*选择*</span><span class="sxs-lookup"><span data-stu-id="21556-293">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="21556-294">-设置**操作**到*OtherNotificationPort.Other.Request*</span><span class="sxs-lookup"><span data-stu-id="21556-294">- Set **Operation** to *OtherNotificationPort.Other.Request*</span></span>|  
  
 <span data-ttu-id="21556-295">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="21556-295">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="21556-296">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21556-296">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="21556-297">有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-297">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="21556-298">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="21556-298">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="21556-299">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="21556-299">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="21556-300">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="21556-300">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="21556-301">有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-301">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>  
  
 <span data-ttu-id="21556-302">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="21556-302">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="21556-303">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="21556-303">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="21556-304">映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="21556-304">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="21556-305">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="21556-305">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="21556-306">定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="21556-306">Define a physical WCF-Custom or WCF-OracleEBS one-way receive port.</span></span> <span data-ttu-id="21556-307">此端口侦听来自 Oracle E-business Suite 的通知。</span><span class="sxs-lookup"><span data-stu-id="21556-307">This port listens for notifications coming from Oracle E-Business Suite.</span></span> <span data-ttu-id="21556-308">有关如何创建接收端口，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-308">For information about how to create receive ports, see [Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).</span></span> <span data-ttu-id="21556-309">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="21556-309">Make sure you specify the following binding properties for the receive port.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="21556-310">不需要执行此步骤中，如果指定在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="21556-310">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="21556-311">在这种情况下，您可以创建 WCF 自定义或 WCF OracleEBS 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21556-311">In such a case, you can create a WCF-custom or WCF-OracleEBS receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="21556-312">有关详细信息请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-312">For more information see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
    |<span data-ttu-id="21556-313">绑定属性</span><span class="sxs-lookup"><span data-stu-id="21556-313">Binding Property</span></span>|<span data-ttu-id="21556-314">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="21556-314">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="21556-315">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="21556-315">**InboundOperationType**</span></span>|<span data-ttu-id="21556-316">将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="21556-316">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="21556-317">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="21556-317">**NotificationPort**</span></span>|<span data-ttu-id="21556-318">指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="21556-318">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span> <span data-ttu-id="21556-319">将此设置为相同的端口号必须已添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="21556-319">Set this to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="21556-320">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="21556-320">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span><br /><br /> <span data-ttu-id="21556-321">**重要**如果将其设置为默认值-1，必须完全禁用 Windows 防火墙，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-321">**Important** If you set this to the default value of -1, you will have to completely disable Windows Firewall to receive notification messages.</span></span>|  
    |<span data-ttu-id="21556-322">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="21556-322">**NotificationStatement**</span></span>|<span data-ttu-id="21556-323">将此设置为：</span><span class="sxs-lookup"><span data-stu-id="21556-323">Set this to:</span></span><br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> <span data-ttu-id="21556-324">**请注意**必须指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="21556-324">**Note** You must specify the table name along with the schema name.</span></span> <span data-ttu-id="21556-325">例如，`SCOTT.ACCOUNTACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="21556-325">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>|  
    |<span data-ttu-id="21556-326">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="21556-326">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="21556-327">将此设置为 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="21556-327">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="21556-328">有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-328">For more information about the different binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="21556-329">如果要配置通知的接口表，则必须通过指定必要的绑定属性来设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="21556-329">If you are configuring notifications for an interface table, you must set the application context by specifying the requisite binding properties.</span></span> <span data-ttu-id="21556-330">有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-330">For more information about setting the application context see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="21556-331">我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21556-331">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="21556-332">您为此，可添加服务行为配置 WCF 自定义时或 WCF OracleEBS 接收端口。</span><span class="sxs-lookup"><span data-stu-id="21556-332">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="21556-333">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-333">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
  - <span data-ttu-id="21556-334">硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Insert 和 Update 操作的 Oracle 数据库的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="21556-334">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the notification messages from the Oracle database for Insert and Update operations.</span></span> <span data-ttu-id="21556-335">配置此端口，放到文件夹 C:\TestLocation\UpsertNotification 通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-335">Configure this port to drop notification messages to the folder C:\TestLocation\UpsertNotification.</span></span>  
  
  - <span data-ttu-id="21556-336">硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Oracle 数据库的所有其他操作的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="21556-336">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the notification messages from the Oracle database for all other operations.</span></span> <span data-ttu-id="21556-337">配置此端口，放到文件夹 C:\TestLocation\OtherNotification 通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-337">Configure this port to drop notification messages to the folder C:\TestLocation\OtherNotification.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="21556-338">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="21556-338">Starting the Application</span></span>  
 <span data-ttu-id="21556-339">必须启动 BizTalk 应用程序从 Oracle 数据库接收通知消息并执行后续的 Select 和 Update 操作。</span><span class="sxs-lookup"><span data-stu-id="21556-339">You must start the BizTalk application for receiving notification messages from the Oracle database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="21556-340">在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-340">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="21556-341">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="21556-341">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="21556-342">WCF 自定义或 WCF OracleEBS 单向接收端口，从而从 Oracle 数据库运行时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-342">The WCF-Custom or WCF-OracleEBS one-way receive port, which receives the notification messages from the Oracle database is running.</span></span>  
  
-   <span data-ttu-id="21556-343">正在从 Oracle 数据库接收消息，两个文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="21556-343">The two FILE send ports, which receive messages from Oracle database, are running.</span></span>  
  
-   <span data-ttu-id="21556-344">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="21556-344">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="21556-345">执行该操作</span><span class="sxs-lookup"><span data-stu-id="21556-345">Executing the Operation</span></span>  
 <span data-ttu-id="21556-346">启动 BizTalk 业务流程后，以下组操作发生：</span><span class="sxs-lookup"><span data-stu-id="21556-346">After you start the BizTalk orchestration, the following set of actions take place:</span></span>  
  
-   <span data-ttu-id="21556-347">因为**NotifyOnListenerStart**绑定属性设置为**True**，收到以下消息：</span><span class="sxs-lookup"><span data-stu-id="21556-347">Because the **NotifyOnListenerStart** binding property is set to **True**, you receive the following message:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="21556-348">请注意，中的值`<Info>`标记为"ListnerStarted"。</span><span class="sxs-lookup"><span data-stu-id="21556-348">Note that the value in the `<Info>` tag is “ListnerStarted”.</span></span> <span data-ttu-id="21556-349">因此，C:\TestLocation\OtherNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="21556-349">Hence, this message is received in C:\TestLocation\OtherNotification folder.</span></span>  
  
-   <span data-ttu-id="21556-350">ACCOUNTACTIVITY 表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="21556-350">Insert a record in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="21556-351">你将收到类似于以下的通知消息：</span><span class="sxs-lookup"><span data-stu-id="21556-351">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
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
  
     <span data-ttu-id="21556-352">请注意，中的值`<Info>`标记为"Insert"。</span><span class="sxs-lookup"><span data-stu-id="21556-352">Note that the value in the `<Info>` tag is “Insert”.</span></span> <span data-ttu-id="21556-353">因此，C:\TestLocation\UpsertNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="21556-353">Hence, this message is received in C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="21556-354">更新 ACCOUNTACTIVITY 表中的记录。</span><span class="sxs-lookup"><span data-stu-id="21556-354">Update a record in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="21556-355">你将收到类似于以下的通知消息：</span><span class="sxs-lookup"><span data-stu-id="21556-355">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
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
  
     <span data-ttu-id="21556-356">请注意，中的值`<Info>`标记为"Update"。</span><span class="sxs-lookup"><span data-stu-id="21556-356">Note that the value in the `<Info>` tag is “Update”.</span></span> <span data-ttu-id="21556-357">因此，C:\TestLocation\UpsertNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="21556-357">Hence, this message is received in C:\TestLocation\UpsertNotification folder.</span></span>  
  
-   <span data-ttu-id="21556-358">从 ACCOUNTACTIVITY 表中删除一条记录。</span><span class="sxs-lookup"><span data-stu-id="21556-358">Delete a record from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="21556-359">你将收到类似于以下的通知消息：</span><span class="sxs-lookup"><span data-stu-id="21556-359">You will receive a notification message resembling the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
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
  
     <span data-ttu-id="21556-360">请注意，中的值`<Info>`标记为"Delete"。</span><span class="sxs-lookup"><span data-stu-id="21556-360">Note that the value in the `<Info>` tag is “Delete”.</span></span> <span data-ttu-id="21556-361">因此，C:\TestLocation\OtherNotification 文件夹中收到此消息。</span><span class="sxs-lookup"><span data-stu-id="21556-361">Hence, this message is received in C:\TestLocation\OtherNotification folder.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="21556-362">最佳实践</span><span class="sxs-lookup"><span data-stu-id="21556-362">Best Practices</span></span>  
 <span data-ttu-id="21556-363">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="21556-363">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="21556-364">后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="21556-364">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="21556-365">有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="21556-365">For more information about binding files, see [Reuse Adapter Bindings with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).</span></span>  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a><span data-ttu-id="21556-366">接收通知消息后执行复杂的操作</span><span class="sxs-lookup"><span data-stu-id="21556-366">Performing Complex Operations After Receiving Notification Messages</span></span>  
 <span data-ttu-id="21556-367">对于简单起见，更好地了解本主题中的业务流程将消息复制到不同的文件夹的通知类型。</span><span class="sxs-lookup"><span data-stu-id="21556-367">For simplicity and better understanding, the orchestration in this topic copies messages to different folders based on the notification type.</span></span> <span data-ttu-id="21556-368">但是，在实际方案中你可能想要执行更复杂的操作。</span><span class="sxs-lookup"><span data-stu-id="21556-368">However, in real-world scenarios you might want to perform more complex operations.</span></span> <span data-ttu-id="21556-369">在此主题，并对其执行操作需要的生成中提供，可以执行类似的过程。</span><span class="sxs-lookup"><span data-stu-id="21556-369">You can perform similar procedures as provided in this topic and build on them to perform the operations you wish.</span></span> <span data-ttu-id="21556-370">例如，可以更改业务流程，以在另一个表中插入记录，如果 ACCOUNTACTIVITY 表上的插入操作获取通知消息。</span><span class="sxs-lookup"><span data-stu-id="21556-370">For example, you can change the orchestration to insert records in another table if you get a notification message for an Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="21556-371">在这种情况下，您可以判定形状中的相应更改。</span><span class="sxs-lookup"><span data-stu-id="21556-371">In such a case, you can make appropriate changes within the Decide shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21556-372">请参阅</span><span class="sxs-lookup"><span data-stu-id="21556-372">See Also</span></span>  
 [<span data-ttu-id="21556-373">接收 Oracle E-business Suite 数据库更改通知使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="21556-373">Receive Oracle E-Business Suite Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)