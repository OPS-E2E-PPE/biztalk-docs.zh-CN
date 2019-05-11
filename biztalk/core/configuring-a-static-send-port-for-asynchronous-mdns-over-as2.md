---
title: 配置静态发送端口通过 AS2 发送异步 Mdn 的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24119db6566207455867b0a2e6b998870d445d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391410"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="186cc-102">配置通过 AS2 发送异步 Mdn 的静态发送端口</span><span class="sxs-lookup"><span data-stu-id="186cc-102">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="186cc-103">本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送异步 EDIINT/AS2 编码的 MDN 消息通过静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="186cc-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send an asynchronous EDIINT/AS2-encoded MDN message over a static send port.</span></span> <span data-ttu-id="186cc-104">此配置包括创建静态发送端口，然后如果需要，设置加密证书用于通过发送端口。</span><span class="sxs-lookup"><span data-stu-id="186cc-104">This configuration includes creating the static send port and if required, setting up an encryption certificate to be used by the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="186cc-105">可以配置动态发送端口以发送 MDN 消息，而不是静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="186cc-105">You can configure a dynamic send port to send MDN messages, instead of a static send port.</span></span> <span data-ttu-id="186cc-106">有关详细信息，请参阅[配置动态发送端口通过 AS2 发送异步 Mdn 的](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="186cc-106">For more information, see [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
 <span data-ttu-id="186cc-107">若要发送 MDN 消息，请使用以下配置创建一个单向 HTTP 发送端口：</span><span class="sxs-lookup"><span data-stu-id="186cc-107">To send an MDN message, create a one-way HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="186cc-108">Location</span><span class="sxs-lookup"><span data-stu-id="186cc-108">Location</span></span>|<span data-ttu-id="186cc-109">属性</span><span class="sxs-lookup"><span data-stu-id="186cc-109">Property</span></span>|<span data-ttu-id="186cc-110">设置</span><span class="sxs-lookup"><span data-stu-id="186cc-110">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="186cc-111">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="186cc-111">**Send Port Properties: General**</span></span>|<span data-ttu-id="186cc-112">端口类型</span><span class="sxs-lookup"><span data-stu-id="186cc-112">Port Type</span></span>|<span data-ttu-id="186cc-113">静态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="186cc-113">Static One-way Send Port</span></span>|  
|<span data-ttu-id="186cc-114">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="186cc-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="186cc-115">传输类型</span><span class="sxs-lookup"><span data-stu-id="186cc-115">Transport Type</span></span>|<span data-ttu-id="186cc-116">HTTP**注意：** 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="186cc-116">HTTP **Note:**  Only the HTTP adapter can be used for transporting EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="186cc-117">此传输不会使用非 HTTP 适配器的适配器。</span><span class="sxs-lookup"><span data-stu-id="186cc-117">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="186cc-118">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="186cc-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="186cc-119">发送处理程序</span><span class="sxs-lookup"><span data-stu-id="186cc-119">Send handler</span></span>|<span data-ttu-id="186cc-120">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="186cc-120">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="186cc-121">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="186cc-121">**Send Port Properties: General**</span></span>|<span data-ttu-id="186cc-122">发送管道</span><span class="sxs-lookup"><span data-stu-id="186cc-122">Send pipeline</span></span>|<span data-ttu-id="186cc-123">AS2Send</span><span class="sxs-lookup"><span data-stu-id="186cc-123">AS2Send</span></span>|  
|<span data-ttu-id="186cc-124">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="186cc-124">**HTTP Transport Properties**</span></span>|<span data-ttu-id="186cc-125">目标 URL</span><span class="sxs-lookup"><span data-stu-id="186cc-125">Destination URL</span></span>|<span data-ttu-id="186cc-126">\<目标 URL 字符串\></span><span class="sxs-lookup"><span data-stu-id="186cc-126">\<Destination URL string\></span></span>|  
|<span data-ttu-id="186cc-127">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="186cc-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="186cc-128">启用 chunked 编码</span><span class="sxs-lookup"><span data-stu-id="186cc-128">Enable chunked encoding</span></span>|<span data-ttu-id="186cc-129">已清除</span><span class="sxs-lookup"><span data-stu-id="186cc-129">Cleared</span></span>|  
|<span data-ttu-id="186cc-130">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="186cc-130">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="186cc-131">属性</span><span class="sxs-lookup"><span data-stu-id="186cc-131">Property</span></span>|<span data-ttu-id="186cc-132">EdiIntAS.IsAS2AsynchronousMdn**注意：** 你还应指定附加的筛选器表达式，以确保仅有的 MDN 消息要发送到此发送端口中指定的地址会选取此订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="186cc-132">EdiIntAS.IsAS2AsynchronousMdn **Note:**  You should also specify additional filter expressions to ensure that only MDN messages destined to the address specified in this send port are picked up by this subscription filter.</span></span>|  
|<span data-ttu-id="186cc-133">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="186cc-133">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="186cc-134">运算符</span><span class="sxs-lookup"><span data-stu-id="186cc-134">Operator</span></span>|==|  
|<span data-ttu-id="186cc-135">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="186cc-135">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="186cc-136">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="186cc-136">Value</span></span>|<span data-ttu-id="186cc-137">True</span><span class="sxs-lookup"><span data-stu-id="186cc-137">True</span></span>|  
|<span data-ttu-id="186cc-138">**发送端口属性：证书**</span><span class="sxs-lookup"><span data-stu-id="186cc-138">**Send Port Properties: Certificates**</span></span>|<span data-ttu-id="186cc-139">公用名称和指纹</span><span class="sxs-lookup"><span data-stu-id="186cc-139">Common Name  and thumbprint</span></span>|<span data-ttu-id="186cc-140">如果使用的加密证书进行出站 MDN 消息，请输入证书名称和指纹。</span><span class="sxs-lookup"><span data-stu-id="186cc-140">Enter the certificate name and thumbprint if using an encryption certificate for the outbound MDN message.</span></span>|  
  
 <span data-ttu-id="186cc-141">异步 MDN 应发送到中指定的地址**回执送达选项**所接收 AS2 消息的标头。</span><span class="sxs-lookup"><span data-stu-id="186cc-141">An asynchronous MDN should be sent to the address specified in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="186cc-142">动态发送端口将自动完成此操作，而静态发送端口将消息发送到**目标 URL**发送端口属性中。</span><span class="sxs-lookup"><span data-stu-id="186cc-142">A dynamic send port will do so automatically, whereas a static send port will send the message to the **Destination URL** in the send port properties.</span></span> <span data-ttu-id="186cc-143">在发送异步 MDN 使用静态发送端口时，请确保将发送到的 URL 正确。</span><span class="sxs-lookup"><span data-stu-id="186cc-143">When sending an asynchronous MDN with a static send port, ensure that the URL you are sending to is correct.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="186cc-144">功能</span><span class="sxs-lookup"><span data-stu-id="186cc-144">Functionality</span></span>  
 <span data-ttu-id="186cc-145">发送端口和管道必须执行以下操作来发送一个 MDN:</span><span class="sxs-lookup"><span data-stu-id="186cc-145">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="186cc-146">进行筛选来获取该 MDN`EdiIntAS.IsAS2AsynchronousMdn==True`属性。</span><span class="sxs-lookup"><span data-stu-id="186cc-146">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="186cc-147">生成 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="186cc-147">Build an AS2 message.</span></span> <span data-ttu-id="186cc-148">有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="186cc-148">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="186cc-149">将 MDN 路由到发送端口中定义的地址。</span><span class="sxs-lookup"><span data-stu-id="186cc-149">Route the MDN to the address defined in the send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186cc-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="186cc-150">See Also</span></span>  
 [<span data-ttu-id="186cc-151">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="186cc-151">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)