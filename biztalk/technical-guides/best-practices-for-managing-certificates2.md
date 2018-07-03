---
title: 用于管理 Certificates2 最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e2b79e2a0d7e4758ac87503f4bfac122c9ee215
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994782"
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="66ac2-102">管理证书的最佳实践</span><span class="sxs-lookup"><span data-stu-id="66ac2-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="66ac2-103">本部分提供有关在 Microsoft BizTalk Server 环境中管理证书的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="66ac2-103">This section provides best practices for managing certificates in your Microsoft BizTalk Server environment.</span></span>  
  
## <a name="assess-and-plan-your-use-of-certificates"></a><span data-ttu-id="66ac2-104">评估和规划证书的使用</span><span class="sxs-lookup"><span data-stu-id="66ac2-104">Assess and Plan Your Use of Certificates</span></span>  
 <span data-ttu-id="66ac2-105">**进行威胁模型分析您的环境**</span><span class="sxs-lookup"><span data-stu-id="66ac2-105">**Do a Threat Model Analysis of your environment**</span></span>  
  
- <span data-ttu-id="66ac2-106">对您的环境进行威胁模型分析可以确定签名证书和加密证书是否有助于缓解安全威胁。</span><span class="sxs-lookup"><span data-stu-id="66ac2-106">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
  <span data-ttu-id="66ac2-107">**创建与合作伙伴的公钥证书计划**</span><span class="sxs-lookup"><span data-stu-id="66ac2-107">**Create a plan for public key certificates with partners**</span></span>  
  
- <span data-ttu-id="66ac2-108">创建发送到的公钥证书和从合作伙伴接收的公钥证书的计划。</span><span class="sxs-lookup"><span data-stu-id="66ac2-108">Create a plan for sending public key certificates to and receiving public key certificates from partners.</span></span> <span data-ttu-id="66ac2-109">如果您不准备使用签名证书进行参与方解析，则公共证书可以附加到消息上，在此情况下，您无需事先在系统中复制证书。</span><span class="sxs-lookup"><span data-stu-id="66ac2-109">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
  <span data-ttu-id="66ac2-110">**指导原则与合作伙伴建立提交公钥的**</span><span class="sxs-lookup"><span data-stu-id="66ac2-110">**Establish guidelines with partners for submitting public keys**</span></span>  
  
- <span data-ttu-id="66ac2-111">在与合作伙伴达成的服务级别协议 (SLA) 中，建立提交公钥的准则以及在他们的证书即将过期或要吊销证书时通知您。</span><span class="sxs-lookup"><span data-stu-id="66ac2-111">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
## <a name="install-certificates"></a><span data-ttu-id="66ac2-112">安装证书</span><span class="sxs-lookup"><span data-stu-id="66ac2-112">Install Certificates</span></span>  
 <span data-ttu-id="66ac2-113">**在设置的时间间隔下载证书吊销列表**</span><span class="sxs-lookup"><span data-stu-id="66ac2-113">**Download the certificate revocation list at set intervals**</span></span>  
  
- <span data-ttu-id="66ac2-114">以固定的时间间隔从证书颁发机构 (CA) 下载证书吊销列表 (CRL)。</span><span class="sxs-lookup"><span data-stu-id="66ac2-114">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="66ac2-115">建议每周进行一次。</span><span class="sxs-lookup"><span data-stu-id="66ac2-115">We recommend doing this once a week.</span></span> <span data-ttu-id="66ac2-116">对于 BizTalk Server 所加入的域，如果有 CA 存在，则将自动下载 CRL。</span><span class="sxs-lookup"><span data-stu-id="66ac2-116">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
  <span data-ttu-id="66ac2-117">**验证签名证书**</span><span class="sxs-lookup"><span data-stu-id="66ac2-117">**Verify signing certificates**</span></span>  
  
- <span data-ttu-id="66ac2-118">确保根据证书吊销列表来验证签名证书。</span><span class="sxs-lookup"><span data-stu-id="66ac2-118">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="66ac2-119">有关如何验证签名证书的详细信息，请参阅[如何配置 MIME/SMIME 解码器管道组件](http://go.microsoft.com/fwlink/?LinkId=155145)(<http://go.microsoft.com/fwlink/?LinkId=155145>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="66ac2-119">For more information about how to verify the signing certificates, see [How to Configure the MIME/SMIME Decoder Pipeline Component](http://go.microsoft.com/fwlink/?LinkId=155145) (<http://go.microsoft.com/fwlink/?LinkId=155145>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  <span data-ttu-id="66ac2-120">**管理证书与合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="66ac2-120">**Manage certificates with partners**</span></span>  
  
- <span data-ttu-id="66ac2-121">将证书管理作为您的合作伙伴管理实践的一部分。</span><span class="sxs-lookup"><span data-stu-id="66ac2-121">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="66ac2-122">在 BizTalk Server 环境中添加或删除参与方时，建议您添加或删除与该合作伙伴相关联的各个证书。</span><span class="sxs-lookup"><span data-stu-id="66ac2-122">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
  <span data-ttu-id="66ac2-123">**删除主机实例前删除证书**</span><span class="sxs-lookup"><span data-stu-id="66ac2-123">**Remove certificates before removing a host instance**</span></span>  
  
- <span data-ttu-id="66ac2-124">在从 BizTalk Server 中删除主机实例前，先删除运行该主机实例的帐户的个人存储中的证书。</span><span class="sxs-lookup"><span data-stu-id="66ac2-124">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a><span data-ttu-id="66ac2-125">配置 BizTalk Server 以便使用 MIME/SMIME 证书</span><span class="sxs-lookup"><span data-stu-id="66ac2-125">Configure BizTalk Server to Use Certificates for MIME/SMIME</span></span>  
 <span data-ttu-id="66ac2-126">**避免拒绝服务攻击的数字签名**</span><span class="sxs-lookup"><span data-stu-id="66ac2-126">**Avoid denial of service attacks for digital signatures**</span></span>  
  
- <span data-ttu-id="66ac2-127">确定你想要在 BizTalk Server 无法验证数字签名时使用消息执行操作。</span><span class="sxs-lookup"><span data-stu-id="66ac2-127">Determine what you want to do with messages when BizTalk Server cannot validate the digital signature.</span></span> <span data-ttu-id="66ac2-128">设置接收端口上的身份验证属性有助于防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="66ac2-128">Setting the Authentication property on the receive port will help prevent denial of service attacks.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="66ac2-129">身份验证-删除消息和身份验证-保留消息的接收端口上的标志需要正确配置参与方解析管道组件和 BizTalk Server 中，定义参与方。</span><span class="sxs-lookup"><span data-stu-id="66ac2-129">The Authentication - Drop messages and Authentication - Keep messages flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="66ac2-130">有关详细信息，请参阅[参与方解析管道组件](http://go.microsoft.com/fwlink/?LinkId=155146)(<http://go.microsoft.com/fwlink/?LinkId=155146>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="66ac2-130">For more information, see [Party Resolution Pipeline Component](http://go.microsoft.com/fwlink/?LinkId=155146) (<http://go.microsoft.com/fwlink/?LinkId=155146>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  <span data-ttu-id="66ac2-131">**创建单独的加密和未加密消息接收位置**</span><span class="sxs-lookup"><span data-stu-id="66ac2-131">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
- <span data-ttu-id="66ac2-132">如果计划从某些合作伙伴接收 MIME 加密的消息而从其他合作伙伴接收未加密的消息，请在不同主机上为加密消息和未加密消息创建单独的接收位置。</span><span class="sxs-lookup"><span data-stu-id="66ac2-132">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="66ac2-133">要得到仅 MIME 加密的消息，请配置允许非 MIME 消息选项在解码 MIME/SMIME 管道组件中为 no。</span><span class="sxs-lookup"><span data-stu-id="66ac2-133">When you expect only MIME-encrypted messages, configure the Allow Non MIME Message option in the Decode MIME/SMIME pipeline component to No.</span></span>  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a><span data-ttu-id="66ac2-134">配置为使用证书的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="66ac2-134">Configure a BizTalk Adapter to Use Certificates</span></span>  
 <span data-ttu-id="66ac2-135">**测试与目标网站的连接**</span><span class="sxs-lookup"><span data-stu-id="66ac2-135">**Test your connection to the target Web site**</span></span>  
  
- <span data-ttu-id="66ac2-136">如果在使用 SSL，确保你可以连接到目标 Web 站点使用 Microsoft Internet Explorer® 然后再尝试连接到目标网站，使用 HTTP 或 SOAP 传输。</span><span class="sxs-lookup"><span data-stu-id="66ac2-136">If you are using SSL, ensure that you can connect to the target Web site with Microsoft Internet Explorer® before attempting to connect to the target Web site with the HTTP or SOAP transports.</span></span> <span data-ttu-id="66ac2-137">验证连接到目标网站时无对话框显示在 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="66ac2-137">Verify that no dialog boxes are displayed in Internet Explorer when you connect to the target Web site.</span></span> <span data-ttu-id="66ac2-138">BizTalk Server 已连接的任何机制与连接到目标网站时可能会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="66ac2-138">BizTalk Server has no mechanism for interfacing with any dialog boxes that might be displayed when connecting to the target web site.</span></span> <span data-ttu-id="66ac2-139">Internet Explorer 可能会显示一个对话框，如果目标网站名称不匹配的 SSL 证书中的 Web 站点为指定的名称或根证书颁发机构的 SSL 证书不在相应的受信任的根证书颁发机构存储区。</span><span class="sxs-lookup"><span data-stu-id="66ac2-139">A dialog box may be displayed by Internet Explorer if the target Web site name does not match the name specified for the Web site in the SSL certificate or if the Root Certification Authority for the SSL certificate is not in the appropriate Trusted Root Certification Authorities store.</span></span>  
  
  <span data-ttu-id="66ac2-140">**使用 SSL 诊断工具可以分析 SSL 连接问题**</span><span class="sxs-lookup"><span data-stu-id="66ac2-140">**Use the SSL Diagnostics tool to analyze SSL connection issues**</span></span>  
  
- <span data-ttu-id="66ac2-141">SSL 诊断工具是 IIS 诊断工具包的可选组件。</span><span class="sxs-lookup"><span data-stu-id="66ac2-141">The SSL Diagnostics tool is an optional component of the IIS Diagnostics Toolkit.</span></span> <span data-ttu-id="66ac2-142">您可以下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkID=64426)页 (http://go.microsoft.com/fwlink/?LinkID=64426)。</span><span class="sxs-lookup"><span data-stu-id="66ac2-142">You can download the IIS Diagnostics Toolkit from the [Internet Information Services Diagnostics Tools](http://go.microsoft.com/fwlink/?LinkID=64426) page (http://go.microsoft.com/fwlink/?LinkID=64426).</span></span>  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a><span data-ttu-id="66ac2-143">将证书从一个 BizTalk 组导出到另一个</span><span class="sxs-lookup"><span data-stu-id="66ac2-143">Exporting a Certificate from One BizTalk Group to Another</span></span>  
 <span data-ttu-id="66ac2-144">**请确保导入的证书，用于其预期目的**</span><span class="sxs-lookup"><span data-stu-id="66ac2-144">**Ensure that an imported certificate is being used for its intended purpose**</span></span>  
  
-   <span data-ttu-id="66ac2-145">如果证书导入组后，导入的证书必须符合其预期用途的使用情况属性。</span><span class="sxs-lookup"><span data-stu-id="66ac2-145">If you import a certificate into a group, the imported certificate must have a usage property that is consistent with its intended use.</span></span> <span data-ttu-id="66ac2-146">若要检查的使用情况属性，请双击中的证书**证书管理控制台**接口，然后依次**详细信息**选项卡**证书**对话框。</span><span class="sxs-lookup"><span data-stu-id="66ac2-146">To check the usage property, double-click the certificate in the **Certificates Management Console** interface, and then click the **Details** tab of the **Certificate** dialog box.</span></span> <span data-ttu-id="66ac2-147">然后单击**所有**选项**显示**下拉列表，然后单击此项可选择**密钥用法**和/或**增强型密钥用法**字段若要验证的预期的用途。</span><span class="sxs-lookup"><span data-stu-id="66ac2-147">Then click the **All** option for the **Show** drop-down list, and then click to select the **Key Usage** and/or **Enhanced Key Usage** fields to verify the intended purpose.</span></span> <span data-ttu-id="66ac2-148">如果 BizTalk Server 尝试使用超出预期用途的证书将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="66ac2-148">If BizTalk Server attempts to use a certificate for other than its intended purpose a runtime error will occur.</span></span>