---
title: 配置错误。 消息签名不&#39;t 与为此参与方配置的签名匹配 |Microsoft Docs
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
ms.openlocfilehash: b78dc27ff21787c6b57e65a2cadb7564e080c1a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391556"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a><span data-ttu-id="6a393-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="6a393-103">Configuration error.</span></span> <span data-ttu-id="6a393-104">消息签名不&#39;t 与为此参与方配置的签名匹配</span><span class="sxs-lookup"><span data-stu-id="6a393-104">The message signature doesn&#39;t match the signature configured for this party</span></span>
## <a name="details"></a><span data-ttu-id="6a393-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a393-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a393-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a393-106">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="6a393-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a393-107">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="6a393-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a393-108">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="6a393-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6a393-109">Event Source</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6a393-110">EDI</span><span class="sxs-lookup"><span data-stu-id="6a393-110">EDI</span></span>                                                           |
|    <span data-ttu-id="6a393-111">组件</span><span class="sxs-lookup"><span data-stu-id="6a393-111">Component</span></span>    |                                                                                                 <span data-ttu-id="6a393-112">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="6a393-112">AS2 Engine</span></span>                                                                                                 |
|  <span data-ttu-id="6a393-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a393-113">Symbolic Name</span></span>  |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="6a393-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a393-114">Message Text</span></span>   | <span data-ttu-id="6a393-115">配置错误。</span><span class="sxs-lookup"><span data-stu-id="6a393-115">Configuration error.</span></span> <span data-ttu-id="6a393-116">消息签名与为此参与方配置的签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="6a393-116">The message signature doesn't match the signature configured for this party.</span></span> <span data-ttu-id="6a393-117">与发送合作伙伴联系，并验证使用的证书。</span><span class="sxs-lookup"><span data-stu-id="6a393-117">Contact the sending partner and verify the certificate used.</span></span> <span data-ttu-id="6a393-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span><span class="sxs-lookup"><span data-stu-id="6a393-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6a393-119">解释</span><span class="sxs-lookup"><span data-stu-id="6a393-119">Explanation</span></span>  
 <span data-ttu-id="6a393-120">此错误/警告/信息事件表明 AS2 接收管道无法验证签名，在执行 MIME 处理时。</span><span class="sxs-lookup"><span data-stu-id="6a393-120">This Error/Warning/Information event indicates that the AS2 receive pipeline could not verify the signature when performing MIME processing.</span></span> <span data-ttu-id="6a393-121">这可能会导致从使用不同的证书来处理不用于对消息进行签名是发送方接收的消息。</span><span class="sxs-lookup"><span data-stu-id="6a393-121">This could result from using a different certificate to process the received message than the sender used to sign the message.</span></span> <span data-ttu-id="6a393-122">如果 BizTalk Server 使用错误参与方的设置来验证传入的 AS2 消息的签名，这可能发生。</span><span class="sxs-lookup"><span data-stu-id="6a393-122">This can occur if BizTalk Server uses the settings of the wrong party to verify the signature of the incoming AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a393-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a393-123">User Action</span></span>  
 <span data-ttu-id="6a393-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="6a393-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="6a393-125">请确保正确的参与方由传入的 AS2 消息的参与方解析过程。</span><span class="sxs-lookup"><span data-stu-id="6a393-125">Ensure that the correct party is determined by the party resolution process for the incoming AS2 message.</span></span> <span data-ttu-id="6a393-126">通过验证正确的参与方解析时 BizTalk Server 尝试查找匹配项的 as2-From 标头中的传入消息和参与方属性对话框中的常规页中的别名列表中的 EDIINT-AS2 起始值。</span><span class="sxs-lookup"><span data-stu-id="6a393-126">Do so by verifying that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From header in the incoming message and the value for EDIINT-AS2 From in the Aliases list in the General page of the Party Properties dialog box.</span></span> <span data-ttu-id="6a393-127">如果没有解析参与方，验证是否正确的参与方解决在 BizTalk Server 尝试查找匹配 AS2-From 上下文属性设置为传入消息和参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="6a393-127">If that does not resolve the party, verify that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From context property that is set for the incoming message and the name of a party.</span></span>  
  
-   <span data-ttu-id="6a393-128">请确保参与方属性对话框中，在证书页中定义并存储在本地计算机 \ 其他人的存储区中的证书对应于用于对消息进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="6a393-128">Ensure that the certificate defined in the Certificate page of the Party Properties dialog box, and stored in the Local computer\Other People store, corresponds to the certificate used to sign the message.</span></span>