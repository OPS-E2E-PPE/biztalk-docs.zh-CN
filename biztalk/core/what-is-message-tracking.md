---
title: 什么是消息跟踪？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, metadata
- HAT, messages
- messages, tracking
- data, HAT
- metadata, tracking
- tracking, metadata
- HAT, data security
- tracking, messages
- configuring [HAT tracking], messages
- data, security
ms.assetid: 51cec59d-b411-4d8f-b771-7b2cf0f38945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e20978905628072269b0acf0990d67dc4582b414
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394027"
---
# <a name="what-is-message-tracking"></a><span data-ttu-id="10652-103">什么是消息跟踪？</span><span class="sxs-lookup"><span data-stu-id="10652-103">What is Message Tracking?</span></span>
<span data-ttu-id="10652-104">一条消息是通常交换两个之间的数据电子实例运行的业务流程或应用程序。</span><span class="sxs-lookup"><span data-stu-id="10652-104">A message is an electronic instance of data, as typically exchanged between two running business processes or applications.</span></span> <span data-ttu-id="10652-105">消息实例消息正文、 消息属性和元数据组成。</span><span class="sxs-lookup"><span data-stu-id="10652-105">A message instance is made up of a message body, message properties, and metadata.</span></span>  
  
 <span data-ttu-id="10652-106">可以使用 BizTalk Server 管理控制台来启用消息正文和消息属性跟踪。</span><span class="sxs-lookup"><span data-stu-id="10652-106">You can use the BizTalk Server Administration Console to enable message body and message property tracking.</span></span> <span data-ttu-id="10652-107">那里您还可以查看跟踪的消息正文，包括架构信息、 强名称，以及所生成消息的升级的所有属性。</span><span class="sxs-lookup"><span data-stu-id="10652-107">There you can also view the tracked message body, including schema information, strong name, and all the promoted properties for the generated message.</span></span>  
  
## <a name="message-body"></a><span data-ttu-id="10652-108">消息正文</span><span class="sxs-lookup"><span data-stu-id="10652-108">Message Body</span></span>  
 <span data-ttu-id="10652-109">跟踪消息正文，可发送和接收消息的记录。</span><span class="sxs-lookup"><span data-stu-id="10652-109">Tracking the message body provides a record of messages sent and received.</span></span> <span data-ttu-id="10652-110">您必须具有消息正文跟踪，以便将消息保存在服务实例处理后打开已完成。</span><span class="sxs-lookup"><span data-stu-id="10652-110">You must have message body tracking turned on in order to save messages after service instances processing is complete.</span></span> <span data-ttu-id="10652-111">设置跟踪选项后，它可能需要几分钟之后您可以查看的消息。</span><span class="sxs-lookup"><span data-stu-id="10652-111">After you have set the tracking options, it can take a few minutes before you can view the messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10652-112">SQL Server 代理服务必须在所有 MessageBox 数据库上运行。</span><span class="sxs-lookup"><span data-stu-id="10652-112">The SQL Server Agent service must be running on all MessageBox databases.</span></span> <span data-ttu-id="10652-113">TrackedMessages_Copy_\<MessageBoxName\>作业，消息正文跟踪查询和 WMI 可。</span><span class="sxs-lookup"><span data-stu-id="10652-113">The TrackedMessages_Copy_\<MessageBoxName\> job makes message bodies available to tracking queries and WMI.</span></span> <span data-ttu-id="10652-114">若要有效地复制消息正文，它们在 MessageBox 数据库中保留和 TrackedMessages_Copy_ 通过定期复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库\<MessageBoxName\>作业。</span><span class="sxs-lookup"><span data-stu-id="10652-114">To efficiently copy the message bodies, they remain in the MessageBox database and are periodically copied to the BizTalk Tracking (BizTalkDTADb) database by the TrackedMessages_Copy_\<MessageBoxName\> job.</span></span> <span data-ttu-id="10652-115">具有运行的 SQL Server 代理服务也是存档和清除进程才能正常工作的先决条件。</span><span class="sxs-lookup"><span data-stu-id="10652-115">Having the SQL Server Agent service running is also a prerequisite for the archiving and purging process to work correctly.</span></span>  
  
 <span data-ttu-id="10652-116">跟踪的消息可用于提供回执，以实现故障排除，并允许数据挖掘的历史事务确认。</span><span class="sxs-lookup"><span data-stu-id="10652-116">You can use tracked messages to provide confirmation of receipt, to enable troubleshooting, and to allow data mining of historical transactions.</span></span> <span data-ttu-id="10652-117">你可以跟踪输入和输出端口、 管道和业务流程的消息正文。</span><span class="sxs-lookup"><span data-stu-id="10652-117">You can track the message bodies at the input and output of ports, pipelines, and orchestrations.</span></span> <span data-ttu-id="10652-118">您可以恢复这些消息使用 BizTalk Server 管理控制台，使用操作对象模型 (OM) （推荐） 或通过 Windows Management Instrumentation (WMI) 应用程序编程接口 (Api)。</span><span class="sxs-lookup"><span data-stu-id="10652-118">You can recover these messages using the BizTalk Server Administration Console, using the Operations object model (OM) (recommended) or through Windows Management Instrumentation (WMI) application programming interfaces (APIs).</span></span>  
  
 <span data-ttu-id="10652-119">BizTalk Server 不会跟踪不成功使其通过其中一个跟踪点的消息。</span><span class="sxs-lookup"><span data-stu-id="10652-119">BizTalk Server does not track messages that do not successfully make it through one of the tracking points.</span></span> <span data-ttu-id="10652-120">在某些情况下，如当被挂起一条消息，因为它是无效的或如果没有主机接收消息，它可能被放在挂起队列而不被跟踪。</span><span class="sxs-lookup"><span data-stu-id="10652-120">In some cases—such as when a message is suspended because it is invalid, or if no host is expecting the message—it may be placed in the Suspended queue without being tracked.</span></span> <span data-ttu-id="10652-121">如果您终止此消息将有它的任何记录。</span><span class="sxs-lookup"><span data-stu-id="10652-121">If you terminate this message there will be no record of it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10652-122">消息正文跟踪不能代替具有法律约束力的审核，并不支持不可否认性。</span><span class="sxs-lookup"><span data-stu-id="10652-122">Message body tracking is not a substitute for legally binding auditing, and does not support nonrepudiation.</span></span>  
  
## <a name="message-properties"></a><span data-ttu-id="10652-123">消息属性</span><span class="sxs-lookup"><span data-stu-id="10652-123">Message Properties</span></span>  
 <span data-ttu-id="10652-124">消息属性包括升级的属性，路由信息和贸易合作伙伴数据。</span><span class="sxs-lookup"><span data-stu-id="10652-124">Message properties include promoted properties, routing information, and trading partner data.</span></span> <span data-ttu-id="10652-125">消息属性跟踪，可查找你可能会跟踪的结果列表中每个消息中提供的升级属性的记录与千位特定的消息。</span><span class="sxs-lookup"><span data-stu-id="10652-125">Message property tracking enables you to locate a specific message from the thousands that you may have tracked, by providing a record of promoted properties for each message in the results list.</span></span> <span data-ttu-id="10652-126">你可以跟踪消息本身的子集使用这些属性之一。</span><span class="sxs-lookup"><span data-stu-id="10652-126">You can then track a subset of the message itself, using one of these properties.</span></span>  
  
 <span data-ttu-id="10652-127">若要跟踪上下文属性，您定义的上下文中用于存储属性的命名空间的属性架构。</span><span class="sxs-lookup"><span data-stu-id="10652-127">To track context properties, you define a property schema for the namespace used in the context to store the properties.</span></span> <span data-ttu-id="10652-128">在这里，可以选择想要跟踪的上下文属性。BizTalk Server 跟踪与跟踪升级的消息属性的方式相同。</span><span class="sxs-lookup"><span data-stu-id="10652-128">From there, you can select the context properties you want to track. BizTalk Server tracks them in the same way it tracks promoted message properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10652-129">请确保为架构中的属性不同的名称。</span><span class="sxs-lookup"><span data-stu-id="10652-129">Make sure you give different names to the properties in the schema.</span></span> <span data-ttu-id="10652-130">如果您创建重复的名称，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="10652-130">An error message appears if you create duplicate names.</span></span>  
  
 <span data-ttu-id="10652-131">例如，可以使用架构编辑器将从采购订单架构升级采购订单编号字段。</span><span class="sxs-lookup"><span data-stu-id="10652-131">For example, you could use the Schema Editor to promote the PO Number field from a Purchase Order schema.</span></span> <span data-ttu-id="10652-132">然后，使用查找消息视图，您会发现消息实例，包含特定值该跟踪字段，如 PO Number = 16995。</span><span class="sxs-lookup"><span data-stu-id="10652-132">Then, using the Find Message View, you could find the message instances that contain a particular value for that tracked field, such as PO Number = 16995.</span></span>  
  
 <span data-ttu-id="10652-133">消息属性跟踪产生要少得多的开销比消息正文跟踪，因为消息属性跟踪只跟踪选定的字段。</span><span class="sxs-lookup"><span data-stu-id="10652-133">Message property tracking creates much less overhead than message body tracking, because message property tracking only tracks the selected fields.</span></span> <span data-ttu-id="10652-134">设置消息属性的跟踪选项后，它可能需要几分钟之后您可以查看的属性。</span><span class="sxs-lookup"><span data-stu-id="10652-134">After you set the tracking options for the message property, it can take a few minutes before you can view the properties.</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="10652-135">元数据</span><span class="sxs-lookup"><span data-stu-id="10652-135">Metadata</span></span>  
 <span data-ttu-id="10652-136">元数据，例如消息实例标识符、 业务流程或管道记录消息的业务流程或管道记录消息，以及其他相关的跟踪详细信息的点。</span><span class="sxs-lookup"><span data-stu-id="10652-136">Metadata, such as the message instance identifier, the orchestration or pipeline logging the message, the point at which the orchestration or pipeline logs the message, and other relevant tracking details.</span></span> <span data-ttu-id="10652-137">对于路由业务流程到 MessageBox 数据库中的消息，它必须包含上下文属性，如消息类型和源。</span><span class="sxs-lookup"><span data-stu-id="10652-137">For a message in the MessageBox database to route to a business process, it must contain context properties such as message type and origin.</span></span> <span data-ttu-id="10652-138">这些属性将成为元数据。</span><span class="sxs-lookup"><span data-stu-id="10652-138">These properties become metadata.</span></span> <span data-ttu-id="10652-139">消息和服务实例跟踪使用订阅条件来查询此类元数据。</span><span class="sxs-lookup"><span data-stu-id="10652-139">Message and service instance tracking uses subscription criteria to query against this metadata.</span></span>  
  
 <span data-ttu-id="10652-140">通过 BizTalk Server 管理控制台中，您可以通过选择特定的系统架构升级上下文属性。</span><span class="sxs-lookup"><span data-stu-id="10652-140">Through the BizTalk Server Administration Console, you can promote context properties by selecting the particular system schema.</span></span> <span data-ttu-id="10652-141">系统架构位于 Applications\BizTalk.System\Schemas 节点中。</span><span class="sxs-lookup"><span data-stu-id="10652-141">The system schemas are located in the Applications\BizTalk.System\Schemas node.</span></span> <span data-ttu-id="10652-142">BizTalk Server 全局跟踪这些上下文属性 — 也就是说，所有消息现在都跟踪特定的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="10652-142">BizTalk Server tracks these context properties globally—that is, all messages now track the particular context property.</span></span> <span data-ttu-id="10652-143">这可以显著提高 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="10652-143">This may significantly increase the size of the BizTalk Tracking database.</span></span>  
  
## <a name="sensitive-data"></a><span data-ttu-id="10652-144">敏感数据</span><span class="sxs-lookup"><span data-stu-id="10652-144">Sensitive Data</span></span>  
 <span data-ttu-id="10652-145">可以保护以下数据确保它没有显示在相应的架构属性窗口中，从而避免进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="10652-145">You can secure the following data ensuring that it does not appear in corresponding schemas property window and therefore becomes unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="10652-146">将应用**isSensitive**属性在属性架构中，任何敏感属性，这样就不再显示在消息属性跟踪的配置选择。</span><span class="sxs-lookup"><span data-stu-id="10652-146">Apply the **isSensitive** attribute to any sensitive properties in a property schema, so that it is no longer visible in the Message Property tracking configuration selections.</span></span>  
  
-   <span data-ttu-id="10652-147">所有的开箱传输包含标记为敏感，因此无法跟踪传输的密码。</span><span class="sxs-lookup"><span data-stu-id="10652-147">All out-of-box transports contain passwords marked as sensitive, so the transports cannot be tracked.</span></span>  
  
-   <span data-ttu-id="10652-148">此外，这些敏感属性将不再在管理数据库中，因此，如果您在设置跟踪选项直接在数据库中的，它们用于跟踪不可用。</span><span class="sxs-lookup"><span data-stu-id="10652-148">In addition, these sensitive properties are no longer in the Management database, so if you are setting tracking options directly in the database, they are unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="10652-149">如果您跟踪出站网络上消息正文，跟踪的消息将从所跟踪的消息正文的快捷方式删除所有传输属性。</span><span class="sxs-lookup"><span data-stu-id="10652-149">If you track outbound on-the-wire message bodies, message tracking removes all the transport properties from the shortcut of the tracked message body.</span></span> <span data-ttu-id="10652-150">因此，除了从所跟踪的消息正文的快捷方式中删除出站传输属性，消息跟踪还会删除属性从入站传输。</span><span class="sxs-lookup"><span data-stu-id="10652-150">Therefore, in addition to removing outbound transport properties from the shortcut of the tracked message body, message tracking also removes properties from inbound transports.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="10652-151">升级的属性可以包含敏感数据。</span><span class="sxs-lookup"><span data-stu-id="10652-151">A promoted property can contain sensitive data.</span></span> <span data-ttu-id="10652-152">如果从组中心页的跟踪查询跟踪包含敏感数据的属性，有权运行跟踪查询的任何用户可以查看此数据。</span><span class="sxs-lookup"><span data-stu-id="10652-152">If tracking queries from the Group Hub page track a property which includes sensitive data, any user with permissions to run the tracking queries can view this data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10652-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="10652-153">See Also</span></span>  
 [<span data-ttu-id="10652-154">使用 BizTalk Server 管理控制台配置跟踪</span><span class="sxs-lookup"><span data-stu-id="10652-154">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)
