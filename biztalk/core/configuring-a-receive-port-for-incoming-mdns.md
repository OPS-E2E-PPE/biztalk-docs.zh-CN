---
title: "配置传入 Mdn 的接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8585ae946e15d2677e225d42f6c123d5dd5e8e49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a><span data-ttu-id="30ebf-102">配置传入 MDN 的接收端口</span><span class="sxs-lookup"><span data-stu-id="30ebf-102">Configuring a Receive Port for Incoming MDNs</span></span>
<span data-ttu-id="30ebf-103">若要接收 AS2 MDN，请创建一个单向 HTTP 接收端口以接收消息并向参与方返回响应。</span><span class="sxs-lookup"><span data-stu-id="30ebf-103">To receive an AS2 MDN, create a one-way HTTP receive port to receive the message and return a response back to the party.</span></span>  
  
 <span data-ttu-id="30ebf-104">不应将用来接收 AS2 消息的双向请求-响应接收端口用于接收 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="30ebf-104">A two-way request-response receive port that is used to receive AS2 messages should not be used to receive MDN messages.</span></span> <span data-ttu-id="30ebf-105">为 MDN 使用一个请求-响应接收端口可防止为了响应传入的 MDN 而返回一条 200OK 消息以及由此导致的不必要的 MDN 传输重试。</span><span class="sxs-lookup"><span data-stu-id="30ebf-105">Using a request-response receive port for an MDN would prevent a 200OK message from being returned in response to the incoming MDN, thereby causing unnecessary retries of the MDN transmission.</span></span>  
  
 <span data-ttu-id="30ebf-106">既可以使用 AS2Receive 管道也可以使用 AS2EdiReceive 管道处理收到的 MDN。</span><span class="sxs-lookup"><span data-stu-id="30ebf-106">You can use either the AS2Receive or the AS2EdiReceive pipeline to process a received MDN.</span></span> <span data-ttu-id="30ebf-107">但是，如果你使用 AS2EdiReceive，你不能将发送 MDN 到 MessageBox 通过设置**路由/传递到 MessageBox 处理入站的 MDN**属性**确认**页单向协议的选项卡。如果尝试进行此操作，将会导致一个 EDI 错误，因为 MSN 将传递至 EDI 解码器，而 EDI 解码器无法对 MDN 进行处理。</span><span class="sxs-lookup"><span data-stu-id="30ebf-107">However, if you use AS2EdiReceive, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property on the **Acknowledgements** page of the one-way agreement tab. Trying to do so will result in an EDI error because the MSN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="30ebf-108">如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此不会将其传递到 EDI 解码器。</span><span class="sxs-lookup"><span data-stu-id="30ebf-108">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
 <span data-ttu-id="30ebf-109">使用下列配置创建接收端口：</span><span class="sxs-lookup"><span data-stu-id="30ebf-109">Create the receive port with the following configuration:</span></span>  
  
|<span data-ttu-id="30ebf-110">位置</span><span class="sxs-lookup"><span data-stu-id="30ebf-110">Location</span></span>|<span data-ttu-id="30ebf-111">属性</span><span class="sxs-lookup"><span data-stu-id="30ebf-111">Property</span></span>|<span data-ttu-id="30ebf-112">设置</span><span class="sxs-lookup"><span data-stu-id="30ebf-112">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="30ebf-113">**接收端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="30ebf-113">**Receive Port Properties: General**</span></span>|<span data-ttu-id="30ebf-114">端口类型</span><span class="sxs-lookup"><span data-stu-id="30ebf-114">Port type</span></span>|<span data-ttu-id="30ebf-115">单向</span><span class="sxs-lookup"><span data-stu-id="30ebf-115">One-Way</span></span>|  
|<span data-ttu-id="30ebf-116">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="30ebf-116">**Receive Location Properties: General**</span></span>|<span data-ttu-id="30ebf-117">传输类型</span><span class="sxs-lookup"><span data-stu-id="30ebf-117">Transport Type</span></span>|<span data-ttu-id="30ebf-118">HTTP</span><span class="sxs-lookup"><span data-stu-id="30ebf-118">HTTP</span></span><br /><br /> <span data-ttu-id="30ebf-119">**请注意**仅 HTTP 适配器可以用于传输 Mdn，编码 EDIINT/AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="30ebf-119">**Note** Only the HTTP adapter can be used for transporting MDNs, which are EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="30ebf-120">此传输不能用于除 HTTP 适配器之外的其他适配器。</span><span class="sxs-lookup"><span data-stu-id="30ebf-120">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="30ebf-121">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="30ebf-121">**Receive Location Properties: General**</span></span>|<span data-ttu-id="30ebf-122">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="30ebf-122">Receive handler</span></span>|<span data-ttu-id="30ebf-123">BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="30ebf-123">BizTalkServerIsolatedHost</span></span>|  
|<span data-ttu-id="30ebf-124">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="30ebf-124">**Receive Location Properties: General**</span></span>|<span data-ttu-id="30ebf-125">接收管道</span><span class="sxs-lookup"><span data-stu-id="30ebf-125">Receive pipeline</span></span>|<span data-ttu-id="30ebf-126">AS2Receive 或 AS2EdiReceive</span><span class="sxs-lookup"><span data-stu-id="30ebf-126">AS2Receive or AS2EdiReceive</span></span>|  
|<span data-ttu-id="30ebf-127">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="30ebf-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="30ebf-128">虚拟目录和 ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="30ebf-128">Virtual directory plus ISAPI extension</span></span>|<span data-ttu-id="30ebf-129">/\<虚拟目录名称\>/BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="30ebf-129">/\<name of virtual directory\>/BTSHTTPReceive.dll</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30ebf-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30ebf-130">See Also</span></span>  
 [<span data-ttu-id="30ebf-131">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="30ebf-131">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)