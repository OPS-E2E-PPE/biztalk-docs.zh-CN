---
title: 如何使用 MSMQ 适配器配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd2e59f6e238d4af1e926ba7d85612520c402f9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253570"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a><span data-ttu-id="93d70-102">如何使用 MSMQ 适配器配置证书</span><span class="sxs-lookup"><span data-stu-id="93d70-102">How to Configure Certificates with an MSMQ Adapter</span></span>
<span data-ttu-id="93d70-103">MSMQ 发送适配器可帮助保护与接受或不需要客户端证书的服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="93d70-103">The MSMQ send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="93d70-104">如果指定客户端证书，则 MSMQ 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。</span><span class="sxs-lookup"><span data-stu-id="93d70-104">If a client certificate is specified, the MSMQ send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="93d70-105">如果未指定客户端证书和目标服务器需要客户端证书、 发件人未经过身份验证和 MSMQ 发送适配器无法发送消息，并按照标准的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="93d70-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the MSMQ send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="93d70-106">MSMQ 发送适配器使用的客户端证书所用的帐户的个人存储中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程正在运行。</span><span class="sxs-lookup"><span data-stu-id="93d70-106">The MSMQ send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="93d70-107">证书的指纹来指定。</span><span class="sxs-lookup"><span data-stu-id="93d70-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="93d70-108">如果 MSMQ 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="93d70-108">If the MSMQ send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="93d70-109">当使用 MSMQ 适配器发送加密或签名邮件时，配置发送端口的证书指纹 MSMQ 传输属性。</span><span class="sxs-lookup"><span data-stu-id="93d70-109">When using an MSMQ adapter to send an encrypted or signed message, configure the Certificate Thumbprint MSMQ transport property for the send port.</span></span> <span data-ttu-id="93d70-110">此属性中指定要用于消息身份验证的证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="93d70-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span> <span data-ttu-id="93d70-111">使用此属性结合使用身份验证属性对消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="93d70-111">Use this property in combination with the Use Authentication property to verify the message.</span></span> <span data-ttu-id="93d70-112">使用用户名和密码属性来访问队列。</span><span class="sxs-lookup"><span data-stu-id="93d70-112">Use the User Name and Password properties to gain access to queues.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="93d70-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="93d70-113">Prerequisites</span></span>  
 <span data-ttu-id="93d70-114">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="93d70-114">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a><span data-ttu-id="93d70-115">若要配置 BizTalk Server 通过 MSMQ 连接发送消息</span><span class="sxs-lookup"><span data-stu-id="93d70-115">To configure BizTalk Server to send messages over an MSMQ connection</span></span>  

1. <span data-ttu-id="93d70-116">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 MSMQ 发送端口或打开现有的 MSMQ 发送端口的属性。</span><span class="sxs-lookup"><span data-stu-id="93d70-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new MSMQ send port or open the properties for an existing MSMQ send port.</span></span>  

2. <span data-ttu-id="93d70-117">单击**配置**中**传输**一部分**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="93d70-117">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="93d70-118">在中**MSMQ 传输属性**对话框中，对于**身份验证**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="93d70-118">In the **MSMQ Transport Properties** dialog box, for **Authentication**, select **True**.</span></span>  

4. <span data-ttu-id="93d70-119">有关**证书指纹**，输入适当的指纹。</span><span class="sxs-lookup"><span data-stu-id="93d70-119">For **Certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

5. <span data-ttu-id="93d70-120">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="93d70-120">Click **OK**, and then click **OK** again.</span></span>
