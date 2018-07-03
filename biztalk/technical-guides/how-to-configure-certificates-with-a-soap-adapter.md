---
title: 如何使用 SOAP 适配器配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0a709ab6b28796328677e7e8ae009e3273565a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012278"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a><span data-ttu-id="a8ebf-102">如何使用 SOAP 适配器配置证书</span><span class="sxs-lookup"><span data-stu-id="a8ebf-102">How to Configure Certificates with a SOAP Adapter</span></span>
<span data-ttu-id="a8ebf-103">SOAP 发送适配器可帮助保护与接受或不需要客户端证书的服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-103">The SOAP send adapter can help secure a connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="a8ebf-104">如果指定了客户端证书，则在连接要求或接受客户端证书的服务器时，SOAP 发送适配器将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-104">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="a8ebf-105">如果未指定客户端证书和目标服务器需要客户端证书、 发件人未经过身份验证和 SOAP 发送适配器无法发送消息，并按照标准的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-105">If you do not specify a client certificate and the destination server requires client certificates, the sender is not authenticated and the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  

 <span data-ttu-id="a8ebf-106">SOAP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-106">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="a8ebf-107">SOAP 适配器根据证书的指纹来指定证书。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-107">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="a8ebf-108">如果 SOAP 发送适配器由于某种原因无法加载证书，则会挂起该适配器正在发送的消息。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-108">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  

 <span data-ttu-id="a8ebf-109">当使用 SOAP 适配器发送加密或签名邮件时，配置发送端口的客户端证书指纹 SOAP 传输属性。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-109">When using a SOAP adapter to send an encrypted or signed message, configure the Client Certificate Thumbprint SOAP transport property for the send port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="a8ebf-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="a8ebf-110">Prerequisites</span></span>  
 <span data-ttu-id="a8ebf-111">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-111">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a><span data-ttu-id="a8ebf-112">若要配置 BizTalk Server 通过 SOAP 连接发送消息</span><span class="sxs-lookup"><span data-stu-id="a8ebf-112">To configure BizTalk Server to send messages over a SOAP connection</span></span>  

1. <span data-ttu-id="a8ebf-113">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 SOAP 发送端口或打开现有的 SOAP 发送端口的属性。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a new SOAP send port or open the properties for an existing SOAP send port.</span></span>  

2. <span data-ttu-id="a8ebf-114">单击**配置**中**传输**一部分**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-114">Click **Configure** in the **Transport** section of the **Send Port Properties** dialog box.</span></span>  

3. <span data-ttu-id="a8ebf-115">上**常规**选项卡上，在**身份验证类型**，选择**Anonymous**，**基本**，**摘要**，或**NTLM**。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-115">On the **General** tab, in **Authentication type**, select **Anonymous**, **Basic**, **Digest**, or **NTLM**.</span></span>  

4. <span data-ttu-id="a8ebf-116">如果身份验证类型为**基本**或**摘要**，选择**不使用单一登录**（在这种情况下必须指定用户名和密码），或选择**使用单一登录**（在这种情况下必须选择关联应用程序）。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-116">If the authentication type is **Basic** or **Digest**, either select **Do not use Single Sign-On** (in which case you must specify the user name and password) or select **Use Single Sign-On** (in which case you must select the Affiliate Application).</span></span>  

5. <span data-ttu-id="a8ebf-117">在中**SSL 客户端证书指纹**，输入适当的指纹。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-117">In **SSL client certificate thumbprint**, enter the appropriate thumbprint.</span></span>  

6. <span data-ttu-id="a8ebf-118">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="a8ebf-118">Click **OK**, and then click **OK** again.</span></span>
