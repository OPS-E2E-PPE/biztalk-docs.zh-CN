---
title: "SMTP 适配器安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-security-recommendations"></a><span data-ttu-id="e6263-102">SMTP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="e6263-102">SMTP Adapter Security Recommendations</span></span>
<span data-ttu-id="e6263-103">使用 SMTP 适配器可以在运行 BizTalk Server 的服务器与其他应用程序之间通过简单邮件传输协议 (SMTP) 协议进行信息交换。</span><span class="sxs-lookup"><span data-stu-id="e6263-103">You use the SMTP adapter to exchange information between a server running BizTalk Server and other applications by means of the Simple Mail Transfer Protocol (SMTP) protocol.</span></span> <span data-ttu-id="e6263-104">BizTalk Server 可以通过创建电子邮件并将其发送到指定的电子邮件地址来向其他应用程序发送消息。</span><span class="sxs-lookup"><span data-stu-id="e6263-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="e6263-105">只能将 SMTP 适配器用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="e6263-105">You can use the SMTP adapter only for sending messages.</span></span> <span data-ttu-id="e6263-106">有关 SMTP 适配器的详细信息，请参阅[SMTP 适配器](../core/smtp-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="e6263-106">For more information about the SMTP adapter, see [SMTP Adapter](../core/smtp-adapter.md).</span></span>  
  
 <span data-ttu-id="e6263-107">在为运行 SMTP 适配器的主机实例配置服务帐户时，需要指定要对远程 SMTP 服务器使用的验证类型。</span><span class="sxs-lookup"><span data-stu-id="e6263-107">When you configure the service account for the host instance running the SMTP adapter, you need to specify the type of authentication you want to use with the remote SMTP server.</span></span> <span data-ttu-id="e6263-108">验证选项为：基本验证（明文）、NTLM（通过使用当前凭据）或无（如果 SMTP 服务器不要求验证）。</span><span class="sxs-lookup"><span data-stu-id="e6263-108">The authentication options are basic authentication (clear text), NTLM (by using current credentials), or none if authentication is not required by the SMTP server.</span></span>  
  
 <span data-ttu-id="e6263-109">在使用 SMTP 适配器发送消息时，默认情况下，BizTalk Server 将以明文形式发送消息。</span><span class="sxs-lookup"><span data-stu-id="e6263-109">When you send a message by using the SMTP adapter, BizTalk Server sends the message in clear text by default.</span></span> <span data-ttu-id="e6263-110">如果使用具有 S/MIME 编码器组件的管道，则可在将消息发送到 SMTP 服务器之前对该消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="e6263-110">If you use a pipeline that has an S/MIME encoder component, you can encrypt the message before you send it to the SMTP server.</span></span> <span data-ttu-id="e6263-111">不过，SMTP 标头仍使用明文形式。</span><span class="sxs-lookup"><span data-stu-id="e6263-111">However, the SMTP header is still in clear text.</span></span>  
  
 <span data-ttu-id="e6263-112">若要对 BizTalk Server 发送的电子邮件进行审核，则您应使用 SMTP 适配器连接到您自己的 SMTP 服务器，然后在其中对这些消息进行审核。</span><span class="sxs-lookup"><span data-stu-id="e6263-112">If you want to audit the e-mail messages that BizTalk Server sends, you should use the SMTP adapter to connect to your own SMTP server, where you can then audit the messages.</span></span>  
  
 <span data-ttu-id="e6263-113">SMTP 适配器不支持安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="e6263-113">The SMTP adapter does not support Secure Sockets Layer (SSL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6263-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6263-114">See Also</span></span>  
 <span data-ttu-id="e6263-115">[用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="e6263-115">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="e6263-116">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="e6263-116">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)