---
title: "通过 AS2 消息配置动态发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6df553a3f03e9d2e60b78de9877ad6113b04e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a><span data-ttu-id="e8582-102">通过 AS2 消息配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="e8582-102">Configuring a Dynamic Send Port for Messages over AS2</span></span>
<span data-ttu-id="e8582-103">本主题介绍如何配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以通过动态发送端口发送 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="e8582-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send AS2 messages over a dynamic send port.</span></span> <span data-ttu-id="e8582-104">此配置包括创建动态发送端口和配置后端应用程序以设置相应的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e8582-104">This configuration includes creating the dynamic send port and configuring a backend application to set the appropriate context properties.</span></span> <span data-ttu-id="e8582-105">在创建动态发送端口以发送 AS2 消息时，您必须升级特定属性才能使相应发送端口工作。</span><span class="sxs-lookup"><span data-stu-id="e8582-105">When you create a dynamic send port to send an AS2 message, you must promote certain properties for the send port to work.</span></span> <span data-ttu-id="e8582-106">有关详细信息，请参阅[配置 BizTalk Server 发送 AS2 消息通过动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc)下面。</span><span class="sxs-lookup"><span data-stu-id="e8582-106">For more information, see [To configure BizTalk Server to send AS2 messages over a dynamic send port](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc) below.</span></span>  
  
 <span data-ttu-id="e8582-107">动态发送端口允许您在参与方配置未进行硬编码的情况下，将消息发送至多个参与方。</span><span class="sxs-lookup"><span data-stu-id="e8582-107">A dynamic send port enables you to send messages to multiple parties without hard-coding the party configuration.</span></span> <span data-ttu-id="e8582-108">发送消息时要使用的协议和目标通过上下文属性动态确定。</span><span class="sxs-lookup"><span data-stu-id="e8582-108">The agreement and destination to be used in sending the message are determined dynamically through context properties.</span></span> <span data-ttu-id="e8582-109">您不必为每个单独的客户创建静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="e8582-109">You do not have to create a static send port for each individual customer.</span></span>  
  
 <span data-ttu-id="e8582-110">若要发送带有 EDI 或非 EDI 消息或者 EDI 确认的 AS2 消息，请使用以下配置创建动态响应 HTTP 发送端口：</span><span class="sxs-lookup"><span data-stu-id="e8582-110">To send an AS2 message with an EDI or non-EDI message or an EDI acknowledgment, create a dynamic response HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="e8582-111">位置</span><span class="sxs-lookup"><span data-stu-id="e8582-111">Location</span></span>|<span data-ttu-id="e8582-112">属性</span><span class="sxs-lookup"><span data-stu-id="e8582-112">Property</span></span>|<span data-ttu-id="e8582-113">设置</span><span class="sxs-lookup"><span data-stu-id="e8582-113">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="e8582-114">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="e8582-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="e8582-115">端口类型</span><span class="sxs-lookup"><span data-stu-id="e8582-115">Port Type</span></span>|<span data-ttu-id="e8582-116">-动态请求响应 (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)</span><span class="sxs-lookup"><span data-stu-id="e8582-116">- Dynamic Solicit Response (if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is selected)</span></span><br /><br /> <span data-ttu-id="e8582-117">-动态单向发送端口 (如果在请求 MDN**确认 (Mdn)**清除的单向协议选项卡中的页)</span><span class="sxs-lookup"><span data-stu-id="e8582-117">- Dynamic One-way Send Port (if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is cleared)</span></span>|  
|<span data-ttu-id="e8582-118">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="e8582-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="e8582-119">发送管道</span><span class="sxs-lookup"><span data-stu-id="e8582-119">Send pipeline</span></span>|<span data-ttu-id="e8582-120">-AS2EdiSend （对于 EDI 编码消息）</span><span class="sxs-lookup"><span data-stu-id="e8582-120">- AS2EdiSend (for EDI-encoded messages)</span></span><br /><br /> <span data-ttu-id="e8582-121">-AS2Send （对于非 EDI 消息）</span><span class="sxs-lookup"><span data-stu-id="e8582-121">- AS2Send (for non-EDI messages)</span></span>|  
|<span data-ttu-id="e8582-122">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="e8582-122">**Send Port Properties: General**</span></span>|<span data-ttu-id="e8582-123">接收管道</span><span class="sxs-lookup"><span data-stu-id="e8582-123">Receive pipeline</span></span><br /><br /> <span data-ttu-id="e8582-124">(如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)</span><span class="sxs-lookup"><span data-stu-id="e8582-124">(if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is selected)</span></span>|<span data-ttu-id="e8582-125">AS2Receive（用于动态要求响应发送端口）</span><span class="sxs-lookup"><span data-stu-id="e8582-125">AS2Receive (for dynamic solicit response send port)</span></span>|  
|<span data-ttu-id="e8582-126">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="e8582-126">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e8582-127">属性</span><span class="sxs-lookup"><span data-stu-id="e8582-127">Property</span></span>|<span data-ttu-id="e8582-128">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="e8582-128">BTS.MessageType</span></span>|  
|<span data-ttu-id="e8582-129">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="e8582-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e8582-130">运算符</span><span class="sxs-lookup"><span data-stu-id="e8582-130">Operator</span></span>|==|  
|<span data-ttu-id="e8582-131">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="e8582-131">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e8582-132">值</span><span class="sxs-lookup"><span data-stu-id="e8582-132">Value</span></span>|<span data-ttu-id="e8582-133">- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>`（对于 EDI 消息）</span><span class="sxs-lookup"><span data-stu-id="e8582-133">- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` (for an EDI message)</span></span><br /><br /> <span data-ttu-id="e8582-134">- `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root`(对于 X12 确认)</span><span class="sxs-lookup"><span data-stu-id="e8582-134">- `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (for an X12 acknowledgment)</span></span><br /><br /> <span data-ttu-id="e8582-135">- `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root`（对于 EDIFACT 确认）</span><span class="sxs-lookup"><span data-stu-id="e8582-135">- `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` (for an EDIFACT acknowledgment)</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="e8582-136">先决条件</span><span class="sxs-lookup"><span data-stu-id="e8582-136">Prerequisites</span></span>  
 <span data-ttu-id="e8582-137">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e8582-137">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
##  <a name="BKMK_Proc"></a><span data-ttu-id="e8582-138">若要配置 BizTalk Server 发送 AS2 消息通过动态发送端口</span><span class="sxs-lookup"><span data-stu-id="e8582-138">To configure BizTalk Server to send AS2 messages over a dynamic send port</span></span>  
  
1.  <span data-ttu-id="e8582-139">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，使用以上配置创建动态单向发送端口（如果未请求 MDN）或动态要求响应发送端口（如果请求了 MDN）。</span><span class="sxs-lookup"><span data-stu-id="e8582-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a dynamic one-way send port (if an MDN is not requested) or a dynamic solicit response send port (if an MDN is requested) with the above configuration.</span></span>  
  
2.  <span data-ttu-id="e8582-140">对于适用于此消息的协议，请设置必需的 AS2 和 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="e8582-140">For the agreement that applies to this message, set the AS2 and EDI properties required.</span></span>  
  
3.  <span data-ttu-id="e8582-141">将下列属性升级到消息上下文：</span><span class="sxs-lookup"><span data-stu-id="e8582-141">Promote the following properties to the message context:</span></span>  
  
    -   `BTS.MessageType`  
  
    -   `EdiIntAS.MessageID`  
  
4.  <span data-ttu-id="e8582-142">向后端应用程序添加功能以将下列属性写入到消息上下文，并为这些属性设置相应的值：</span><span class="sxs-lookup"><span data-stu-id="e8582-142">Add functionality to a backend application to write the following properties to the message context, setting them to the appropriate values:</span></span>  
  
    -   `EdiIntAS.AS2To`  
  
    -   `BTS.OutboundTransportLocation`  
  
    -   `HTTP.EnableChunkedEncoding`  
  
    -   `BTS.EncryptionCert`  
  
    > [!NOTE]
    >  <span data-ttu-id="e8582-143">`AS2To` 上下文属性和 `OutboundTransportLocation` 上下文属性必须写入到消息上下文中，这样才能使动态发送端口正常工作。</span><span class="sxs-lookup"><span data-stu-id="e8582-143">The `AS2To` context property and the `OutboundTransportLocation` context property must be written to the message context for the dynamic send port to function properly.</span></span> <span data-ttu-id="e8582-144">端口需要使用 `AS2To` 属性来确定在处理传出消息时要使用的协议，而发送端口需要使用 `OutboundTransportLocation` 属性来确定消息的目标。</span><span class="sxs-lookup"><span data-stu-id="e8582-144">The `AS2To` property is required for the port to determine the agreement to use in processing the outgoing message and the `OutboundTransportLocation` property is required for the send port to determine the destination of the message.</span></span> <span data-ttu-id="e8582-145">有关详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="e8582-145">For more information, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="e8582-146">功能</span><span class="sxs-lookup"><span data-stu-id="e8582-146">Functionality</span></span>  
 <span data-ttu-id="e8582-147">动态发送端口和管道执行以下操作来通过 AS2 发送同步 EDI 或非 EDI 消息或确认并处理返回的 MDN：</span><span class="sxs-lookup"><span data-stu-id="e8582-147">The dynamic send port and pipeline does the following to send a synchronous EDI or non-EDI message or acknowledgment over AS2 and process the returned MDN:</span></span>  
  
-   <span data-ttu-id="e8582-148">如果发送一个 EDI 消息，则通过设置为 `BTS.MessageType`（例如，864 消息的架构为 X12_00401_864）的属性 `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` 进行筛选来提取 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="e8582-148">If sending an EDI message, picks up the EDI message by filtering on the property `BTS.MessageType` set to the message schema in the `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` (for example, X12_00401_864 for an 864 message).</span></span>  
  
-   <span data-ttu-id="e8582-149">如果发送 EDI 确认，则通过对设置为以下控制架构中某架构的属性 `BTS.MessageType` 进行筛选来提取确认：</span><span class="sxs-lookup"><span data-stu-id="e8582-149">If sending an EDI acknowledgment, picks up the acknowledgment by filtering on the property `BTS.MessageType` set to one of the following control schema:</span></span>  
  
    -   <span data-ttu-id="e8582-150">997 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root`</span><span class="sxs-lookup"><span data-stu-id="e8582-150">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` for a 997 acknowledgment</span></span>  
  
    -   <span data-ttu-id="e8582-151">TA1 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root`</span><span class="sxs-lookup"><span data-stu-id="e8582-151">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` for a TA1 acknowledgment</span></span>  
  
    -   <span data-ttu-id="e8582-152">CONTRL 确认的 `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root`</span><span class="sxs-lookup"><span data-stu-id="e8582-152">`http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` for a CONTRL acknowledgment</span></span>  
  
-   <span data-ttu-id="e8582-153">如果发送非 EDI 消息，则使用相应的筛选器来提取消息。</span><span class="sxs-lookup"><span data-stu-id="e8582-153">If sending a non-EDI message, picks up the message using an appropriate filter.</span></span>  
  
-   <span data-ttu-id="e8582-154">生成 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="e8582-154">Builds an AS2 message.</span></span> <span data-ttu-id="e8582-155">有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="e8582-155">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e8582-156"> 根据 URL 的格式（即 http、smtp、ftp 等）确定动态发送端口要使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="e8582-156"> determines the transport type to be used by the dynamic send port from the format of the URL, i.e., http, smtp, ftp, etc.</span></span>  
  
-   <span data-ttu-id="e8582-157">将消息或确认路由至发送端口的目标 URL。</span><span class="sxs-lookup"><span data-stu-id="e8582-157">Routes the message or acknowledgment to the destination URL for the send port.</span></span>  
  
-   <span data-ttu-id="e8582-158">如果已启用而且是要求响应发送端口，则接收对消息或确认的 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="e8582-158">Receives the MDN response to the message or acknowledgment, if enabled and if a solicit-response send port.</span></span> <span data-ttu-id="e8582-159">有关此过程的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="e8582-159">For more information about this process, see [Processing an Incoming MDN](../core/processing-an-incoming-mdn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8582-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8582-160">See Also</span></span>  
 [<span data-ttu-id="e8582-161">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="e8582-161">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)