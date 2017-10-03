---
title: "动态 MLLP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7d1d7046135de1dc1837d1fb8961ef440b5009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-mllp-adapter"></a><span data-ttu-id="5ea21-102">动态 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="5ea21-102">Dynamic MLLP Adapter</span></span>
<span data-ttu-id="5ea21-103">从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]，可以在运行时使用单向或双向 （请求-响应） 发送端口配置 MLLP 适配器属性。</span><span class="sxs-lookup"><span data-stu-id="5ea21-103">Starting with [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], the MLLP adapter properties can be configured at Runtime using a One-Way or Two-Way (Request-Response) send port.</span></span>  
  
## <a name="dynamic-properties"></a><span data-ttu-id="5ea21-104">动态属性</span><span class="sxs-lookup"><span data-stu-id="5ea21-104">Dynamic Properties</span></span>  
 <span data-ttu-id="5ea21-105">以下属性位于**GlobalPropertySchemas**命名空间：</span><span class="sxs-lookup"><span data-stu-id="5ea21-105">The following properties are in the **GlobalPropertySchemas** namespace:</span></span>  
  
|<span data-ttu-id="5ea21-106">属性</span><span class="sxs-lookup"><span data-stu-id="5ea21-106">Property</span></span>|<span data-ttu-id="5ea21-107">Description</span><span class="sxs-lookup"><span data-stu-id="5ea21-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5ea21-108">消息 (MLLP.acceptableACKCodes) ="所有确认代码";</span><span class="sxs-lookup"><span data-stu-id="5ea21-108">Message(MLLP.acceptableACKCodes)=”All ACK Codes”;</span></span>|<span data-ttu-id="5ea21-109">值包括：</span><span class="sxs-lookup"><span data-stu-id="5ea21-109">Values include:</span></span><br /><br /> <span data-ttu-id="5ea21-110">-所有 ACK 代码</span><span class="sxs-lookup"><span data-stu-id="5ea21-110">-   All ACK Codes</span></span><br /><span data-ttu-id="5ea21-111">-AA 和 CA</span><span class="sxs-lookup"><span data-stu-id="5ea21-111">-   AA and CA</span></span><br /><span data-ttu-id="5ea21-112">-AA、 CA、 遍历和 CE</span><span class="sxs-lookup"><span data-stu-id="5ea21-112">-   AA, CA, AE and CE</span></span><br /><span data-ttu-id="5ea21-113">-AA、 CA、 AR 和 CR</span><span class="sxs-lookup"><span data-stu-id="5ea21-113">-   AA, CA, AR and CR</span></span><br /><br /> <span data-ttu-id="5ea21-114">它类似于**可接受的 ACK 代码**静态 MLLP 发送端口中的属性。</span><span class="sxs-lookup"><span data-stu-id="5ea21-114">This is similar to the **Acceptable ACK Codes** property in a Static MLLP Send Port.</span></span>|  
|<span data-ttu-id="5ea21-115">消息 (MLLP。CarriageReturn) ="0 d";</span><span class="sxs-lookup"><span data-stu-id="5ea21-115">Message(MLLP.CarriageReturn)=”0d”;</span></span>|<span data-ttu-id="5ea21-116">ASCII 回车符</span><span class="sxs-lookup"><span data-stu-id="5ea21-116">ASCII Carriage Return Character</span></span>|  
|<span data-ttu-id="5ea21-117">消息 (MLLP.endBlockDelimiter) ="1 c";</span><span class="sxs-lookup"><span data-stu-id="5ea21-117">Message(MLLP.endBlockDelimiter)=”1c”;</span></span>|<span data-ttu-id="5ea21-118">ASCII 结束块字符</span><span class="sxs-lookup"><span data-stu-id="5ea21-118">ASCII End Block Character</span></span>|  
|<span data-ttu-id="5ea21-119">消息 (MLLP.startBlockDelimiter) ="0b";</span><span class="sxs-lookup"><span data-stu-id="5ea21-119">Message(MLLP.startBlockDelimiter)=”0b”;</span></span>|<span data-ttu-id="5ea21-120">ASCII 起始块字符</span><span class="sxs-lookup"><span data-stu-id="5ea21-120">ASCII Start Block Character</span></span>|  
|<span data-ttu-id="5ea21-121">消息 (MLLP.timeout) ="60000";</span><span class="sxs-lookup"><span data-stu-id="5ea21-121">Message(MLLP.timeout)=”60000”;</span></span>|<span data-ttu-id="5ea21-122">时间段段后 BTAHL7 服务器将会超时的非活动发送套接字 （0 表示无超时）</span><span class="sxs-lookup"><span data-stu-id="5ea21-122">Period after which inactive sending socket on BTAHL7 server will timeout(0 is no timeout)</span></span>|  
|<span data-ttu-id="5ea21-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) ="127.0.0.1:11000";</span><span class="sxs-lookup"><span data-stu-id="5ea21-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;</span></span>|<span data-ttu-id="5ea21-124">地址和端口用于路由消息</span><span class="sxs-lookup"><span data-stu-id="5ea21-124">Address and Port for routing the message</span></span>|  
|<span data-ttu-id="5ea21-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) ="MLLP";</span><span class="sxs-lookup"><span data-stu-id="5ea21-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;</span></span>|<span data-ttu-id="5ea21-126">类型的适配器 (MLLP)</span><span class="sxs-lookup"><span data-stu-id="5ea21-126">Type of Adapter (MLLP)</span></span>|  
  
## <a name="additional"></a><span data-ttu-id="5ea21-127">补充说明</span><span class="sxs-lookup"><span data-stu-id="5ea21-127">Additional</span></span>  
  
-   <span data-ttu-id="5ea21-128">业务流程中创建 HL7，多部分消息时要按照顺序在此创建的消息部分：</span><span class="sxs-lookup"><span data-stu-id="5ea21-128">When creating a multipart message in an orchestration for HL7, create the message parts in this following order:</span></span>  
  
    1.  <span data-ttu-id="5ea21-129">MSH 段</span><span class="sxs-lookup"><span data-stu-id="5ea21-129">MSH Segment</span></span>  
  
    2.  <span data-ttu-id="5ea21-130">BodySegments</span><span class="sxs-lookup"><span data-stu-id="5ea21-130">BodySegments</span></span>  
  
    3.  <span data-ttu-id="5ea21-131">ZSegments</span><span class="sxs-lookup"><span data-stu-id="5ea21-131">ZSegments</span></span>  
  
     <span data-ttu-id="5ea21-132">如果你在不同的顺序指定的消息部分，出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="5ea21-132">If you specify the message parts in a different order, the following error occurs:</span></span>  
  
     <span data-ttu-id="5ea21-133">WrongBodyPartException</span><span class="sxs-lookup"><span data-stu-id="5ea21-133">WrongBodyPartException</span></span>  
  
-   <span data-ttu-id="5ea21-134">在业务流程，以支持动态路由指定的适配器路由属性。</span><span class="sxs-lookup"><span data-stu-id="5ea21-134">The adapter route properties can be specified on the orchestration to support dynamic routing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea21-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea21-135">See Also</span></span>  
 <span data-ttu-id="5ea21-136">[配置参数发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="5ea21-136">[Configuration Parameters for Send and Receive Adapters](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span></span>  
 <span data-ttu-id="5ea21-137">[MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5ea21-137">[MLLP Receive Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span></span>  
 <span data-ttu-id="5ea21-138">[MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5ea21-138">[MLLP Send Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span></span>  
 [<span data-ttu-id="5ea21-139">处理 MLLP 编码消息</span><span class="sxs-lookup"><span data-stu-id="5ea21-139">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)