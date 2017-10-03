---
title: "如何配置 BizTalk Server 接收加密的 MIME 或 SMIME 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e996ea258b8f3ab1c7df2d30ed12aa0d0150b35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a><span data-ttu-id="4e21c-102">如何配置 BizTalk Server 接收加密的 MIME 或 SMIME 消息</span><span class="sxs-lookup"><span data-stu-id="4e21c-102">How to Configure BizTalk Server to Receive Encrypted MIME or SMIME Messages</span></span>
<span data-ttu-id="4e21c-103">本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书来接收加密的 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="4e21c-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="4e21c-104">下面的过程也适用于通过 AS2 传输配置加密的消息的接收。</span><span class="sxs-lookup"><span data-stu-id="4e21c-104">The procedure below also applies to configuring the receiving of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4e21c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="4e21c-105">Prerequisites</span></span>  
 <span data-ttu-id="4e21c-106">若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="4e21c-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a><span data-ttu-id="4e21c-107">若要配置 BizTalk Server 接收加密的消息</span><span class="sxs-lookup"><span data-stu-id="4e21c-107">To configure BizTalk Server to receive encrypted messages</span></span>  
  
1.  <span data-ttu-id="4e21c-108">创建管道用于接收加密的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e21c-108">Create a pipeline to receive encrypted messages, as follows:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e21c-109">此步骤时为接收加密消息，因为 AS2Receive 和 AS2EdiReceive 管道，配置 AS2 传输中包括不需要[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]提供此函数。</span><span class="sxs-lookup"><span data-stu-id="4e21c-109">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] serve this function.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e21c-110">MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="4e21c-110">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="4e21c-111">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。</span><span class="sxs-lookup"><span data-stu-id="4e21c-111">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="4e21c-112">换言之，您不必为解密和数字签名验证创建不同的管道。</span><span class="sxs-lookup"><span data-stu-id="4e21c-112">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
    1.  <span data-ttu-id="4e21c-113">创建接收管道，然后将 MIME/SMIME 解码器管道组件拖到管道的解码阶段。</span><span class="sxs-lookup"><span data-stu-id="4e21c-113">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the pipeline.</span></span>  
  
    2.  <span data-ttu-id="4e21c-114">在**属性**窗口中，配置的 MIME/SMIME 解码器管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="4e21c-114">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e21c-115">包括配置 MIME/SMIME 解码器管道组件属性将检查吊销列表属性设置为 True，如果你想要检查证书吊销列表中的发件人将用于对发送到的消息进行签名的证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e21c-115">Configuring the MIME/SMIME Decoder pipeline component properties includes setting the Check Revocation List property to True if you want to check the certificate revocation list for the certificates that senders use for signing messages that are being sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4e21c-116">禁用此选项可提高该组件的性能。</span><span class="sxs-lookup"><span data-stu-id="4e21c-116">Disabling this option increases the performance of the component.</span></span> <span data-ttu-id="4e21c-117">与证书关联的证书吊销列表从适当的证书服务 Web 站点下载。</span><span class="sxs-lookup"><span data-stu-id="4e21c-117">The certificate revocation list associated with a certificate is downloaded from the appropriate certificate services Web site.</span></span> <span data-ttu-id="4e21c-118">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法连接到远程网站，而管道中，消息将失败。</span><span class="sxs-lookup"><span data-stu-id="4e21c-118">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot connect to the remote Web site, the message fails in the pipeline.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e21c-119">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="4e21c-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4e21c-120">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="4e21c-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
    3.  <span data-ttu-id="4e21c-121">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="4e21c-121">Build and deploy the receive pipeline.</span></span>  
  
2.  <span data-ttu-id="4e21c-122">配置接收位置用于接收加密的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e21c-122">Configure the receive location for receiving encrypted messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="4e21c-123">添加你创建包含 BizTalk 应用程序包括接收位置接收加密的消息的接收管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="4e21c-123">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e21c-124">配置用于接收加密的消息，由于 AS2Receive 和 AS2EdiReceive 管道都包括 BizTalk EDI 应用程序中的 AS2 传输时不需要此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4e21c-124">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="4e21c-125">配置你在上一步中创建接收管道的 BizTalk 应用程序中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4e21c-125">Configure the receive locations in the BizTalk application with the receive pipeline that you created in the previous step.</span></span>  
  
3.  <span data-ttu-id="4e21c-126">配置用于的主机接收处理程序为使用解密证书中，接收位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e21c-126">Configure the host used as the receive handler for the receive location with the decryption certificate, as follows:</span></span>  
  
    1.  <span data-ttu-id="4e21c-127">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击 BizTalk，它是托管的处理程序接收已加密的消息，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4e21c-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e21c-128">此过程不适用于 AS2 传输适用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4e21c-128">This procedure does not apply for AS2 transport available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4e21c-129">它适用于 BizTalk MIME 解码器不 AS2 解码器。</span><span class="sxs-lookup"><span data-stu-id="4e21c-129">It applies for the BizTalk MIME Decoder, not the AS2 Decoder.</span></span> <span data-ttu-id="4e21c-130">AS2 解码器将确定基于消息中的证书信息的证书。</span><span class="sxs-lookup"><span data-stu-id="4e21c-130">The AS2 Decoder will determine the certificate based on certificate information in the message.</span></span>  
  
    2.  <span data-ttu-id="4e21c-131">在**主机属性**对话框中，单击**证书**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="4e21c-131">In the **Host Properties** dialog box, click **Certificate**, and then click **Browse**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e21c-132">以上过程使你能够配置你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，因此，只有某些主机可以接收和处理特定消息。</span><span class="sxs-lookup"><span data-stu-id="4e21c-132">The above procedure enables you to configure your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment so that only certain hosts can receive and process particular messages.</span></span> <span data-ttu-id="4e21c-133">如果主机配置要用于消息解码和解密的证书的指纹和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为该主机的 MessageBox 数据库中创建应用程序属性。</span><span class="sxs-lookup"><span data-stu-id="4e21c-133">When you configure a host with the thumbprint of a certificate to use for message decoding and decryption, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creates an application property for that host in the MessageBox database.</span></span> <span data-ttu-id="4e21c-134">保护接收的消息和解密使用此指纹则仅传送向此服务器和配置具有此指纹的其他主机。</span><span class="sxs-lookup"><span data-stu-id="4e21c-134">Secure messages that are received and decrypted using this thumbprint are then only routed to this and other hosts that are configured with this thumbprint.</span></span>  
  
    3.  <span data-ttu-id="4e21c-135">在**选择证书**对话框中，选择安装，解密证书，然后关闭所有对话框。</span><span class="sxs-lookup"><span data-stu-id="4e21c-135">In the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e21c-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e21c-136">See Also</span></span>  
 [<span data-ttu-id="4e21c-137">为 MIME 或 SMIME 消息配置证书</span><span class="sxs-lookup"><span data-stu-id="4e21c-137">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)