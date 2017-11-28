---
title: "步骤 3： 导入公共和私有证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c910a72f3e5ef39bb2e07e410f484e8c5cbececa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="afdfe-102">步骤 3： 导入公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="afdfe-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="afdfe-103">在此步骤中，你在中创建将证书导入[步骤 2： 创建公钥和私有证书和 #91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)到 Contoso 和 Fabrikam 计算机。</span><span class="sxs-lookup"><span data-stu-id="afdfe-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="afdfe-104">每台计算机将导入自己的私用证书和对方组织的公用证书。</span><span class="sxs-lookup"><span data-stu-id="afdfe-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afdfe-105">你必须将 Fabrikam 私用证书和 Contoso 公用证书传输至 Fabrikam 计算机以导入它们。</span><span class="sxs-lookup"><span data-stu-id="afdfe-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="afdfe-106">此步骤假设你将这些证书存放在 Fabrikam 计算机的 C:\Certs 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="afdfe-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="afdfe-107">在 Contoso 计算机上导入 Contoso 私用证书</span><span class="sxs-lookup"><span data-stu-id="afdfe-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="afdfe-108">Contoso 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="afdfe-109">在命令提示符下，将移到 **\<** *驱动器***>: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK**然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-109">At the command prompt, move to **\<***drive***>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="afdfe-110">在命令提示符处，键入**CertWizard /Privatekey"\<***驱动器***>: \Certs\Contoso 私有 Encryption.pfx"**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-110">At the command prompt, type **CertWizard /Privatekey "\<***drive***>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="afdfe-111">在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="afdfe-112">在**Enter 密码标识 < contoso_machine > \HostSvc**提示，并键入 HostSvc 帐户密码，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="afdfe-113">如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。</span><span class="sxs-lookup"><span data-stu-id="afdfe-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6.  <span data-ttu-id="afdfe-114">在**此主证书将用于**提示符下，键入**D**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="afdfe-115">CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="afdfe-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7.  <span data-ttu-id="afdfe-116">重复步骤 3-6 用于指定它签名证书，通过键入 Contoso 私有 Signature.pfx 证书**S**在**此主证书将用于**在第 6 步中记下的提示。</span><span class="sxs-lookup"><span data-stu-id="afdfe-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="afdfe-117">在 Contoso 计算机上导入 Fabrikam 公用证书</span><span class="sxs-lookup"><span data-stu-id="afdfe-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="afdfe-118">Contoso 计算机上，单击**启动**，单击**运行，**类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="afdfe-119">在命令提示符下，将移到*\<驱动器 >***: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK**然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="afdfe-119">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="afdfe-120">在命令提示符处，键入**CertWizard /Publickey"***\<驱动器 >***: \Certs\Fabrikam 公共 Encryption.cer"**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-120">At the command prompt, type **CertWizard /Publickey "***\<drive>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="afdfe-121">为 Fabrikam Public Signature.cer 证书重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="afdfe-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="afdfe-122">在 Fabrikam 计算机上导入 Fabrikam 私用证书</span><span class="sxs-lookup"><span data-stu-id="afdfe-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="afdfe-123">复制以下文件从 Contoso 的计算机向\<驱动器 >: Fabrikam 计算机上的 \Certs 文件夹： Contoso 公共 Encryption.cer、 Contoso 公共 Signature.cer、 Fabrikam 私有 Encryption.pfx 和 Fabrikam 私有 Signature.pfx。</span><span class="sxs-lookup"><span data-stu-id="afdfe-123">Copy the following files from the Contoso computer to the \<drive>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="afdfe-124">Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="afdfe-125">在命令提示符下，将移到*\<驱动器 >***: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK**然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="afdfe-125">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="afdfe-126">在命令提示符处，键入**CertWizard /Privatekey"***\<驱动器 >***: \Certs\Fabrikam 私有 Encryption.pfx"**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-126">At the command prompt, type **CertWizard /Privatekey "***\<drive>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="afdfe-127">在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="afdfe-128">在**Enter 密码标识 < fabrikam_machine > \HostSvc**提示，并键入 HostSvc 帐户密码，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="afdfe-129">如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。</span><span class="sxs-lookup"><span data-stu-id="afdfe-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="afdfe-130">在**此主证书将用于**提示符下，键入**D**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="afdfe-131">CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="afdfe-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="afdfe-132">重复步骤 4-7 用于指定它签名证书，通过键入 Fabrikam 私有 Signature.pfx 证书**S**在**此主证书将用于**提示在步骤 6 中。</span><span class="sxs-lookup"><span data-stu-id="afdfe-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="afdfe-133">在 Fabrikam 计算机上导入 Contoso 公用证书</span><span class="sxs-lookup"><span data-stu-id="afdfe-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="afdfe-134">Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="afdfe-135">在命令提示符下，将移到*\<驱动器 >***: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK**然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="afdfe-135">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="afdfe-136">在命令提示符处，键入**CertWizard /Publickey"***\<驱动器 >***: \Certs\Contoso 公共 Encryption.cer"**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="afdfe-136">At the command prompt, type **CertWizard /Publickey "***\<drive>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="afdfe-137">为 Contoso Public Signature.cer 证书重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="afdfe-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdfe-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afdfe-138">See Also</span></span>  
 [<span data-ttu-id="afdfe-139">步骤 4： 启用安全套接字在 IIS 中的层</span><span class="sxs-lookup"><span data-stu-id="afdfe-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)