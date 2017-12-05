---
title: "配置错误。 消息签名没有 &#39; t 与预期值的匹配。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7aaba3aa00b15b3e015cbc010901c6d50818c42
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a><span data-ttu-id="bdebf-104">配置错误。</span><span class="sxs-lookup"><span data-stu-id="bdebf-104">Configuration error.</span></span> <span data-ttu-id="bdebf-105">消息签名没有 &#39; t 与预期值的匹配。</span><span class="sxs-lookup"><span data-stu-id="bdebf-105">The message signing doesn&#39;t match the expected value.</span></span>
## <a name="details"></a><span data-ttu-id="bdebf-106">详细信息</span><span class="sxs-lookup"><span data-stu-id="bdebf-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdebf-107">产品名称</span><span class="sxs-lookup"><span data-stu-id="bdebf-107">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bdebf-108">产品版本</span><span class="sxs-lookup"><span data-stu-id="bdebf-108">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bdebf-109">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bdebf-109">Event ID</span></span>|-|  
|<span data-ttu-id="bdebf-110">事件源</span><span class="sxs-lookup"><span data-stu-id="bdebf-110">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bdebf-111"> EDI</span><span class="sxs-lookup"><span data-stu-id="bdebf-111"> EDI</span></span>|  
|<span data-ttu-id="bdebf-112">组件</span><span class="sxs-lookup"><span data-stu-id="bdebf-112">Component</span></span>|<span data-ttu-id="bdebf-113">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="bdebf-113">AS2 Engine</span></span>|  
|<span data-ttu-id="bdebf-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="bdebf-114">Symbolic Name</span></span>|<span data-ttu-id="bdebf-115">AS2DecoderPartySigningConfigurationError</span><span class="sxs-lookup"><span data-stu-id="bdebf-115">AS2DecoderPartySigningConfigurationError</span></span>|  
|<span data-ttu-id="bdebf-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="bdebf-116">Message Text</span></span>|<span data-ttu-id="bdebf-117">配置错误。</span><span class="sxs-lookup"><span data-stu-id="bdebf-117">Configuration error.</span></span> <span data-ttu-id="bdebf-118">消息签名与预期的值不匹配。</span><span class="sxs-lookup"><span data-stu-id="bdebf-118">The message signing doesn't match the expected value.</span></span> <span data-ttu-id="bdebf-119">请与发送合作伙伴联系，以验证签名使用情况。</span><span class="sxs-lookup"><span data-stu-id="bdebf-119">Contact the sending partner and verify signature use.</span></span> <span data-ttu-id="bdebf-120">AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"</span><span class="sxs-lookup"><span data-stu-id="bdebf-120">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bdebf-121">解释</span><span class="sxs-lookup"><span data-stu-id="bdebf-121">Explanation</span></span>  
 <span data-ttu-id="bdebf-122">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法处理 AS2 消息，因为在参与方设置中指定了签名，但未对 AS2 消息进行签名，或者指定不启用签名但已对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="bdebf-122">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because signing is specified in the party settings, but the AS2 message is not signed, or signing is specified not to be enabled, but the message is signed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdebf-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="bdebf-123">User Action</span></span>  
 <span data-ttu-id="bdebf-124">要解决此错误，请验证中的方设置未启用消息进行签名，如果签名方设置中指定或如果签名未签名为传入 AS2 消息指定为传入 AS2。</span><span class="sxs-lookup"><span data-stu-id="bdebf-124">To resolve this error, verify that the incoming AS2 message is signed if signing is specified in the party settings or that the incoming AS2 message is not signed if signing is specified as not enabled in the party settings.</span></span> <span data-ttu-id="bdebf-125">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="bdebf-125">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="bdebf-126">如果**重写入站的消息属性**方中为 AS2 消息发送方页面在 BizTalk Server 管理控制台中，AS2 属性对话框中选择属性**消息应为签名的**选择属性，但未签名消息、 发送消息的组织联系并要求他们对消息进行签名并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="bdebf-126">If the **Override inbound message properties** property is selected in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the BizTalk Server Administration Console, the **Message should be signed** property is selected, but the message is not signed, contact the party that sent the message and ask them to sign the message, and resend it.</span></span> <span data-ttu-id="bdebf-127">也可以清除**应对消息进行签名**属性，或**重写入站的消息属性**属性。</span><span class="sxs-lookup"><span data-stu-id="bdebf-127">Or you can clear the **Message should be signed** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="bdebf-128">如果**重写入站的消息属性**选定属性，则**应对消息进行签名**属性处于未选中状态，但消息已签名，请联系发送消息的当事方并不适用于请求对消息进行签名并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="bdebf-128">If the **Override inbound message properties** property is selected, the **Message should be signed** property is cleared, but the message is signed, contact the party that sent the message and ask them not to sign the message, and resend it.</span></span> <span data-ttu-id="bdebf-129">也可以选择**应对消息进行签名**属性。</span><span class="sxs-lookup"><span data-stu-id="bdebf-129">Or you can select the **Message should be signed** property.</span></span>