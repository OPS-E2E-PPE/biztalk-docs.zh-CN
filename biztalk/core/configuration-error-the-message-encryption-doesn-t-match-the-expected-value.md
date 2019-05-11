---
title: 配置错误。 消息加密并不&#39;t 与预期值匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51756b202d554b2ea85eb8e302497729f524ea2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356511"
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a><span data-ttu-id="0e653-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="0e653-103">Configuration error.</span></span> <span data-ttu-id="0e653-104">消息加密并不&#39;t 匹配预期值</span><span class="sxs-lookup"><span data-stu-id="0e653-104">The message encryption doesn&#39;t match the expected value</span></span>
## <a name="details"></a><span data-ttu-id="0e653-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e653-105">Details</span></span>  
  
|                 |                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e653-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="0e653-106">Product Name</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| <span data-ttu-id="0e653-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="0e653-107">Product Version</span></span> |                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    <span data-ttu-id="0e653-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0e653-108">Event ID</span></span>     |                                                                                        -                                                                                         |
|  <span data-ttu-id="0e653-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0e653-109">Event Source</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0e653-110">EDI</span><span class="sxs-lookup"><span data-stu-id="0e653-110">EDI</span></span>                                              |
|    <span data-ttu-id="0e653-111">组件</span><span class="sxs-lookup"><span data-stu-id="0e653-111">Component</span></span>    |                                                                                    <span data-ttu-id="0e653-112">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="0e653-112">AS2 Engine</span></span>                                                                                    |
|  <span data-ttu-id="0e653-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0e653-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="0e653-114">AS2DecoderPartyEncryptionConfigurationError</span><span class="sxs-lookup"><span data-stu-id="0e653-114">AS2DecoderPartyEncryptionConfigurationError</span></span>                                                                    |
|  <span data-ttu-id="0e653-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0e653-115">Message Text</span></span>   | <span data-ttu-id="0e653-116">配置错误。</span><span class="sxs-lookup"><span data-stu-id="0e653-116">Configuration error.</span></span> <span data-ttu-id="0e653-117">消息加密与预期值不匹配。</span><span class="sxs-lookup"><span data-stu-id="0e653-117">The message encryption doesn't match the expected value.</span></span> <span data-ttu-id="0e653-118">请与发送合作伙伴联系，以验证加密使用。</span><span class="sxs-lookup"><span data-stu-id="0e653-118">Contact the sending partner and verify encryption use.</span></span> <span data-ttu-id="0e653-119">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="0e653-119">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e653-120">解释</span><span class="sxs-lookup"><span data-stu-id="0e653-120">Explanation</span></span>  
 <span data-ttu-id="0e653-121">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法因为在参与方设置中，指定加密但未加密的 AS2 消息，或加密指定为不处理 AS2 消息已启用，但对消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="0e653-121">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because encryption is specified in the party settings, but the AS2 message is not encrypted, or encryption is specified not to be enabled, but the message is encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e653-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0e653-122">User Action</span></span>  
 <span data-ttu-id="0e653-123">若要解决此错误，请验证传入的 AS2 消息进行加密，是否参与方设置中指定加密或为未指定加密未加密的传入 AS2 消息启用参与方设置中。</span><span class="sxs-lookup"><span data-stu-id="0e653-123">To resolve this error, verify that the incoming AS2 message is encrypted if encryption is specified in the party settings or that the incoming AS2 message is not encrypted if encryption is specified as not enabled in the party settings.</span></span> <span data-ttu-id="0e653-124">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="0e653-124">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="0e653-125">如果**选择入站的消息属性属性重写**作为 AS2 消息发送方在 BizTalk Server 管理控制台的 AS2 属性对话框页的参与方**应对消息进行加密**选择属性，但未加密消息，请与发送消息的参与方和要求他们以加密消息，并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="0e653-125">If the **Override inbound message properties property is selected** in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the BizTalk Server Administration Console, the **Message should be encrypted** property is selected, but the message is not encrypted, contact the party that sent the message and ask them to encrypt the message, and resend it.</span></span> <span data-ttu-id="0e653-126">也可以清除**应对消息进行加密**属性，或**替代入站的消息属性**属性。</span><span class="sxs-lookup"><span data-stu-id="0e653-126">Or you can clear the **Message should be encrypted** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="0e653-127">如果**替代入站的消息属性**选定属性，则**应对消息进行加密**清除属性，但对消息进行加密，请与发送消息的参与方，并请求他们无法加密消息，并重新发送它。</span><span class="sxs-lookup"><span data-stu-id="0e653-127">If the **Override inbound message properties** property is selected, the **Message should be encrypted** property is cleared, but the message is encrypted, contact the party that sent the message and ask them not to encrypt the message, and resend it.</span></span> <span data-ttu-id="0e653-128">也可以选择**应对消息进行加密**属性。</span><span class="sxs-lookup"><span data-stu-id="0e653-128">Or you can select the **Message should be encrypted** property.</span></span>