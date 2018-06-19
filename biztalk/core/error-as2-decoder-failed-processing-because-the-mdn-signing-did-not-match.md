---
title: AS2 解码器失败处理，因为 MDN 签名与我们请求不匹配 |Microsoft 文档
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
ms.openlocfilehash: cc0660a64ff0aeb35976ad1aa45a602d8db0913a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239973"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="1ce88-102">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配</span><span class="sxs-lookup"><span data-stu-id="1ce88-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="1ce88-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ce88-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ce88-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1ce88-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1ce88-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1ce88-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1ce88-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1ce88-106">Event ID</span></span>|-|  
|<span data-ttu-id="1ce88-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1ce88-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1ce88-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1ce88-108"> EDI</span></span>|  
|<span data-ttu-id="1ce88-109">组件</span><span class="sxs-lookup"><span data-stu-id="1ce88-109">Component</span></span>|<span data-ttu-id="1ce88-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="1ce88-110">AS2 Engine</span></span>|  
|<span data-ttu-id="1ce88-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1ce88-111">Symbolic Name</span></span>|<span data-ttu-id="1ce88-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="1ce88-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>|  
|<span data-ttu-id="1ce88-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1ce88-113">Message Text</span></span>|<span data-ttu-id="1ce88-114">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。</span><span class="sxs-lookup"><span data-stu-id="1ce88-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="1ce88-115">MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"</span><span class="sxs-lookup"><span data-stu-id="1ce88-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ce88-116">解释</span><span class="sxs-lookup"><span data-stu-id="1ce88-116">Explanation</span></span>  
 <span data-ttu-id="1ce88-117">此错误/警告/信息事件指示接收管道无法处理传入的 MDN 或者因为 MDN 已签名，但签名未请求 MDN 或将 MDN 是无符号整数，但签名为请求 MDN。</span><span class="sxs-lookup"><span data-stu-id="1ce88-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ce88-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1ce88-118">User Action</span></span>  
 <span data-ttu-id="1ce88-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="1ce88-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="1ce88-120">更改 MDN 的签名请求以匹配请求。</span><span class="sxs-lookup"><span data-stu-id="1ce88-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="1ce88-121">为此，请打开“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页，并且选中“请求 MDN”属性，选中或清除“请求经过签名的 MDN”属性。</span><span class="sxs-lookup"><span data-stu-id="1ce88-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="1ce88-122">请与联系以解决 Mdn 应或未进行签名的原始 AS2 消息接收方。</span><span class="sxs-lookup"><span data-stu-id="1ce88-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>