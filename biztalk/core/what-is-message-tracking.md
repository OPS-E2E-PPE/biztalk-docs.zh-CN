---
title: 什么是邮件跟踪？ | Microsoft Docs
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
ms.openlocfilehash: 0d76a4bd4133906a7949fac9e63816168506f412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974635"
---
# <a name="what-is-message-tracking"></a><span data-ttu-id="f326c-103">什么是邮件跟踪？</span><span class="sxs-lookup"><span data-stu-id="f326c-103">What is Message Tracking?</span></span>
<span data-ttu-id="f326c-104">消息是一种电子形式的数据实例，通常在两个运行的业务流程或应用程序之间进行交换。</span><span class="sxs-lookup"><span data-stu-id="f326c-104">A message is an electronic instance of data, as typically exchanged between two running business processes or applications.</span></span> <span data-ttu-id="f326c-105">消息实例由消息正文、消息属性和元数据构成。</span><span class="sxs-lookup"><span data-stu-id="f326c-105">A message instance is made up of a message body, message properties, and metadata.</span></span>  
  
 <span data-ttu-id="f326c-106">可以使用 BizTalk Server 管理控制台来启用消息正文和消息属性的跟踪。</span><span class="sxs-lookup"><span data-stu-id="f326c-106">You can use the BizTalk Server Administration Console to enable message body and message property tracking.</span></span> <span data-ttu-id="f326c-107">那里还可以查看跟踪的消息正文，包括架构信息、强名称以及所生成消息的全部升级属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-107">There you can also view the tracked message body, including schema information, strong name, and all the promoted properties for the generated message.</span></span>  
  
## <a name="message-body"></a><span data-ttu-id="f326c-108">消息正文</span><span class="sxs-lookup"><span data-stu-id="f326c-108">Message Body</span></span>  
 <span data-ttu-id="f326c-109">跟踪消息正文可以对所发送和接收的消息进行记录。</span><span class="sxs-lookup"><span data-stu-id="f326c-109">Tracking the message body provides a record of messages sent and received.</span></span> <span data-ttu-id="f326c-110">必须打开消息正文跟踪功能，才能在服务实例处理完成后保存消息。</span><span class="sxs-lookup"><span data-stu-id="f326c-110">You must have message body tracking turned on in order to save messages after service instances processing is complete.</span></span> <span data-ttu-id="f326c-111">在设置跟踪选项后，可能需要几分钟才能查看消息。</span><span class="sxs-lookup"><span data-stu-id="f326c-111">After you have set the tracking options, it can take a few minutes before you can view the messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f326c-112">所有 MessageBox 数据库中都必须运行 SQL Server 代理服务。</span><span class="sxs-lookup"><span data-stu-id="f326c-112">The SQL Server Agent service must be running on all MessageBox databases.</span></span> <span data-ttu-id="f326c-113">TrackedMessages_Copy_\<MessageBoxName\>作业使消息正文可用于跟踪查询和 WMI。</span><span class="sxs-lookup"><span data-stu-id="f326c-113">The TrackedMessages_Copy_\<MessageBoxName\> job makes message bodies available to tracking queries and WMI.</span></span> <span data-ttu-id="f326c-114">若要有效地复制消息正文，它们在 MessageBox 数据库中保留和 TrackedMessages_Copy_ 定期复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库\<MessageBoxName\>作业。</span><span class="sxs-lookup"><span data-stu-id="f326c-114">To efficiently copy the message bodies, they remain in the MessageBox database and are periodically copied to the BizTalk Tracking (BizTalkDTADb) database by the TrackedMessages_Copy_\<MessageBoxName\> job.</span></span> <span data-ttu-id="f326c-115">运行 SQL Server 代理服务是存档和清除进程得以正常运转的前提条件。</span><span class="sxs-lookup"><span data-stu-id="f326c-115">Having the SQL Server Agent service running is also a prerequisite for the archiving and purging process to work correctly.</span></span>  
  
 <span data-ttu-id="f326c-116">使用跟踪的消息可以提供回执确认、进行故障排除并对历史事务进行数据挖掘。</span><span class="sxs-lookup"><span data-stu-id="f326c-116">You can use tracked messages to provide confirmation of receipt, to enable troubleshooting, and to allow data mining of historical transactions.</span></span> <span data-ttu-id="f326c-117">可以跟踪输入与输出端口、管道及业务流程中的消息正文。</span><span class="sxs-lookup"><span data-stu-id="f326c-117">You can track the message bodies at the input and output of ports, pipelines, and orchestrations.</span></span> <span data-ttu-id="f326c-118">使用 BizTalk Server 管理控制台、使用操作对象模型 (OM)（建议），或通过 Windows 管理规范 (WMI) 应用程序编程接口 (API)，可以恢复这些消息。</span><span class="sxs-lookup"><span data-stu-id="f326c-118">You can recover these messages using the BizTalk Server Administration Console, using the Operations object model (OM) (recommended) or through Windows Management Instrumentation (WMI) application programming interfaces (APIs).</span></span>  
  
 <span data-ttu-id="f326c-119">如果消息未成功地通过任何一个跟踪点，则 BizTalk Server 不会对其进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="f326c-119">BizTalk Server does not track messages that do not successfully make it through one of the tracking points.</span></span> <span data-ttu-id="f326c-120">在某些情况下，例如当消息由于无效而挂起或没有任何主机接收该消息时，该消息将会放入挂起队列中而不被跟踪。</span><span class="sxs-lookup"><span data-stu-id="f326c-120">In some cases—such as when a message is suspended because it is invalid, or if no host is expecting the message—it may be placed in the Suspended queue without being tracked.</span></span> <span data-ttu-id="f326c-121">如果您终止此消息，则不会有它的任何记录。</span><span class="sxs-lookup"><span data-stu-id="f326c-121">If you terminate this message there will be no record of it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f326c-122">消息正文跟踪不能代替具有法律约束力的审核，不能杜绝抵赖现象。</span><span class="sxs-lookup"><span data-stu-id="f326c-122">Message body tracking is not a substitute for legally binding auditing, and does not support nonrepudiation.</span></span>  
  
## <a name="message-properties"></a><span data-ttu-id="f326c-123">消息属性</span><span class="sxs-lookup"><span data-stu-id="f326c-123">Message Properties</span></span>  
 <span data-ttu-id="f326c-124">跟踪的消息属性包括升级的属性、路由信息和贸易合作伙伴数据等。</span><span class="sxs-lookup"><span data-stu-id="f326c-124">Message properties include promoted properties, routing information, and trading partner data.</span></span> <span data-ttu-id="f326c-125">消息属性跟踪功能可以在结果列表中提供对每个消息的升级属性的记录，以便您从所跟踪的数千个消息中找到特定的消息。</span><span class="sxs-lookup"><span data-stu-id="f326c-125">Message property tracking enables you to locate a specific message from the thousands that you may have tracked, by providing a record of promoted properties for each message in the results list.</span></span> <span data-ttu-id="f326c-126">然后，您可以使用这些属性中的某一个属性来跟踪消息本身包含的内容。</span><span class="sxs-lookup"><span data-stu-id="f326c-126">You can then track a subset of the message itself, using one of these properties.</span></span>  
  
 <span data-ttu-id="f326c-127">为跟踪上下文属性，您还需要为上下文中使用的命名空间定义属性架构，以存储这些属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-127">To track context properties, you define a property schema for the namespace used in the context to store the properties.</span></span> <span data-ttu-id="f326c-128">在该视图中可以选择希望跟踪的上下文属性。BizTalk Server 跟踪上下文属性的方式与跟踪升级的消息属性的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f326c-128">From there, you can select the context properties you want to track. BizTalk Server tracks them in the same way it tracks promoted message properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f326c-129">请确保为架构中的属性指定了不同的名称。</span><span class="sxs-lookup"><span data-stu-id="f326c-129">Make sure you give different names to the properties in the schema.</span></span> <span data-ttu-id="f326c-130">如果创建了重复的名称，则会出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="f326c-130">An error message appears if you create duplicate names.</span></span>  
  
 <span data-ttu-id="f326c-131">例如，可以使用架构编辑器升级采购订单架构中的“PO Number”字段。</span><span class="sxs-lookup"><span data-stu-id="f326c-131">For example, you could use the Schema Editor to promote the PO Number field from a Purchase Order schema.</span></span> <span data-ttu-id="f326c-132">然后使用“查找消息”视图可找到包含该跟踪字段的特定值（如 PO Number = 16995）的消息实例。</span><span class="sxs-lookup"><span data-stu-id="f326c-132">Then, using the Find Message View, you could find the message instances that contain a particular value for that tracked field, such as PO Number = 16995.</span></span>  
  
 <span data-ttu-id="f326c-133">消息属性跟踪比消息正文跟踪所产生的系统开销小得多，因为消息属性跟踪只跟踪选定的字段。</span><span class="sxs-lookup"><span data-stu-id="f326c-133">Message property tracking creates much less overhead than message body tracking, because message property tracking only tracks the selected fields.</span></span> <span data-ttu-id="f326c-134">为消息属性设置跟踪选项后，可能需要几分钟才能查看属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-134">After you set the tracking options for the message property, it can take a few minutes before you can view the properties.</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="f326c-135">元数据</span><span class="sxs-lookup"><span data-stu-id="f326c-135">Metadata</span></span>  
 <span data-ttu-id="f326c-136">跟踪的元数据包括消息实例标识符、记录消息的业务流程或管道、业务流程或管道记录消息时的所在点，以及其他相关的跟踪详细信息。</span><span class="sxs-lookup"><span data-stu-id="f326c-136">Metadata, such as the message instance identifier, the orchestration or pipeline logging the message, the point at which the orchestration or pipeline logs the message, and other relevant tracking details.</span></span> <span data-ttu-id="f326c-137">MessageBox 数据库中的消息必须包含上下文属性（如消息类型和来源），才能路由到业务流程。</span><span class="sxs-lookup"><span data-stu-id="f326c-137">For a message in the MessageBox database to route to a business process, it must contain context properties such as message type and origin.</span></span> <span data-ttu-id="f326c-138">这些属性将成为元数据。</span><span class="sxs-lookup"><span data-stu-id="f326c-138">These properties become metadata.</span></span> <span data-ttu-id="f326c-139">消息和服务实例跟踪使用订阅条件来查询此类元数据。</span><span class="sxs-lookup"><span data-stu-id="f326c-139">Message and service instance tracking uses subscription criteria to query against this metadata.</span></span>  
  
 <span data-ttu-id="f326c-140">在 BizTalk Server 管理控制台中，通过选择特定的系统架构可以升级上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-140">Through the BizTalk Server Administration Console, you can promote context properties by selecting the particular system schema.</span></span> <span data-ttu-id="f326c-141">系统架构位于 Applications\BizTalk.System\Schemas 节点中。</span><span class="sxs-lookup"><span data-stu-id="f326c-141">The system schemas are located in the Applications\BizTalk.System\Schemas node.</span></span> <span data-ttu-id="f326c-142">BizTalk Server 全局地跟踪这些上下文属性，也就是说，现在所有消息都跟踪特定的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-142">BizTalk Server tracks these context properties globally—that is, all messages now track the particular context property.</span></span> <span data-ttu-id="f326c-143">这会显著地增大 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="f326c-143">This may significantly increase the size of the BizTalk Tracking database.</span></span>  
  
## <a name="sensitive-data"></a><span data-ttu-id="f326c-144">敏感数据</span><span class="sxs-lookup"><span data-stu-id="f326c-144">Sensitive Data</span></span>  
 <span data-ttu-id="f326c-145">您可以保护以下数据，确保这些数据不会显示在相应的架构属性窗口中，从而避免对其进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="f326c-145">You can secure the following data ensuring that it does not appear in corresponding schemas property window and therefore becomes unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="f326c-146">应用**isSensitive**属性到在属性架构中，任何敏感属性，以便不再跟踪的配置选择的消息属性中可见。</span><span class="sxs-lookup"><span data-stu-id="f326c-146">Apply the **isSensitive** attribute to any sensitive properties in a property schema, so that it is no longer visible in the Message Property tracking configuration selections.</span></span>  
  
-   <span data-ttu-id="f326c-147">所有全新传输都包含标记为“敏感”的密码，因此不会跟踪此类传输。</span><span class="sxs-lookup"><span data-stu-id="f326c-147">All out-of-box transports contain passwords marked as sensitive, so the transports cannot be tracked.</span></span>  
  
-   <span data-ttu-id="f326c-148">此外，管理数据库中不再包含这些敏感属性，因此，如果您在该数据库中直接设置跟踪选项，则无法对其进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="f326c-148">In addition, these sensitive properties are no longer in the Management database, so if you are setting tracking options directly in the database, they are unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="f326c-149">如果您跟踪出站的网络消息正文，则消息跟踪将从所跟踪消息正文的快捷方式中删除所有传输属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-149">If you track outbound on-the-wire message bodies, message tracking removes all the transport properties from the shortcut of the tracked message body.</span></span> <span data-ttu-id="f326c-150">因此，除了从所跟踪消息正文的快捷方式中删除出站传输属性之外，消息跟踪还会删除入站传输的属性。</span><span class="sxs-lookup"><span data-stu-id="f326c-150">Therefore, in addition to removing outbound transport properties from the shortcut of the tracked message body, message tracking also removes properties from inbound transports.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f326c-151">升级的属性可能会包含敏感数据。</span><span class="sxs-lookup"><span data-stu-id="f326c-151">A promoted property can contain sensitive data.</span></span> <span data-ttu-id="f326c-152">如果“组中心”页中的跟踪查询跟踪包含敏感数据的属性，则有权运行跟踪查询的任何用户都可以查看此数据。</span><span class="sxs-lookup"><span data-stu-id="f326c-152">If tracking queries from the Group Hub page track a property which includes sensitive data, any user with permissions to run the tracking queries can view this data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f326c-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f326c-153">See Also</span></span>  
 [<span data-ttu-id="f326c-154">配置使用 BizTalk Server 管理控制台的跟踪</span><span class="sxs-lookup"><span data-stu-id="f326c-154">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)