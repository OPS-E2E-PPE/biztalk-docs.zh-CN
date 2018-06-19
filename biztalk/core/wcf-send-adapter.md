---
title: WCF 发送适配器 |Microsoft 文档
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
ms.openlocfilehash: 70604fbc15f5f15b0a7ff2325debdc28ac3a97c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288757"
---
# <a name="wcf-send-adapter"></a><span data-ttu-id="37514-102">WCF 发送适配器</span><span class="sxs-lookup"><span data-stu-id="37514-102">WCF Send Adapter</span></span>
<span data-ttu-id="37514-103">WCF 发送适配器允许您通过无类型的协定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="37514-103">The WCF send adapter enables you to call a WCF service through the typeless contract.</span></span>  
  
## <a name="specifying-the-wcf-message-body"></a><span data-ttu-id="37514-104">指定 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="37514-104">Specifying the WCF Message Body</span></span>  
 <span data-ttu-id="37514-105">可以通过使用下列选项之一将需要从 BizTalk Server 发送的消息正文插入到 SOAP 消息中：</span><span class="sxs-lookup"><span data-stu-id="37514-105">The message body that needs to be sent from BizTalk Server can be inserted into the SOAP message by using one of the following options:</span></span>  
  
-   <span data-ttu-id="37514-106">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="37514-106">Extract the content of the BizTalk message body</span></span>  
  
-   <span data-ttu-id="37514-107">通过使用模板中指定的内容</span><span class="sxs-lookup"><span data-stu-id="37514-107">Specify the content by using the template</span></span>  
  
 <span data-ttu-id="37514-108">您可以在“发送端口传输属性”对话框中配置这些选项。</span><span class="sxs-lookup"><span data-stu-id="37514-108">You can configure these options in the send port transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a><span data-ttu-id="37514-109">提取 BizTalk 消息正文的内容</span><span class="sxs-lookup"><span data-stu-id="37514-109">Extract the Content of the BizTalk Message Body</span></span>  
 <span data-ttu-id="37514-110">当选中此选项时，BizTalk 消息正文的内容会插入到出站 WCF 消息正文的 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="37514-110">When this option is selected, the content of the BizTalk message body is inserted into the SOAP Body element for the outbound WCF message body.</span></span>  
  
#### <a name="specify-the-content-by-using-the-template"></a><span data-ttu-id="37514-111">通过使用模板指定内容</span><span class="sxs-lookup"><span data-stu-id="37514-111">Specify the Content by Using the Template</span></span>  
 <span data-ttu-id="37514-112">当选中此选项时，会将 BizTalk 消息正文放置到出站 WCF 消息正文的给定的 XML 模板下的 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="37514-112">When this option is selected, the BizTalk message body is placed in the SOAP body element under the given XML template for the outbound WCF message body.</span></span>  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a><span data-ttu-id="37514-113">将 BizTalk 消息序列化到 SOAP 消息中</span><span class="sxs-lookup"><span data-stu-id="37514-113">Serializing the BizTalk Message into a SOAP Message</span></span>  
 <span data-ttu-id="37514-114">在发出 BizTalk 消息之前，发送适配器会将 BizTalk 消息序列化到 SOAP 消息中。在消息的序列化过程中，以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="37514-114">The send adapter serializes the BizTalk message into a SOAP message before sending it out. The following rules apply during serialization of the message:</span></span>  
  
-   <span data-ttu-id="37514-115">如果 BizTalk 消息是由多个部分组成的消息，则只会使用正文部分。</span><span class="sxs-lookup"><span data-stu-id="37514-115">If the BizTalk message is a multipart message, then only the body part is used.</span></span>  
  
-   <span data-ttu-id="37514-116">如果 BizTalk 消息包含整个 SOAP 信封，则会将其包装到另一个 SOAP 信封中。</span><span class="sxs-lookup"><span data-stu-id="37514-116">If the BizTalk message contains the entire SOAP envelope, then it is wrapped into another SOAP envelope.</span></span>  
  
-   <span data-ttu-id="37514-117">如果 BizTalk 消息包含任意 XML 数据，则会将 BizTalk 消息放置到 SOAP 正文元素中。</span><span class="sxs-lookup"><span data-stu-id="37514-117">If the BizTalk message contains arbitrary XML data, then the BizTalk message is placed into the SOAP Body element.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="37514-118">处理 Web Services 标头</span><span class="sxs-lookup"><span data-stu-id="37514-118">Handling Web Services Headers</span></span>  
 <span data-ttu-id="37514-119">在发送操作期间，BizTalk Server 无法控制 Web Services 标准标头。</span><span class="sxs-lookup"><span data-stu-id="37514-119">During send operations BizTalk Server does not have control over Web services standard headers.</span></span> <span data-ttu-id="37514-120">这些标头会通过 WCF 进行设置和处理。</span><span class="sxs-lookup"><span data-stu-id="37514-120">Those headers are set and processed by the WCF.</span></span> <span data-ttu-id="37514-121">可以修改 BizTalk 服务器应用程序的唯一的标准标头是 **： 操作**标头。</span><span class="sxs-lookup"><span data-stu-id="37514-121">The only standard header that can be modified by the BizTalk Server application is the **a:Action** header.</span></span> <span data-ttu-id="37514-122">如果上下文属性**操作**适配器命名空间，则 WCF 发送适配器将使用属性的值设置指定**操作**对 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="37514-122">If the context property **Action** is specified on the adapter namespace, then the WCF send adapter will use the value of the property to set the **Action** on the SOAP message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37514-123">要进行动态发送端口，如果**操作**中指定**OutboundHeaders**，为设置的上下文属性**WCF。操作**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="37514-123">For dynamic send ports, if **Action** is specified in the **OutboundHeaders**, the context property you set for the **WCF.Action** will be ignored.</span></span>  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a><span data-ttu-id="37514-124">指定 BTS.IsDynamicSend 上下文属性</span><span class="sxs-lookup"><span data-stu-id="37514-124">Specifying the BTS.IsDynamicSend Context Property</span></span>  
 <span data-ttu-id="37514-125">WCF 发送适配器缓存发送端口的配置。</span><span class="sxs-lookup"><span data-stu-id="37514-125">The WCF send adapter caches the configuration for send ports.</span></span> <span data-ttu-id="37514-126">如果**BTS。IsDynamicSend**属性设置为 true，WCF 发送适配器将不使用缓存的配置，但改为所有配置信息从都读取消息的出站消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="37514-126">If the **BTS.IsDynamicSend** property is set to true, the WCF send adapter does not use the cached configuration, but instead reads all configuration information from the message context properties of the outbound messages.</span></span> <span data-ttu-id="37514-127">WCF 静态发送端口上发送适配器使用**BTS。SPLastUpdatedTime**，上次修改静态发送端口设置的时间，以检测是否存在任何配置更改的静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="37514-127">On a static send port, the WCF send adapter uses **BTS.SPLastUpdatedTime**, which is the time that the static send port settings were last modified, to detect if there are any configuration changes on the static send port.</span></span> <span data-ttu-id="37514-128">这样，WCF 发送适配器就不需要从每个消息上下文中读取所有设置。</span><span class="sxs-lookup"><span data-stu-id="37514-128">In this way the WCF send adapter does not need to read all of the settings from every message context.</span></span>  
  
 <span data-ttu-id="37514-129">如果你想要重写静态发送端口属性以外**WCF。操作**发送管道中的属性，你需要设置**BTS。IsDynamicSend**属性设置为 true，以便 WCF 发送适配器将不会使用缓存的配置，即使上次更新时间戳仍是如此。</span><span class="sxs-lookup"><span data-stu-id="37514-129">If you want to override the static send port properties other than the **WCF.Action** property in a send pipeline, you need to set the **BTS.IsDynamicSend** property to true so that the WCF send adapter will not use the cached configuration even though the last updated timestamp has not changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37514-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37514-130">See Also</span></span>  
 <span data-ttu-id="37514-131">[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="37514-131">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="37514-132">[WCF 接收适配器](../core/wcf-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="37514-132">[WCF Receive Adapter](../core/wcf-receive-adapter.md) </span></span>  
 <span data-ttu-id="37514-133">[WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="37514-133">[What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="37514-134">如何使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="37514-134">How to Use Message Context Properties</span></span>](../core/how-to-use-message-context-properties.md)