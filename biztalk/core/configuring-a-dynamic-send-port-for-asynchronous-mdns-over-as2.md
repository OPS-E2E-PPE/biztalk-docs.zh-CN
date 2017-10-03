---
title: "配置动态发送端口异步 Mdn 的通过 AS2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 754917ed1a089e3182c8543e8a132a9eff73615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="9a863-102">配置用于 AS2 上的异步 MDN 的动态发送端口</span><span class="sxs-lookup"><span data-stu-id="9a863-102">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="9a863-103">要通过 HTTP/HTTPS 发送异步的 EDIINT/AS2 编码消息，请使用以下配置创建一个动态 HTTP 发送端口：</span><span class="sxs-lookup"><span data-stu-id="9a863-103">To send an asynchronous EDIINT/AS2-encoded MDN message over HTTP/HTTPS, create a dynamic HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="9a863-104">位置</span><span class="sxs-lookup"><span data-stu-id="9a863-104">Location</span></span>|<span data-ttu-id="9a863-105">属性</span><span class="sxs-lookup"><span data-stu-id="9a863-105">Property</span></span>|<span data-ttu-id="9a863-106">设置</span><span class="sxs-lookup"><span data-stu-id="9a863-106">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="9a863-107">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="9a863-107">**Send Port Properties: General**</span></span>|<span data-ttu-id="9a863-108">端口类型</span><span class="sxs-lookup"><span data-stu-id="9a863-108">Port Type</span></span>|<span data-ttu-id="9a863-109">动态单向</span><span class="sxs-lookup"><span data-stu-id="9a863-109">Dynamic One-Way</span></span>|  
|<span data-ttu-id="9a863-110">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="9a863-110">**Send Port Properties: General**</span></span>|<span data-ttu-id="9a863-111">发送管道</span><span class="sxs-lookup"><span data-stu-id="9a863-111">Send pipeline</span></span>|<span data-ttu-id="9a863-112">AS2Send</span><span class="sxs-lookup"><span data-stu-id="9a863-112">AS2Send</span></span>|  
|<span data-ttu-id="9a863-113">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="9a863-113">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="9a863-114">属性</span><span class="sxs-lookup"><span data-stu-id="9a863-114">Property</span></span>|<span data-ttu-id="9a863-115">EdiIntAS.IsAS2AsynchronousMdn</span><span class="sxs-lookup"><span data-stu-id="9a863-115">EdiIntAS.IsAS2AsynchronousMdn</span></span>|  
|<span data-ttu-id="9a863-116">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="9a863-116">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="9a863-117">运算符</span><span class="sxs-lookup"><span data-stu-id="9a863-117">Operator</span></span>|==|  
|<span data-ttu-id="9a863-118">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="9a863-118">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="9a863-119">值</span><span class="sxs-lookup"><span data-stu-id="9a863-119">Value</span></span>|<span data-ttu-id="9a863-120">True</span><span class="sxs-lookup"><span data-stu-id="9a863-120">True</span></span>|  
  
 <span data-ttu-id="9a863-121">应将异步 MDN 发送到中包含的地址**回执送达选项**已接收的 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="9a863-121">An asynchronous MDN should be sent to the address contained in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="9a863-122">动态发送端口将执行此操作，而静态发送端口将消息发送到**目标 URL**发送端口定义中。</span><span class="sxs-lookup"><span data-stu-id="9a863-122">A dynamic send port will do so, whereas a static send port will send the message to the **Destination URL** in the send port definition.</span></span> <span data-ttu-id="9a863-123">此规则的例外是如果**使用验证和 MDN 的协议设置，而不是消息标头**属性在中设置**验证**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="9a863-123">The exception to this is if the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="9a863-124">在这种情况下，发送端口将将 MDN 消息发送到的 URL 输入到**回执送达选项**协议属性。</span><span class="sxs-lookup"><span data-stu-id="9a863-124">In that case, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property.</span></span> <span data-ttu-id="9a863-125">但是，用于执行此操作的发送端口仍然必须是一个动态发送端口，而不是静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="9a863-125">However, the send port used to do so must still be a dynamic send port, not a static send port.</span></span>  
  
 <span data-ttu-id="9a863-126">可以将此发送端口配置为既返回 MDN 确认也返回 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="9a863-126">You can configure this send port to return both MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="9a863-127">在此情况下，如果成功地通过 HTTP/HTTPS 传输了 EDIINT/AS2 编码的消息，但是在处理 EDI 编码的负载时失败，原始消息的发送方既会收到表示成功处理了 AS2 的 MDN 确认，也会收到表示 EDI 处理失败的 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="9a863-127">In the instance, if an EDIINT/AS2-encoded message is transported over HTTP/HTTPS successfully, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="9a863-128">EDI 编码的负载将被挂起并产生一个错误。</span><span class="sxs-lookup"><span data-stu-id="9a863-128">The EDI-encoded payload would be suspended and an error posted.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="9a863-129">功能</span><span class="sxs-lookup"><span data-stu-id="9a863-129">Functionality</span></span>  
 <span data-ttu-id="9a863-130">若要发送一个 MDN，发送端口和管道必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9a863-130">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="9a863-131">通过对 `EdiIntAS.IsAS2AsynchronousMdn==True` 属性进行筛选，获取该 MDN。</span><span class="sxs-lookup"><span data-stu-id="9a863-131">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="9a863-132">生成一条 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="9a863-132">Build an AS2 message.</span></span> <span data-ttu-id="9a863-133">有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="9a863-133">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="9a863-134">将 MDN 路由到中的地址**回执送达选项**消息的标头中的行。</span><span class="sxs-lookup"><span data-stu-id="9a863-134">Route the MDN to the address in the **Receipt-Delivery-Option** line in the header of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a863-135">如果**使用验证和 MDN 的协议设置，而不是消息标头**属性在中设置**验证**的单向协议选项卡页**协议属性**对话框中，发送端口将 MDN 消息发送到的 URL 输入到**回执送达选项**协议属性，而不是中所述的地址**回执送达选项**已接收的 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="9a863-135">If the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property, not to the address mentioned in **Receipt-Delivery-Option** header of the received AS2 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a863-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a863-136">See Also</span></span>  
 [<span data-ttu-id="9a863-137">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="9a863-137">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)