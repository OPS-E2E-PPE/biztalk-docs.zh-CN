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
ms.openlocfilehash: 86d7f307a9c7dae45e81e8c9c1e5bcf57a6ef6b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266391"
---
# <a name="wcf-receive-adapter"></a><span data-ttu-id="fff75-102">WCF 接收适配器</span><span class="sxs-lookup"><span data-stu-id="fff75-102">WCF Receive Adapter</span></span>
<span data-ttu-id="fff75-103">WCF 接收适配器使您可以接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="fff75-103">The WCF receive adapter enables you to receive WCF service requests.</span></span>  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a><span data-ttu-id="fff75-104">从 SOAP 消息提取 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="fff75-104">Extracting the BizTalk Message Body from the SOAP Message</span></span>  
 <span data-ttu-id="fff75-105">可以使用以下选项之一从 SOAP 消息中提取入站的 BizTalk 消息正文：</span><span class="sxs-lookup"><span data-stu-id="fff75-105">The inbound BizTalk message body can be extracted from the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="fff75-106">提取 SOAP Body 元素的内容</span><span class="sxs-lookup"><span data-stu-id="fff75-106">Extract the content of the SOAP Body element</span></span>  
  
- <span data-ttu-id="fff75-107">提取整个 SOAP 信封</span><span class="sxs-lookup"><span data-stu-id="fff75-107">Extract the entire SOAP envelope</span></span>  
  
- <span data-ttu-id="fff75-108">使用 XPath 表达式提取 SOAP 信封内的元素的内容</span><span class="sxs-lookup"><span data-stu-id="fff75-108">Extract the content of the element inside the SOAP envelope by using an XPath expression</span></span>  
  
  <span data-ttu-id="fff75-109">在传输属性对话框中，可以配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="fff75-109">You can configure these options in the transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a><span data-ttu-id="fff75-110">提取 SOAP Body 元素的内容</span><span class="sxs-lookup"><span data-stu-id="fff75-110">Extract the Content of the SOAP Body Element</span></span>  
 <span data-ttu-id="fff75-111">选中此选项后，SOAP Body 元素内部内容是从 SOAP 消息中读取并放置到 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="fff75-111">When this option is selected, the inner content of the SOAP Body element is read from the SOAP message and placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-entire-soap-envelope"></a><span data-ttu-id="fff75-112">提取整个 SOAP 信封</span><span class="sxs-lookup"><span data-stu-id="fff75-112">Extract the Entire SOAP Envelope</span></span>  
 <span data-ttu-id="fff75-113">选择此选项，包括标记的整个 SOAP envelope 放置到 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="fff75-113">When this option is selected, the entire SOAP envelope including the tag is placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a><span data-ttu-id="fff75-114">使用 XPath 表达式提取元素的内容</span><span class="sxs-lookup"><span data-stu-id="fff75-114">Extract the Content of the Element by Using an XPath Expression</span></span>  
 <span data-ttu-id="fff75-115">选中此选项后，根据 XPath 表达式定位的 SOAP Body 元素内的元素的内部内容放置到 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="fff75-115">When this option is selected, the inner content of the element inside the SOAP Body element that is located by the XPath expression is placed into the body part of the BizTalk message.</span></span> <span data-ttu-id="fff75-116">正文元素中的数据的其余部分将被忽略。</span><span class="sxs-lookup"><span data-stu-id="fff75-116">The rest of the data in the Body element is ignored.</span></span> <span data-ttu-id="fff75-117">此外需要指定节点编码 — 示例中，XML、 Base64、 Hex 或字符串编码。</span><span class="sxs-lookup"><span data-stu-id="fff75-117">You also need to specify the node encoding—for example, XML, Base64, Hex, or String encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fff75-118">选择 XML 编码时，是根据 XPath 表达式定位外部元素的内容并将其放置到正文部分。</span><span class="sxs-lookup"><span data-stu-id="fff75-118">When the XML encoding is selected, the outer content of the element is located by the XPath expression and placed into the body part.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="fff75-119">处理 Web Services 标头</span><span class="sxs-lookup"><span data-stu-id="fff75-119">Handling Web Services Headers</span></span>  
 <span data-ttu-id="fff75-120">接收适配器将 BizTalk 消息上下文，能够轻松地访问标准 Web services 标头的子集和路由基于这些标头的值。</span><span class="sxs-lookup"><span data-stu-id="fff75-120">The receive adapter promotes a subset of the standard Web services headers onto the BizTalk message context to enable easy access and routing based on values of those headers.</span></span> <span data-ttu-id="fff75-121">下表列出了将由接收适配器保存到消息上下文上的属性。</span><span class="sxs-lookup"><span data-stu-id="fff75-121">The following table lists the properties that will be saved onto the message context by the receive adapter.</span></span> <span data-ttu-id="fff75-122">在以下命名空间定义的属性： http://www.w3.org/2005/addressing和 http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties。</span><span class="sxs-lookup"><span data-stu-id="fff75-122">The properties are defined under the following namespaces: http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span></span>  
  
|<span data-ttu-id="fff75-123">Header</span><span class="sxs-lookup"><span data-stu-id="fff75-123">Header</span></span>|<span data-ttu-id="fff75-124">BizTalk 属性名称</span><span class="sxs-lookup"><span data-stu-id="fff75-124">BizTalk property name</span></span>|<span data-ttu-id="fff75-125">是否升级？</span><span class="sxs-lookup"><span data-stu-id="fff75-125">Is promoted?</span></span>|  
|------------|---------------------------|------------------|  
|<span data-ttu-id="fff75-126">操作</span><span class="sxs-lookup"><span data-stu-id="fff75-126">Action</span></span>|<span data-ttu-id="fff75-127">操作</span><span class="sxs-lookup"><span data-stu-id="fff75-127">Action</span></span>|<span data-ttu-id="fff75-128">是</span><span class="sxs-lookup"><span data-stu-id="fff75-128">Yes</span></span>|  
|<span data-ttu-id="fff75-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="fff75-129">MessageID</span></span>|<span data-ttu-id="fff75-130">MessageID</span><span class="sxs-lookup"><span data-stu-id="fff75-130">MessageID</span></span>|<span data-ttu-id="fff75-131">否</span><span class="sxs-lookup"><span data-stu-id="fff75-131">No</span></span>|  
|<span data-ttu-id="fff75-132">若要</span><span class="sxs-lookup"><span data-stu-id="fff75-132">To</span></span>|<span data-ttu-id="fff75-133">若要</span><span class="sxs-lookup"><span data-stu-id="fff75-133">To</span></span>|<span data-ttu-id="fff75-134">是</span><span class="sxs-lookup"><span data-stu-id="fff75-134">Yes</span></span>|  
|<span data-ttu-id="fff75-135">ReplyTo/Address</span><span class="sxs-lookup"><span data-stu-id="fff75-135">ReplyTo/Address</span></span>|<span data-ttu-id="fff75-136">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="fff75-136">ReplyTo</span></span>|<span data-ttu-id="fff75-137">是</span><span class="sxs-lookup"><span data-stu-id="fff75-137">Yes</span></span>|  
|<span data-ttu-id="fff75-138">从地址</span><span class="sxs-lookup"><span data-stu-id="fff75-138">From/Address</span></span>|<span data-ttu-id="fff75-139">From</span><span class="sxs-lookup"><span data-stu-id="fff75-139">From</span></span>|<span data-ttu-id="fff75-140">是</span><span class="sxs-lookup"><span data-stu-id="fff75-140">Yes</span></span>|  
|<span data-ttu-id="fff75-141">序列/标识符</span><span class="sxs-lookup"><span data-stu-id="fff75-141">Sequence/Identifier</span></span>|<span data-ttu-id="fff75-142">SequenceId</span><span class="sxs-lookup"><span data-stu-id="fff75-142">SequenceId</span></span>|<span data-ttu-id="fff75-143">是</span><span class="sxs-lookup"><span data-stu-id="fff75-143">Yes</span></span>|  
|<span data-ttu-id="fff75-144">Sequence/MessageNumber</span><span class="sxs-lookup"><span data-stu-id="fff75-144">Sequence/MessageNumber</span></span>|<span data-ttu-id="fff75-145">SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="fff75-145">SequenceNumber</span></span>|<span data-ttu-id="fff75-146">是</span><span class="sxs-lookup"><span data-stu-id="fff75-146">Yes</span></span>|  
|<span data-ttu-id="fff75-147">Sequence/LastMessage</span><span class="sxs-lookup"><span data-stu-id="fff75-147">Sequence/LastMessage</span></span>|<span data-ttu-id="fff75-148">SequenceLastMessage</span><span class="sxs-lookup"><span data-stu-id="fff75-148">SequenceLastMessage</span></span>|<span data-ttu-id="fff75-149">是</span><span class="sxs-lookup"><span data-stu-id="fff75-149">Yes</span></span>|  
|<span data-ttu-id="fff75-150">\<soap:Header\></span><span class="sxs-lookup"><span data-stu-id="fff75-150">\<soap:Header\></span></span>|<span data-ttu-id="fff75-151">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="fff75-151">InboundHeaders</span></span>|<span data-ttu-id="fff75-152">否</span><span class="sxs-lookup"><span data-stu-id="fff75-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fff75-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="fff75-153">See Also</span></span>  
 <span data-ttu-id="fff75-154">[指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="fff75-154">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="fff75-155">[WCF 发送适配器](../core/wcf-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fff75-155">[WCF Send Adapter](../core/wcf-send-adapter.md) </span></span>  
 [<span data-ttu-id="fff75-156">WCF 适配器概述</span><span class="sxs-lookup"><span data-stu-id="fff75-156">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)