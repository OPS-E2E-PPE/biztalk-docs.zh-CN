---
title: 用于管理 Certificates1 最佳做法 |Microsoft Docs
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
ms.openlocfilehash: b01936259f9259335f43b39ed19b741b20bf25b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358213"
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="66520-102">管理证书的最佳实践</span><span class="sxs-lookup"><span data-stu-id="66520-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="66520-103">本部分提供有关在中管理证书的最佳做法在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="66520-103">This section provides best practices for managing certificates in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
- <span data-ttu-id="66520-104">**进行威胁模型分析您的环境**</span><span class="sxs-lookup"><span data-stu-id="66520-104">**Do a Threat Model Analysis of your environment**</span></span>  
  
   <span data-ttu-id="66520-105">进行威胁模型分析 (TMA) 的你的环境以确定是否签名或加密的证书将帮助您缓解安全威胁。</span><span class="sxs-lookup"><span data-stu-id="66520-105">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
- <span data-ttu-id="66520-106">**创建与合作伙伴的公钥证书计划**</span><span class="sxs-lookup"><span data-stu-id="66520-106">**Create a plan for public key certificates with partners**</span></span>  
  
   <span data-ttu-id="66520-107">创建用于发送和接收公钥证书与合作伙伴计划。</span><span class="sxs-lookup"><span data-stu-id="66520-107">Create a plan for sending and receiving public key certificates with partners.</span></span> <span data-ttu-id="66520-108">如果不使用签名证书进行参与方解析，公共证书可以附加到消息中，在这种情况下不需要证书的副本在系统中事先。</span><span class="sxs-lookup"><span data-stu-id="66520-108">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
- <span data-ttu-id="66520-109">**在设置的时间间隔下载证书吊销列表**</span><span class="sxs-lookup"><span data-stu-id="66520-109">**Download the certificate revocation list at set intervals**</span></span>  
  
   <span data-ttu-id="66520-110">在设置的时间间隔下载证书吊销列表 (CRL) 从证书颁发机构 (CA)。</span><span class="sxs-lookup"><span data-stu-id="66520-110">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="66520-111">我们建议执行此操作每周一次。</span><span class="sxs-lookup"><span data-stu-id="66520-111">We recommend doing this once a week.</span></span> <span data-ttu-id="66520-112">如果没有为 BizTalk server 已加入的域的 CA，将会自动下载 Crl。</span><span class="sxs-lookup"><span data-stu-id="66520-112">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
- <span data-ttu-id="66520-113">**指导原则与合作伙伴建立提交公钥的**</span><span class="sxs-lookup"><span data-stu-id="66520-113">**Establish guidelines with partners for submitting public keys**</span></span>  
  
   <span data-ttu-id="66520-114">过程与您的合作伙伴的服务级别协议 (SLA) 中，建立提交公钥，通知你证书即将过期，并吊销证书时通知您的准则。</span><span class="sxs-lookup"><span data-stu-id="66520-114">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
- <span data-ttu-id="66520-115">**验证签名证书**</span><span class="sxs-lookup"><span data-stu-id="66520-115">**Verify signing certificates**</span></span>  
  
   <span data-ttu-id="66520-116">请确保验证签名证书对证书吊销列表。</span><span class="sxs-lookup"><span data-stu-id="66520-116">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="66520-117">有关如何验证签名证书的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="66520-117">For more information about how to verify the signing certificates, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
- <span data-ttu-id="66520-118">**避免拒绝服务攻击的数字签名**</span><span class="sxs-lookup"><span data-stu-id="66520-118">**Avoid denial of service attacks for digital signatures**</span></span>  
  
   <span data-ttu-id="66520-119">确定您想如何处理消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="66520-119">Determine what you want to do with messages when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot validate the digital signature.</span></span> <span data-ttu-id="66520-120">设置**身份验证**接收端口上的属性将有助于防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="66520-120">Setting the **Authentication** property on the receive port will help prevent denial of service attacks.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="66520-121">**身份验证-删除消息**并**身份验证-保留消息**接收端口上的标志需要正确配置参与方解析管道组件和参与方是在 BizTalk Server 中定义。</span><span class="sxs-lookup"><span data-stu-id="66520-121">The **Authentication - Drop messages** and **Authentication - Keep messages** flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="66520-122">有关配置参与方解析管道组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="66520-122">For more information about configuring the Party Resolution pipeline component, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
- <span data-ttu-id="66520-123">**创建单独的加密和未加密消息接收位置**</span><span class="sxs-lookup"><span data-stu-id="66520-123">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
   <span data-ttu-id="66520-124">如果你计划从某些合作伙伴和未加密的消息从其他合作伙伴接收 MIME 加密的消息，请创建单独的加密和未加密消息的不同主机中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="66520-124">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="66520-125">要得到仅 MIME 加密的消息，请配置**允许非 MIME 消息**解码 MIME/SMIME 管道组件中的选项**否**。</span><span class="sxs-lookup"><span data-stu-id="66520-125">When you expect only MIME-encrypted messages, configure the **Allow Non MIME Message** option in the Decode MIME/SMIME pipeline component to **No**.</span></span>  
  
- <span data-ttu-id="66520-126">**管理证书与合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="66520-126">**Manage certificates with partners**</span></span>  
  
   <span data-ttu-id="66520-127">使证书管理属于您的合作伙伴管理实践。</span><span class="sxs-lookup"><span data-stu-id="66520-127">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="66520-128">当添加或删除参与方从 BizTalk Server 环境时，我们建议您添加或删除与该合作伙伴相关联的证书。</span><span class="sxs-lookup"><span data-stu-id="66520-128">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
- <span data-ttu-id="66520-129">**删除主机实例前删除证书**</span><span class="sxs-lookup"><span data-stu-id="66520-129">**Remove certificates before removing a host instance**</span></span>  
  
   <span data-ttu-id="66520-130">从 BizTalk server 中删除主机实例之前, 在其下运行的主机实例的帐户的个人存储中删除的证书。</span><span class="sxs-lookup"><span data-stu-id="66520-130">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66520-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="66520-131">See Also</span></span>  
 <span data-ttu-id="66520-132">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="66520-132">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 [<span data-ttu-id="66520-133">管理 Windows 组和用户帐户的最佳做法</span><span class="sxs-lookup"><span data-stu-id="66520-133">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)