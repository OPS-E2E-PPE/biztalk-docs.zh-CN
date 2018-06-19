---
title: 处理验证 MIC 值返回在 MDN 时 AS2 解码器失败 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90388f27c44314d1c5bc795744366cfc88ed6321
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241333"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a><span data-ttu-id="29308-102">AS2 解码器在验证 MDN 中返回的 MIC 值时处理失败</span><span class="sxs-lookup"><span data-stu-id="29308-102">The AS2 Decoder failed processing when validating the MIC value returned in the MDN</span></span>
## <a name="details"></a><span data-ttu-id="29308-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="29308-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29308-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="29308-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="29308-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="29308-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="29308-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="29308-106">Event ID</span></span>|-|  
|<span data-ttu-id="29308-107">事件源</span><span class="sxs-lookup"><span data-stu-id="29308-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="29308-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="29308-108"> EDI</span></span>|  
|<span data-ttu-id="29308-109">组件</span><span class="sxs-lookup"><span data-stu-id="29308-109">Component</span></span>|<span data-ttu-id="29308-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="29308-110">AS2 Engine</span></span>|  
|<span data-ttu-id="29308-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="29308-111">Symbolic Name</span></span>|<span data-ttu-id="29308-112">AS2DecoderMdnMicFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="29308-112">AS2DecoderMdnMicFailureDuringProcessing</span></span>|  
|<span data-ttu-id="29308-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="29308-113">Message Text</span></span>|<span data-ttu-id="29308-114">AS2 解码器在验证 MDN 中返回的 MIC 值时处理失败。</span><span class="sxs-lookup"><span data-stu-id="29308-114">The AS2 Decoder failed processing when validating the MIC value returned in the MDN.</span></span>  <span data-ttu-id="29308-115">MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"</span><span class="sxs-lookup"><span data-stu-id="29308-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="29308-116">解释</span><span class="sxs-lookup"><span data-stu-id="29308-116">Explanation</span></span>  
 <span data-ttu-id="29308-117">此错误/警告/信息事件表明接收管道无法处理传入的 MDN，因为 MIC（消息完整性检查）未通过验证。</span><span class="sxs-lookup"><span data-stu-id="29308-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN because the MIC (Message Integrity Check) failed validation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29308-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="29308-118">User Action</span></span>  
 <span data-ttu-id="29308-119">若要解决此错误，请验证用于生成 MDN 的算法（在原始消息的 Signed-Receipt-MICalg 标头中）是否与 AS2 消息接收方的 Signed-Receipt-MICalg 属性中指定的算法相同。</span><span class="sxs-lookup"><span data-stu-id="29308-119">To resolve this error, verify that the algorithm used for generating the MDN (in the Signed-Receipt-MICalg header of the original message) is the same as the algorithm specified in the Signed-Receipt-MICalg property for the AS2 Message Receiver.</span></span> <span data-ttu-id="29308-120">都应是 SHA1 或 MD5。</span><span class="sxs-lookup"><span data-stu-id="29308-120">Both should be either SHA1 or MD5.</span></span> <span data-ttu-id="29308-121">如果指定的算法相同，请验证多部分签名的 MDN 消息的第二部分中的接收时间内容 MIC 扩展字段包括有效的 MIC 摘要。</span><span class="sxs-lookup"><span data-stu-id="29308-121">If the algorithm specified is the same, verify that Received-Content-MIC extension field in the second part of the multipart signed MDN message includes a valid MIC digest.</span></span> <span data-ttu-id="29308-122">如果是这样，确定为何 MDN 不对应于已发送的交换。</span><span class="sxs-lookup"><span data-stu-id="29308-122">If it does, determine why the MDN does not correspond to the interchange that was sent.</span></span>