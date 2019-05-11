---
title: 生成传出 AS2 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd96debd3099eee795ebb661a9f5828d7de6f10f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387775"
---
# <a name="generating-an-outgoing-as2-message"></a><span data-ttu-id="efb5c-102">生成传出 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="efb5c-102">Generating an Outgoing AS2 Message</span></span>
<span data-ttu-id="efb5c-103">AS2EDISend 和 AS2Send 发送管道生成出站消息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="efb5c-103">The AS2EDISend and AS2Send send pipelines generate an outbound message as follows.</span></span> <span data-ttu-id="efb5c-104">每个管道的单向协议选项卡中使用的属性**协议属性**对话框来生成传出 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="efb5c-104">Each pipeline uses the properties in the one-way agreement tab of the **Agreement Properties** dialog box to generate the outgoing AS2 message.</span></span>  
  
## <a name="agreement-destination-and-messageid-determination"></a><span data-ttu-id="efb5c-105">协议、 目标和 MessageID 确定</span><span class="sxs-lookup"><span data-stu-id="efb5c-105">Agreement, Destination, and MessageID Determination</span></span>  
 <span data-ttu-id="efb5c-106">AS2 发送管道确定要在中，如下所示发送 AS2 消息使用的协议和目标：</span><span class="sxs-lookup"><span data-stu-id="efb5c-106">The AS2 send pipelines determine the agreement and destination to be used in sending an AS2 message as follows:</span></span>  
  
-   <span data-ttu-id="efb5c-107">若要确定在处理传出消息要使用的协议，AS2 编码器尝试匹配 AS2-与订阅的消息的发送端口关联到的消息和 AS2Identity 进行参与方的业务配置文件或发送端口中的属性协议。</span><span class="sxs-lookup"><span data-stu-id="efb5c-107">To determine the agreement to use in processing an outgoing message, the AS2 encoder attempts to match the AS2-To properties in the message and the AS2Identity for a party’s business profile, or the send port subscribing to the message with a send port associated with the agreement.</span></span> <span data-ttu-id="efb5c-108">此过程的详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="efb5c-108">For more information on this process, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="efb5c-109">若要确定消息的目标，在动态发送端口的发送管道使用 OutboundTransportLocation 属性，它必须写入或通过动态发送端口，若要运行的后端应用程序升级到上下文。</span><span class="sxs-lookup"><span data-stu-id="efb5c-109">To determine the destination of the message, the send pipeline in a dynamic send port uses the OutboundTransportLocation property, which must be written or promoted to the context by a backend application for the dynamic send port to work.</span></span> <span data-ttu-id="efb5c-110">在静态发送管道中的发送管道将确定目标中的 AS2-From AS2 协议属性和业务配置文件属性的标识中的属性。</span><span class="sxs-lookup"><span data-stu-id="efb5c-110">The send pipeline in a static send pipeline will determine the destination from the AS2-From property in the AS2 agreement properties and the identities of the business profile properties.</span></span>  
  
-   <span data-ttu-id="efb5c-111">AS2 编码器需要设置传出 AS2 消息的 MessageId 标头。</span><span class="sxs-lookup"><span data-stu-id="efb5c-111">The AS2 Encoder needs to set the MessageId header of an outgoing AS2 message.</span></span> <span data-ttu-id="efb5c-112">发送管道确定从 MessageId`EdiIntAS.MessageId`上下文属性或`HTTP.UserHttpHeaders`上下文属性。</span><span class="sxs-lookup"><span data-stu-id="efb5c-112">The send pipeline determines the MessageId from either the `EdiIntAS.MessageId` context property or the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="efb5c-113">如果设置了这两个上下文属性，编码器使用的值`HTTP.UserHttpHeaders`上下文属性。</span><span class="sxs-lookup"><span data-stu-id="efb5c-113">If both of those context properties are set, the encoder uses the value from the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="efb5c-114">如果它们未设置，发送管道自动生成值的消息 Id。</span><span class="sxs-lookup"><span data-stu-id="efb5c-114">If neither of them is set, the send pipeline autogenerates a value for MessageID.</span></span>  
  
## <a name="outgoing-message-processing"></a><span data-ttu-id="efb5c-115">传出消息处理</span><span class="sxs-lookup"><span data-stu-id="efb5c-115">Outgoing Message Processing</span></span>  
 <span data-ttu-id="efb5c-116">AS2 发送管道使用在处理传出的 AS2 消息的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="efb5c-116">The steps that the AS2 send pipelines use in processing an outgoing AS2 message are as follows:</span></span>  
  
-   <span data-ttu-id="efb5c-117">以本机格式创建消息的副本并将该副本存储在不可否认数据库中，如果在协议属性中启用不可否认性的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="efb5c-117">Makes a copy of the message in native format, and stores the copy in the non-repudiation database, if non-repudiation of AS2 messages is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="efb5c-118">AS2 编码器生成到的 HTTP （和 AS2） 标头`HTTP.UserHttpHeaders`上下文属性。</span><span class="sxs-lookup"><span data-stu-id="efb5c-118">The AS2 Encoder builds the HTTP (and AS2) headers into the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="efb5c-119">此过程的详细信息，请参阅[发送端处理通过 AS2 传出的 EDI 消息的](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="efb5c-119">For more information on this process, see [Send-Side Processing of an Outgoing EDI Message over AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="efb5c-120">写入`HTTP.UserHttpHeaders`到上下文。</span><span class="sxs-lookup"><span data-stu-id="efb5c-120">Writes `HTTP.UserHttpHeaders` to the context.</span></span>  
  
-   <span data-ttu-id="efb5c-121">如果启用了，压缩的传出消息。</span><span class="sxs-lookup"><span data-stu-id="efb5c-121">Compresses the outgoing message, if enabled.</span></span>  
  
-   <span data-ttu-id="efb5c-122">执行 MIME 处理，其中包括对消息进行加密 (如果在中启用**应对消息进行加密**协议属性) 并应用数字签名 (如果在中启用**应对消息进行签名的**协议属性)。</span><span class="sxs-lookup"><span data-stu-id="efb5c-122">Performs MIME processing, including encrypting the message (if enabled in the **Message should be encrypted** agreement property) and applying a digital signature (if enabled in the **Message should be signed** agreement properties).</span></span> <span data-ttu-id="efb5c-123">AS2Send 管道使用 SHA1 或 MD5 应用签名，根据协议设置。</span><span class="sxs-lookup"><span data-stu-id="efb5c-123">The AS2Send pipeline uses either SHA1 or MD5 to apply the signature, based upon agreement settings.</span></span>  
  
-   <span data-ttu-id="efb5c-124">创建的 Content-disposition MIME 标头包含指定的值，如果将文件传输协议属性中启用了名称。</span><span class="sxs-lookup"><span data-stu-id="efb5c-124">Creates a Content-Disposition MIME header containing the specified value, if transmit file name is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="efb5c-125">创建加密的消息的副本 （以传输格式），并将该副本存储在不可否认数据库中，如果在中启用**已为出站编码 AS2 消息启用 NRR**协议属性中。</span><span class="sxs-lookup"><span data-stu-id="efb5c-125">Makes a copy of the encrypted message (in wire format), and stores the copy in the non-repudiation database, if enabled in the **NRR enabled for outbound encoded AS2 messages** in the agreement property.</span></span>  
  
-   <span data-ttu-id="efb5c-126">如果 MDN 是必需的计算的 MIC 值并将其存储在数据存储区。</span><span class="sxs-lookup"><span data-stu-id="efb5c-126">If an MDN is required, computes the MIC value and stores it in the data store.</span></span>  
  
-   <span data-ttu-id="efb5c-127">将该消息传送到 HTTP 适配器，将标头从 UserHTTPHeaders 上下文属性写入到传出的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="efb5c-127">Delivers the message to the HTTP adapter, which writes the headers from the UserHTTPHeaders context property into the outgoing AS2 message.</span></span>  
  
-   <span data-ttu-id="efb5c-128">如果可靠消息传送是必需的重新发送该消息，直到收到 MDN。</span><span class="sxs-lookup"><span data-stu-id="efb5c-128">If reliable messaging is required, resends the message until an MDN is received.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb5c-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="efb5c-129">See Also</span></span>  
 <span data-ttu-id="efb5c-130">[BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="efb5c-130">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="efb5c-131">AS2 发送组件</span><span class="sxs-lookup"><span data-stu-id="efb5c-131">AS2 Send Components</span></span>](../core/as2-send-components.md)