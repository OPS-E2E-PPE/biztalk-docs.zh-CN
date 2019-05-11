---
title: BizTalk Server 使用的证书存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public key certificates
- certificate stores, warnings
- private key certificates
- certificates, private key
- Other People stores [certificates]
- certificate stores, Personal store
- Personal store [certificates]
- certificate stores, Windows stores
- certificates, public key
- certificates, certificate stores
- certificate stores
ms.assetid: 29b65913-be3b-45d9-9865-02e52e4370f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55164b3c96bf0cc5ee5c9eac7d0d70a04b2a9d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358022"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a><span data-ttu-id="8728f-102">BizTalk Server 使用的证书存储</span><span class="sxs-lookup"><span data-stu-id="8728f-102">Certificate Stores that BizTalk Server Uses</span></span>
<span data-ttu-id="8728f-103">BizTalk Server 将专用密钥的每个主机实例服务帐户使用两种类型的证书存储、 公共密钥的其他人证书存储和个人证书存储区。</span><span class="sxs-lookup"><span data-stu-id="8728f-103">BizTalk Server uses two types of certificate stores, the Other People certificate store for public keys, and the Personal certificate store for each host instance service account for the private key.</span></span>  
  
 <span data-ttu-id="8728f-104">**其他人证书存储区。**</span><span class="sxs-lookup"><span data-stu-id="8728f-104">**Other People certificate store.**</span></span> <span data-ttu-id="8728f-105">公钥证书，正如其名，是公开的具有访问权限的任何人都在其存储他们的计算机可访问。</span><span class="sxs-lookup"><span data-stu-id="8728f-105">Public key certificates, as their name implies, are public and accessible by anyone with access to the computer on which they are stored.</span></span> <span data-ttu-id="8728f-106">BizTalk Server 使用公钥证书来加密发送给特定参与方的消息并验证来自特定参与方的传入消息的数字签名。</span><span class="sxs-lookup"><span data-stu-id="8728f-106">BizTalk Server uses public key certificates to encrypt messages to specific parties and to verify the digital signatures for incoming messages from specific parties.</span></span> <span data-ttu-id="8728f-107">Windows 提供了其他人证书存储来存储在计算机上使用的公钥证书。</span><span class="sxs-lookup"><span data-stu-id="8728f-107">Windows provides the Other People certificate store to store the public key certificates used on the computer.</span></span> <span data-ttu-id="8728f-108">所有用户可以读取和使用此存储区中的证书和 Windows 管理员有权维护此存储区。</span><span class="sxs-lookup"><span data-stu-id="8728f-108">All users can read and use the certificates in this store, and Windows administrators have permissions to maintain this store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8728f-109">必须将公钥证书保存在本地计算机 \ 其他人证书存储的本地计算机上没有用于验证签名或加密消息发送到远程合作伙伴的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="8728f-109">You must save the public key certificates on the Local Machine\Other People certificate store of the local computer where there is a BizTalk Host instance that is used to verify the signature or encrypt messages sent to a remote partner.</span></span>  
  
 <span data-ttu-id="8728f-110">下图显示了 BizTalk Server 使用的公钥证书的其他人证书存储：</span><span class="sxs-lookup"><span data-stu-id="8728f-110">The following figure shows the Other People certificate store that BizTalk Server uses for public key certificates:</span></span>  
  
 <span data-ttu-id="8728f-111">![其他人的证书存储区](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")</span><span class="sxs-lookup"><span data-stu-id="8728f-111">![Other People's Certificates Store](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")</span></span>  
  
 <span data-ttu-id="8728f-112">**个人证书存储区。**</span><span class="sxs-lookup"><span data-stu-id="8728f-112">**Personal certificate store.**</span></span> <span data-ttu-id="8728f-113">BizTalk Server 使用私钥证书来解密传入消息和出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="8728f-113">BizTalk Server uses private key certificates to decrypt incoming messages and sign outbound messages.</span></span> <span data-ttu-id="8728f-114">若要以交互方式登录的计算机上启用了每个 Windows 帐户具有通过操作系统，只有相应的帐户可以访问存储的个人证书。</span><span class="sxs-lookup"><span data-stu-id="8728f-114">Every Windows account enabled to log on interactively on a computer has a personal certificate store by the operating system, which only that account can access.</span></span> <span data-ttu-id="8728f-115">BizTalk Server 使用的个人证书存储为每个主机实例服务帐户来访问每个服务帐户有权访问的私钥证书。</span><span class="sxs-lookup"><span data-stu-id="8728f-115">BizTalk Server uses the personal certificate stores for each of the host instances service accounts to access the private key certificates to which each service account has access.</span></span> <span data-ttu-id="8728f-116">只有证书存储区的所有者可以访问和维护他们的个人证书存储。</span><span class="sxs-lookup"><span data-stu-id="8728f-116">Only owners of the certificate store can access and maintain their personal certificate stores.</span></span> <span data-ttu-id="8728f-117">换而言之，你必须登录到每台计算机，将主机 S/MIME 解码管道为每个主机服务帐户，并导入到个人证书的解密证书存储区使用证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="8728f-117">In other words, you must log in into each computer that will host S/MIME decode pipelines as each host service account, and import the decryption certificate to the personal certificate store using the Certificates snap-in.</span></span>  
  
 <span data-ttu-id="8728f-118">下图显示了 BizTalk Server 用于私钥证书的个人证书存储：</span><span class="sxs-lookup"><span data-stu-id="8728f-118">The following figure shows the Personal certificate store that BizTalk Server uses for private key certificates:</span></span>  
  
 <span data-ttu-id="8728f-119">![当前用户的证书存储](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")</span><span class="sxs-lookup"><span data-stu-id="8728f-119">![Current User's Certificates Store](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8728f-120">必须具有 BizTalk 正在运行的主机实例，需要该证书进行解密或签名出站的每台计算机上每个主机实例服务帐户的当前用户 \ 个人证书存储中存储私钥证书消息。</span><span class="sxs-lookup"><span data-stu-id="8728f-120">The private key certificates must be stored in the Current User\Personal certificate store for each host instance service account on each computer that has a BizTalk a running host instance that requires the certificate for decryption or for signing outbound messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8728f-121">你已使用私钥将证书添加到将出站消息进行签名的服务帐户的个人证书存储后，还必须在 BizTalk 管理控制台中指定此签名证书。</span><span class="sxs-lookup"><span data-stu-id="8728f-121">After you have added the certificate with the private key to the personal certificate store of the service accounts that will sign outbound messages, you must also specify this signing certificate in the BizTalk Administration console.</span></span> <span data-ttu-id="8728f-122">有关详细信息，请参阅[如何配置为发送签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8728f-122">For more information, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8728f-123">用于以编程方式操作，如脚本导入和导出证书时，个人证书存储区也被称为 MY 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="8728f-123">The personal certificate store is also called the MY certificate store when it is used for programmatic operations, such as scripting the importing and exporting of certificates.</span></span>  
  
 <span data-ttu-id="8728f-124">下表描述了必须在每个 Windows 证书存储区中安装的证书。</span><span class="sxs-lookup"><span data-stu-id="8728f-124">The following table describes the certificates that you must install in each Windows certificate store.</span></span>  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a><span data-ttu-id="8728f-125">每个 Windows 证书存储区的表 1 证书</span><span class="sxs-lookup"><span data-stu-id="8728f-125">Table 1 Certificates for each Windows certificate store</span></span>  
  
|<span data-ttu-id="8728f-126">**证书用途**</span><span class="sxs-lookup"><span data-stu-id="8728f-126">**Certificate purpose**</span></span>|<span data-ttu-id="8728f-127">**证书类型**</span><span class="sxs-lookup"><span data-stu-id="8728f-127">**Certificate type**</span></span>|<span data-ttu-id="8728f-128">**证书存储区**</span><span class="sxs-lookup"><span data-stu-id="8728f-128">**Certificate store**</span></span>|  
|-----------------------------|--------------------------|---------------------------|  
|<span data-ttu-id="8728f-129">签名</span><span class="sxs-lookup"><span data-stu-id="8728f-129">Signing</span></span>|<span data-ttu-id="8728f-130">自己的私钥</span><span class="sxs-lookup"><span data-stu-id="8728f-130">Own private key</span></span>|<span data-ttu-id="8728f-131">每个服务帐户配置为对消息进行签名的 MIME/SMIME 编码器管道组件都具有发送管道的主机实例的个人存储区 (**到消息中添加签名的证书**属性设置为`True`)。</span><span class="sxs-lookup"><span data-stu-id="8728f-131">Personal store for each service account of a host instance that has a send pipeline with a MIME/SMIME Encoder pipeline component configured to sign messages (**Add Signing Cert To Message** property set to `True`).</span></span> <span data-ttu-id="8728f-132">有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8728f-132">For more information, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)</span></span>|  
|<span data-ttu-id="8728f-133">验证签名</span><span class="sxs-lookup"><span data-stu-id="8728f-133">Verifying signature</span></span>|<span data-ttu-id="8728f-134">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8728f-134">Partner's public key</span></span>|<span data-ttu-id="8728f-135">已使用 MIME/SMIME 解码器管道组件的接收管道的主机实例的每台计算机上存储其他人。</span><span class="sxs-lookup"><span data-stu-id="8728f-135">Other People store on each computer that has a host instance that has a receive pipeline with a MIME/SMIME Decoder pipeline component.</span></span> <span data-ttu-id="8728f-136">有关详细信息，请参阅[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8728f-136">For more information, see [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>|  
|<span data-ttu-id="8728f-137">解密</span><span class="sxs-lookup"><span data-stu-id="8728f-137">Decrypting</span></span>|<span data-ttu-id="8728f-138">自己的私钥</span><span class="sxs-lookup"><span data-stu-id="8728f-138">Own private key</span></span>|<span data-ttu-id="8728f-139">使用 MIME/SMIME 解码器管道组件的接收管道的主机实例的每个服务帐户的个人存储区。</span><span class="sxs-lookup"><span data-stu-id="8728f-139">Personal store for each service account of a host instance that has a receive pipeline with a MIME/SMIME Decoder pipeline component.</span></span> <span data-ttu-id="8728f-140">有关详细信息，请参阅[如何配置为接收加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8728f-140">For more information, see [How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md).</span></span>|  
|<span data-ttu-id="8728f-141">加密</span><span class="sxs-lookup"><span data-stu-id="8728f-141">Encrypting</span></span>|<span data-ttu-id="8728f-142">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8728f-142">Partner's public key</span></span>|<span data-ttu-id="8728f-143">在已配置为对消息进行加密的 MIME/SMIME 编码器管道组件都具有发送管道的主机实例的每台计算机上存储其他人 (**启用加密**属性设置为`True)`。</span><span class="sxs-lookup"><span data-stu-id="8728f-143">Other People store on each computer that has a host instance that has a send pipeline with a MIME/SMIME Encoder pipeline component configured to encrypt messages (**Enable encryption** property set to `True)`.</span></span> <span data-ttu-id="8728f-144">有关详细信息，请参阅[如何配置为发送加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8728f-144">For more information, see [How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md).</span></span>|  
|<span data-ttu-id="8728f-145">参与方解析</span><span class="sxs-lookup"><span data-stu-id="8728f-145">Party resolution</span></span>|<span data-ttu-id="8728f-146">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8728f-146">Partner's public key</span></span>|<span data-ttu-id="8728f-147">要从其配置参与方解析在管理计算机上存储其他人。</span><span class="sxs-lookup"><span data-stu-id="8728f-147">Other People store on the administration computer from which you are configuring party resolution.</span></span> <span data-ttu-id="8728f-148">有关详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="8728f-148">For more information, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>|  
  
 <span data-ttu-id="8728f-149">下图显示了的证书，需要在每个证书存储在 BizTalk Server 专用于接收消息。</span><span class="sxs-lookup"><span data-stu-id="8728f-149">The following figure shows what certificates you will need in each certificate store on a BizTalk Server dedicated to receiving messages.</span></span>  
  
 <span data-ttu-id="8728f-150">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="8728f-150">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
 <span data-ttu-id="8728f-151">下图显示了的证书，需要在每个证书存储在 BizTalk Server 专用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="8728f-151">The following figure shows what certificates you will need in each certificate store on a BizTalk Server dedicated to sending messages.</span></span>  
  
 <span data-ttu-id="8728f-152">![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="8728f-152">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
 <span data-ttu-id="8728f-153">有关证书存储和中的 Microsoft 管理控制台 (MMC) 证书管理单元的详细信息，搜索"证书控制台"上的 Windows 帮助。</span><span class="sxs-lookup"><span data-stu-id="8728f-153">For more information about the Certificate stores and the Certificate snap-in for the Microsoft Management Console (MMC), search for "Certificate console" on the Windows Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8728f-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="8728f-154">See Also</span></span>  
 <span data-ttu-id="8728f-155">[BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8728f-155">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="8728f-156">[BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8728f-156">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="8728f-157">[加密和签名证书](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="8728f-157">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="8728f-158">实现消息安全性</span><span class="sxs-lookup"><span data-stu-id="8728f-158">Implementing Message Security</span></span>](../core/implementing-message-security.md)