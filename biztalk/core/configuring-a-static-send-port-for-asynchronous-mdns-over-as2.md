---
title: "配置静态发送端口异步 Mdn 的通过 AS2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e023dc6f2165e9427fa57e109715dda6cdb258f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="feabe-102">配置用于通过 AS2 发送异步 MDN 的静态发送端口</span><span class="sxs-lookup"><span data-stu-id="feabe-102">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="feabe-103">本主题介绍如何配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以通过静态发送端口发送异步 EDIINT/AS2 编码的 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="feabe-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send an asynchronous EDIINT/AS2-encoded MDN message over a static send port.</span></span> <span data-ttu-id="feabe-104">此配置包括创建静态发送端口，以及设置发送端口使用的加密证书（如需要）。</span><span class="sxs-lookup"><span data-stu-id="feabe-104">This configuration includes creating the static send port and if required, setting up an encryption certificate to be used by the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="feabe-105">可以配置动态发送端口而不是静态发送端口来发送 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="feabe-105">You can configure a dynamic send port to send MDN messages, instead of a static send port.</span></span> <span data-ttu-id="feabe-106">有关详细信息，请参阅[通过 AS2 异步 Mdn 的配置动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="feabe-106">For more information, see [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
 <span data-ttu-id="feabe-107">若要发送 MDN 消息，请使用下列配置创建一个单向 HTTP 发送端口：</span><span class="sxs-lookup"><span data-stu-id="feabe-107">To send an MDN message, create a one-way HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="feabe-108">位置</span><span class="sxs-lookup"><span data-stu-id="feabe-108">Location</span></span>|<span data-ttu-id="feabe-109">属性</span><span class="sxs-lookup"><span data-stu-id="feabe-109">Property</span></span>|<span data-ttu-id="feabe-110">设置</span><span class="sxs-lookup"><span data-stu-id="feabe-110">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="feabe-111">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="feabe-111">**Send Port Properties: General**</span></span>|<span data-ttu-id="feabe-112">端口类型</span><span class="sxs-lookup"><span data-stu-id="feabe-112">Port Type</span></span>|<span data-ttu-id="feabe-113">静态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="feabe-113">Static One-way Send Port</span></span>|  
|<span data-ttu-id="feabe-114">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="feabe-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="feabe-115">传输类型</span><span class="sxs-lookup"><span data-stu-id="feabe-115">Transport Type</span></span>|<span data-ttu-id="feabe-116">HTTP**注意：**仅 HTTP 适配器可以用于编码 EDIINT/AS2 消息传输。</span><span class="sxs-lookup"><span data-stu-id="feabe-116">HTTP **Note:**  Only the HTTP adapter can be used for transporting EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="feabe-117">此传输不能用于除 HTTP 适配器之外的其他适配器。</span><span class="sxs-lookup"><span data-stu-id="feabe-117">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="feabe-118">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="feabe-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="feabe-119">发送处理程序</span><span class="sxs-lookup"><span data-stu-id="feabe-119">Send handler</span></span>|<span data-ttu-id="feabe-120">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="feabe-120">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="feabe-121">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="feabe-121">**Send Port Properties: General**</span></span>|<span data-ttu-id="feabe-122">发送管道</span><span class="sxs-lookup"><span data-stu-id="feabe-122">Send pipeline</span></span>|<span data-ttu-id="feabe-123">AS2Send</span><span class="sxs-lookup"><span data-stu-id="feabe-123">AS2Send</span></span>|  
|<span data-ttu-id="feabe-124">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="feabe-124">**HTTP Transport Properties**</span></span>|<span data-ttu-id="feabe-125">目标 URL</span><span class="sxs-lookup"><span data-stu-id="feabe-125">Destination URL</span></span>|<span data-ttu-id="feabe-126">\<目标 URL 字符串\></span><span class="sxs-lookup"><span data-stu-id="feabe-126">\<Destination URL string\></span></span>|  
|<span data-ttu-id="feabe-127">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="feabe-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="feabe-128">启用 Chunked 编码</span><span class="sxs-lookup"><span data-stu-id="feabe-128">Enable chunked encoding</span></span>|<span data-ttu-id="feabe-129">已清除</span><span class="sxs-lookup"><span data-stu-id="feabe-129">Cleared</span></span>|  
|<span data-ttu-id="feabe-130">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="feabe-130">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="feabe-131">属性</span><span class="sxs-lookup"><span data-stu-id="feabe-131">Property</span></span>|<span data-ttu-id="feabe-132">EdiIntAS.IsAS2AsynchronousMdn**注意：**还应指定附加的筛选器表达式，以确保仅 MDN 消息要发送到在此指定的地址发送端口将拾取此订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="feabe-132">EdiIntAS.IsAS2AsynchronousMdn **Note:**  You should also specify additional filter expressions to ensure that only MDN messages destined to the address specified in this send port are picked up by this subscription filter.</span></span>|  
|<span data-ttu-id="feabe-133">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="feabe-133">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="feabe-134">运算符</span><span class="sxs-lookup"><span data-stu-id="feabe-134">Operator</span></span>|==|  
|<span data-ttu-id="feabe-135">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="feabe-135">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="feabe-136">值</span><span class="sxs-lookup"><span data-stu-id="feabe-136">Value</span></span>|<span data-ttu-id="feabe-137">True</span><span class="sxs-lookup"><span data-stu-id="feabe-137">True</span></span>|  
|<span data-ttu-id="feabe-138">**发送端口属性： 证书**</span><span class="sxs-lookup"><span data-stu-id="feabe-138">**Send Port Properties: Certificates**</span></span>|<span data-ttu-id="feabe-139">公用名和指纹</span><span class="sxs-lookup"><span data-stu-id="feabe-139">Common Name  and thumbprint</span></span>|<span data-ttu-id="feabe-140">如果对出站 MDN 消息使用加密证书，请输入证书名称和指纹。</span><span class="sxs-lookup"><span data-stu-id="feabe-140">Enter the certificate name and thumbprint if using an encryption certificate for the outbound MDN message.</span></span>|  
  
 <span data-ttu-id="feabe-141">应将异步 MDN 发送到中指定的地址**回执送达选项**已接收的 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="feabe-141">An asynchronous MDN should be sent to the address specified in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="feabe-142">动态发送端口将自动这样做，而静态发送端口将消息发送到**目标 URL**发送端口属性中。</span><span class="sxs-lookup"><span data-stu-id="feabe-142">A dynamic send port will do so automatically, whereas a static send port will send the message to the **Destination URL** in the send port properties.</span></span> <span data-ttu-id="feabe-143">使用静态发送端口发送异步 MDN 时，请确保您发送到的 URL 是正确的。</span><span class="sxs-lookup"><span data-stu-id="feabe-143">When sending an asynchronous MDN with a static send port, ensure that the URL you are sending to is correct.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="feabe-144">功能</span><span class="sxs-lookup"><span data-stu-id="feabe-144">Functionality</span></span>  
 <span data-ttu-id="feabe-145">若要发送一个 MDN，发送端口和管道必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="feabe-145">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="feabe-146">通过对 `EdiIntAS.IsAS2AsynchronousMdn==True` 属性进行筛选，获取该 MDN。</span><span class="sxs-lookup"><span data-stu-id="feabe-146">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="feabe-147">生成一条 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="feabe-147">Build an AS2 message.</span></span> <span data-ttu-id="feabe-148">有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="feabe-148">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="feabe-149">将 MDN 路由到在发送端口中定义的地址。</span><span class="sxs-lookup"><span data-stu-id="feabe-149">Route the MDN to the address defined in the send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feabe-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feabe-150">See Also</span></span>  
 [<span data-ttu-id="feabe-151">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="feabe-151">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)