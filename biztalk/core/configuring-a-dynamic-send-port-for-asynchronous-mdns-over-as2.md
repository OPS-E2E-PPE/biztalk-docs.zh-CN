---
title: 配置动态发送端口通过 AS2 发送异步 Mdn 的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6d8c962e1a417e1b97fd6fe8224718785133fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391423"
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="a5e50-102">配置通过 AS2 发送异步 Mdn 的动态发送端口</span><span class="sxs-lookup"><span data-stu-id="a5e50-102">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="a5e50-103">若要通过 HTTP/HTTPS 发送异步 EDIINT/AS2 编码的 MDN 消息，请使用以下配置创建一个动态 HTTP 发送端口：</span><span class="sxs-lookup"><span data-stu-id="a5e50-103">To send an asynchronous EDIINT/AS2-encoded MDN message over HTTP/HTTPS, create a dynamic HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="a5e50-104">Location</span><span class="sxs-lookup"><span data-stu-id="a5e50-104">Location</span></span>|<span data-ttu-id="a5e50-105">属性</span><span class="sxs-lookup"><span data-stu-id="a5e50-105">Property</span></span>|<span data-ttu-id="a5e50-106">设置</span><span class="sxs-lookup"><span data-stu-id="a5e50-106">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="a5e50-107">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="a5e50-107">**Send Port Properties: General**</span></span>|<span data-ttu-id="a5e50-108">端口类型</span><span class="sxs-lookup"><span data-stu-id="a5e50-108">Port Type</span></span>|<span data-ttu-id="a5e50-109">动态单向</span><span class="sxs-lookup"><span data-stu-id="a5e50-109">Dynamic One-Way</span></span>|  
|<span data-ttu-id="a5e50-110">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="a5e50-110">**Send Port Properties: General**</span></span>|<span data-ttu-id="a5e50-111">发送管道</span><span class="sxs-lookup"><span data-stu-id="a5e50-111">Send pipeline</span></span>|<span data-ttu-id="a5e50-112">AS2Send</span><span class="sxs-lookup"><span data-stu-id="a5e50-112">AS2Send</span></span>|  
|<span data-ttu-id="a5e50-113">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="a5e50-113">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="a5e50-114">属性</span><span class="sxs-lookup"><span data-stu-id="a5e50-114">Property</span></span>|<span data-ttu-id="a5e50-115">EdiIntAS.IsAS2AsynchronousMdn</span><span class="sxs-lookup"><span data-stu-id="a5e50-115">EdiIntAS.IsAS2AsynchronousMdn</span></span>|  
|<span data-ttu-id="a5e50-116">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="a5e50-116">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="a5e50-117">运算符</span><span class="sxs-lookup"><span data-stu-id="a5e50-117">Operator</span></span>|==|  
|<span data-ttu-id="a5e50-118">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="a5e50-118">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="a5e50-119">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="a5e50-119">Value</span></span>|<span data-ttu-id="a5e50-120">True</span><span class="sxs-lookup"><span data-stu-id="a5e50-120">True</span></span>|  
  
 <span data-ttu-id="a5e50-121">异步 MDN 应发送到中包含的地址**回执送达选项**所接收 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="a5e50-121">An asynchronous MDN should be sent to the address contained in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="a5e50-122">动态发送端口将完成此操作，而静态发送端口将消息发送到**目标 URL**发送端口定义中。</span><span class="sxs-lookup"><span data-stu-id="a5e50-122">A dynamic send port will do so, whereas a static send port will send the message to the **Destination URL** in the send port definition.</span></span> <span data-ttu-id="a5e50-123">此规则的例外是如果**使用的验证和 MDN 的协议设置而非消息标头**属性中设置**验证**页的单向协议选项卡的**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a5e50-123">The exception to this is if the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="a5e50-124">在这种情况下，发送端口将发送 MDN 消息，到输入的 url**回执送达选项**协议属性。</span><span class="sxs-lookup"><span data-stu-id="a5e50-124">In that case, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property.</span></span> <span data-ttu-id="a5e50-125">但是，用来执行此操作的发送端口必须仍是一个动态发送端口，不是静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="a5e50-125">However, the send port used to do so must still be a dynamic send port, not a static send port.</span></span>  
  
 <span data-ttu-id="a5e50-126">可以配置此发送端口返回 Mdn 和 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="a5e50-126">You can configure this send port to return both MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="a5e50-127">在实例中，如果成功，通过 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息，是但处理 EDI 编码的负载将失败，原始消息的发件人将收到同时表示成功处理了 AS2 和 EDI 的 MDN表示在 EDI 处理中的失败的确认。</span><span class="sxs-lookup"><span data-stu-id="a5e50-127">In the instance, if an EDIINT/AS2-encoded message is transported over HTTP/HTTPS successfully, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="a5e50-128">EDI 编码的负载将被挂起并产生一个错误。</span><span class="sxs-lookup"><span data-stu-id="a5e50-128">The EDI-encoded payload would be suspended and an error posted.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="a5e50-129">功能</span><span class="sxs-lookup"><span data-stu-id="a5e50-129">Functionality</span></span>  
 <span data-ttu-id="a5e50-130">发送端口和管道必须执行以下操作来发送一个 MDN:</span><span class="sxs-lookup"><span data-stu-id="a5e50-130">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="a5e50-131">进行筛选来获取该 MDN`EdiIntAS.IsAS2AsynchronousMdn==True`属性。</span><span class="sxs-lookup"><span data-stu-id="a5e50-131">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="a5e50-132">生成 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="a5e50-132">Build an AS2 message.</span></span> <span data-ttu-id="a5e50-133">有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="a5e50-133">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="a5e50-134">将 MDN 路由到中的地址**回执送达选项**消息的标头中的行。</span><span class="sxs-lookup"><span data-stu-id="a5e50-134">Route the MDN to the address in the **Receipt-Delivery-Option** line in the header of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5e50-135">如果**使用的验证和 MDN 的协议设置而非消息标头**属性中设置**验证**页的单向协议选项卡的**协议属性**对话框中，发送端口将 MDN 消息发送到输入的 url**回执送达选项**协议属性，而不是所述的地址**回执送达选项**接收 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="a5e50-135">If the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property, not to the address mentioned in **Receipt-Delivery-Option** header of the received AS2 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e50-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5e50-136">See Also</span></span>  
 [<span data-ttu-id="a5e50-137">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="a5e50-137">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)