---
title: SMTP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d3451ab6eb6d9dc52538f5b1b9289e2cb99d7a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314490"
---
# <a name="smtp-adapter"></a><span data-ttu-id="d68f1-102">SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="d68f1-102">SMTP Adapter</span></span>
<span data-ttu-id="d68f1-103">使用简单邮件传输协议 (SMTP) 适配器运行通过 SMTP 协议的 Microsoft BizTalk Server 和其他应用程序的服务器之间交换信息。</span><span class="sxs-lookup"><span data-stu-id="d68f1-103">You use the Simple Mail Transfer Protocol (SMTP) adapter to exchange information between a server running Microsoft BizTalk Server and other applications by means of the SMTP protocol.</span></span> <span data-ttu-id="d68f1-104">BizTalk Server 可以通过创建一封电子邮件并将它传递到指定的电子邮件地址，对其他应用程序发送消息。</span><span class="sxs-lookup"><span data-stu-id="d68f1-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="d68f1-105">在内部，SMTP 发送适配器创建基于 SMTP 的电子邮件消息，并将其发送到目标电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d68f1-105">Internally, the SMTP send adapter creates an SMTP-based e-mail message and sends it to a target e-mail address.</span></span> <span data-ttu-id="d68f1-106">目标电子邮件地址是 SMTP 适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="d68f1-106">The target e-mail address is a property of the SMTP adapter.</span></span> <span data-ttu-id="d68f1-107">配置 SMTP 发送端口时，BizTalk 浏览器中公开此属性。</span><span class="sxs-lookup"><span data-stu-id="d68f1-107">BizTalk Explorer exposes this property when you configure the SMTP send port.</span></span>  
  
 <span data-ttu-id="d68f1-108">SMTP 适配器支持的通配符字符**TO**， **FROM**，**抄送**并**使用者**属性，并将它们解析为其实际值。</span><span class="sxs-lookup"><span data-stu-id="d68f1-108">The SMTP adapter supports wildcard characters in the **TO**, **FROM**, **CC** and **SUBJECT** properties, and resolves them to their actual values.</span></span> <span data-ttu-id="d68f1-109">如果中的通配符**TO**， **FROM**，并**CC**无法解析属性，SMTP 传输记录错误并将消息置于挂起队列或将该消息重定向到备份传输。</span><span class="sxs-lookup"><span data-stu-id="d68f1-109">If wildcard characters in the **TO**, **FROM**, and **CC** properties cannot be resolved, the SMTP transport logs an error and puts the message into the suspended queue or redirects the message to the backup transport.</span></span> <span data-ttu-id="d68f1-110">如果不能在中解析的通配符**使用者**属性，将消息发送与**主题**属性中指定的属性 （例如，"消息 %messageid%")。</span><span class="sxs-lookup"><span data-stu-id="d68f1-110">If the wildcard characters cannot be resolved in the **SUBJECT** property, the message is sent with the **SUBJECT** property specified exactly as in the property (for example, "Message %MessageID%").</span></span>  
  
 <span data-ttu-id="d68f1-111">默认情况下，SMTP 消息的消息文本为纯文本。</span><span class="sxs-lookup"><span data-stu-id="d68f1-111">By default, the message text of SMTP messages is plain text.</span></span> <span data-ttu-id="d68f1-112">若要在消息正文中使用 HTML，可以配置的适配器的消息文本中使用某一 HTML 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d68f1-112">To use HTML in message bodies, you can configure the adapter to use the contents of an HTML file for the message text.</span></span>  
  
 <span data-ttu-id="d68f1-113">有关 SMTP 安全问题的详细信息，请参阅[SMTP 适配器的安全建议](../core/smtp-adapter-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="d68f1-113">For more information about SMTP security issues, see [SMTP Adapter Security Recommendations](../core/smtp-adapter-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="d68f1-114">SMTP 适配器包含只有一个适配器，发送适配器。</span><span class="sxs-lookup"><span data-stu-id="d68f1-114">The SMTP adapter consists of only one adapter, a send adapter.</span></span> <span data-ttu-id="d68f1-115">发送适配器控制使用 SMTP 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="d68f1-115">The send adapter controls the send ports that use the SMTP adapter.</span></span>  
  
 <span data-ttu-id="d68f1-116">本主题讨论通过 SMTP 发送适配器消息流。</span><span class="sxs-lookup"><span data-stu-id="d68f1-116">This topic discusses the flow of a message through the SMTP send adapter.</span></span>  
  
 <span data-ttu-id="d68f1-117">**SMTP 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="d68f1-117">**SMTP Send Adapter**</span></span>  
  
 <span data-ttu-id="d68f1-118">SMTP 从服务器发送适配器获取消息，并将它们发布到 SMTP 服务器发送这些电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="d68f1-118">The SMTP send adapter gets messages from the server and posts them to an SMTP server that sends them to e-mail recipients.</span></span> <span data-ttu-id="d68f1-119">从 BizTalk 消息对象正文部分、 指定的文件，或配置适配器时是可用的对话框中输入文本，将 SMTP 发送适配器获取消息内容。</span><span class="sxs-lookup"><span data-stu-id="d68f1-119">The SMTP send adapter gets the message content from the body part of the BizTalk Message object, from a specified file, or from a text entered into a dialog box that is available when configuring the adapter.</span></span>  
  
 <span data-ttu-id="d68f1-120">SMTP 发送适配器将消息成功发布到 SMTP 服务器上后，SMTP 发送适配器从 MessageBox 数据库中删除该消息。</span><span class="sxs-lookup"><span data-stu-id="d68f1-120">After the SMTP send adapter successfully posts a message onto the SMTP server, the SMTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="d68f1-121">SMTP 发送适配器可以请求送达通知和阅读回执通过 SMTP 发送适配器发送的消息。</span><span class="sxs-lookup"><span data-stu-id="d68f1-121">The SMTP send adapter can request delivery notification and read receipts for messages sent over the SMTP send adapter.</span></span> <span data-ttu-id="d68f1-122">SMTP 适配器将通知和阅读回执传送到指定对 SMTP 地址**从**标头。</span><span class="sxs-lookup"><span data-stu-id="d68f1-122">The SMTP adapter delivers the notification and read receipt to the address specified on the SMTP **From** header.</span></span>  
  
 <span data-ttu-id="d68f1-123">**SMTP 服务器的身份验证**</span><span class="sxs-lookup"><span data-stu-id="d68f1-123">**Authentication with SMTP Server**</span></span>  
  
 <span data-ttu-id="d68f1-124">如果需要 SMTP 服务器身份验证，则 SMTP 发送适配器将使用以下身份验证类型之一：</span><span class="sxs-lookup"><span data-stu-id="d68f1-124">If you require SMTP server authentication, the SMTP send adapter uses one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="d68f1-125">**基本。**</span><span class="sxs-lookup"><span data-stu-id="d68f1-125">**Basic.**</span></span> <span data-ttu-id="d68f1-126">SMTP 服务器使用用户提供的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d68f1-126">The SMTP server uses user-provided credentials for authentication.</span></span>  
  
-   <span data-ttu-id="d68f1-127">**进程帐户 (NTLM)。**</span><span class="sxs-lookup"><span data-stu-id="d68f1-127">**Process account (NTLM).**</span></span> <span data-ttu-id="d68f1-128">SMTP 服务器使用当前进程凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d68f1-128">The SMTP server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d68f1-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="d68f1-129">In This Section</span></span>  
  
-   [<span data-ttu-id="d68f1-130">配置 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="d68f1-130">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="d68f1-131">配置 SMTP 适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="d68f1-131">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="d68f1-132">SMTP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="d68f1-132">SMTP Adapter Security Recommendations</span></span>](../core/smtp-adapter-security-recommendations.md)