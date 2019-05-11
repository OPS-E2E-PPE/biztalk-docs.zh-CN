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
ms.openlocfilehash: cc48f4da993c4e19c0053342c56b00deff16ead1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266247"
---
# <a name="wcf-send-adapter"></a><span data-ttu-id="a14d4-102">WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="a14d4-102">WCF Send Adapter</span></span>
<span data-ttu-id="a14d4-103">WCF 发送适配器可以调用 WCF 服务通过无类型约定。</span><span class="sxs-lookup"><span data-stu-id="a14d4-103">The WCF send adapter enables you to call a WCF service through the typeless contract.</span></span>  
  
## <a name="specifying-the-wcf-message-body"></a><span data-ttu-id="a14d4-104">指定 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="a14d4-104">Specifying the WCF Message Body</span></span>  
 <span data-ttu-id="a14d4-105">需要从 BizTalk Server 发送的消息正文可以插入到 SOAP 消息中，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a14d4-105">The message body that needs to be sent from BizTalk Server can be inserted into the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="a14d4-106">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="a14d4-106">Extract the content of the BizTalk message body</span></span>  
  
- <span data-ttu-id="a14d4-107">通过使用模板中指定的内容</span><span class="sxs-lookup"><span data-stu-id="a14d4-107">Specify the content by using the template</span></span>  
  
  <span data-ttu-id="a14d4-108">可以在发送端口传输属性对话框中配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="a14d4-108">You can configure these options in the send port transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a><span data-ttu-id="a14d4-109">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="a14d4-109">Extract the Content of the BizTalk Message Body</span></span>  
 <span data-ttu-id="a14d4-110">选中此选项后，BizTalk 消息正文的内容插入到出站 WCF 消息正文的 SOAP Body 元素。</span><span class="sxs-lookup"><span data-stu-id="a14d4-110">When this option is selected, the content of the BizTalk message body is inserted into the SOAP Body element for the outbound WCF message body.</span></span>  
  
#### <a name="specify-the-content-by-using-the-template"></a><span data-ttu-id="a14d4-111">通过使用模板中指定的内容</span><span class="sxs-lookup"><span data-stu-id="a14d4-111">Specify the Content by Using the Template</span></span>  
 <span data-ttu-id="a14d4-112">选中此选项后，BizTalk 消息正文位于出站 WCF 消息正文的给定 XML 模板下的 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="a14d4-112">When this option is selected, the BizTalk message body is placed in the SOAP body element under the given XML template for the outbound WCF message body.</span></span>  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a><span data-ttu-id="a14d4-113">BizTalk 消息序列化为 SOAP 消息</span><span class="sxs-lookup"><span data-stu-id="a14d4-113">Serializing the BizTalk Message into a SOAP Message</span></span>  
 <span data-ttu-id="a14d4-114">发送适配器序列化为 BizTalk 消息的 SOAP 消息发送出去之前。消息序列化期间适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="a14d4-114">The send adapter serializes the BizTalk message into a SOAP message before sending it out. The following rules apply during serialization of the message:</span></span>  
  
-   <span data-ttu-id="a14d4-115">如果 BizTalk 消息是多部分消息，则使用仅正文部分。</span><span class="sxs-lookup"><span data-stu-id="a14d4-115">If the BizTalk message is a multipart message, then only the body part is used.</span></span>  
  
-   <span data-ttu-id="a14d4-116">如果 BizTalk 消息包含整个 SOAP 信封，然后将其包装到另一个 SOAP 信封。</span><span class="sxs-lookup"><span data-stu-id="a14d4-116">If the BizTalk message contains the entire SOAP envelope, then it is wrapped into another SOAP envelope.</span></span>  
  
-   <span data-ttu-id="a14d4-117">如果 BizTalk 消息包含任意 XML 数据，然后 BizTalk 消息放置到 SOAP 正文元素。</span><span class="sxs-lookup"><span data-stu-id="a14d4-117">If the BizTalk message contains arbitrary XML data, then the BizTalk message is placed into the SOAP Body element.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="a14d4-118">处理 Web Services 标头</span><span class="sxs-lookup"><span data-stu-id="a14d4-118">Handling Web Services Headers</span></span>  
 <span data-ttu-id="a14d4-119">在 BizTalk Server 不具有发送操作期间控制 Web services 标准标头。</span><span class="sxs-lookup"><span data-stu-id="a14d4-119">During send operations BizTalk Server does not have control over Web services standard headers.</span></span> <span data-ttu-id="a14d4-120">这些标头是设置并由 WCF 处理。</span><span class="sxs-lookup"><span data-stu-id="a14d4-120">Those headers are set and processed by the WCF.</span></span> <span data-ttu-id="a14d4-121">可以修改 BizTalk Server 应用程序的唯一标准标头是 **： 操作**标头。</span><span class="sxs-lookup"><span data-stu-id="a14d4-121">The only standard header that can be modified by the BizTalk Server application is the **a:Action** header.</span></span> <span data-ttu-id="a14d4-122">如果上下文属性**操作**指定适配器命名空间，则 WCF 发送适配器将使用的属性的值来设置**操作**对 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="a14d4-122">If the context property **Action** is specified on the adapter namespace, then the WCF send adapter will use the value of the property to set the **Action** on the SOAP message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a14d4-123">对于动态发送端口，如果**操作**中指定**OutboundHeaders**，为设置的上下文属性**WCF。操作**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a14d4-123">For dynamic send ports, if **Action** is specified in the **OutboundHeaders**, the context property you set for the **WCF.Action** will be ignored.</span></span>  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a><span data-ttu-id="a14d4-124">指定 BTS。IsDynamicSend 上下文属性</span><span class="sxs-lookup"><span data-stu-id="a14d4-124">Specifying the BTS.IsDynamicSend Context Property</span></span>  
 <span data-ttu-id="a14d4-125">WCF 发送适配器缓存发送端口的配置。</span><span class="sxs-lookup"><span data-stu-id="a14d4-125">The WCF send adapter caches the configuration for send ports.</span></span> <span data-ttu-id="a14d4-126">如果**BTS。IsDynamicSend**属性设置为 true，则 WCF 发送适配器将不使用缓存的配置，而改为所有配置信息从都读取消息的出站消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a14d4-126">If the **BTS.IsDynamicSend** property is set to true, the WCF send adapter does not use the cached configuration, but instead reads all configuration information from the message context properties of the outbound messages.</span></span> <span data-ttu-id="a14d4-127">静态发送端口，WCF 发送适配器将使用**BTS。SPLastUpdatedTime**，上次修改对象指的是静态发送端口设置的时间，以检测是否存在任何配置更改的静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="a14d4-127">On a static send port, the WCF send adapter uses **BTS.SPLastUpdatedTime**, which is the time that the static send port settings were last modified, to detect if there are any configuration changes on the static send port.</span></span> <span data-ttu-id="a14d4-128">以这种方式 WCF 发送适配器不需要从每个消息上下文中读取的所有设置。</span><span class="sxs-lookup"><span data-stu-id="a14d4-128">In this way the WCF send adapter does not need to read all of the settings from every message context.</span></span>  
  
 <span data-ttu-id="a14d4-129">如果你想要重写静态发送端口属性而不**WCF。操作**发送管道中的属性，则需要设置**BTS。IsDynamicSend**属性设置为 true，以便即使的上次更新时间戳，则 WCF 发送适配器将使用缓存的配置未更改。</span><span class="sxs-lookup"><span data-stu-id="a14d4-129">If you want to override the static send port properties other than the **WCF.Action** property in a send pipeline, you need to set the **BTS.IsDynamicSend** property to true so that the WCF send adapter will not use the cached configuration even though the last updated timestamp has not changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14d4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="a14d4-130">See Also</span></span>  
 <span data-ttu-id="a14d4-131">[指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="a14d4-131">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="a14d4-132">[WCF 接收适配器](../core/wcf-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a14d4-132">[WCF Receive Adapter](../core/wcf-receive-adapter.md) </span></span>  
 <span data-ttu-id="a14d4-133">[WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="a14d4-133">[What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="a14d4-134">如何使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="a14d4-134">How to Use Message Context Properties</span></span>](../core/how-to-use-message-context-properties.md)