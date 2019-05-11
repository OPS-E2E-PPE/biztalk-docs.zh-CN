---
title: SMTP 适配器的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b89406529c2a112d667888a67df02e9ab9a693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314406"
---
# <a name="smtp-adapter-security-recommendations"></a><span data-ttu-id="0fedb-102">SMTP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="0fedb-102">SMTP Adapter Security Recommendations</span></span>
<span data-ttu-id="0fedb-103">SMTP 适配器用于运行 BizTalk Server 和其他应用程序通过简单邮件传输协议 (SMTP) 协议的服务器之间交换信息。</span><span class="sxs-lookup"><span data-stu-id="0fedb-103">You use the SMTP adapter to exchange information between a server running BizTalk Server and other applications by means of the Simple Mail Transfer Protocol (SMTP) protocol.</span></span> <span data-ttu-id="0fedb-104">BizTalk Server 可以通过创建一封电子邮件并将它传递到指定的电子邮件地址，对其他应用程序发送消息。</span><span class="sxs-lookup"><span data-stu-id="0fedb-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="0fedb-105">您可以使用 SMTP 适配器仅用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="0fedb-105">You can use the SMTP adapter only for sending messages.</span></span> <span data-ttu-id="0fedb-106">有关 SMTP 适配器的详细信息，请参阅[SMTP 适配器](../core/smtp-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0fedb-106">For more information about the SMTP adapter, see [SMTP Adapter](../core/smtp-adapter.md).</span></span>  
  
 <span data-ttu-id="0fedb-107">在配置为运行 SMTP 适配器的主机实例的服务帐户时，需要指定想要使用远程 SMTP 服务器的身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="0fedb-107">When you configure the service account for the host instance running the SMTP adapter, you need to specify the type of authentication you want to use with the remote SMTP server.</span></span> <span data-ttu-id="0fedb-108">如果 SMTP 服务器不要求身份验证，身份验证选项是基本身份验证 （明文）、 NTLM （通过使用当前凭据） 或 none。</span><span class="sxs-lookup"><span data-stu-id="0fedb-108">The authentication options are basic authentication (clear text), NTLM (by using current credentials), or none if authentication is not required by the SMTP server.</span></span>  
  
 <span data-ttu-id="0fedb-109">当使用 SMTP 适配器发送一条消息时，BizTalk Server 将消息以明文形式发送默认情况下。</span><span class="sxs-lookup"><span data-stu-id="0fedb-109">When you send a message by using the SMTP adapter, BizTalk Server sends the message in clear text by default.</span></span> <span data-ttu-id="0fedb-110">如果使用具有 S/MIME 编码器组件的管道，可以加密消息前将其发送到 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="0fedb-110">If you use a pipeline that has an S/MIME encoder component, you can encrypt the message before you send it to the SMTP server.</span></span> <span data-ttu-id="0fedb-111">但是，SMTP 标头是仍以明文形式。</span><span class="sxs-lookup"><span data-stu-id="0fedb-111">However, the SMTP header is still in clear text.</span></span>  
  
 <span data-ttu-id="0fedb-112">如果你想要审核的 BizTalk Server 发送的电子邮件消息，您应使用 SMTP 适配器连接到您自己的 SMTP 服务器，然后可以审核消息。</span><span class="sxs-lookup"><span data-stu-id="0fedb-112">If you want to audit the e-mail messages that BizTalk Server sends, you should use the SMTP adapter to connect to your own SMTP server, where you can then audit the messages.</span></span>  
  
 <span data-ttu-id="0fedb-113">SMTP 适配器不支持安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="0fedb-113">The SMTP adapter does not support Secure Sockets Layer (SSL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fedb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fedb-114">See Also</span></span>  
 <span data-ttu-id="0fedb-115">[用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="0fedb-115">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="0fedb-116">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="0fedb-116">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)