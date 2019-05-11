---
title: 有关 AS2 处理的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389184d177fe1b192db22660bdf382a6e64f37bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329372"
---
# <a name="known-issues-with-as2-processing"></a><span data-ttu-id="d8304-102">AS2 处理的已知的问题</span><span class="sxs-lookup"><span data-stu-id="d8304-102">Known Issues with AS2 Processing</span></span>
<span data-ttu-id="d8304-103">本部分包含介绍了 BizTalk Server AS2 解决方案的已知的问题的主题。</span><span class="sxs-lookup"><span data-stu-id="d8304-103">This section contains topics that describe known issues with BizTalk Server AS2 solutions.</span></span>  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a><span data-ttu-id="d8304-104">不支持在 64 位计算机上的 AS2 处理</span><span class="sxs-lookup"><span data-stu-id="d8304-104">AS2 Processing Not Supported on 64-Bit Computers</span></span>  
 <span data-ttu-id="d8304-105">64 位计算机上不支持 BizTalk Server AS2 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d8304-105">The BizTalk Server AS2 solution is not supported on 64-bit computers.</span></span> <span data-ttu-id="d8304-106">AS2 处理只能在 32 位计算机上或在 64 位计算机上在 WOW64 仿真器下运行。</span><span class="sxs-lookup"><span data-stu-id="d8304-106">AS2 processing only works on 32-bit computers or when running under the WOW64 emulator on 64-bit computers.</span></span>  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a><span data-ttu-id="d8304-107">AS2 接收管道要求，BizTalk 独立主机实例进程正在运行的是一部分 BizTalk Application Users 组的帐户</span><span class="sxs-lookup"><span data-stu-id="d8304-107">The AS2 Receive Pipelines Require the Account that the BizTalk Isolated Host Instance Process is Running Under to Be Part of the BizTalk Application Users Group</span></span>  
 <span data-ttu-id="d8304-108">如果使用 AS2EdiReceive 或 AS2Receive 管道，则必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d8304-108">If you are using the AS2EdiReceive or AS2Receive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="d8304-109">AS2EdiReceive 和 AS2Receive 管道在 BizTalk 独立主机实例进程中执行。</span><span class="sxs-lookup"><span data-stu-id="d8304-109">The AS2EdiReceive and AS2Receive pipelines execute in the BizTalk Isolated Host Instance process.</span></span>  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a><span data-ttu-id="d8304-110">回执送达选项标头为空将导致同步发送 MDN</span><span class="sxs-lookup"><span data-stu-id="d8304-110">An Empty Receipt-Delivery-Option Header Will Cause an MDN to Be Sent Synchronously</span></span>  
 <span data-ttu-id="d8304-111">如果 AS2Receive 管道接收的消息回执送达选项标头为空，并且请求异步 MDN，则该管道将忽略异步 MDN 请求。</span><span class="sxs-lookup"><span data-stu-id="d8304-111">If the AS2Receive pipeline receives a message with an empty receipt-delivery-option header, and an asynchronous MDN is requested, the pipeline will ignore the asynchronous MDN request.</span></span> <span data-ttu-id="d8304-112">它将发送回一个同步 MDN，并发布错误，事件日志和 AS2 状态报告 （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="d8304-112">It will send back a synchronous MDN instead, and post an error in the event log and in AS2 status reporting (if it is enabled).</span></span> <span data-ttu-id="d8304-113">如果未选中"替代入站的消息属性"属性，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d8304-113">This occurs if the "Override inbound message properties" property is not selected.</span></span> <span data-ttu-id="d8304-114">如果已选择该属性，它将会替代的消息的参与方中的回执送达选项属性的值的回执送达选项标头作为 AS2 消息发送方的 AS2 属性对话框的页。</span><span class="sxs-lookup"><span data-stu-id="d8304-114">If that property were selected, it would override the Receipt-Delivery-Option header in the message with the value of the Receipt-Delivery-Option property in the Party as AS2 Message Sender page of the AS2 Properties dialog box.</span></span>  
  
 <span data-ttu-id="d8304-115">在此情况下，由于回执送达选项标头为空，因此 AS2Receive 管道没有要发送的 MDN 响应通过异步连接的地址。</span><span class="sxs-lookup"><span data-stu-id="d8304-115">In this instance, because the receipt-delivery-option header is empty, the AS2Receive pipeline does not have an address to send the MDN response to over an asynchronous connection.</span></span> <span data-ttu-id="d8304-116">但是，该管道仍然具有打开的同步连接，因此它将返回通过该连接发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="d8304-116">However, the pipeline still has an open synchronous connection, so it will send the MDN back over that connection.</span></span> <span data-ttu-id="d8304-117">如果它是一个单向接收端口，BizTalk Server 将关闭在发送 HTTP 200OK 消息之后连接。</span><span class="sxs-lookup"><span data-stu-id="d8304-117">If it is a one-way receive port, BizTalk Server will close the connection after sending the HTTP 200OK message.</span></span>  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a><span data-ttu-id="d8304-118">使用展开和折叠 HTTP 行标头</span><span class="sxs-lookup"><span data-stu-id="d8304-118">Use of Unfolded and Folded HTTP Line Headers</span></span>  
 <span data-ttu-id="d8304-119">最大互操作性，应为 AS2 消息使用的 HTTP 行标的头。</span><span class="sxs-lookup"><span data-stu-id="d8304-119">For maximum interoperability, you should use unfolded HTTP line headers for AS2 messages.</span></span> <span data-ttu-id="d8304-120">信息服务 (IIS) 7.0 支持仅展开的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="d8304-120">Information Services (IIS) 7.0 supports only unfolded HTTP headers.</span></span> <span data-ttu-id="d8304-121">IIS 6.0 支持折叠和展开的标头。</span><span class="sxs-lookup"><span data-stu-id="d8304-121">IIS 6.0 supports folded and unfolded headers.</span></span> <span data-ttu-id="d8304-122">但是，不是所有系统可以都支持标头与每行，超过 80 个字符，因此对于此类系统，应使用折叠的行。</span><span class="sxs-lookup"><span data-stu-id="d8304-122">However, not all systems can support headers with more than 80 characters per line, so for such systems folded lines should be used.</span></span>  
  
 <span data-ttu-id="d8304-123">在 BizTalk Server 中 as2 默认值为 HTTP 行标的头。</span><span class="sxs-lookup"><span data-stu-id="d8304-123">The default for AS2 in BizTalk Server is unfolded HTTP line headers.</span></span>  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a><span data-ttu-id="d8304-124">参与方解析可能会受到本地化名称</span><span class="sxs-lookup"><span data-stu-id="d8304-124">Party Resolution Can Be Affected by a Localized Name</span></span>  
 <span data-ttu-id="d8304-125">当 BizTalk Server 上的出站 AS2 消息执行参与方解析时，参与方解析可能受到消息标头中本地化的值。</span><span class="sxs-lookup"><span data-stu-id="d8304-125">When BizTalk Server performs party resolution on an outbound AS2 message, the party resolution can be affected by a localized value in the message headers.</span></span> <span data-ttu-id="d8304-126">如果 AS2-To 参与方的参与方中的属性，因为 AS2 消息接收方的 AS2 属性对话框的页设置为英文参与方名称，而 AS2 中的值默认情况下-To 标头的 as2 消息设置为非英文名称，则将找不到匹配项。</span><span class="sxs-lookup"><span data-stu-id="d8304-126">If the AS2-To party property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
## <a name="as2-message-size-limitation"></a><span data-ttu-id="d8304-127">AS2 消息大小限制</span><span class="sxs-lookup"><span data-stu-id="d8304-127">AS2 Message Size Limitation</span></span>  
 <span data-ttu-id="d8304-128">加密的 AS2 消息应小于 96 兆字节为单位，才能进行处理。</span><span class="sxs-lookup"><span data-stu-id="d8304-128">Encrypted AS2 messages should be smaller than 96 megabytes in order to be processed.</span></span> <span data-ttu-id="d8304-129">此限制规定 AS2 解码器，它是 AS2Receive 和 AS2EdiReceive 管道的一部分。</span><span class="sxs-lookup"><span data-stu-id="d8304-129">This limitation is imposed by the AS2 Decoder, which is the part of the AS2Receive and AS2EdiReceive pipelines.</span></span>  
  
 <span data-ttu-id="d8304-130">若要解决此大小限制的一种方法是使用压缩，因为 AS2 消息进行压缩，再对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="d8304-130">One way to work around this size limitation is to use compression, because an AS2 message is compressed before it is encrypted.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="d8304-131">不得修改 BizTalk EDI 应用程序</span><span class="sxs-lookup"><span data-stu-id="d8304-131">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="d8304-132">不得修改或删除 BizTalk EDI 应用程序中的项目。</span><span class="sxs-lookup"><span data-stu-id="d8304-132">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="d8304-133">如果修改此应用程序，则没有办法可以恢复到原始应用程序通过取消配置和重新配置 EDI 和 AS2 功能。</span><span class="sxs-lookup"><span data-stu-id="d8304-133">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="partner-may-reject-multipart-messages"></a><span data-ttu-id="d8304-134">合作伙伴可能会拒绝多部分消息</span><span class="sxs-lookup"><span data-stu-id="d8304-134">Partner May Reject Multipart Messages</span></span>  
 <span data-ttu-id="d8304-135">**症状**</span><span class="sxs-lookup"><span data-stu-id="d8304-135">**Symptom**</span></span>  
  
 <span data-ttu-id="d8304-136">在发送多部分消息使用 AS2 发送管道时，你的合作伙伴可能会拒绝消息，因为缺少内容类型 MIME 标头。</span><span class="sxs-lookup"><span data-stu-id="d8304-136">When sending multipart messages using the AS2 send pipeline, your partner may reject the message due to a missing Content-Type MIME header.</span></span>  
  
 <span data-ttu-id="d8304-137">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d8304-137">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d8304-138">内容类型是一个可为每个正文部分出现在多部分消息的可选标头。</span><span class="sxs-lookup"><span data-stu-id="d8304-138">Content-Type is an optional header that can be present for each body part in a multipart message.</span></span> <span data-ttu-id="d8304-139">一些合作伙伴要求此标头存在每个正文部分，并将设置为特定的内容类型。</span><span class="sxs-lookup"><span data-stu-id="d8304-139">Some partners require that this header is present for each body part, and set to a specific content-type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8304-140">消息的正文将拥有通过 AS2 发送管道中，设置内容类型的属性，但任何附件都不会将内容类型属性设置。</span><span class="sxs-lookup"><span data-stu-id="d8304-140">The body of the message will have the Content-Type property set by the AS2 send pipeline, however any attachments will not have the Content-Type property set.</span></span>  
  
 <span data-ttu-id="d8304-141">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d8304-141">**Resolution**</span></span>  
  
 <span data-ttu-id="d8304-142">如果您的合作伙伴要求各正文部分内容类型标头值，必须创建一个自定义管道组件设置此属性，并在发送管道中使用该组件。</span><span class="sxs-lookup"><span data-stu-id="d8304-142">If your partner requires the Content-Type header value for each body part, you must create a custom pipeline component that sets this property and use the component in the send pipeline.</span></span>  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a><span data-ttu-id="d8304-143">当接收多部分消息，第一部分视为正文</span><span class="sxs-lookup"><span data-stu-id="d8304-143">When Receiving Multipart Messages, the First Part is Considered the Body</span></span>  
 <span data-ttu-id="d8304-144">**症状**</span><span class="sxs-lookup"><span data-stu-id="d8304-144">**Symptom**</span></span>  
  
 <span data-ttu-id="d8304-145">当接收多部分 AS2 消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能错误地将其中一个附件标识为消息正文。</span><span class="sxs-lookup"><span data-stu-id="d8304-145">When receiving a multipart AS2 message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may incorrectly identify one of the attachments as the message body.</span></span>  
  
 <span data-ttu-id="d8304-146">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d8304-146">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d8304-147">多部分/相关消息的 MIME 标头可能包含一个可选 start 参数，用于指示该部分应视为通过指定部件的内容 ID 的消息的正文。</span><span class="sxs-lookup"><span data-stu-id="d8304-147">The MIME header of a multipart/related message may contain an optional ‘start’ parameter that indicates which of the parts should be treated as the body of the message by specifying the Content-ID of the part.</span></span> <span data-ttu-id="d8304-148">如果不存在 start 参数，第一部分应被视为消息正文。</span><span class="sxs-lookup"><span data-stu-id="d8304-148">If the start parameter is not present, the first part should be considered the body of the message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d8304-149">如果它存在，并且始终会将第一部分视为消息正文，则不会遵循 start 参数。</span><span class="sxs-lookup"><span data-stu-id="d8304-149">does not honor the start parameter if it is present, and will always treat the first part as the body of the message.</span></span>  
  
 <span data-ttu-id="d8304-150">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d8304-150">**Resolution**</span></span>  
  
 <span data-ttu-id="d8304-151">如果你的合作伙伴不能发送正文作为多部分/相关消息的第一部分，则必须创建正确标识消息的正文的管道组件。</span><span class="sxs-lookup"><span data-stu-id="d8304-151">If your partner is unable to send the body as the first part of the multipart/related message, you must create a pipeline component that correctly identifies the body of the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8304-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8304-152">See Also</span></span>  
 <span data-ttu-id="d8304-153">[EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="d8304-153">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="d8304-154">[AS2 解决方案体系结构](../core/as2-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d8304-154">[AS2 Solution Architecture](../core/as2-solution-architecture.md) </span></span>  
 [<span data-ttu-id="d8304-155">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="d8304-155">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)