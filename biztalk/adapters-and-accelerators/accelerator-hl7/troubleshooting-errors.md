---
title: 错误故障排除 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ad99b699da29d4d8680375f88e4d4a74ff66a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207165"
---
# <a name="troubleshooting-errors"></a><span data-ttu-id="e0a2a-102">排除错误</span><span class="sxs-lookup"><span data-stu-id="e0a2a-102">Troubleshooting Errors</span></span>
<span data-ttu-id="e0a2a-103">本部分讲述与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成了错误。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-103">This section addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generated errors.</span></span>  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a><span data-ttu-id="e0a2a-104">只能在单个主机实例下运行 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="e0a2a-104">The MLLP adapter can run only on a single host instance</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-105">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-105">Symptom</span></span>  
 <span data-ttu-id="e0a2a-106">不能启用与传输类型为 MLLP 接收位置和比另一个现有的接收位置不同的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-106">You cannot enable a receive location with a transport type of MLLP and a different receive handler than another existing receive location.</span></span> <span data-ttu-id="e0a2a-107">此外，无法登记，并开始发送端口不是另一个现有发送端口开始与不同的发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-107">In addition, you cannot enlist and start a send port with a different send handler than another existing send port.</span></span>  
  
<span data-ttu-id="e0a2a-108">**可能的原因**： 你只能使用一个 MLLP 接收 （或发送） 的单个服务器上的处理程序。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-108">**Possible Cause** : You can only use one MLLP receive (or send) handler on a single server.</span></span> <span data-ttu-id="e0a2a-109">此外，该 URI 指定用于接收位置 （或发送端口） （MLLP 传输属性中的主机名称） 必须是"localhost"或运行其中主机实例接收 （或发送） 适配器处理程序的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-109">In addition, the URI designated for the receive location (or send port) (the Host name in the MLLP Transport Properties) must either be "localhost" or the server name where the host instance for the receive (or send) adapter handler is running.</span></span>  
  
<span data-ttu-id="e0a2a-110">**解析**： 一台服务器上的所有 MLLP 接收位置 （或发送端口） 指定相同的接收 （或发送） 处理程序。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-110">**Resolution** : Designate the same receive (or send) handler for all MLLP receive locations (or send ports) on a single server.</span></span>  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a><span data-ttu-id="e0a2a-111">MSH 和 ACK 架构必须添加到只有一个项目</span><span class="sxs-lookup"><span data-stu-id="e0a2a-111">MSH and ACK schemas must be added to only one project</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-112">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-112">Symptom</span></span>  
 <span data-ttu-id="e0a2a-113">当你尝试生成项目时，会得到以下错误之一：</span><span class="sxs-lookup"><span data-stu-id="e0a2a-113">When you attempt to build a project, you get one of the following errors:</span></span>  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
<span data-ttu-id="e0a2a-114">**可能的原因**: MSH 和 ACK 架构 （MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd） 已部署在多个项目。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-114">**Possible Cause** : The MSH and ACK schemas (MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd) have been deployed in multiple projects.</span></span>  
  
<span data-ttu-id="e0a2a-115">**解析**： 确保 MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd 已添加到只有一个项目。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-115">**Resolution** : Ensure that MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd have been added to only one project.</span></span>  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a><span data-ttu-id="e0a2a-116">具有事件日志中引发了错误类型 System.OutOfMemoryException 异常</span><span class="sxs-lookup"><span data-stu-id="e0a2a-116">Exception of type System.OutOfMemoryException has thrown an error in the Event Log</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-117">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-117">Symptom</span></span>  
 <span data-ttu-id="e0a2a-118">事件日志中获取以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="e0a2a-118">You get the following or similar error in the Event Log:</span></span>  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
<span data-ttu-id="e0a2a-119">**可能的原因**： 某些处理大量消息时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎组件可能会出现内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-119">**Possible Cause** : While processing a large number of messages, some [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] engine components may exhibit memory leaks.</span></span>  
  
<span data-ttu-id="e0a2a-120">**解析**： 重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-120">**Resolution** : Restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a><span data-ttu-id="e0a2a-121">标头序列化在事件查看器中生成错误</span><span class="sxs-lookup"><span data-stu-id="e0a2a-121">Header serialization generates an error in the Event Viewer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-122">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-122">Symptom</span></span>  
 <span data-ttu-id="e0a2a-123">即使在运行状况和活动跟踪 (HAT) 工具消息指示安装成功，可以在事件日志中，收到以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="e0a2a-123">You get the following or similar error in the Event Log, even though the message in the Health and Activity Tracking (HAT) tool indicates success:</span></span>  
  
`An error happened in the header during serialization.`
  
<span data-ttu-id="e0a2a-124">**可能的原因**： 未正确设置消息标头转换值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-124">**Possible Cause** : The message header transformation value is not set correctly in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
<span data-ttu-id="e0a2a-125">**解析**： 验证 MSH 映射中的值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-125">**Resolution** : Verify MSH map values in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a><span data-ttu-id="e0a2a-126">重复事件 ID 4133 记录序列化程序错误</span><span class="sxs-lookup"><span data-stu-id="e0a2a-126">Duplicate Event ID 4133 serializer errors are logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-127">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-127">Symptom</span></span>  
 <span data-ttu-id="e0a2a-128">事件 ID 4133 –"过程中发生错误标头中序列化"两次进行 MSH11 值不是有效的消息的每个实例。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-128">Event ID 4133 – "Error happened in header during serialization" occurs twice for every instance of a message with a MSH11 value that is not valid.</span></span>  
  
<span data-ttu-id="e0a2a-129">**可能的原因**： 而无需重复事件日志中的错误处理 （提交和应用程序确认） 的两个确认时出错。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-129">**Possible Cause** : An error occurred while processing two acknowledgments (Commit and Application ACKs) without duplicate errors in the Event Log.</span></span> <span data-ttu-id="e0a2a-130">相反，每两个 Ack 收到一个事件 ID 4133。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-130">Instead, you receive one Event ID 4133 for each of the two ACKs.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e0a2a-131">它会生成每个 ACK 为创建一个日志条目。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-131"> creates a log entry for each ACK it generates.</span></span>  
  
<span data-ttu-id="e0a2a-132">**解析**： 确保你的消息具有正确格式化和填充 MSH11 字段。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-132">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH11 field.</span></span>  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a><span data-ttu-id="e0a2a-133">发送管道将双向 MLLP 适配器时生成错误</span><span class="sxs-lookup"><span data-stu-id="e0a2a-133">Send pipeline generates an error when using the 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="e0a2a-134">故障现象</span><span class="sxs-lookup"><span data-stu-id="e0a2a-134">Symptom</span></span>  
 <span data-ttu-id="e0a2a-135">事件日志中获取以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="e0a2a-135">You get the following or similar error in the Event Log:</span></span>  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
<span data-ttu-id="e0a2a-136">**可能的原因**： 接收应用程序不响应与确认和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预期向接收应用程序的响应。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-136">**Possible Cause** : The receiving application does not respond with an Acknowledgment and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is expecting a response from the receiving application.</span></span>  
  
<span data-ttu-id="e0a2a-137">**解析**： 这是设计使然，并且你可以忽略该错误消息。</span><span class="sxs-lookup"><span data-stu-id="e0a2a-137">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a2a-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a2a-138">See Also</span></span>  
 [<span data-ttu-id="e0a2a-139">在 HL7 疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="e0a2a-139">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)