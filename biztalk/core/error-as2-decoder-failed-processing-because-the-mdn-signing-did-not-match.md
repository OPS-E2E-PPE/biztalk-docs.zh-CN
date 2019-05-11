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
ms.openlocfilehash: 2e79b28c69786bad3e261cc3269329bd6465a8ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388999"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="77390-102">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配</span><span class="sxs-lookup"><span data-stu-id="77390-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="77390-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="77390-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="77390-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="77390-104">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="77390-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="77390-105">Product Version</span></span> |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="77390-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="77390-106">Event ID</span></span>     |                                                                                                   -                                                                                                    |
|  <span data-ttu-id="77390-107">事件源</span><span class="sxs-lookup"><span data-stu-id="77390-107">Event Source</span></span>   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="77390-108">EDI</span><span class="sxs-lookup"><span data-stu-id="77390-108">EDI</span></span>                                                         |
|    <span data-ttu-id="77390-109">组件</span><span class="sxs-lookup"><span data-stu-id="77390-109">Component</span></span>    |                                                                                               <span data-ttu-id="77390-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="77390-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="77390-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="77390-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="77390-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="77390-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="77390-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="77390-113">Message Text</span></span>   | <span data-ttu-id="77390-114">AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。</span><span class="sxs-lookup"><span data-stu-id="77390-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="77390-115">MDN 消息的详细信息如下所示：AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="77390-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="77390-116">解释</span><span class="sxs-lookup"><span data-stu-id="77390-116">Explanation</span></span>  
 <span data-ttu-id="77390-117">此错误/警告/信息事件表明接收管道无法处理传入 MDN 是因为已签名 MDN，但签名不请求的 MDN 或 MDN 是无符号整数，但签名请求了 MDN。</span><span class="sxs-lookup"><span data-stu-id="77390-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77390-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="77390-118">User Action</span></span>  
 <span data-ttu-id="77390-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="77390-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="77390-120">更改以匹配请求的 MDN 的签名请求。</span><span class="sxs-lookup"><span data-stu-id="77390-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="77390-121">为此，请打开作为 AS2 消息接收方页的 AS2 属性对话框中，并选择"请求 MDN"属性的参与方，请选中或清除"请求经过签名的 MDN"属性。</span><span class="sxs-lookup"><span data-stu-id="77390-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="77390-122">请与原始的 AS2 消息，若要解决是否应签名 Mdn 的接收方。</span><span class="sxs-lookup"><span data-stu-id="77390-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>