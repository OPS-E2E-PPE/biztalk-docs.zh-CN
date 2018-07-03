---
title: 步骤 3： 导入公用和私用证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18074fd3b72322d79e10895214352837ccf907bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002342"
---
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="d92d1-102">步骤 3： 导入公用和私用证书</span><span class="sxs-lookup"><span data-stu-id="d92d1-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="d92d1-103">在此步骤中创建的证书导入[步骤 2： 创建公用和私用证书&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)到 Contoso 和 Fabrikam 计算机。</span><span class="sxs-lookup"><span data-stu-id="d92d1-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="d92d1-104">每台计算机将导入自己的私用证书和对方组织的公用证书。</span><span class="sxs-lookup"><span data-stu-id="d92d1-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d92d1-105">你必须将 Fabrikam 私用证书和 Contoso 公用证书传输至 Fabrikam 计算机以导入它们。</span><span class="sxs-lookup"><span data-stu-id="d92d1-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="d92d1-106">此步骤假设你将这些证书存放在 Fabrikam 计算机的 C:\Certs 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d92d1-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="d92d1-107">在 Contoso 计算机上导入 Contoso 私用证书</span><span class="sxs-lookup"><span data-stu-id="d92d1-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1. <span data-ttu-id="d92d1-108">在 Contoso 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="d92d1-109">在命令提示符处，转到**\<**<em>驱动器</em>**\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK** ，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-109">At the command prompt, move to **\<**<em>drive</em>**\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="d92d1-110">在命令提示符处，键入**CertWizard /Privatekey"\<**<em>驱动器</em>**\>: \Certs\Contoso Private Encryption.pfx"**，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-110">At the command prompt, type **CertWizard /Privatekey "\<**<em>drive</em>**\>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4. <span data-ttu-id="d92d1-111">在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5. <span data-ttu-id="d92d1-112">在**输入密码，用于标识 < contoso 计算机 > \HostSvc**提示中，键入 HostSvc 帐户密码，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d92d1-113">如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d92d1-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6. <span data-ttu-id="d92d1-114">在**此本组织证书将用于**提示符下，键入**D**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
    <span data-ttu-id="d92d1-115">CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="d92d1-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7. <span data-ttu-id="d92d1-116">重复步骤 3-6 Contoso Private Signature.pfx 证书指定它是签名证书，通过键入**S**处**此本组织证书将用于**提示符在步骤 6 中所述。</span><span class="sxs-lookup"><span data-stu-id="d92d1-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="d92d1-117">在 Contoso 计算机上导入 Fabrikam 公用证书</span><span class="sxs-lookup"><span data-stu-id="d92d1-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="d92d1-118">在 Contoso 计算机上，单击**启动**，单击**运行，请**类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d92d1-119">在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="d92d1-119">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="d92d1-120">在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Fabrikam Public Encryption.cer"**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="d92d1-120">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="d92d1-121">为 Fabrikam Public Signature.cer 证书重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="d92d1-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="d92d1-122">在 Fabrikam 计算机上导入 Fabrikam 私用证书</span><span class="sxs-lookup"><span data-stu-id="d92d1-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="d92d1-123">将以下文件从 Contoso 计算机添加到复制\<驱动器\>: Fabrikam 计算机上的 \Certs 文件夹： Contoso Public Encryption.cer、 Contoso Public Signature.cer、 Fabrikam Private Encryption.pfx 和 Fabrikam PrivateSignature.pfx。</span><span class="sxs-lookup"><span data-stu-id="d92d1-123">Copy the following files from the Contoso computer to the \<drive\>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="d92d1-124">在 Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d92d1-125">在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="d92d1-125">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="d92d1-126">在命令提示符处，键入**CertWizard /Privatekey"***\<驱动器\>***: \Certs\Fabrikam Private Encryption.pfx"**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="d92d1-126">At the command prompt, type **CertWizard /Privatekey "***\<drive\>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="d92d1-127">在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="d92d1-128">在**输入密码，用于标识 < fabrikam_machine > \HostSvc**提示中，键入 HostSvc 帐户密码，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d92d1-129">如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d92d1-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="d92d1-130">在**此本组织证书将用于**提示符下，键入**D**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="d92d1-131">CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="d92d1-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="d92d1-132">重复步骤 4-7 为 Fabrikam Private Signature.pfx 证书来指定它签名证书，通过键入**S**处**此本组织证书将用于**提示在步骤 6 中。</span><span class="sxs-lookup"><span data-stu-id="d92d1-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="d92d1-133">在 Fabrikam 计算机上导入 Contoso 公用证书</span><span class="sxs-lookup"><span data-stu-id="d92d1-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="d92d1-134">在 Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d92d1-135">在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="d92d1-135">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="d92d1-136">在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Contoso Public Encryption.cer"**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d92d1-136">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="d92d1-137">为 Contoso Public Signature.cer 证书重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="d92d1-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92d1-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="d92d1-138">See Also</span></span>  
 [<span data-ttu-id="d92d1-139">步骤 4：在 IIS 中启用安全套接字层</span><span class="sxs-lookup"><span data-stu-id="d92d1-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)