---
title: 证书向导实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff147004773bfb620898f5e381fd242a6416f158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357563"
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="a6132-102">证书向导实用工具</span><span class="sxs-lookup"><span data-stu-id="a6132-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="a6132-103">使用 CertWizard 实用工具导入证书从.pfx 或.cer 文件到专用或公用存储区中，以用于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a6132-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a6132-104">证书向导的源代码可在**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6132-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="a6132-105">使用 64 位操作系统和版本的 BizTalk Server，它位于**C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6132-105">With a 64-bit operating system and version of BizTalk Server, it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="a6132-106">若要使用证书向导首先需要使用 Visual Studio 生成它。</span><span class="sxs-lookup"><span data-stu-id="a6132-106">To use the Certificate Wizard you will first have to build it using Visual Studio.</span></span>  
  
 <span data-ttu-id="a6132-107">CertWizard 将私钥从.pfx 文件导入到个人存储中，并将公钥从.cer 文件导入公共存储。</span><span class="sxs-lookup"><span data-stu-id="a6132-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="a6132-108">在导入私钥，证书可以是传入消息的解密证书或传出消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="a6132-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="a6132-109">**语法说明**</span><span class="sxs-lookup"><span data-stu-id="a6132-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="a6132-110">下表介绍了 CertWizard 实用工具使用的语法的每个部分。</span><span class="sxs-lookup"><span data-stu-id="a6132-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6132-111">语法</span><span class="sxs-lookup"><span data-stu-id="a6132-111">Syntax</span></span>|<span data-ttu-id="a6132-112">Description</span><span class="sxs-lookup"><span data-stu-id="a6132-112">Description</span></span>|  
|<span data-ttu-id="a6132-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="a6132-113">Privatekey</span></span>|<span data-ttu-id="a6132-114">用于导入私钥。</span><span class="sxs-lookup"><span data-stu-id="a6132-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="a6132-115">公钥</span><span class="sxs-lookup"><span data-stu-id="a6132-115">Publickey</span></span>|<span data-ttu-id="a6132-116">用于导入公钥。</span><span class="sxs-lookup"><span data-stu-id="a6132-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="a6132-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="a6132-117">Rootkey</span></span>|<span data-ttu-id="a6132-118">用于导入根钥 — 从证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="a6132-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="a6132-119">filename.pfx （或.cer）</span><span class="sxs-lookup"><span data-stu-id="a6132-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="a6132-120">.Pfx （私钥） 或.cer （公钥） 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="a6132-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="a6132-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="a6132-121">Filepassword</span></span>|<span data-ttu-id="a6132-122">若要解锁的.pfx 文件所需的密码。</span><span class="sxs-lookup"><span data-stu-id="a6132-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="a6132-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="a6132-123">Useridentity</span></span>|<span data-ttu-id="a6132-124">一个或多个 BizTalk 主机使用的服务标识。</span><span class="sxs-lookup"><span data-stu-id="a6132-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="a6132-125">如果不想指定主机，但想要导入用户帐户下的证书，请输入用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a6132-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="a6132-126">**注意：** 如果不添加 Useridentity 开关，该实用工具将导入，并为所有用户设置的证书。</span><span class="sxs-lookup"><span data-stu-id="a6132-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="a6132-127">**注意：** 如果添加 Useridentity 开关，但不要输入一个值，WMI 会自动生成的用户标识。</span><span class="sxs-lookup"><span data-stu-id="a6132-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="a6132-128">Password</span><span class="sxs-lookup"><span data-stu-id="a6132-128">Password</span></span>|<span data-ttu-id="a6132-129">服务标识用户的密码。</span><span class="sxs-lookup"><span data-stu-id="a6132-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="a6132-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="a6132-130">Thumbprint</span></span>|<span data-ttu-id="a6132-131">用例文件中的特定证书的指纹包含多个证书。</span><span class="sxs-lookup"><span data-stu-id="a6132-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="a6132-132">**注意：** 对于公共证书文件，如果该文件包含多个证书，并且不指定指纹，实用工具将导入该文件中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="a6132-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="a6132-133">对于私用证书文件，该实用工具会提示您选择要导入的证书。</span><span class="sxs-lookup"><span data-stu-id="a6132-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="a6132-134">用法</span><span class="sxs-lookup"><span data-stu-id="a6132-134">Usage</span></span>|<span data-ttu-id="a6132-135">导入私钥证书的预期使用情况。</span><span class="sxs-lookup"><span data-stu-id="a6132-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="a6132-136">可以为以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="a6132-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="a6132-137">**登录**（适用于签名证书）</span><span class="sxs-lookup"><span data-stu-id="a6132-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="a6132-138">**解密**（用于解密证书）</span><span class="sxs-lookup"><span data-stu-id="a6132-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="a6132-139">**同时**（适用于签名证书和解密证书的证书）</span><span class="sxs-lookup"><span data-stu-id="a6132-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="a6132-140">**无**（也用于签名的证书和解密证书的证书）。</span><span class="sxs-lookup"><span data-stu-id="a6132-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="a6132-141">**注意：** 如果将 /Usage 开关设置为无，该向导不会在 BizTalk 主机或 BizTalk 组上设置证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a6132-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="a6132-142">可导出</span><span class="sxs-lookup"><span data-stu-id="a6132-142">Exportable</span></span>|<span data-ttu-id="a6132-143">可以是 **，则返回 True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="a6132-143">Can be **True** or **False**.</span></span> <span data-ttu-id="a6132-144">如果 **，则返回 True**，私钥可重新导出。</span><span class="sxs-lookup"><span data-stu-id="a6132-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="a6132-145">**导入私钥的语法**</span><span class="sxs-lookup"><span data-stu-id="a6132-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="a6132-146">**导入公钥的语法**</span><span class="sxs-lookup"><span data-stu-id="a6132-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="a6132-147">**导入根钥的语法**</span><span class="sxs-lookup"><span data-stu-id="a6132-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="a6132-148">先决条件</span><span class="sxs-lookup"><span data-stu-id="a6132-148">Prerequisites</span></span>  
 <span data-ttu-id="a6132-149">以下是执行本主题中的过程的先决条件：</span><span class="sxs-lookup"><span data-stu-id="a6132-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="a6132-150">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="a6132-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="a6132-151">若要运行证书向导</span><span class="sxs-lookup"><span data-stu-id="a6132-151">To run the certificate wizard</span></span>  
  
1. <span data-ttu-id="a6132-152">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a6132-152">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="a6132-153">将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities。</span><span class="sxs-lookup"><span data-stu-id="a6132-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3. <span data-ttu-id="a6132-154">在命令提示符处，键入**CertWizard**，键入必需的和适当的开关，，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a6132-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a6132-155">如果您不要在命令提示符处提供完整的命令，CertWizard 会提示你提供所需的值。</span><span class="sxs-lookup"><span data-stu-id="a6132-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6132-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6132-156">See Also</span></span>  
 [<span data-ttu-id="a6132-157">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="a6132-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)