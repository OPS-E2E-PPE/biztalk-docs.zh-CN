---
title: "生成传出的 AS2 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generating-an-outgoing-as2-message"></a><span data-ttu-id="56643-102">生成传出的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="56643-102">Generating an Outgoing AS2 Message</span></span>
<span data-ttu-id="56643-103">AS2EDISend 和 AS2Send 发送管道生成出站消息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="56643-103">The AS2EDISend and AS2Send send pipelines generate an outbound message as follows.</span></span> <span data-ttu-id="56643-104">每个管道的单向协议选项卡中使用的属性**协议属性**对话框生成传出的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="56643-104">Each pipeline uses the properties in the one-way agreement tab of the **Agreement Properties** dialog box to generate the outgoing AS2 message.</span></span>  
  
## <a name="agreement-destination-and-messageid-determination"></a><span data-ttu-id="56643-105">确定协议、目标和 MessageID</span><span class="sxs-lookup"><span data-stu-id="56643-105">Agreement, Destination, and MessageID Determination</span></span>  
 <span data-ttu-id="56643-106">AS2 发送管道确定用于发送 AS2 消息，如下所示的协议和目标：</span><span class="sxs-lookup"><span data-stu-id="56643-106">The AS2 send pipelines determine the agreement and destination to be used in sending an AS2 message as follows:</span></span>  
  
-   <span data-ttu-id="56643-107">为了确定处理传出消息时使用的协议，AS2 编码器尝试将消息中的 AS2-To 属性和参与方业务配置文件的 AS2Identity 进行匹配，或者将订阅消息的发送端口和与协议关联的发送端口进行匹配。</span><span class="sxs-lookup"><span data-stu-id="56643-107">To determine the agreement to use in processing an outgoing message, the AS2 encoder attempts to match the AS2-To properties in the message and the AS2Identity for a party’s business profile, or the send port subscribing to the message with a send port associated with the agreement.</span></span> <span data-ttu-id="56643-108">此过程的详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="56643-108">For more information on this process, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="56643-109">若要确定消息的目标，在动态发送端口发送管道，请使用 OutboundTransportLocation 属性，必须编写或通过动态发送端口工作的后端应用程序提升到上下文。</span><span class="sxs-lookup"><span data-stu-id="56643-109">To determine the destination of the message, the send pipeline in a dynamic send port uses the OutboundTransportLocation property, which must be written or promoted to the context by a backend application for the dynamic send port to work.</span></span> <span data-ttu-id="56643-110">静态发送管道中的发送管道将通过 AS2 协议属性中的 AS2-From 属性和业务配置文件属性的标识来确定目标。</span><span class="sxs-lookup"><span data-stu-id="56643-110">The send pipeline in a static send pipeline will determine the destination from the AS2-From property in the AS2 agreement properties and the identities of the business profile properties.</span></span>  
  
-   <span data-ttu-id="56643-111">AS2 编码器需要设置传出的 AS2 消息的 MessageId 标头。</span><span class="sxs-lookup"><span data-stu-id="56643-111">The AS2 Encoder needs to set the MessageId header of an outgoing AS2 message.</span></span> <span data-ttu-id="56643-112">发送管道将从 `EdiIntAS.MessageId` 上下文属性或 `HTTP.UserHttpHeaders` 上下文属性来确定 MessageId。</span><span class="sxs-lookup"><span data-stu-id="56643-112">The send pipeline determines the MessageId from either the `EdiIntAS.MessageId` context property or the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="56643-113">如果上述两个上下文属性均已设置，则编码器将使用 `HTTP.UserHttpHeaders` 上下文属性中的值。</span><span class="sxs-lookup"><span data-stu-id="56643-113">If both of those context properties are set, the encoder uses the value from the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="56643-114">如果这些都不设置，发送管道自动生成一个值的 MessageID。</span><span class="sxs-lookup"><span data-stu-id="56643-114">If neither of them is set, the send pipeline autogenerates a value for MessageID.</span></span>  
  
## <a name="outgoing-message-processing"></a><span data-ttu-id="56643-115">传出消息处理</span><span class="sxs-lookup"><span data-stu-id="56643-115">Outgoing Message Processing</span></span>  
 <span data-ttu-id="56643-116">AS2 发送管道处理传出 AS2 消息中使用的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="56643-116">The steps that the AS2 send pipelines use in processing an outgoing AS2 message are as follows:</span></span>  
  
-   <span data-ttu-id="56643-117">以本机格式创建消息的副本，并将该副本存储在不可否认数据库中（如果在协议属性中启用 AS2 消息的不可否认）。</span><span class="sxs-lookup"><span data-stu-id="56643-117">Makes a copy of the message in native format, and stores the copy in the non-repudiation database, if non-repudiation of AS2 messages is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="56643-118">AS2 编码器将 HTTP（和 AS2）标头生成到 `HTTP.UserHttpHeaders` 上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="56643-118">The AS2 Encoder builds the HTTP (and AS2) headers into the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="56643-119">此过程的详细信息，请参阅[发送方的传出通过 AS2 EDI 消息处理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="56643-119">For more information on this process, see [Send-Side Processing of an Outgoing EDI Message over AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="56643-120">将 `HTTP.UserHttpHeaders` 写入到上下文。</span><span class="sxs-lookup"><span data-stu-id="56643-120">Writes `HTTP.UserHttpHeaders` to the context.</span></span>  
  
-   <span data-ttu-id="56643-121">如果启用，将压缩的传出消息。</span><span class="sxs-lookup"><span data-stu-id="56643-121">Compresses the outgoing message, if enabled.</span></span>  
  
-   <span data-ttu-id="56643-122">执行 MIME 处理，包括加密消息 (如果在中启用**应对消息进行加密**协议属性) 并将其应用数字签名 (如果在中启用**消息应为签名的**协议属性)。</span><span class="sxs-lookup"><span data-stu-id="56643-122">Performs MIME processing, including encrypting the message (if enabled in the **Message should be encrypted** agreement property) and applying a digital signature (if enabled in the **Message should be signed** agreement properties).</span></span> <span data-ttu-id="56643-123">AS2Send 管道使用 SHA1 或 MD5 应用签名，基于协议设置。</span><span class="sxs-lookup"><span data-stu-id="56643-123">The AS2Send pipeline uses either SHA1 or MD5 to apply the signature, based upon agreement settings.</span></span>  
  
-   <span data-ttu-id="56643-124">如果已在协议属性中启用传输文件名，则创建一个包含指定值的 Content-Disposition MIME 标头。</span><span class="sxs-lookup"><span data-stu-id="56643-124">Creates a Content-Disposition MIME header containing the specified value, if transmit file name is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="56643-125">（在连网格式），将加密的消息的副本，并将副本存储在不可否认性数据库中，如果在中启用**为出站的已编码 AS2 消息启用 NRR**协议属性中。</span><span class="sxs-lookup"><span data-stu-id="56643-125">Makes a copy of the encrypted message (in wire format), and stores the copy in the non-repudiation database, if enabled in the **NRR enabled for outbound encoded AS2 messages** in the agreement property.</span></span>  
  
-   <span data-ttu-id="56643-126">如果需要 MDN，计算 MIC 值并将其存储在数据存储。</span><span class="sxs-lookup"><span data-stu-id="56643-126">If an MDN is required, computes the MIC value and stores it in the data store.</span></span>  
  
-   <span data-ttu-id="56643-127">消息传送至 HTTP 适配器，这将从 UserHTTPHeaders 上下文属性的标头写入到传出的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="56643-127">Delivers the message to the HTTP adapter, which writes the headers from the UserHTTPHeaders context property into the outgoing AS2 message.</span></span>  
  
-   <span data-ttu-id="56643-128">如果可靠消息传递是必需的重新发送消息，直到收到 MDN。</span><span class="sxs-lookup"><span data-stu-id="56643-128">If reliable messaging is required, resends the message until an MDN is received.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56643-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56643-129">See Also</span></span>  
 <span data-ttu-id="56643-130">[BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="56643-130">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="56643-131">AS2 发送组件</span><span class="sxs-lookup"><span data-stu-id="56643-131">AS2 Send Components</span></span>](../core/as2-send-components.md)