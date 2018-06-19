---
title: SMTP 适配器 |Microsoft 文档
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
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277597"
---
# <a name="smtp-adapter"></a><span data-ttu-id="8d465-102">SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="8d465-102">SMTP Adapter</span></span>
<span data-ttu-id="8d465-103">使用简单邮件传输协议 (SMTP) 适配器可以通过 SMTP 协议在运行 Microsoft BizTalk Server 的服务器和其他应用程序之间交换信息。</span><span class="sxs-lookup"><span data-stu-id="8d465-103">You use the Simple Mail Transfer Protocol (SMTP) adapter to exchange information between a server running Microsoft BizTalk Server and other applications by means of the SMTP protocol.</span></span> <span data-ttu-id="8d465-104">BizTalk Server 可以通过创建电子邮件并将其发送到指定的电子邮件地址来向其他应用程序发送消息。</span><span class="sxs-lookup"><span data-stu-id="8d465-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="8d465-105">SMTP 发送适配器可在内部创建基于 SMTP 的电子邮件，并将其发送到目标电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d465-105">Internally, the SMTP send adapter creates an SMTP-based e-mail message and sends it to a target e-mail address.</span></span> <span data-ttu-id="8d465-106">目标电子邮件地址是 SMTP 适配器的一个属性。</span><span class="sxs-lookup"><span data-stu-id="8d465-106">The target e-mail address is a property of the SMTP adapter.</span></span> <span data-ttu-id="8d465-107">在您配置 SMTP 发送端口时，BizTalk 浏览器将公开此属性。</span><span class="sxs-lookup"><span data-stu-id="8d465-107">BizTalk Explorer exposes this property when you configure the SMTP send port.</span></span>  
  
 <span data-ttu-id="8d465-108">SMTP 适配器支持的通配符字符**收件人**， **FROM**， **CC**和**主题**属性，并将其解析为其实际值。</span><span class="sxs-lookup"><span data-stu-id="8d465-108">The SMTP adapter supports wildcard characters in the **TO**, **FROM**, **CC** and **SUBJECT** properties, and resolves them to their actual values.</span></span> <span data-ttu-id="8d465-109">如果中的通配符字符**收件人**， **FROM**，和**CC**属性无法解决，SMTP 传输记录错误并将消息放入挂起的队列或将该消息重定向到备份传输。</span><span class="sxs-lookup"><span data-stu-id="8d465-109">If wildcard characters in the **TO**, **FROM**, and **CC** properties cannot be resolved, the SMTP transport logs an error and puts the message into the suspended queue or redirects the message to the backup transport.</span></span> <span data-ttu-id="8d465-110">如果在中无法解析的通配符字符**主题**属性，不会发送该消息**主题**完全如下所示的属性 （例如，"消息 %messageid%") 指定的属性。</span><span class="sxs-lookup"><span data-stu-id="8d465-110">If the wildcard characters cannot be resolved in the **SUBJECT** property, the message is sent with the **SUBJECT** property specified exactly as in the property (for example, "Message %MessageID%").</span></span>  
  
 <span data-ttu-id="8d465-111">默认情况下，SMTP 消息文本为纯文本格式。</span><span class="sxs-lookup"><span data-stu-id="8d465-111">By default, the message text of SMTP messages is plain text.</span></span> <span data-ttu-id="8d465-112">若要在消息正文中使用 HTML 格式，则可以将该适配器配置为对消息文本使用 HTML 文件内容。</span><span class="sxs-lookup"><span data-stu-id="8d465-112">To use HTML in message bodies, you can configure the adapter to use the contents of an HTML file for the message text.</span></span>  
  
 <span data-ttu-id="8d465-113">有关 SMTP 安全问题的详细信息，请参阅[SMTP 适配器安全建议](../core/smtp-adapter-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="8d465-113">For more information about SMTP security issues, see [SMTP Adapter Security Recommendations](../core/smtp-adapter-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="8d465-114">SMTP 适配器仅由一个适配器组成，即发送适配器。</span><span class="sxs-lookup"><span data-stu-id="8d465-114">The SMTP adapter consists of only one adapter, a send adapter.</span></span> <span data-ttu-id="8d465-115">该发送适配器控制使用 SMTP 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="8d465-115">The send adapter controls the send ports that use the SMTP adapter.</span></span>  
  
 <span data-ttu-id="8d465-116">本主题将介绍消息通过 SMTP 发送适配器的流程。</span><span class="sxs-lookup"><span data-stu-id="8d465-116">This topic discusses the flow of a message through the SMTP send adapter.</span></span>  
  
 <span data-ttu-id="8d465-117">**SMTP 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="8d465-117">**SMTP Send Adapter**</span></span>  
  
 <span data-ttu-id="8d465-118">SMTP 发送适配器可获取来自服务器的消息，并将这些消息发布到 SMTP 服务器，该服务器可将这些消息发送给电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="8d465-118">The SMTP send adapter gets messages from the server and posts them to an SMTP server that sends them to e-mail recipients.</span></span> <span data-ttu-id="8d465-119">SMTP 发送适配器获取的消息内容可来自 BizTalk 消息对象的正文部分、指定的文件或配置适配器时在可用对话框中输入的文本。</span><span class="sxs-lookup"><span data-stu-id="8d465-119">The SMTP send adapter gets the message content from the body part of the BizTalk Message object, from a specified file, or from a text entered into a dialog box that is available when configuring the adapter.</span></span>  
  
 <span data-ttu-id="8d465-120">在 SMTP 发送适配器将消息成功发布到 SMTP 服务器之后，SMTP 发送适配器将从 MessageBox 数据库中删除该消息。</span><span class="sxs-lookup"><span data-stu-id="8d465-120">After the SMTP send adapter successfully posts a message onto the SMTP server, the SMTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="8d465-121">SMTP 发送适配器可以对通过 SMTP 发送适配器发送的消息请求送达通知和阅读回执。</span><span class="sxs-lookup"><span data-stu-id="8d465-121">The SMTP send adapter can request delivery notification and read receipts for messages sent over the SMTP send adapter.</span></span> <span data-ttu-id="8d465-122">SMTP 适配器提供的通知和读取回执的 SMTP 上指定的地址到**从**标头。</span><span class="sxs-lookup"><span data-stu-id="8d465-122">The SMTP adapter delivers the notification and read receipt to the address specified on the SMTP **From** header.</span></span>  
  
 <span data-ttu-id="8d465-123">**SMTP 服务器的身份验证**</span><span class="sxs-lookup"><span data-stu-id="8d465-123">**Authentication with SMTP Server**</span></span>  
  
 <span data-ttu-id="8d465-124">若要对 SMTP 服务器进行验证，则 SMTP 发送适配器可使用以下验证类型之一：</span><span class="sxs-lookup"><span data-stu-id="8d465-124">If you require SMTP server authentication, the SMTP send adapter uses one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="8d465-125">**基本。**</span><span class="sxs-lookup"><span data-stu-id="8d465-125">**Basic.**</span></span> <span data-ttu-id="8d465-126">SMTP 服务器使用用户提供的凭据进行验证。</span><span class="sxs-lookup"><span data-stu-id="8d465-126">The SMTP server uses user-provided credentials for authentication.</span></span>  
  
-   <span data-ttu-id="8d465-127">**进程帐户 (NTLM)。**</span><span class="sxs-lookup"><span data-stu-id="8d465-127">**Process account (NTLM).**</span></span> <span data-ttu-id="8d465-128">SMTP 服务器使用当前进程凭据进行验证。</span><span class="sxs-lookup"><span data-stu-id="8d465-128">The SMTP server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d465-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d465-129">In This Section</span></span>  
  
-   [<span data-ttu-id="8d465-130">配置 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="8d465-130">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="8d465-131">配置 SMTP 适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="8d465-131">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="8d465-132">SMTP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="8d465-132">SMTP Adapter Security Recommendations</span></span>](../core/smtp-adapter-security-recommendations.md)