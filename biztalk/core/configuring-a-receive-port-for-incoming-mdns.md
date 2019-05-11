---
title: 配置传入 Mdn 的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b630555d5ec32ca9c1a3d48a8320f138a977284f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391391"
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a><span data-ttu-id="e2370-102">配置传入 Mdn 的接收端口</span><span class="sxs-lookup"><span data-stu-id="e2370-102">Configuring a Receive Port for Incoming MDNs</span></span>
<span data-ttu-id="e2370-103">若要接收 AS2 MDN，创建一个单向 HTTP 接收端口以接收消息并返回响应返回给参与方。</span><span class="sxs-lookup"><span data-stu-id="e2370-103">To receive an AS2 MDN, create a one-way HTTP receive port to receive the message and return a response back to the party.</span></span>  
  
 <span data-ttu-id="e2370-104">双向请求-响应接收端口用于接收的 AS2 消息不应该用于接收 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="e2370-104">A two-way request-response receive port that is used to receive AS2 messages should not be used to receive MDN messages.</span></span> <span data-ttu-id="e2370-105">使用请求-响应接收端口将 MDN 将阻止 200OK 消息来响应传入 MDN，从而导致不必要的 MDN 传输返回。</span><span class="sxs-lookup"><span data-stu-id="e2370-105">Using a request-response receive port for an MDN would prevent a 200OK message from being returned in response to the incoming MDN, thereby causing unnecessary retries of the MDN transmission.</span></span>  
  
 <span data-ttu-id="e2370-106">可以使用 AS2Receive 或 AS2EdiReceive 管道处理收到的 MDN。</span><span class="sxs-lookup"><span data-stu-id="e2370-106">You can use either the AS2Receive or the AS2EdiReceive pipeline to process a received MDN.</span></span> <span data-ttu-id="e2370-107">但是，如果使用 AS2EdiReceive，则不能将 MDN 路由到 MessageBox 中通过设置**到 MessageBox 中处理入站的 MDN 以进行路由/传递**上的属性**确认**页单向协议选项卡。尝试进行此操作将导致一个 EDI 错误，因为 MSN 将传递至 EDI 解码器，将无法对 MDN 进行处理。</span><span class="sxs-lookup"><span data-stu-id="e2370-107">However, if you use AS2EdiReceive, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property on the **Acknowledgements** page of the one-way agreement tab. Trying to do so will result in an EDI error because the MSN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="e2370-108">如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此它不会传递到 EDI 解码器。</span><span class="sxs-lookup"><span data-stu-id="e2370-108">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
 <span data-ttu-id="e2370-109">使用以下配置创建接收端口：</span><span class="sxs-lookup"><span data-stu-id="e2370-109">Create the receive port with the following configuration:</span></span>  
  
|<span data-ttu-id="e2370-110">Location</span><span class="sxs-lookup"><span data-stu-id="e2370-110">Location</span></span>|<span data-ttu-id="e2370-111">属性</span><span class="sxs-lookup"><span data-stu-id="e2370-111">Property</span></span>|<span data-ttu-id="e2370-112">设置</span><span class="sxs-lookup"><span data-stu-id="e2370-112">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="e2370-113">**接收端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="e2370-113">**Receive Port Properties: General**</span></span>|<span data-ttu-id="e2370-114">端口类型</span><span class="sxs-lookup"><span data-stu-id="e2370-114">Port type</span></span>|<span data-ttu-id="e2370-115">单向</span><span class="sxs-lookup"><span data-stu-id="e2370-115">One-Way</span></span>|  
|<span data-ttu-id="e2370-116">**接收位置属性：常规**</span><span class="sxs-lookup"><span data-stu-id="e2370-116">**Receive Location Properties: General**</span></span>|<span data-ttu-id="e2370-117">传输类型</span><span class="sxs-lookup"><span data-stu-id="e2370-117">Transport Type</span></span>|<span data-ttu-id="e2370-118">HTTP</span><span class="sxs-lookup"><span data-stu-id="e2370-118">HTTP</span></span><br /><br /> <span data-ttu-id="e2370-119">**请注意**只有 HTTP 适配器可用于传输 Mdn，是 EDIINT/AS2 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="e2370-119">**Note** Only the HTTP adapter can be used for transporting MDNs, which are EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="e2370-120">此传输不会使用非 HTTP 适配器的适配器。</span><span class="sxs-lookup"><span data-stu-id="e2370-120">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="e2370-121">**接收位置属性：常规**</span><span class="sxs-lookup"><span data-stu-id="e2370-121">**Receive Location Properties: General**</span></span>|<span data-ttu-id="e2370-122">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="e2370-122">Receive handler</span></span>|<span data-ttu-id="e2370-123">BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="e2370-123">BizTalkServerIsolatedHost</span></span>|  
|<span data-ttu-id="e2370-124">**接收位置属性：常规**</span><span class="sxs-lookup"><span data-stu-id="e2370-124">**Receive Location Properties: General**</span></span>|<span data-ttu-id="e2370-125">接收管道</span><span class="sxs-lookup"><span data-stu-id="e2370-125">Receive pipeline</span></span>|<span data-ttu-id="e2370-126">AS2Receive 或 AS2EdiReceive</span><span class="sxs-lookup"><span data-stu-id="e2370-126">AS2Receive or AS2EdiReceive</span></span>|  
|<span data-ttu-id="e2370-127">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="e2370-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="e2370-128">虚拟目录和 ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="e2370-128">Virtual directory plus ISAPI extension</span></span>|<span data-ttu-id="e2370-129">/\<虚拟目录名称\>/BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="e2370-129">/\<name of virtual directory\>/BTSHTTPReceive.dll</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2370-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2370-130">See Also</span></span>  
 [<span data-ttu-id="e2370-131">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="e2370-131">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)