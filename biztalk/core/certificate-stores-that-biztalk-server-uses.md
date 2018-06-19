---
title: BizTalk Server 使用的证书存储 |Microsoft 文档
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
ms.openlocfilehash: b142ff5b9c9007a86b09acd25f53f8c88796988c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233797"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a><span data-ttu-id="8378e-102">BizTalk Server 使用的证书存储</span><span class="sxs-lookup"><span data-stu-id="8378e-102">Certificate Stores that BizTalk Server Uses</span></span>
<span data-ttu-id="8378e-103">BizTalk Server 使用两种类型的证书存储：用于存储公钥的“其他人”证书存储和用于存储私钥的每个主机实例服务帐户的“个人”证书存储。</span><span class="sxs-lookup"><span data-stu-id="8378e-103">BizTalk Server uses two types of certificate stores, the Other People certificate store for public keys, and the Personal certificate store for each host instance service account for the private key.</span></span>  
  
 <span data-ttu-id="8378e-104">**其他人证书存储区。**</span><span class="sxs-lookup"><span data-stu-id="8378e-104">**Other People certificate store.**</span></span> <span data-ttu-id="8378e-105">公钥证书，顾名思义，是指对存储该公钥证书的计算机具有访问权限的任何人可访问的公共证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-105">Public key certificates, as their name implies, are public and accessible by anyone with access to the computer on which they are stored.</span></span> <span data-ttu-id="8378e-106">BizTalk Server 使用公钥证书对发送给特定参与方的消息进行加密，并对来自特定参与方的传入消息的数字签名进行验证。</span><span class="sxs-lookup"><span data-stu-id="8378e-106">BizTalk Server uses public key certificates to encrypt messages to specific parties and to verify the digital signatures for incoming messages from specific parties.</span></span> <span data-ttu-id="8378e-107">Windows 提供“其他人”证书存储来存储该计算机上所用的公钥证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-107">Windows provides the Other People certificate store to store the public key certificates used on the computer.</span></span> <span data-ttu-id="8378e-108">所有用户都可读取和使用此存储区中的证书，而 Windows 管理员有维护此存储区的权限。</span><span class="sxs-lookup"><span data-stu-id="8378e-108">All users can read and use the certificates in this store, and Windows administrators have permissions to maintain this store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8378e-109">在具有 BizTalk 主机实例的本地计算机上，必须将用于验证发送到远程合作伙伴的签名或加密消息的公钥证书保存在“本地计算机”\“其他人”证书存储中。</span><span class="sxs-lookup"><span data-stu-id="8378e-109">You must save the public key certificates on the Local Machine\Other People certificate store of the local computer where there is a BizTalk Host instance that is used to verify the signature or encrypt messages sent to a remote partner.</span></span>  
  
 <span data-ttu-id="8378e-110">下图显示了 BizTalk Server 用来存储公钥证书的“其他人”证书存储：</span><span class="sxs-lookup"><span data-stu-id="8378e-110">The following figure shows the Other People certificate store that BizTalk Server uses for public key certificates:</span></span>  
  
 <span data-ttu-id="8378e-111">![其他人的证书存储](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")</span><span class="sxs-lookup"><span data-stu-id="8378e-111">![Other People's Certificates Store](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")</span></span>  
  
 <span data-ttu-id="8378e-112">**个人证书存储区。**</span><span class="sxs-lookup"><span data-stu-id="8378e-112">**Personal certificate store.**</span></span> <span data-ttu-id="8378e-113">BizTalk Server 使用私钥证书来解密传入消息并对出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="8378e-113">BizTalk Server uses private key certificates to decrypt incoming messages and sign outbound messages.</span></span> <span data-ttu-id="8378e-114">启用以交互方式登录的计算机上每个 Windows 帐户已通过操作系统，仅该帐户可以访问存储的个人证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-114">Every Windows account enabled to log on interactively on a computer has a personal certificate store by the operating system, which only that account can access.</span></span> <span data-ttu-id="8378e-115">BizTalk Server 使用对应于每个主机实例服务帐户的个人证书存储来访问每个服务帐户有权访问的私钥证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-115">BizTalk Server uses the personal certificate stores for each of the host instances service accounts to access the private key certificates to which each service account has access.</span></span> <span data-ttu-id="8378e-116">只有证书存储的所有者可以访问和维护他们的个人证书存储。</span><span class="sxs-lookup"><span data-stu-id="8378e-116">Only owners of the certificate store can access and maintain their personal certificate stores.</span></span> <span data-ttu-id="8378e-117">换句话说，您必须以每个主机服务帐户的身份登录到将作为 S/MIME 解码管道宿主的每台计算机上，然后使用证书管理单元将解密证书导入个人证书存储。</span><span class="sxs-lookup"><span data-stu-id="8378e-117">In other words, you must log in into each computer that will host S/MIME decode pipelines as each host service account, and import the decryption certificate to the personal certificate store using the Certificates snap-in.</span></span>  
  
 <span data-ttu-id="8378e-118">下图显示了 BizTalk Server 用来存储私钥证书的“个人”证书存储：</span><span class="sxs-lookup"><span data-stu-id="8378e-118">The following figure shows the Personal certificate store that BizTalk Server uses for private key certificates:</span></span>  
  
 <span data-ttu-id="8378e-119">![当前用户证书存储区](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")</span><span class="sxs-lookup"><span data-stu-id="8378e-119">![Current User's Certificates Store](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8378e-120">对于运行 BizTalk 主机实例的每台计算机上的每个主机实例服务帐户，如果需要使用私钥证书进行解密或对出站消息进行签名，则私钥证书必须存储在“当前用户”\“个人”证书存储中。</span><span class="sxs-lookup"><span data-stu-id="8378e-120">The private key certificates must be stored in the Current User\Personal certificate store for each host instance service account on each computer that has a BizTalk a running host instance that requires the certificate for decryption or for signing outbound messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8378e-121">将带有私钥的证书（用于对出站消息进行签名）添加到服务帐户的个人证书存储后，还必须在 BizTalk 管理控制台中指定此签名证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-121">After you have added the certificate with the private key to the personal certificate store of the service accounts that will sign outbound messages, you must also specify this signing certificate in the BizTalk Administration console.</span></span> <span data-ttu-id="8378e-122">有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8378e-122">For more information, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8378e-123">当个人证书存储用于编程操作，例如编写导入和导出证书的脚本时，个人证书存储也称为 MY 证书存储。</span><span class="sxs-lookup"><span data-stu-id="8378e-123">The personal certificate store is also called the MY certificate store when it is used for programmatic operations, such as scripting the importing and exporting of certificates.</span></span>  
  
 <span data-ttu-id="8378e-124">下表说明了在每个 Windows 证书存储中必须安装的证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-124">The following table describes the certificates that you must install in each Windows certificate store.</span></span>  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a><span data-ttu-id="8378e-125">表 1 证书对于每个 Windows 证书存储</span><span class="sxs-lookup"><span data-stu-id="8378e-125">Table 1 Certificates for each Windows certificate store</span></span>  
  
|<span data-ttu-id="8378e-126">**证书用途**</span><span class="sxs-lookup"><span data-stu-id="8378e-126">**Certificate purpose**</span></span>|<span data-ttu-id="8378e-127">**证书类型**</span><span class="sxs-lookup"><span data-stu-id="8378e-127">**Certificate type**</span></span>|<span data-ttu-id="8378e-128">**证书存储**</span><span class="sxs-lookup"><span data-stu-id="8378e-128">**Certificate store**</span></span>|  
|-----------------------------|--------------------------|---------------------------|  
|<span data-ttu-id="8378e-129">签名</span><span class="sxs-lookup"><span data-stu-id="8378e-129">Signing</span></span>|<span data-ttu-id="8378e-130">自己的私钥</span><span class="sxs-lookup"><span data-stu-id="8378e-130">Own private key</span></span>|<span data-ttu-id="8378e-131">对于配置为对消息进行签名的 MIME/SMIME 编码器管道组件具有的发送管道的主机实例的每个服务帐户的个人存储区 (**到消息中添加签名的证书**属性设置为`True`)。</span><span class="sxs-lookup"><span data-stu-id="8378e-131">Personal store for each service account of a host instance that has a send pipeline with a MIME/SMIME Encoder pipeline component configured to sign messages (**Add Signing Cert To Message** property set to `True`).</span></span> <span data-ttu-id="8378e-132">有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8378e-132">For more information, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)</span></span>|  
|<span data-ttu-id="8378e-133">验证签名</span><span class="sxs-lookup"><span data-stu-id="8378e-133">Verifying signature</span></span>|<span data-ttu-id="8378e-134">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8378e-134">Partner's public key</span></span>|<span data-ttu-id="8378e-135">每台具有主机实例的计算机上的“其他人”存储区，该存储区的接收管道中含有 MIME/SMIME 解码器管道组件。</span><span class="sxs-lookup"><span data-stu-id="8378e-135">Other People store on each computer that has a host instance that has a receive pipeline with a MIME/SMIME Decoder pipeline component.</span></span> <span data-ttu-id="8378e-136">有关详细信息，请参阅[如何为接收签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8378e-136">For more information, see [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>|  
|<span data-ttu-id="8378e-137">解密</span><span class="sxs-lookup"><span data-stu-id="8378e-137">Decrypting</span></span>|<span data-ttu-id="8378e-138">自己的私钥</span><span class="sxs-lookup"><span data-stu-id="8378e-138">Own private key</span></span>|<span data-ttu-id="8378e-139">主机实例的每个服务帐户的“个人”存储区，该存储区的接收管道中含有 MIME/SMIME 解码器管道组件。</span><span class="sxs-lookup"><span data-stu-id="8378e-139">Personal store for each service account of a host instance that has a receive pipeline with a MIME/SMIME Decoder pipeline component.</span></span> <span data-ttu-id="8378e-140">有关详细信息，请参阅[如何为接收加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8378e-140">For more information, see [How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md).</span></span>|  
|<span data-ttu-id="8378e-141">加密</span><span class="sxs-lookup"><span data-stu-id="8378e-141">Encrypting</span></span>|<span data-ttu-id="8378e-142">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8378e-142">Partner's public key</span></span>|<span data-ttu-id="8378e-143">其他人将存储已配置为加密的消息的 MIME/SMIME 编码器管道组件具有的发送管道的主机实例的每台计算机上 (**启用加密**属性设置为`True)`。</span><span class="sxs-lookup"><span data-stu-id="8378e-143">Other People store on each computer that has a host instance that has a send pipeline with a MIME/SMIME Encoder pipeline component configured to encrypt messages (**Enable encryption** property set to `True)`.</span></span> <span data-ttu-id="8378e-144">有关详细信息，请参阅[如何为发送加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8378e-144">For more information, see [How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md).</span></span>|  
|<span data-ttu-id="8378e-145">参与方解析</span><span class="sxs-lookup"><span data-stu-id="8378e-145">Party resolution</span></span>|<span data-ttu-id="8378e-146">合作伙伴的公钥</span><span class="sxs-lookup"><span data-stu-id="8378e-146">Partner's public key</span></span>|<span data-ttu-id="8378e-147">管理计算机上的“其他人”存储区，要在其中配置参与方解析。</span><span class="sxs-lookup"><span data-stu-id="8378e-147">Other People store on the administration computer from which you are configuring party resolution.</span></span> <span data-ttu-id="8378e-148">有关详细信息，请参阅[使用证书的参与方解析](../core/using-certificates-for-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="8378e-148">For more information, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>|  
  
 <span data-ttu-id="8378e-149">下图显示了 BizTalk Server 接收消息时，需要每个证书存储中的哪些证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-149">The following figure shows what certificates you will need in each certificate store on a BizTalk Server dedicated to receiving messages.</span></span>  
  
 <span data-ttu-id="8378e-150">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="8378e-150">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
 <span data-ttu-id="8378e-151">下图显示了 BizTalk Server 发送消息时，需要每个证书存储中的哪些证书。</span><span class="sxs-lookup"><span data-stu-id="8378e-151">The following figure shows what certificates you will need in each certificate store on a BizTalk Server dedicated to sending messages.</span></span>  
  
 <span data-ttu-id="8378e-152">![将发送安全消息所需的证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="8378e-152">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
 <span data-ttu-id="8378e-153">有关 Microsoft 管理控制台 (MMC) 的证书存储和证书管理单元的详细信息，请参阅 Windows 帮助中的“证书控制台”。</span><span class="sxs-lookup"><span data-stu-id="8378e-153">For more information about the Certificate stores and the Certificate snap-in for the Microsoft Management Console (MMC), search for "Certificate console" on the Windows Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8378e-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8378e-154">See Also</span></span>  
 <span data-ttu-id="8378e-155">[BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8378e-155">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="8378e-156">[BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8378e-156">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="8378e-157">[加密和签名证书](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="8378e-157">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="8378e-158">实现消息安全性</span><span class="sxs-lookup"><span data-stu-id="8378e-158">Implementing Message Security</span></span>](../core/implementing-message-security.md)