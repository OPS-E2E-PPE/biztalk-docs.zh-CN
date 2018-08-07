---
title: WCF 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- receive adapters, Web service headers
- SOAP messages, extracting information
- SOAP messages, WCF adapters
- WCF adapters, receive adapters
- messages, SOAP
- receive adapters, WCF adapters
- Web services, headers
- headers [messages]
- SOAP messages, receive adapters
ms.assetid: 6b3d5df1-5d9d-4240-a98f-ea29c3272e38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c30d858c08da8a0f8d71d56397e43d591b3d773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965830"
---
# <a name="wcf-receive-adapter"></a><span data-ttu-id="bbf39-102">WCF 接收适配器</span><span class="sxs-lookup"><span data-stu-id="bbf39-102">WCF Receive Adapter</span></span>
<span data-ttu-id="bbf39-103">WCF 接收适配器使您可以接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="bbf39-103">The WCF receive adapter enables you to receive WCF service requests.</span></span>  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a><span data-ttu-id="bbf39-104">从 SOAP 消息中提取 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="bbf39-104">Extracting the BizTalk Message Body from the SOAP Message</span></span>  
 <span data-ttu-id="bbf39-105">可使用下列选项之一从 SOAP 消息中提取入站 BizTalk 消息正文：</span><span class="sxs-lookup"><span data-stu-id="bbf39-105">The inbound BizTalk message body can be extracted from the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="bbf39-106">提取 SOAP Body 元素的内容</span><span class="sxs-lookup"><span data-stu-id="bbf39-106">Extract the content of the SOAP Body element</span></span>  
  
- <span data-ttu-id="bbf39-107">提取整个 SOAP 信封</span><span class="sxs-lookup"><span data-stu-id="bbf39-107">Extract the entire SOAP envelope</span></span>  
  
- <span data-ttu-id="bbf39-108">使用 XPath 表达式提取 SOAP 信封内部的元素的内容</span><span class="sxs-lookup"><span data-stu-id="bbf39-108">Extract the content of the element inside the SOAP envelope by using an XPath expression</span></span>  
  
  <span data-ttu-id="bbf39-109">您可以在“传输属性”对话框中配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="bbf39-109">You can configure these options in the transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a><span data-ttu-id="bbf39-110">提取 SOAP Body 元素的内容</span><span class="sxs-lookup"><span data-stu-id="bbf39-110">Extract the Content of the SOAP Body Element</span></span>  
 <span data-ttu-id="bbf39-111">当选中此选项时，将从 SOAP 消息读取 SOAP Body 元素的内部内容，并将其放置到 BizTalk 消息的正文部分中。</span><span class="sxs-lookup"><span data-stu-id="bbf39-111">When this option is selected, the inner content of the SOAP Body element is read from the SOAP message and placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-entire-soap-envelope"></a><span data-ttu-id="bbf39-112">提取整个 SOAP 信封</span><span class="sxs-lookup"><span data-stu-id="bbf39-112">Extract the Entire SOAP Envelope</span></span>  
 <span data-ttu-id="bbf39-113">当选中此选项时，整个 SOAP 信封（包括标记）都将被放置到 BizTalk 消息的正文部分中。</span><span class="sxs-lookup"><span data-stu-id="bbf39-113">When this option is selected, the entire SOAP envelope including the tag is placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a><span data-ttu-id="bbf39-114">使用 XPath 表达式提取元素的内容</span><span class="sxs-lookup"><span data-stu-id="bbf39-114">Extract the Content of the Element by Using an XPath Expression</span></span>  
 <span data-ttu-id="bbf39-115">当选中此选项时，根据 XPath 表达式定位的 SOAP Body 元素内部的元素内部内容将被放置到 BizTalk 消息的正文部分中，</span><span class="sxs-lookup"><span data-stu-id="bbf39-115">When this option is selected, the inner content of the element inside the SOAP Body element that is located by the XPath expression is placed into the body part of the BizTalk message.</span></span> <span data-ttu-id="bbf39-116">并忽略 Body 元素中的其余数据。</span><span class="sxs-lookup"><span data-stu-id="bbf39-116">The rest of the data in the Body element is ignored.</span></span> <span data-ttu-id="bbf39-117">此外需要指定节点编码 — 示例中，XML、 Base64、 Hex 或字符串编码。</span><span class="sxs-lookup"><span data-stu-id="bbf39-117">You also need to specify the node encoding—for example, XML, Base64, Hex, or String encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbf39-118">当选择 XML 编码时，将根据 XPath 表达式定位元素的外部内容，并将其放置到正文部分中。</span><span class="sxs-lookup"><span data-stu-id="bbf39-118">When the XML encoding is selected, the outer content of the element is located by the XPath expression and placed into the body part.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="bbf39-119">处理 Web Services 标头</span><span class="sxs-lookup"><span data-stu-id="bbf39-119">Handling Web Services Headers</span></span>  
 <span data-ttu-id="bbf39-120">接收适配器将标准 Web Services 标头的一部分升级为 BizTalk 消息上下文，以便基于这些标头的值进行更方便的访问和路由。</span><span class="sxs-lookup"><span data-stu-id="bbf39-120">The receive adapter promotes a subset of the standard Web services headers onto the BizTalk message context to enable easy access and routing based on values of those headers.</span></span> <span data-ttu-id="bbf39-121">下表列出了接收适配器将保存为消息上下文的属性。</span><span class="sxs-lookup"><span data-stu-id="bbf39-121">The following table lists the properties that will be saved onto the message context by the receive adapter.</span></span> <span data-ttu-id="bbf39-122">在以下命名空间定义的属性：http://www.w3.org/2005/addressing和http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties。</span><span class="sxs-lookup"><span data-stu-id="bbf39-122">The properties are defined under the following namespaces: http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span></span>  
  
|<span data-ttu-id="bbf39-123">标题</span><span class="sxs-lookup"><span data-stu-id="bbf39-123">Header</span></span>|<span data-ttu-id="bbf39-124">BizTalk 属性名称</span><span class="sxs-lookup"><span data-stu-id="bbf39-124">BizTalk property name</span></span>|<span data-ttu-id="bbf39-125">是否升级？</span><span class="sxs-lookup"><span data-stu-id="bbf39-125">Is promoted?</span></span>|  
|------------|---------------------------|------------------|  
|<span data-ttu-id="bbf39-126">操作</span><span class="sxs-lookup"><span data-stu-id="bbf39-126">Action</span></span>|<span data-ttu-id="bbf39-127">操作</span><span class="sxs-lookup"><span data-stu-id="bbf39-127">Action</span></span>|<span data-ttu-id="bbf39-128">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-128">Yes</span></span>|  
|<span data-ttu-id="bbf39-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="bbf39-129">MessageID</span></span>|<span data-ttu-id="bbf39-130">MessageID</span><span class="sxs-lookup"><span data-stu-id="bbf39-130">MessageID</span></span>|<span data-ttu-id="bbf39-131">“否”</span><span class="sxs-lookup"><span data-stu-id="bbf39-131">No</span></span>|  
|<span data-ttu-id="bbf39-132">若要</span><span class="sxs-lookup"><span data-stu-id="bbf39-132">To</span></span>|<span data-ttu-id="bbf39-133">若要</span><span class="sxs-lookup"><span data-stu-id="bbf39-133">To</span></span>|<span data-ttu-id="bbf39-134">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-134">Yes</span></span>|  
|<span data-ttu-id="bbf39-135">ReplyTo/Address</span><span class="sxs-lookup"><span data-stu-id="bbf39-135">ReplyTo/Address</span></span>|<span data-ttu-id="bbf39-136">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="bbf39-136">ReplyTo</span></span>|<span data-ttu-id="bbf39-137">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-137">Yes</span></span>|  
|<span data-ttu-id="bbf39-138">From/Address</span><span class="sxs-lookup"><span data-stu-id="bbf39-138">From/Address</span></span>|<span data-ttu-id="bbf39-139">From</span><span class="sxs-lookup"><span data-stu-id="bbf39-139">From</span></span>|<span data-ttu-id="bbf39-140">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-140">Yes</span></span>|  
|<span data-ttu-id="bbf39-141">Sequence/Identifier</span><span class="sxs-lookup"><span data-stu-id="bbf39-141">Sequence/Identifier</span></span>|<span data-ttu-id="bbf39-142">SequenceId</span><span class="sxs-lookup"><span data-stu-id="bbf39-142">SequenceId</span></span>|<span data-ttu-id="bbf39-143">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-143">Yes</span></span>|  
|<span data-ttu-id="bbf39-144">Sequence/MessageNumber</span><span class="sxs-lookup"><span data-stu-id="bbf39-144">Sequence/MessageNumber</span></span>|<span data-ttu-id="bbf39-145">SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bbf39-145">SequenceNumber</span></span>|<span data-ttu-id="bbf39-146">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-146">Yes</span></span>|  
|<span data-ttu-id="bbf39-147">Sequence/LastMessage</span><span class="sxs-lookup"><span data-stu-id="bbf39-147">Sequence/LastMessage</span></span>|<span data-ttu-id="bbf39-148">SequenceLastMessage</span><span class="sxs-lookup"><span data-stu-id="bbf39-148">SequenceLastMessage</span></span>|<span data-ttu-id="bbf39-149">是</span><span class="sxs-lookup"><span data-stu-id="bbf39-149">Yes</span></span>|  
|<span data-ttu-id="bbf39-150">\<soap： 标头\></span><span class="sxs-lookup"><span data-stu-id="bbf39-150">\<soap:Header\></span></span>|<span data-ttu-id="bbf39-151">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="bbf39-151">InboundHeaders</span></span>|<span data-ttu-id="bbf39-152">“否”</span><span class="sxs-lookup"><span data-stu-id="bbf39-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbf39-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf39-153">See Also</span></span>  
 <span data-ttu-id="bbf39-154">[指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="bbf39-154">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="bbf39-155">[WCF 发送适配器](../core/wcf-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bbf39-155">[WCF Send Adapter](../core/wcf-send-adapter.md) </span></span>  
 [<span data-ttu-id="bbf39-156">WCF 适配器概述</span><span class="sxs-lookup"><span data-stu-id="bbf39-156">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)