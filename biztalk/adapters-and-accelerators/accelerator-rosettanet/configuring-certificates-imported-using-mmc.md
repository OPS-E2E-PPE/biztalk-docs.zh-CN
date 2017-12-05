---
title: "配置证书导入使用 MMC |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d8896691557f48a8e85e67e09e35d20e1d606d0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-certificates-imported-using-mmc"></a><span data-ttu-id="43326-102">配置使用 MMC 导入的证书</span><span class="sxs-lookup"><span data-stu-id="43326-102">Configuring Certificates Imported Using MMC</span></span>
<span data-ttu-id="43326-103">使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理控制台 (MMC) 的证书管理单元导入证书后，必须对证书的使用进行配置。</span><span class="sxs-lookup"><span data-stu-id="43326-103">After you have imported certificates using the Certificates snap-in for the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC), you must configure their use.</span></span> <span data-ttu-id="43326-104">这要求配置 BizTalk 组、 BizTalk 主机和独立的主机服务帐户、 合作伙伴接口进程 (Pip)、 贸易合作伙伴协议和合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="43326-104">This requires configuring the BizTalk Group, the BizTalk Host and Isolated Host service accounts, Partner Interface Processes (PIPs), trading partner agreements, and partners.</span></span> <span data-ttu-id="43326-105">你必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="43326-105">You must perform the following steps:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43326-106">如果你使用 CertWizard 实用程序导入和配置证书，你不需要执行以下手动步骤。</span><span class="sxs-lookup"><span data-stu-id="43326-106">If you use the CertWizard utility to import and configure a certificate, you do not have to perform these manual steps.</span></span>  
  
-   <span data-ttu-id="43326-107">配置用于本组织使用签名证书。</span><span class="sxs-lookup"><span data-stu-id="43326-107">Configure the use of a signing certificate for the home organization.</span></span> <span data-ttu-id="43326-108">这意味着使用私钥来标识主组织中为传出消息。</span><span class="sxs-lookup"><span data-stu-id="43326-108">This means that you use a private key to identify the home organization in outgoing messages.</span></span> <span data-ttu-id="43326-109">若要执行此操作，请为 BizTalk 组配置签名证书。</span><span class="sxs-lookup"><span data-stu-id="43326-109">To do this, you configure the signing certificate for the BizTalk Group.</span></span>  
  
-   <span data-ttu-id="43326-110">配置用于本组织使用的解密证书。</span><span class="sxs-lookup"><span data-stu-id="43326-110">Configure the use of a decryption certificate for the home organization.</span></span> <span data-ttu-id="43326-111">这意味着使用私钥对应于合作伙伴的公共密钥，对传入消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="43326-111">This means that you use a private key, which corresponds to the partner's public key, to decrypt incoming messages.</span></span> <span data-ttu-id="43326-112">若要执行此操作，请对每个 BizTalk 主机和 BizTalk 独立主机服务帐户配置解密证书。</span><span class="sxs-lookup"><span data-stu-id="43326-112">To do this, you configure the decryption certificate for each BizTalk Host and the BizTalk Isolated Host service accounts.</span></span> <span data-ttu-id="43326-113">您必须为主机和独立主机的服务帐户输入相同的解密证书，在使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 时，必须将这些帐户设置为同样的帐户。</span><span class="sxs-lookup"><span data-stu-id="43326-113">You must enter the same decryption certificate for both the host and isolated host service accounts, which for [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] you must set to the same account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43326-114">BizTalk 主机和独立的主机必须具有相同的解密证书，以便它们可以同时解密已加密为相同的传入消息。</span><span class="sxs-lookup"><span data-stu-id="43326-114">The BizTalk Hosts and the Isolated Host must have the same decryption certificate so that they can both decrypt the same encrypted incoming messages.</span></span> <span data-ttu-id="43326-115">BizTalk 独立的主机运行 HTTP 适配器必须具有要接收的消息的证书，因为它不具有访问主机证书。</span><span class="sxs-lookup"><span data-stu-id="43326-115">The BizTalk Isolated Host that runs the HTTP adapter must have the certificate to receive the messages, because it does not have access to the Host certificate.</span></span> <span data-ttu-id="43326-116">BizTalk 主机也必须拥有该证书，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接收到消息后执行消息处理。</span><span class="sxs-lookup"><span data-stu-id="43326-116">The BizTalk Host also must have the certificate to process the messages after [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] has received them.</span></span>  
  
-   <span data-ttu-id="43326-117">配置加密和签名证书，每个伙伴。</span><span class="sxs-lookup"><span data-stu-id="43326-117">Configure encryption and signing certificates for each partner.</span></span> <span data-ttu-id="43326-118">若要执行此操作，则输入证书**常规**选项卡**合作伙伴**属性页中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="43326-118">To do this, you enter the certificates on the **General** tab of the **Partner** properties page in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="43326-119">其中包括到合作伙伴的传出消息进行加密的公钥加密证书和公钥的签名证书，以验证对传入的消息的合作伙伴的标识。</span><span class="sxs-lookup"><span data-stu-id="43326-119">These include a public-key encryption certificate to encrypt outgoing messages to a partner, and a public-key signing certificate to verify the partner's identity on incoming messages.</span></span> <span data-ttu-id="43326-120">有关详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="43326-120">For more information, see [Creating or Editing a Partner](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).</span></span>  
  
-   <span data-ttu-id="43326-121">配置本组织和贸易合作伙伴之间的加密策略。</span><span class="sxs-lookup"><span data-stu-id="43326-121">Configure the encryption policy between a home organization and a trading partner.</span></span> <span data-ttu-id="43326-122">若要执行此操作，你配置贸易合作伙伴协议上**协议**选项卡**协议属性**页面[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="43326-122">To do this, you configure the trading partner agreement on the **Protocol** tab of the **Agreement Properties** page in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="43326-123">有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="43326-123">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a><span data-ttu-id="43326-124">若要为 BizTalk 主机配置 BizTalk 组或解密证书的签名证书</span><span class="sxs-lookup"><span data-stu-id="43326-124">To configure the signing certificate for a BizTalk Group or the decryption certificate for a BizTalk Host</span></span>  
  
1.  <span data-ttu-id="43326-125">单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="43326-125">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43326-126">有关\<*承载服务*\>，键入你在安装时，在与主机服务关联的服务名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43326-126">For \<*host service*\>, type the name of the service that you associated with the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
2.  <span data-ttu-id="43326-127">键入的密码\<*承载服务*\>，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="43326-127">Type the password for \<*host service*\>, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="43326-128">单击**启动**，指向**所有程序**，指向[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="43326-128">Click **Start**, point to **All Programs**, point to [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
4.  <span data-ttu-id="43326-129">展开**证书-当前用户**，展开**个人**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="43326-129">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
5.  <span data-ttu-id="43326-130">在右窗格中，双击私有证书。</span><span class="sxs-lookup"><span data-stu-id="43326-130">In the right pane, double-click a private certificate.</span></span>  
  
6.  <span data-ttu-id="43326-131">在证书窗口上**详细信息**选项卡上，单击**指纹**，然后在显示窗口中选择的十六进制的标识号。</span><span class="sxs-lookup"><span data-stu-id="43326-131">In the Certificate window, on the **Details** tab, click **Thumbprint**, and then select the hexadecimal identification number in the display window.</span></span> <span data-ttu-id="43326-132">按 CTRL + C 将它复制。</span><span class="sxs-lookup"><span data-stu-id="43326-132">Press CTRL+C to copy it.</span></span>  
  
7.  <span data-ttu-id="43326-133">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="43326-133">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8.  <span data-ttu-id="43326-134">若要配置 BizTalk 组签名证书，右键单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="43326-134">To configure the signing certificate for a BizTalk Group, right-click **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**(Local)**, and then click **Properties**.</span></span> <span data-ttu-id="43326-135">在文本框中的右侧单击**指纹**，按 CTRL + V 粘贴到文本框中，指纹编号，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="43326-135">Click in the text box to the right of **Thumbprint**, press CTRL+V to paste the thumbprint number into the text box, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="43326-136">若要配置 BizTalk 主机解密证书，请展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，展开**主机**，右键单击你希望的主机配置，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="43326-136">To configure the decryption certificate for a BizTalk Host, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, expand **Hosts**, right-click the host that you want to configure, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="43326-137">上**证书**选项卡上，单击文本框右侧的**指纹**，按 CTRL + V 粘贴到文本框中，指纹编号，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="43326-137">On the **Certificate** tab, click in the text box to the right of **Thumbprint**, press CTRL+V to paste the thumbprint number into the text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43326-138">你必须配置 BizTalk 主机 (BizTalkServerApplication) 和 BizTalk 独立主机 (BizTalkServerIsolatedHost) 上的解密证书。</span><span class="sxs-lookup"><span data-stu-id="43326-138">You must configure the decrypting certificates on both the BizTalk Host (BizTalkServerApplication) and the BizTalk Isolated Host (BizTalkServerIsolatedHost).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43326-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43326-139">See Also</span></span>  
 [<span data-ttu-id="43326-140">管理证书</span><span class="sxs-lookup"><span data-stu-id="43326-140">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)