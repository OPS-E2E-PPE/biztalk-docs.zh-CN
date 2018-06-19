---
title: 配置错误。 消息签名没有 &#39; 与为此方配置的签名匹配的 t |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23214832300fe6125318ce67083f6bee0a364158
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232485"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a><span data-ttu-id="bd9a3-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-103">Configuration error.</span></span> <span data-ttu-id="bd9a3-104">消息签名没有 &#39; t 匹配此方配置的签名</span><span class="sxs-lookup"><span data-stu-id="bd9a3-104">The message signature doesn&#39;t match the signature configured for this party</span></span>
## <a name="details"></a><span data-ttu-id="bd9a3-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="bd9a3-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd9a3-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="bd9a3-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bd9a3-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="bd9a3-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bd9a3-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bd9a3-108">Event ID</span></span>|-|  
|<span data-ttu-id="bd9a3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bd9a3-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bd9a3-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="bd9a3-110"> EDI</span></span>|  
|<span data-ttu-id="bd9a3-111">组件</span><span class="sxs-lookup"><span data-stu-id="bd9a3-111">Component</span></span>|<span data-ttu-id="bd9a3-112">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="bd9a3-112">AS2 Engine</span></span>|  
|<span data-ttu-id="bd9a3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bd9a3-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="bd9a3-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="bd9a3-114">Message Text</span></span>|<span data-ttu-id="bd9a3-115">配置错误。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-115">Configuration error.</span></span> <span data-ttu-id="bd9a3-116">消息签名与为此参与方配置的签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-116">The message signature doesn't match the signature configured for this party.</span></span> <span data-ttu-id="bd9a3-117">请与发送合作伙伴联系，以验证使用的证书。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-117">Contact the sending partner and verify the certificate used.</span></span> <span data-ttu-id="bd9a3-118">AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"</span><span class="sxs-lookup"><span data-stu-id="bd9a3-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd9a3-119">解释</span><span class="sxs-lookup"><span data-stu-id="bd9a3-119">Explanation</span></span>  
 <span data-ttu-id="bd9a3-120">此错误/警告/信息事件表明 AS2 接收管道在执行 MIME 处理时无法验证签名。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-120">This Error/Warning/Information event indicates that the AS2 receive pipeline could not verify the signature when performing MIME processing.</span></span> <span data-ttu-id="bd9a3-121">这可能是由于用于处理所接收的消息的证书不是发送方用于对消息进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-121">This could result from using a different certificate to process the received message than the sender used to sign the message.</span></span> <span data-ttu-id="bd9a3-122">如果 BizTalk Server 使用错误参与方的设置来验证传入的 AS2 消息的签名，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-122">This can occur if BizTalk Server uses the settings of the wrong party to verify the signature of the incoming AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd9a3-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="bd9a3-123">User Action</span></span>  
 <span data-ttu-id="bd9a3-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="bd9a3-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="bd9a3-125">确保通过传入的 AS2 消息的参与方解析过程确定正确的参与方。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-125">Ensure that the correct party is determined by the party resolution process for the incoming AS2 message.</span></span> <span data-ttu-id="bd9a3-126">通过在 BizTalk Server 尝试在传入消息中的 AS2-From 标头和“参与方属性”对话框的“常规”页中“别名”列表的“EDIINT-AS2 起始”值之间查找匹配项时，验证是否解析了正确的参与方来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-126">Do so by verifying that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From header in the incoming message and the value for EDIINT-AS2 From in the Aliases list in the General page of the Party Properties dialog box.</span></span> <span data-ttu-id="bd9a3-127">如果没有解析参与方，请在 BizTalk Server 尝试在为传入消息设置的 AS2-From 上下文属性和参与方的名称之间查找匹配项时验证是否解析了正确的参与方。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-127">If that does not resolve the party, verify that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From context property that is set for the incoming message and the name of a party.</span></span>  
  
-   <span data-ttu-id="bd9a3-128">确保在“参与方属性”对话框的“证书”页定义的证书（存储在“本地计算机\其他人”存储区中）与用于对消息进行签名的证书相符。</span><span class="sxs-lookup"><span data-stu-id="bd9a3-128">Ensure that the certificate defined in the Certificate page of the Party Properties dialog box, and stored in the Local computer\Other People store, corresponds to the certificate used to sign the message.</span></span>