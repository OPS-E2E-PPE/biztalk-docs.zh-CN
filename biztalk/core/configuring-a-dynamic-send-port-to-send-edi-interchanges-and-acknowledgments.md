---
title: "配置动态发送端口发送 EDI 交换和确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a793fc22394c2b4d294bcd48fae1f9403ae9278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a><span data-ttu-id="d29f2-102">配置动态发送端口以发送 EDI 交换和确认</span><span class="sxs-lookup"><span data-stu-id="d29f2-102">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>
<span data-ttu-id="d29f2-103">若要发送 EDI 确认或交换，可以使用静态发送端口或动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="d29f2-103">To send an EDI acknowledgment or interchange, you can use either a static send port or a dynamic send port.</span></span> <span data-ttu-id="d29f2-104">使用动态发送端口，您可以向多个目标中的任何一个发送交换，原因是它将对协议进行解析，并基于 DestinationPartyName 上下文属性中的值确定目标地址。</span><span class="sxs-lookup"><span data-stu-id="d29f2-104">A dynamic send port enables you to send an interchange to any one of multiple destinations, because it resolves the agreement and determines the destination address based upon the value in the DestinationPartyName context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d29f2-105">如果您基于收到的 XML 消息发送 EDI 交换，并且使用直通接收管道接收该应用程序，则必须升级 DestinationPartyName 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d29f2-105">If you are sending an EDI interchange that is based upon an XML message received, and you are using a passthrough receive pipeline to receive that application, you will have to promote the DestinationPartyName context property.</span></span> <span data-ttu-id="d29f2-106">有关详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="d29f2-106">For more information, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d29f2-107">如果发送确认的将是动态发送端口，则一定已经升级 DestinationPartyName 上下文属性，原因是已接收交换的端口中的 EDI 拆装器将填充确认上的 DestinationPartyName 属性。</span><span class="sxs-lookup"><span data-stu-id="d29f2-107">If the dynamic send port will be sending an acknowledgment, the DestinationPartyName context property will already be promoted because the EDI Disassembler in the port that received the interchange populates the DestinationPartyName property on the acknowledgment.</span></span>  
  
 <span data-ttu-id="d29f2-108">若要创建单向动态发送端口，请使用以下配置：</span><span class="sxs-lookup"><span data-stu-id="d29f2-108">To create a one-way dynamic send port, use the following configuration:</span></span>  
  
|<span data-ttu-id="d29f2-109">位置</span><span class="sxs-lookup"><span data-stu-id="d29f2-109">Location</span></span>|<span data-ttu-id="d29f2-110">属性</span><span class="sxs-lookup"><span data-stu-id="d29f2-110">Property</span></span>|<span data-ttu-id="d29f2-111">设置</span><span class="sxs-lookup"><span data-stu-id="d29f2-111">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="d29f2-112">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="d29f2-112">**Send Port Properties: General**</span></span>|<span data-ttu-id="d29f2-113">端口类型</span><span class="sxs-lookup"><span data-stu-id="d29f2-113">Port type</span></span>|<span data-ttu-id="d29f2-114">动态单向</span><span class="sxs-lookup"><span data-stu-id="d29f2-114">Dynamic One-Way</span></span>|  
|<span data-ttu-id="d29f2-115">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="d29f2-115">**Send Port Properties: General**</span></span>|<span data-ttu-id="d29f2-116">发送处理程序</span><span class="sxs-lookup"><span data-stu-id="d29f2-116">Send handler</span></span>|<span data-ttu-id="d29f2-117">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="d29f2-117">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="d29f2-118">**发送端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="d29f2-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="d29f2-119">发送管道</span><span class="sxs-lookup"><span data-stu-id="d29f2-119">Send pipeline</span></span>|<span data-ttu-id="d29f2-120">EdiSend</span><span class="sxs-lookup"><span data-stu-id="d29f2-120">EdiSend</span></span>|  
|<span data-ttu-id="d29f2-121">**文件传输属性： 身份验证**</span><span class="sxs-lookup"><span data-stu-id="d29f2-121">**FILE Transport Properties: Authentication**</span></span>|<span data-ttu-id="d29f2-122">在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）</span><span class="sxs-lookup"><span data-stu-id="d29f2-122">Use these credentials when host does not have access to network share (with User name and Password)</span></span>|<span data-ttu-id="d29f2-123">如果需要验证，则加以设置。</span><span class="sxs-lookup"><span data-stu-id="d29f2-123">Set if authentication is required.</span></span>|  
|<span data-ttu-id="d29f2-124">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="d29f2-124">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="d29f2-125">属性</span><span class="sxs-lookup"><span data-stu-id="d29f2-125">Property</span></span>|<span data-ttu-id="d29f2-126">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="d29f2-126">BTS.MessageType</span></span>|  
|<span data-ttu-id="d29f2-127">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="d29f2-127">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="d29f2-128">运算符</span><span class="sxs-lookup"><span data-stu-id="d29f2-128">Operator</span></span>|==|  
|<span data-ttu-id="d29f2-129">**发送端口属性： 筛选器**</span><span class="sxs-lookup"><span data-stu-id="d29f2-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="d29f2-130">值</span><span class="sxs-lookup"><span data-stu-id="d29f2-130">Value</span></span>|<span data-ttu-id="d29f2-131">**为交换**:</span><span class="sxs-lookup"><span data-stu-id="d29f2-131">**For interchanges**:</span></span><br /><br /> <span data-ttu-id="d29f2-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`或</span><span class="sxs-lookup"><span data-stu-id="d29f2-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, or</span></span><br /><br /> <span data-ttu-id="d29f2-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`或</span><span class="sxs-lookup"><span data-stu-id="d29f2-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`,or</span></span><br /><br /> <span data-ttu-id="d29f2-134">**Ack**:</span><span class="sxs-lookup"><span data-stu-id="d29f2-134">**For ACKs**:</span></span><br /><br /> <span data-ttu-id="d29f2-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`或</span><span class="sxs-lookup"><span data-stu-id="d29f2-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, or</span></span><br /><br /> <span data-ttu-id="d29f2-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`或</span><span class="sxs-lookup"><span data-stu-id="d29f2-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, or</span></span><br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a><span data-ttu-id="d29f2-137">设置协议属性</span><span class="sxs-lookup"><span data-stu-id="d29f2-137">Setting Agreement Properties</span></span>  
 <span data-ttu-id="d29f2-138">在创建后发送端口，你需要设置所需的函数到发送管道协议属性。</span><span class="sxs-lookup"><span data-stu-id="d29f2-138">After creating the send port, you need to set the agreement properties required for the send pipeline to function.</span></span> <span data-ttu-id="d29f2-139">各种页中设置这些属性**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d29f2-139">These properties are set in various pages of the **Agreement Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29f2-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d29f2-140">See Also</span></span>  
 [<span data-ttu-id="d29f2-141">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="d29f2-141">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)