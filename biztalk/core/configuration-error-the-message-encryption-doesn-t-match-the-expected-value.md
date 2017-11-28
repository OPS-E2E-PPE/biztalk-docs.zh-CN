---
title: "配置错误。 消息加密不 &#39; 与预期值匹配的 t |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b17460c4dcd6f9d2a8c18e5e7284cd36940d6820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a><span data-ttu-id="71068-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="71068-103">Configuration error.</span></span> <span data-ttu-id="71068-104">消息加密不 &#39; t 匹配预期值</span><span class="sxs-lookup"><span data-stu-id="71068-104">The message encryption doesn&#39;t match the expected value</span></span>
## <a name="details"></a><span data-ttu-id="71068-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="71068-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71068-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="71068-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="71068-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="71068-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="71068-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="71068-108">Event ID</span></span>|-|  
|<span data-ttu-id="71068-109">事件源</span><span class="sxs-lookup"><span data-stu-id="71068-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="71068-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="71068-110"> EDI</span></span>|  
|<span data-ttu-id="71068-111">组件</span><span class="sxs-lookup"><span data-stu-id="71068-111">Component</span></span>|<span data-ttu-id="71068-112">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="71068-112">AS2 Engine</span></span>|  
|<span data-ttu-id="71068-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="71068-113">Symbolic Name</span></span>|<span data-ttu-id="71068-114">AS2DecoderPartyEncryptionConfigurationError</span><span class="sxs-lookup"><span data-stu-id="71068-114">AS2DecoderPartyEncryptionConfigurationError</span></span>|  
|<span data-ttu-id="71068-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="71068-115">Message Text</span></span>|<span data-ttu-id="71068-116">配置错误。</span><span class="sxs-lookup"><span data-stu-id="71068-116">Configuration error.</span></span> <span data-ttu-id="71068-117">消息加密与预期值不匹配。</span><span class="sxs-lookup"><span data-stu-id="71068-117">The message encryption doesn't match the expected value.</span></span> <span data-ttu-id="71068-118">请与发送合作伙伴联系，以验证加密使用情况。</span><span class="sxs-lookup"><span data-stu-id="71068-118">Contact the sending partner and verify encryption use.</span></span> <span data-ttu-id="71068-119">AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"</span><span class="sxs-lookup"><span data-stu-id="71068-119">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="71068-120">解释</span><span class="sxs-lookup"><span data-stu-id="71068-120">Explanation</span></span>  
 <span data-ttu-id="71068-121">此错误/警告/信息事件指示接收管道的 AS2 解码器组件无法因加密指定在方设置中，但未加密 AS2 消息，或者加密指定不准备处理 AS2 消息启用，但对消息加密。</span><span class="sxs-lookup"><span data-stu-id="71068-121">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because encryption is specified in the party settings, but the AS2 message is not encrypted, or encryption is specified not to be enabled, but the message is encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71068-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="71068-122">User Action</span></span>  
 <span data-ttu-id="71068-123">若要解决此错误，请验证是否已对传入的 AS2 消息进行加密（如果在参与方设置中指定了加密），或者验证是否未对传入的 AS2 消息进行加密（如果在参与方设置中指定了不启用加密）。</span><span class="sxs-lookup"><span data-stu-id="71068-123">To resolve this error, verify that the incoming AS2 message is encrypted if encryption is specified in the party settings or that the incoming AS2 message is not encrypted if encryption is specified as not enabled in the party settings.</span></span> <span data-ttu-id="71068-124">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="71068-124">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="71068-125">如果**替代选择入站的消息属性属性**中作为 AS2 属性对话框中的 AS2 消息发送方页方[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，**应对消息进行加密**选择属性，但未加密消息，发送消息的组织联系并要求他们来加密消息，并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="71068-125">If the **Override inbound message properties property is selected** in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, the **Message should be encrypted** property is selected, but the message is not encrypted, contact the party that sent the message and ask them to encrypt the message, and resend it.</span></span> <span data-ttu-id="71068-126">也可以清除**应对消息进行加密**属性，或**重写入站的消息属性**属性。</span><span class="sxs-lookup"><span data-stu-id="71068-126">Or you can clear the **Message should be encrypted** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="71068-127">如果**重写入站的消息属性**选定属性，则**应对消息进行加密**属性处于未选中状态，但对消息加密，请联系发送消息的当事方，并请求无法加密消息，并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="71068-127">If the **Override inbound message properties** property is selected, the **Message should be encrypted** property is cleared, but the message is encrypted, contact the party that sent the message and ask them not to encrypt the message, and resend it.</span></span> <span data-ttu-id="71068-128">也可以选择**应对消息进行加密**属性。</span><span class="sxs-lookup"><span data-stu-id="71068-128">Or you can select the **Message should be encrypted** property.</span></span>