---
title: 如何使用 HTTP 适配器配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520204a6c0f411f8f622838b846a3af41b6c60a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007094"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a><span data-ttu-id="61e79-102">如何使用 HTTP 适配器配置证书</span><span class="sxs-lookup"><span data-stu-id="61e79-102">How to Configure Certificates with an HTTP Adapter</span></span>
<span data-ttu-id="61e79-103">HTTP 发送适配器可帮助保护与接受或不需要客户端证书的服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="61e79-103">The HTTP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="61e79-104">如果指定客户端证书，则 HTTP 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。</span><span class="sxs-lookup"><span data-stu-id="61e79-104">If a client certificate is specified, the HTTP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="61e79-105">如果未指定客户端证书和目标服务器需要客户端证书，发送方未经过身份验证和 HTTP 发送适配器将无法发送消息，并遵循标准的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="61e79-105">If the client certificate is not specified and the destination server requires client certificates, the sender is not authenticated and the HTTP send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="61e79-106">HTTP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。</span><span class="sxs-lookup"><span data-stu-id="61e79-106">The HTTP send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="61e79-107">证书的指纹来指定。</span><span class="sxs-lookup"><span data-stu-id="61e79-107">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="61e79-108">如果 HTTP 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="61e79-108">If the HTTP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="61e79-109">当使用 HTTP 适配器发送加密或签名邮件时，配置 SSL 证书指纹的发送端口的 HTTP 传输属性。</span><span class="sxs-lookup"><span data-stu-id="61e79-109">When using an HTTP adapter to send an encrypted or signed message, configure the SSL certificate thumbprint HTTP transport property for the send port.</span></span> <span data-ttu-id="61e79-110">此属性中指定要用于消息身份验证的证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="61e79-110">In this property, specify the thumbprint of the certificate to use for message authentication.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="61e79-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="61e79-111">Prerequisites</span></span>  
 <span data-ttu-id="61e79-112">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="61e79-112">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a><span data-ttu-id="61e79-113">若要配置 BizTalk Server 通过 HTTP 连接发送消息</span><span class="sxs-lookup"><span data-stu-id="61e79-113">To configure BizTalk Server to send messages over an HTTP connection</span></span>  

1. <span data-ttu-id="61e79-114">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个新的 HTTP 发送端口或打开现有 HTTP 发送端口的属性。</span><span class="sxs-lookup"><span data-stu-id="61e79-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new HTTP send port or open the properties for an existing HTTP send port.</span></span>  

2. <span data-ttu-id="61e79-115">单击**配置**中的传输部分**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="61e79-115">Click **Configure** in the Transport section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="61e79-116">单击**身份验证**中**HTTP 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="61e79-116">Click **Authentication** in the **HTTP Transport Properties** dialog box.</span></span>  

4. <span data-ttu-id="61e79-117">在中**身份验证类型**，选择**Anonymous**，**基本**，**摘要**，或**Kerberos**。</span><span class="sxs-lookup"><span data-stu-id="61e79-117">In **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **Kerberos**.</span></span>  

5. <span data-ttu-id="61e79-118">如果身份验证类型为**基本**或**摘要**，选择**不使用单一登录**（在这种情况下必须指定用户名和密码），或选择**使用单一登录**（在这种情况下必须选择关联应用程序）。</span><span class="sxs-lookup"><span data-stu-id="61e79-118">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  

6. <span data-ttu-id="61e79-119">在中**SSL 客户端证书指纹**，输入适当的指纹。</span><span class="sxs-lookup"><span data-stu-id="61e79-119">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

7. <span data-ttu-id="61e79-120">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="61e79-120">Click **OK**, and then click **OK** again.</span></span>
