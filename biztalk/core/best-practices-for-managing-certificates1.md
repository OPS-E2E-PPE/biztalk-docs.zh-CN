---
title: 用于管理 Certificates1 最佳实践 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e72d87530e5d080bd98ed55c2d29ca9554430375
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232085"
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="6075a-102">管理证书的最佳实践</span><span class="sxs-lookup"><span data-stu-id="6075a-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="6075a-103">本部分提供了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中管理证书的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6075a-103">This section provides best practices for managing certificates in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="6075a-104">**执行你环境的威胁模型分析**</span><span class="sxs-lookup"><span data-stu-id="6075a-104">**Do a Threat Model Analysis of your environment**</span></span>  
  
     <span data-ttu-id="6075a-105">对您的环境进行威胁模型分析可以确定签名证书和加密证书是否有助于缓解安全威胁。</span><span class="sxs-lookup"><span data-stu-id="6075a-105">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
-   <span data-ttu-id="6075a-106">**创建与合作伙伴公钥证书的计划**</span><span class="sxs-lookup"><span data-stu-id="6075a-106">**Create a plan for public key certificates with partners**</span></span>  
  
     <span data-ttu-id="6075a-107">与合作伙伴制定发送和接收公钥证书的计划。</span><span class="sxs-lookup"><span data-stu-id="6075a-107">Create a plan for sending and receiving public key certificates with partners.</span></span> <span data-ttu-id="6075a-108">如果您不准备使用签名证书进行参与方解析，则公共证书可以附加到消息上，在此情况下，您无需事先在系统中复制证书。</span><span class="sxs-lookup"><span data-stu-id="6075a-108">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
-   <span data-ttu-id="6075a-109">**在设置的时间间隔中下载证书吊销列表**</span><span class="sxs-lookup"><span data-stu-id="6075a-109">**Download the certificate revocation list at set intervals**</span></span>  
  
     <span data-ttu-id="6075a-110">以固定的时间间隔从证书颁发机构 (CA) 下载证书吊销列表 (CRL)。</span><span class="sxs-lookup"><span data-stu-id="6075a-110">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="6075a-111">建议每周进行一次。</span><span class="sxs-lookup"><span data-stu-id="6075a-111">We recommend doing this once a week.</span></span> <span data-ttu-id="6075a-112">对于 BizTalk Server 所加入的域，如果有 CA 存在，则将自动下载 CRL。</span><span class="sxs-lookup"><span data-stu-id="6075a-112">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
-   <span data-ttu-id="6075a-113">**用于提交公钥与合作伙伴建立准则**</span><span class="sxs-lookup"><span data-stu-id="6075a-113">**Establish guidelines with partners for submitting public keys**</span></span>  
  
     <span data-ttu-id="6075a-114">在与合作伙伴达成的服务级别协议 (SLA) 中，建立提交公钥的准则以及在他们的证书即将过期或要吊销证书时通知您。</span><span class="sxs-lookup"><span data-stu-id="6075a-114">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
-   <span data-ttu-id="6075a-115">**验证签名证书**</span><span class="sxs-lookup"><span data-stu-id="6075a-115">**Verify signing certificates**</span></span>  
  
     <span data-ttu-id="6075a-116">确保根据证书吊销列表来验证签名证书。</span><span class="sxs-lookup"><span data-stu-id="6075a-116">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="6075a-117">有关如何验证签名的证书的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="6075a-117">For more information about how to verify the signing certificates, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="6075a-118">**避免拒绝服务攻击的数字签名**</span><span class="sxs-lookup"><span data-stu-id="6075a-118">**Avoid denial of service attacks for digital signatures**</span></span>  
  
     <span data-ttu-id="6075a-119">确定在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法验证数字签名时可以对消息执行哪种操作。</span><span class="sxs-lookup"><span data-stu-id="6075a-119">Determine what you want to do with messages when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot validate the digital signature.</span></span> <span data-ttu-id="6075a-120">设置**身份验证**接收端口上的属性将有助于防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="6075a-120">Setting the **Authentication** property on the receive port will help prevent denial of service attacks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6075a-121">**身份验证-放置消息**和**身份验证-保留消息**接收端口上的标志需要参与方解析管道组件配置正确，并且双方是在 BizTalk Server 中定义。</span><span class="sxs-lookup"><span data-stu-id="6075a-121">The **Authentication - Drop messages** and **Authentication - Keep messages** flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="6075a-122">有关配置参与方解析管道组件的详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="6075a-122">For more information about configuring the Party Resolution pipeline component, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="6075a-123">**创建单独的加密和未加密消息接收位置**</span><span class="sxs-lookup"><span data-stu-id="6075a-123">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
     <span data-ttu-id="6075a-124">如果计划从某些合作伙伴接收 MIME 加密的消息而从其他合作伙伴接收未加密的消息，请在不同主机上为加密消息和未加密消息创建单独的接收位置。</span><span class="sxs-lookup"><span data-stu-id="6075a-124">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="6075a-125">当希望仅 MIME 加密的消息时，配置**允许非组成的 MIME 消息**为解码 MIME/SMIME 管道组件中的选项**否**。</span><span class="sxs-lookup"><span data-stu-id="6075a-125">When you expect only MIME-encrypted messages, configure the **Allow Non MIME Message** option in the Decode MIME/SMIME pipeline component to **No**.</span></span>  
  
-   <span data-ttu-id="6075a-126">**与合作伙伴管理证书**</span><span class="sxs-lookup"><span data-stu-id="6075a-126">**Manage certificates with partners**</span></span>  
  
     <span data-ttu-id="6075a-127">将证书管理作为您的合作伙伴管理实践的一部分。</span><span class="sxs-lookup"><span data-stu-id="6075a-127">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="6075a-128">在 BizTalk Server 环境中添加或删除参与方时，建议您添加或删除与该合作伙伴相关联的各个证书。</span><span class="sxs-lookup"><span data-stu-id="6075a-128">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
-   <span data-ttu-id="6075a-129">**在删除的主机实例之前删除证书**</span><span class="sxs-lookup"><span data-stu-id="6075a-129">**Remove certificates before removing a host instance**</span></span>  
  
     <span data-ttu-id="6075a-130">在从 BizTalk Server 中删除主机实例前，先删除运行该主机实例的帐户的个人存储中的证书。</span><span class="sxs-lookup"><span data-stu-id="6075a-130">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6075a-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6075a-131">See Also</span></span>  
 <span data-ttu-id="6075a-132">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="6075a-132">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 [<span data-ttu-id="6075a-133">管理 Windows 组和用户帐户的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6075a-133">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)