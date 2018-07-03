---
title: 使用 CertWizard 实用工具导入证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, root keys
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- CertWizard utility
- certificates, importing
- root keys
ms.assetid: 0c54d7ab-69cf-4f4a-b976-6f740a41280b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50bdce5ff094153e0aaa0e6ca69b106993722722
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993798"
---
# <a name="importing-certificates-using-the-certwizard-utility"></a><span data-ttu-id="767f9-102">使用 CertWizard 实用工具导入证书</span><span class="sxs-lookup"><span data-stu-id="767f9-102">Importing Certificates Using the CertWizard Utility</span></span>
<span data-ttu-id="767f9-103">本主题介绍如何使用 CertWizard 实用程序，在 Microsoft 中可用的分步命令行实用工具导入证书[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。</span><span class="sxs-lookup"><span data-stu-id="767f9-103">This topic describes how to import a certificate by using CertWizard utility, a step-by-step command-line utility available in the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="767f9-104">本主题说明如何导入私钥、公钥和根钥，</span><span class="sxs-lookup"><span data-stu-id="767f9-104">This topic discusses importing a private, public, or root key.</span></span> <span data-ttu-id="767f9-105">还说明了用于配置证书的开关。</span><span class="sxs-lookup"><span data-stu-id="767f9-105">It describes the switches that you use to configure the certificate.</span></span>  
  
 <span data-ttu-id="767f9-106">CertWizard 实用工具可自动执行许多必须通过使用 Microsoft 管理控制台 (MMC) 手动执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="767f9-106">The CertWizard utility automates many of the steps that you would have to do manually by using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="767f9-107">CertWizard 实用工具可执行**runas**命令，以打开 MMC 主机服务帐户。</span><span class="sxs-lookup"><span data-stu-id="767f9-107">The CertWizard utility performs the **runas** command to open MMC as the host service account.</span></span> <span data-ttu-id="767f9-108">如果不添加**Useridentity**开关，它将检测并使用主机服务帐户，提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="767f9-108">If you do not add a **Useridentity** switch, it will detect and use the host service account, prompting you for a password.</span></span> <span data-ttu-id="767f9-109">该实用工具存储并配置证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-109">It stores and configures the certificate.</span></span>  
  
 <span data-ttu-id="767f9-110">通过使用多个 CertWizard 实用工具命令创建批处理文件，可以同时导入多个证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-110">You can import multiple certificates at the same time by creating a batch file with multiple CertWizard utility commands.</span></span>  
  
### <a name="to-import-a-private-key"></a><span data-ttu-id="767f9-111">导入私钥</span><span class="sxs-lookup"><span data-stu-id="767f9-111">To import a private key</span></span>  
  
1. <span data-ttu-id="767f9-112">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="767f9-112">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="767f9-113">在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK** 。</span><span class="sxs-lookup"><span data-stu-id="767f9-113">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** .</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="767f9-114">使用 CertWizard 实用工具的帮助，请键入**CertWizard /？**</span><span class="sxs-lookup"><span data-stu-id="767f9-114">For help with the CertWizard utility, type **CertWizard /?**</span></span> <span data-ttu-id="767f9-115">在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="767f9-115">at the command prompt.</span></span>  
  
3. <span data-ttu-id="767f9-116">在命令提示符处，键入**CertWizard /Privatekey\<文件名\>.pfx**，其中\< *filename*\>.pfx 包含私有证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-116">At the command prompt, type **CertWizard /Privatekey \<filename\>.pfx**, where \<*filename*\>.pfx contains the private certificate.</span></span> <span data-ttu-id="767f9-117">若要为该文件提供密码，请追加 **/Filepassword \<filepassword\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="767f9-117">To provide the password for the file, append **/Filepassword \<filepassword\>** to the command.</span></span>  
  
4. <span data-ttu-id="767f9-118">如果你想要将证书导入 BizTalk 主机所使用的特定帐户中，追加 **/Useridentity \<useridentity\> /Password\<密码\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="767f9-118">If you want to import the certificate into a specific account used by the BizTalk Host, append **/Useridentity \<useridentity\> /Password \<password\>** to the command.</span></span>  
  
5. <span data-ttu-id="767f9-119">如果你想要指定特定的指纹，以防.pfx 文件包含多个证书，并追加 **/Thumbprint\<指纹\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="767f9-119">If you want to designate a specific thumbprint in case the .pfx file contains more than one certificate, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
6. <span data-ttu-id="767f9-120">如果你想要配置的证书的使用情况，则将追加 **/Usage**到命令，然后追加以下值之一：</span><span class="sxs-lookup"><span data-stu-id="767f9-120">If you want to configure the usage of the certificate, append **/Usage** to the command, and then append one of the following values:</span></span>  
  
   -   <span data-ttu-id="767f9-121">追加**登录**为 BizTalk 组签名证书添加证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="767f9-121">Append **sign** to add the certificate's thumbprint as the signing certificate for the BizTalk Group.</span></span> <span data-ttu-id="767f9-122">在 BizTalk 管理控制台中的 Microsoft BizTalk server （本地） 对话框的上的设置。</span><span class="sxs-lookup"><span data-stu-id="767f9-122">as set on the dialog box for Microsoft BizTalk Server (Local) in the BizTalk Administration Console.</span></span>  
  
   -   <span data-ttu-id="767f9-123">追加**解密**添加证书的指纹解密证书的 BizTalk 主机中，作为 BizTalk 管理控制台中每个主机组的属性页的证书选项卡上。</span><span class="sxs-lookup"><span data-stu-id="767f9-123">Append **decrypt** to add the certificate's thumbprint as the decryption certificate for the BizTalk Hosts, as set on the certificate tab of the property pages for each host in the BizTalk Administration Console.</span></span>  
  
   -   <span data-ttu-id="767f9-124">追加**同时**以添加该证书的指纹为这两个 BizTalk 组的签名证书和 BizTalk 主机的解密证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-124">Append **both** to add the certificate's thumbprint for both the BizTalk Group's signing certificate and the BizTalk Host's decryption certificate.</span></span>  
  
   -   <span data-ttu-id="767f9-125">追加**none**不要设置的 BizTalk 组或 BizTalk 主机配置。</span><span class="sxs-lookup"><span data-stu-id="767f9-125">Append **none** when you do not want to set the configuration for the BizTalk Group or the BizTalk Hosts.</span></span>  
  
7. <span data-ttu-id="767f9-126">如果你想要的证书配置为可导出，则将追加 **/可导出，则返回 true**。</span><span class="sxs-lookup"><span data-stu-id="767f9-126">If you want to configure the certificate as exportable, append **/Exportable true**.</span></span> <span data-ttu-id="767f9-127">若要设置为非可导出的证书，请追加 **/可导出 false**，这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="767f9-127">To set the certificate as non-exportable, append **/Exportable false**, which is the default behavior.</span></span>  
  
8. <span data-ttu-id="767f9-128">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="767f9-128">Press **Enter**.</span></span>  
  
9. <span data-ttu-id="767f9-129">如果你没有键入命令所要求的密码，该工具将提示你键入密码。</span><span class="sxs-lookup"><span data-stu-id="767f9-129">If you did not type one of the passwords required in the command, the tool prompts you for it.</span></span> <span data-ttu-id="767f9-130">键入密码，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="767f9-130">Type the password, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="767f9-131">如果该文件包含多个证书，但是你在命令中没有键入指纹，则该工具将显示出可用的指纹并提示你选择其中一个。</span><span class="sxs-lookup"><span data-stu-id="767f9-131">If the file contains multiple certificates, but you did not type a thumbprint in the command, the tool displays the available thumbprints, and prompts you to select one.</span></span> <span data-ttu-id="767f9-132">键入指纹，然后按数**Enter**。</span><span class="sxs-lookup"><span data-stu-id="767f9-132">Type the number of the thumbprint that you want, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="767f9-133">该工具将证书导入中指定的用户 \Personal\Certificates 存储 **/useridentity**切换。</span><span class="sxs-lookup"><span data-stu-id="767f9-133">The tool imports the certificate into the \Personal\Certificates store for the user specified in the **/useridentity** switch.</span></span> <span data-ttu-id="767f9-134">如果未指定用户，默认的用户将是 BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机的用户标识。</span><span class="sxs-lookup"><span data-stu-id="767f9-134">If you do not specify a user, the default user is the user identity for the BizTalkServerApplication and BizTalkServerIsolatedHost hosts.</span></span>  
  
### <a name="to-import-a-public-key"></a><span data-ttu-id="767f9-135">导入公钥</span><span class="sxs-lookup"><span data-stu-id="767f9-135">To import a public key</span></span>  
  
1. <span data-ttu-id="767f9-136">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="767f9-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="767f9-137">在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹，使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK**。</span><span class="sxs-lookup"><span data-stu-id="767f9-137">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3. <span data-ttu-id="767f9-138">在命令提示符处，键入**CertWizard /Publickey\<文件名\>.cer**，其中\< *filename*\>.cer 包含公用证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-138">At the command prompt, type **CertWizard /Publickey \<filename\>.cer**, where \<*filename*\>.cer contains the public certificate.</span></span>  
  
4. <span data-ttu-id="767f9-139">如果你想要指定.cer 或.der 文件中的证书指纹，则将追加 **/Thumbprint\<指纹\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="767f9-139">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
    <span data-ttu-id="767f9-140">该工具将证书导入“证书（本地计算机）”\“其他人”\“证书”存储区，然后设置其配置。</span><span class="sxs-lookup"><span data-stu-id="767f9-140">The tool imports the certificate into the Certificates (Local Computer)\Other People\Certificates store, and sets its configuration.</span></span>  
  
### <a name="to-import-a-root-key"></a><span data-ttu-id="767f9-141">导入根钥</span><span class="sxs-lookup"><span data-stu-id="767f9-141">To import a root key</span></span>  
  
1. <span data-ttu-id="767f9-142">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="767f9-142">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="767f9-143">在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹，使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK**。</span><span class="sxs-lookup"><span data-stu-id="767f9-143">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3. <span data-ttu-id="767f9-144">在命令提示符处，键入**CertWizard /Rootkey\<文件名\>.cer**，其中\< *filename*\>.cer 包含根证书。</span><span class="sxs-lookup"><span data-stu-id="767f9-144">At the command prompt, type **CertWizard /Rootkey \<filename\>.cer**, where \<*filename*\>.cer contains the root certificate.</span></span>  
  
4. <span data-ttu-id="767f9-145">如果你想要指定.cer 或.der 文件中的证书指纹，则将追加 **/Thumbprint\<指纹\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="767f9-145">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
    <span data-ttu-id="767f9-146">该工具将证书导入“证书（本地计算机）”\“受信任根证书授权机构”\“证书”存储区，然后设置其配置。</span><span class="sxs-lookup"><span data-stu-id="767f9-146">The tool imports the certificate into the Certificates (Local Computer)\Trusted Root Certification Authority\Certificates store, and sets its configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767f9-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="767f9-147">See Also</span></span>  
 <span data-ttu-id="767f9-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span><span class="sxs-lookup"><span data-stu-id="767f9-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span></span>  
 [<span data-ttu-id="767f9-149">管理证书</span><span class="sxs-lookup"><span data-stu-id="767f9-149">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)