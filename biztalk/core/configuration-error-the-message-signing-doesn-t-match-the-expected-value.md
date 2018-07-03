---
title: 配置错误。 消息签名不&#39;t 与预期值匹配。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfe2b610724a346ed31fb0951aa90c660f41d82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975934"
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a><span data-ttu-id="dacd0-104">配置错误。</span><span class="sxs-lookup"><span data-stu-id="dacd0-104">Configuration error.</span></span> <span data-ttu-id="dacd0-105">消息签名不&#39;t 与预期值匹配。</span><span class="sxs-lookup"><span data-stu-id="dacd0-105">The message signing doesn&#39;t match the expected value.</span></span>
## <a name="details"></a><span data-ttu-id="dacd0-106">详细信息</span><span class="sxs-lookup"><span data-stu-id="dacd0-106">Details</span></span>  
  
|                 |                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dacd0-107">产品名称</span><span class="sxs-lookup"><span data-stu-id="dacd0-107">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                              |
| <span data-ttu-id="dacd0-108">产品版本</span><span class="sxs-lookup"><span data-stu-id="dacd0-108">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                          |
|    <span data-ttu-id="dacd0-109">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dacd0-109">Event ID</span></span>     |                                                                                      -                                                                                       |
|  <span data-ttu-id="dacd0-110">事件源</span><span class="sxs-lookup"><span data-stu-id="dacd0-110">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dacd0-111"> EDI</span><span class="sxs-lookup"><span data-stu-id="dacd0-111"> EDI</span></span>                                            |
|    <span data-ttu-id="dacd0-112">组件</span><span class="sxs-lookup"><span data-stu-id="dacd0-112">Component</span></span>    |                                                                                  <span data-ttu-id="dacd0-113">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="dacd0-113">AS2 Engine</span></span>                                                                                  |
|  <span data-ttu-id="dacd0-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="dacd0-114">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="dacd0-115">AS2DecoderPartySigningConfigurationError</span><span class="sxs-lookup"><span data-stu-id="dacd0-115">AS2DecoderPartySigningConfigurationError</span></span>                                                                   |
|  <span data-ttu-id="dacd0-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="dacd0-116">Message Text</span></span>   | <span data-ttu-id="dacd0-117">配置错误。</span><span class="sxs-lookup"><span data-stu-id="dacd0-117">Configuration error.</span></span> <span data-ttu-id="dacd0-118">消息签名与预期的值不匹配。</span><span class="sxs-lookup"><span data-stu-id="dacd0-118">The message signing doesn't match the expected value.</span></span> <span data-ttu-id="dacd0-119">请与发送合作伙伴联系，以验证签名使用情况。</span><span class="sxs-lookup"><span data-stu-id="dacd0-119">Contact the sending partner and verify signature use.</span></span> <span data-ttu-id="dacd0-120">AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="dacd0-120">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dacd0-121">解释</span><span class="sxs-lookup"><span data-stu-id="dacd0-121">Explanation</span></span>  
 <span data-ttu-id="dacd0-122">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法处理 AS2 消息，因为在参与方设置中指定了签名，但未对 AS2 消息进行签名，或者指定不启用签名但已对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="dacd0-122">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because signing is specified in the party settings, but the AS2 message is not signed, or signing is specified not to be enabled, but the message is signed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dacd0-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="dacd0-123">User Action</span></span>  
 <span data-ttu-id="dacd0-124">若要解决此错误，请验证传入的 AS2 消息进行签名，如果在参与方设置中指定了签名，或如果签名未签名传入的 AS2 消息指定为未启用参与方设置中。</span><span class="sxs-lookup"><span data-stu-id="dacd0-124">To resolve this error, verify that the incoming AS2 message is signed if signing is specified in the party settings or that the incoming AS2 message is not signed if signing is specified as not enabled in the party settings.</span></span> <span data-ttu-id="dacd0-125">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="dacd0-125">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="dacd0-126">如果**替代入站的消息属性**属性选择的参与方中作为 AS2 消息发送方在 BizTalk Server 管理控制台的 AS2 属性对话框页**应对消息进行签名的**选择属性，但未签名消息，请与发送消息的参与方和要求他们对消息进行签名并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="dacd0-126">If the **Override inbound message properties** property is selected in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the BizTalk Server Administration Console, the **Message should be signed** property is selected, but the message is not signed, contact the party that sent the message and ask them to sign the message, and resend it.</span></span> <span data-ttu-id="dacd0-127">也可以清除**应对消息进行签名**属性，或**替代入站的消息属性**属性。</span><span class="sxs-lookup"><span data-stu-id="dacd0-127">Or you can clear the **Message should be signed** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="dacd0-128">如果**替代入站的消息属性**选定属性，则**应对消息进行签名**清除属性，但对消息进行签名、 联系发送消息的参与方并请求他们不这样做对消息进行签名，然后重新发送它。</span><span class="sxs-lookup"><span data-stu-id="dacd0-128">If the **Override inbound message properties** property is selected, the **Message should be signed** property is cleared, but the message is signed, contact the party that sent the message and ask them not to sign the message, and resend it.</span></span> <span data-ttu-id="dacd0-129">也可以选择**应对消息进行签名**属性。</span><span class="sxs-lookup"><span data-stu-id="dacd0-129">Or you can select the **Message should be signed** property.</span></span>