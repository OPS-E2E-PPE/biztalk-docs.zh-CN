---
title: WCF 发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f36bca73ebd178d8d4052bfbcfa837c0d548ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020666"
---
# <a name="wcf-send-adapter"></a><span data-ttu-id="e54a0-102">WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="e54a0-102">WCF Send Adapter</span></span>
<span data-ttu-id="e54a0-103">WCF 发送适配器允许您通过无类型的协定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e54a0-103">The WCF send adapter enables you to call a WCF service through the typeless contract.</span></span>  
  
## <a name="specifying-the-wcf-message-body"></a><span data-ttu-id="e54a0-104">指定 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="e54a0-104">Specifying the WCF Message Body</span></span>  
 <span data-ttu-id="e54a0-105">可以通过使用下列选项之一将需要从 BizTalk Server 发送的消息正文插入到 SOAP 消息中：</span><span class="sxs-lookup"><span data-stu-id="e54a0-105">The message body that needs to be sent from BizTalk Server can be inserted into the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="e54a0-106">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="e54a0-106">Extract the content of the BizTalk message body</span></span>  
  
- <span data-ttu-id="e54a0-107">通过使用模板中指定的内容</span><span class="sxs-lookup"><span data-stu-id="e54a0-107">Specify the content by using the template</span></span>  
  
  <span data-ttu-id="e54a0-108">您可以在“发送端口传输属性”对话框中配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="e54a0-108">You can configure these options in the send port transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a><span data-ttu-id="e54a0-109">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="e54a0-109">Extract the Content of the BizTalk Message Body</span></span>  
 <span data-ttu-id="e54a0-110">当选中此选项时，BizTalk 消息正文的内容会插入到出站 WCF 消息正文的 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="e54a0-110">When this option is selected, the content of the BizTalk message body is inserted into the SOAP Body element for the outbound WCF message body.</span></span>  
  
#### <a name="specify-the-content-by-using-the-template"></a><span data-ttu-id="e54a0-111">通过使用模板指定内容</span><span class="sxs-lookup"><span data-stu-id="e54a0-111">Specify the Content by Using the Template</span></span>  
 <span data-ttu-id="e54a0-112">当选中此选项时，会将 BizTalk 消息正文放置到出站 WCF 消息正文的给定的 XML 模板下的 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="e54a0-112">When this option is selected, the BizTalk message body is placed in the SOAP body element under the given XML template for the outbound WCF message body.</span></span>  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a><span data-ttu-id="e54a0-113">将 BizTalk 消息序列化到 SOAP 消息中</span><span class="sxs-lookup"><span data-stu-id="e54a0-113">Serializing the BizTalk Message into a SOAP Message</span></span>  
 <span data-ttu-id="e54a0-114">在发出 BizTalk 消息之前，发送适配器会将 BizTalk 消息序列化到 SOAP 消息中。在消息的序列化过程中，以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="e54a0-114">The send adapter serializes the BizTalk message into a SOAP message before sending it out. The following rules apply during serialization of the message:</span></span>  
  
-   <span data-ttu-id="e54a0-115">如果 BizTalk 消息是由多个部分组成的消息，则只会使用正文部分。</span><span class="sxs-lookup"><span data-stu-id="e54a0-115">If the BizTalk message is a multipart message, then only the body part is used.</span></span>  
  
-   <span data-ttu-id="e54a0-116">如果 BizTalk 消息包含整个 SOAP 信封，则会将其包装到另一个 SOAP 信封中。</span><span class="sxs-lookup"><span data-stu-id="e54a0-116">If the BizTalk message contains the entire SOAP envelope, then it is wrapped into another SOAP envelope.</span></span>  
  
-   <span data-ttu-id="e54a0-117">如果 BizTalk 消息包含任意 XML 数据，则会将 BizTalk 消息放置到 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="e54a0-117">If the BizTalk message contains arbitrary XML data, then the BizTalk message is placed into the SOAP Body element.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="e54a0-118">处理 Web Services 标头</span><span class="sxs-lookup"><span data-stu-id="e54a0-118">Handling Web Services Headers</span></span>  
 <span data-ttu-id="e54a0-119">在发送操作期间，BizTalk Server 无法控制 Web Services 标准标头。</span><span class="sxs-lookup"><span data-stu-id="e54a0-119">During send operations BizTalk Server does not have control over Web services standard headers.</span></span> <span data-ttu-id="e54a0-120">这些标头会通过 WCF 进行设置和处理。</span><span class="sxs-lookup"><span data-stu-id="e54a0-120">Those headers are set and processed by the WCF.</span></span> <span data-ttu-id="e54a0-121">可以修改 BizTalk Server 应用程序的唯一标准标头是 **： 操作**标头。</span><span class="sxs-lookup"><span data-stu-id="e54a0-121">The only standard header that can be modified by the BizTalk Server application is the **a:Action** header.</span></span> <span data-ttu-id="e54a0-122">如果上下文属性**操作**指定适配器命名空间，则 WCF 发送适配器将使用的属性的值来设置**操作**对 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="e54a0-122">If the context property **Action** is specified on the adapter namespace, then the WCF send adapter will use the value of the property to set the **Action** on the SOAP message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e54a0-123">对于动态发送端口，如果**操作**中指定**OutboundHeaders**，为设置的上下文属性**WCF。操作**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="e54a0-123">For dynamic send ports, if **Action** is specified in the **OutboundHeaders**, the context property you set for the **WCF.Action** will be ignored.</span></span>  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a><span data-ttu-id="e54a0-124">指定 BTS.IsDynamicSend 上下文属性</span><span class="sxs-lookup"><span data-stu-id="e54a0-124">Specifying the BTS.IsDynamicSend Context Property</span></span>  
 <span data-ttu-id="e54a0-125">WCF 发送适配器缓存发送端口的配置。</span><span class="sxs-lookup"><span data-stu-id="e54a0-125">The WCF send adapter caches the configuration for send ports.</span></span> <span data-ttu-id="e54a0-126">如果**BTS。IsDynamicSend**属性设置为 true，则 WCF 发送适配器将不使用缓存的配置，而改为所有配置信息从都读取消息的出站消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e54a0-126">If the **BTS.IsDynamicSend** property is set to true, the WCF send adapter does not use the cached configuration, but instead reads all configuration information from the message context properties of the outbound messages.</span></span> <span data-ttu-id="e54a0-127">静态发送端口，WCF 发送适配器将使用**BTS。SPLastUpdatedTime**，上次修改对象指的是静态发送端口设置的时间，以检测是否存在任何配置更改的静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="e54a0-127">On a static send port, the WCF send adapter uses **BTS.SPLastUpdatedTime**, which is the time that the static send port settings were last modified, to detect if there are any configuration changes on the static send port.</span></span> <span data-ttu-id="e54a0-128">这样，WCF 发送适配器就不需要从每个消息上下文中读取所有设置。</span><span class="sxs-lookup"><span data-stu-id="e54a0-128">In this way the WCF send adapter does not need to read all of the settings from every message context.</span></span>  
  
 <span data-ttu-id="e54a0-129">如果你想要重写静态发送端口属性而不**WCF。操作**发送管道中的属性，则需要设置**BTS。IsDynamicSend**属性设置为 true，以便即使的上次更新时间戳，则 WCF 发送适配器将使用缓存的配置未更改。</span><span class="sxs-lookup"><span data-stu-id="e54a0-129">If you want to override the static send port properties other than the **WCF.Action** property in a send pipeline, you need to set the **BTS.IsDynamicSend** property to true so that the WCF send adapter will not use the cached configuration even though the last updated timestamp has not changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54a0-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e54a0-130">See Also</span></span>  
 <span data-ttu-id="e54a0-131">[指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e54a0-131">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="e54a0-132">[WCF 接收适配器](../core/wcf-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e54a0-132">[WCF Receive Adapter](../core/wcf-receive-adapter.md) </span></span>  
 <span data-ttu-id="e54a0-133">[WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e54a0-133">[What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="e54a0-134">如何使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="e54a0-134">How to Use Message Context Properties</span></span>](../core/how-to-use-message-context-properties.md)