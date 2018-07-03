---
title: 错误故障排除 |Microsoft Docs
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
ms.openlocfilehash: 2f5af933f83f292bfae3f92f70d2c247274c159c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976854"
---
# <a name="troubleshooting-errors"></a><span data-ttu-id="56312-102">错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="56312-102">Troubleshooting Errors</span></span>
<span data-ttu-id="56312-103">本部分解决与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成了错误。</span><span class="sxs-lookup"><span data-stu-id="56312-103">This section addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generated errors.</span></span>  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a><span data-ttu-id="56312-104">MLLP 适配器可以仅在单个主机实例上运行</span><span class="sxs-lookup"><span data-stu-id="56312-104">The MLLP adapter can run only on a single host instance</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-105">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-105">Symptom</span></span>  
 <span data-ttu-id="56312-106">不能启用与传输类型为 MLLP 的接收位置和不同的接收处理程序比另一个现有的接收位置。</span><span class="sxs-lookup"><span data-stu-id="56312-106">You cannot enable a receive location with a transport type of MLLP and a different receive handler than another existing receive location.</span></span> <span data-ttu-id="56312-107">此外，不能登记并启动发送端口与不同的发送处理程序，不是另一个现有发送端口。</span><span class="sxs-lookup"><span data-stu-id="56312-107">In addition, you cannot enlist and start a send port with a different send handler than another existing send port.</span></span>  
  
<span data-ttu-id="56312-108">**可能的原因**： 你只能使用一个 MLLP 接收 （或发送） 在单个服务器上的处理程序。</span><span class="sxs-lookup"><span data-stu-id="56312-108">**Possible Cause** : You can only use one MLLP receive (or send) handler on a single server.</span></span> <span data-ttu-id="56312-109">此外，该 URI 指定为接收位置 （或发送端口） （MLLP 传输属性中的主机名） 必须是"localhost"或运行主机实例接收 （或发送） 适配器处理程序的位置的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="56312-109">In addition, the URI designated for the receive location (or send port) (the Host name in the MLLP Transport Properties) must either be "localhost" or the server name where the host instance for the receive (or send) adapter handler is running.</span></span>  
  
<span data-ttu-id="56312-110">**解析**： 一台服务器上的所有 MLLP 接收位置 （或发送端口） 指定相同的接收 （或发送） 处理程序。</span><span class="sxs-lookup"><span data-stu-id="56312-110">**Resolution** : Designate the same receive (or send) handler for all MLLP receive locations (or send ports) on a single server.</span></span>  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a><span data-ttu-id="56312-111">MSH 和确认架构必须添加到只有一个项目</span><span class="sxs-lookup"><span data-stu-id="56312-111">MSH and ACK schemas must be added to only one project</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-112">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-112">Symptom</span></span>  
 <span data-ttu-id="56312-113">在尝试生成项目，将获得以下错误之一：</span><span class="sxs-lookup"><span data-stu-id="56312-113">When you attempt to build a project, you get one of the following errors:</span></span>  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
<span data-ttu-id="56312-114">**可能的原因**: MSH 和确认架构 （MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd） 已部署在多个项目中。</span><span class="sxs-lookup"><span data-stu-id="56312-114">**Possible Cause** : The MSH and ACK schemas (MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd) have been deployed in multiple projects.</span></span>  
  
<span data-ttu-id="56312-115">**解析**： 请确保 MSH_25_GLO_DEF.xsd 和 ACK_24_GLO_DEF.xsd 已添加到一个项目。</span><span class="sxs-lookup"><span data-stu-id="56312-115">**Resolution** : Ensure that MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd have been added to only one project.</span></span>  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a><span data-ttu-id="56312-116">具有事件日志中引发错误异常类型 System.OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="56312-116">Exception of type System.OutOfMemoryException has thrown an error in the Event Log</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-117">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-117">Symptom</span></span>  
 <span data-ttu-id="56312-118">事件日志中收到以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="56312-118">You get the following or similar error in the Event Log:</span></span>  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
<span data-ttu-id="56312-119">**可能的原因**： 某些处理大量消息，时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎组件可能会出现内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="56312-119">**Possible Cause** : While processing a large number of messages, some [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] engine components may exhibit memory leaks.</span></span>  
  
<span data-ttu-id="56312-120">**解决方法**： 重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="56312-120">**Resolution** : Restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a><span data-ttu-id="56312-121">标头序列化事件查看器中生成一个错误</span><span class="sxs-lookup"><span data-stu-id="56312-121">Header serialization generates an error in the Event Viewer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-122">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-122">Symptom</span></span>  
 <span data-ttu-id="56312-123">尽管运行状况与活动跟踪 (HAT) 工具中的消息表示成功事件日志中获取以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="56312-123">You get the following or similar error in the Event Log, even though the message in the Health and Activity Tracking (HAT) tool indicates success:</span></span>  
  
`An error happened in the header during serialization.`
  
<span data-ttu-id="56312-124">**可能的原因**： 未正确设置消息标头转换值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="56312-124">**Possible Cause** : The message header transformation value is not set correctly in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
<span data-ttu-id="56312-125">**解决方法**： 验证 MSH 映射中的值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="56312-125">**Resolution** : Verify MSH map values in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a><span data-ttu-id="56312-126">重复事件 ID 4133 序列化程序错误记录</span><span class="sxs-lookup"><span data-stu-id="56312-126">Duplicate Event ID 4133 serializer errors are logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-127">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-127">Symptom</span></span>  
 <span data-ttu-id="56312-128">事件 ID 4133 –"过程中发生错误标头中序列化"两次发生 MSH11 值不是有效的消息的每个实例。</span><span class="sxs-lookup"><span data-stu-id="56312-128">Event ID 4133 – "Error happened in header during serialization" occurs twice for every instance of a message with a MSH11 value that is not valid.</span></span>  
  
<span data-ttu-id="56312-129">**可能的原因**： 不包含在事件日志中的重复错误处理两个确认 （提交和应用程序的确认） 时出错。</span><span class="sxs-lookup"><span data-stu-id="56312-129">**Possible Cause** : An error occurred while processing two acknowledgments (Commit and Application ACKs) without duplicate errors in the Event Log.</span></span> <span data-ttu-id="56312-130">相反，为每个的两个确认收到一个事件 ID 4133。</span><span class="sxs-lookup"><span data-stu-id="56312-130">Instead, you receive one Event ID 4133 for each of the two ACKs.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="56312-131"> 创建的每个 ACK 中它将生成一个日志条目。</span><span class="sxs-lookup"><span data-stu-id="56312-131"> creates a log entry for each ACK it generates.</span></span>  
  
<span data-ttu-id="56312-132">**解析**： 确保消息是否具有正确格式化和填充 MSH11 字段。</span><span class="sxs-lookup"><span data-stu-id="56312-132">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH11 field.</span></span>  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a><span data-ttu-id="56312-133">发送管道时使用 2 种方法处的 MLLP 适配器生成错误</span><span class="sxs-lookup"><span data-stu-id="56312-133">Send pipeline generates an error when using the 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="56312-134">故障现象</span><span class="sxs-lookup"><span data-stu-id="56312-134">Symptom</span></span>  
 <span data-ttu-id="56312-135">事件日志中收到以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="56312-135">You get the following or similar error in the Event Log:</span></span>  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "Microsoft.Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
<span data-ttu-id="56312-136">**可能的原因**： 接收应用程序不响应与确认和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]期望来自接收应用程序的响应。</span><span class="sxs-lookup"><span data-stu-id="56312-136">**Possible Cause** : The receiving application does not respond with an Acknowledgment and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is expecting a response from the receiving application.</span></span>  
  
<span data-ttu-id="56312-137">**解析**： 这是设计使然，并且可以忽略的错误消息。</span><span class="sxs-lookup"><span data-stu-id="56312-137">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56312-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="56312-138">See Also</span></span>  
 [<span data-ttu-id="56312-139">HL7 的疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="56312-139">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)