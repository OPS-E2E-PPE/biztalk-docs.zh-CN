---
title: "证书向导实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3acbb1198034e76bb1e0f45c0f9755ec6ac95d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="9e068-102">证书向导实用工具</span><span class="sxs-lookup"><span data-stu-id="9e068-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="9e068-103">使用 CertWizard 实用工具可以将证书从 .pfx 或 .cer 文件导入到专用或公用存储区中，以用于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e068-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9e068-104">在找不到证书向导的源代码**C:\Program Files\Microsoft BizTalk Server\<版本 > \SDK\Utilities\Certificate 向导**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e068-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="9e068-105">与 64 位操作系统和版本[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，则将为**C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \SDK\Utilities\Certificate 向导**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e068-105">With a 64-bit operating system and version of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="9e068-106">若要使用证书向导，必须首先使用 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 来生成该向导。</span><span class="sxs-lookup"><span data-stu-id="9e068-106">To use the Certificate Wizard you will first have to build it using [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
 <span data-ttu-id="9e068-107">CertWizard 将私钥从 .pfx 文件导入到个人存储区中，将公钥从 .cer 文件导入到公用存储区中。</span><span class="sxs-lookup"><span data-stu-id="9e068-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="9e068-108">导入私钥时，证书可为传入消息的解密证书或传出消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="9e068-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="9e068-109">**语法说明**</span><span class="sxs-lookup"><span data-stu-id="9e068-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="9e068-110">下表介绍了 CertWizard 实用工具使用的语法的每个部分。</span><span class="sxs-lookup"><span data-stu-id="9e068-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e068-111">语法</span><span class="sxs-lookup"><span data-stu-id="9e068-111">Syntax</span></span>|<span data-ttu-id="9e068-112">Description</span><span class="sxs-lookup"><span data-stu-id="9e068-112">Description</span></span>|  
|<span data-ttu-id="9e068-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="9e068-113">Privatekey</span></span>|<span data-ttu-id="9e068-114">用于导入私钥。</span><span class="sxs-lookup"><span data-stu-id="9e068-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="9e068-115">Publickey</span><span class="sxs-lookup"><span data-stu-id="9e068-115">Publickey</span></span>|<span data-ttu-id="9e068-116">用于导入公钥。</span><span class="sxs-lookup"><span data-stu-id="9e068-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="9e068-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="9e068-117">Rootkey</span></span>|<span data-ttu-id="9e068-118">用于导入根钥（来自证书颁发机构）。</span><span class="sxs-lookup"><span data-stu-id="9e068-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="9e068-119">filename.pfx（或 .cer）</span><span class="sxs-lookup"><span data-stu-id="9e068-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="9e068-120">.pfx（私钥）或 .cer（公钥）文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="9e068-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="9e068-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="9e068-121">Filepassword</span></span>|<span data-ttu-id="9e068-122">对 .pfx 文件进行解锁所需的密码。</span><span class="sxs-lookup"><span data-stu-id="9e068-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="9e068-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="9e068-123">Useridentity</span></span>|<span data-ttu-id="9e068-124">一个或多个 BizTalk 主机使用的服务标识。</span><span class="sxs-lookup"><span data-stu-id="9e068-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="9e068-125">如果不想指定主机，而想以用户帐户导入证书，请输入一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9e068-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="9e068-126">**注意：**如果不希望添加用户身份交换机，该实用程序导入，并为所有用户设置的证书。</span><span class="sxs-lookup"><span data-stu-id="9e068-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="9e068-127">**注意：** WMI 如果添加用户身份开关，但未输入值时，会自动生成的用户标识。</span><span class="sxs-lookup"><span data-stu-id="9e068-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="9e068-128">密码</span><span class="sxs-lookup"><span data-stu-id="9e068-128">Password</span></span>|<span data-ttu-id="9e068-129">服务标识用户的口令。</span><span class="sxs-lookup"><span data-stu-id="9e068-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="9e068-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="9e068-130">Thumbprint</span></span>|<span data-ttu-id="9e068-131">特定证书的指纹（如果证书文件包含多个证书）。</span><span class="sxs-lookup"><span data-stu-id="9e068-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="9e068-132">**注意：**对于公共证书文件，如果该文件包含多个证书且未指定指纹，该实用程序导入文件中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="9e068-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="9e068-133">对于私用证书文件，实用工具会提示你选择要导入的证书。</span><span class="sxs-lookup"><span data-stu-id="9e068-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="9e068-134">用法</span><span class="sxs-lookup"><span data-stu-id="9e068-134">Usage</span></span>|<span data-ttu-id="9e068-135">导入的私用证书的预期用途。</span><span class="sxs-lookup"><span data-stu-id="9e068-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="9e068-136">可以为以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="9e068-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="9e068-137">**登录**（用于签名的证书）</span><span class="sxs-lookup"><span data-stu-id="9e068-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="9e068-138">**解密**（用于解密证书）</span><span class="sxs-lookup"><span data-stu-id="9e068-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="9e068-139">**同时**（用于解密证书和签名证书的证书）</span><span class="sxs-lookup"><span data-stu-id="9e068-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="9e068-140">**无**（还用于解密证书和签名证书的证书）。</span><span class="sxs-lookup"><span data-stu-id="9e068-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="9e068-141">**注意：**如果 /Usage 开关设置为 none 时，向导不会在 BizTalk 主机或 BizTalk 组上设置证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="9e068-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="9e068-142">Exportable</span><span class="sxs-lookup"><span data-stu-id="9e068-142">Exportable</span></span>|<span data-ttu-id="9e068-143">可以是**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="9e068-143">Can be **True** or **False**.</span></span> <span data-ttu-id="9e068-144">如果**True**，可以重新导出私钥。</span><span class="sxs-lookup"><span data-stu-id="9e068-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="9e068-145">**用于导入私钥的语法**</span><span class="sxs-lookup"><span data-stu-id="9e068-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="9e068-146">**导入公钥的语法**</span><span class="sxs-lookup"><span data-stu-id="9e068-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="9e068-147">**用于导入的根项的语法**</span><span class="sxs-lookup"><span data-stu-id="9e068-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="9e068-148">先决条件</span><span class="sxs-lookup"><span data-stu-id="9e068-148">Prerequisites</span></span>  
 <span data-ttu-id="9e068-149">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="9e068-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="9e068-150">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9e068-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="9e068-151">运行证书向导</span><span class="sxs-lookup"><span data-stu-id="9e068-151">To run the certificate wizard</span></span>  
  
1.  <span data-ttu-id="9e068-152">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9e068-152">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="9e068-153">移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities。</span><span class="sxs-lookup"><span data-stu-id="9e068-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3.  <span data-ttu-id="9e068-154">在命令提示符处，键入**CertWizard**，键入必选和相应的交换机，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="9e068-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e068-155">如果在命令提示符处提供的命令不完整，CertWizard 会提示你提供必需的值。</span><span class="sxs-lookup"><span data-stu-id="9e068-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e068-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e068-156">See Also</span></span>  
 [<span data-ttu-id="9e068-157">SDK 中的实用程序</span><span class="sxs-lookup"><span data-stu-id="9e068-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)