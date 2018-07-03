---
title: AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a4d5cb5cd1825f5620ab39e4c770eb9818a5ade
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978866"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="4305d-102">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配</span><span class="sxs-lookup"><span data-stu-id="4305d-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="4305d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4305d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4305d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4305d-104">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="4305d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4305d-105">Product Version</span></span> |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="4305d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4305d-106">Event ID</span></span>     |                                                                                                   -                                                                                                    |
|  <span data-ttu-id="4305d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4305d-107">Event Source</span></span>   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4305d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4305d-108"> EDI</span></span>                                                         |
|    <span data-ttu-id="4305d-109">组件</span><span class="sxs-lookup"><span data-stu-id="4305d-109">Component</span></span>    |                                                                                               <span data-ttu-id="4305d-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="4305d-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="4305d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4305d-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="4305d-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="4305d-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="4305d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4305d-113">Message Text</span></span>   | <span data-ttu-id="4305d-114">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。</span><span class="sxs-lookup"><span data-stu-id="4305d-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="4305d-115">MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="4305d-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4305d-116">解释</span><span class="sxs-lookup"><span data-stu-id="4305d-116">Explanation</span></span>  
 <span data-ttu-id="4305d-117">此错误/警告/信息事件表明接收管道无法处理传入 MDN 是因为已签名 MDN，但签名不请求的 MDN 或 MDN 是无符号整数，但签名请求了 MDN。</span><span class="sxs-lookup"><span data-stu-id="4305d-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4305d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="4305d-118">User Action</span></span>  
 <span data-ttu-id="4305d-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4305d-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="4305d-120">更改 MDN 的签名请求以匹配请求。</span><span class="sxs-lookup"><span data-stu-id="4305d-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="4305d-121">为此，请打开“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页，并且选中“请求 MDN”属性，选中或清除“请求经过签名的 MDN”属性。</span><span class="sxs-lookup"><span data-stu-id="4305d-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="4305d-122">请与原始的 AS2 消息，若要解决是否应签名 Mdn 的接收方。</span><span class="sxs-lookup"><span data-stu-id="4305d-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>