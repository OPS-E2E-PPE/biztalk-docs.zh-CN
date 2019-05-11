---
title: CertWizard | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b028deda4ef180a4983e1c58fa7a9487804a0232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284776"
---
# <a name="certwizard"></a><span data-ttu-id="f4f90-102">CertWizard</span><span class="sxs-lookup"><span data-stu-id="f4f90-102">CertWizard</span></span>
<span data-ttu-id="f4f90-103">使用 CertWizard 实用工具导入证书从.pfx 或.cer 文件到专用或公用存储区中，以用于 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f4f90-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="f4f90-104">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="f4f90-104">Location in SDK</span></span>  
 <span data-ttu-id="f4f90-105">\<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span><span class="sxs-lookup"><span data-stu-id="f4f90-105">\<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span></span>  
  
## <a name="running-certwizard"></a><span data-ttu-id="f4f90-106">运行 CertWizard</span><span class="sxs-lookup"><span data-stu-id="f4f90-106">Running CertWizard</span></span>  
  
#### <a name="to-run-certwizard"></a><span data-ttu-id="f4f90-107">若要运行 CertWizard</span><span class="sxs-lookup"><span data-stu-id="f4f90-107">To run CertWizard</span></span>  
  
1. <span data-ttu-id="f4f90-108">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f4f90-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="f4f90-109">将移动到\<*驱动器*\>\ Program Files (x86)\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="f4f90-109">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3. <span data-ttu-id="f4f90-110">在命令提示符处，键入**CertWizard**，键入必需的和适当的开关，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f4f90-110">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press ENTER.</span></span>  
  
## <a name="syntax-for-certwizard"></a><span data-ttu-id="f4f90-111">CertWizard 的语法</span><span class="sxs-lookup"><span data-stu-id="f4f90-111">Syntax for CertWizard</span></span>  
 <span data-ttu-id="f4f90-112">下面显示的语法，用于启动此命令行实用程序：</span><span class="sxs-lookup"><span data-stu-id="f4f90-112">The following shows the syntax that you use to start this command-line utility:</span></span>  
  
### <a name="syntax-for-importing-a-private-key"></a><span data-ttu-id="f4f90-113">导入私钥的语法</span><span class="sxs-lookup"><span data-stu-id="f4f90-113">Syntax for Importing a Private Key</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a><span data-ttu-id="f4f90-114">导入公钥的语法</span><span class="sxs-lookup"><span data-stu-id="f4f90-114">Syntax for Importing a Public Key</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a><span data-ttu-id="f4f90-115">导入根钥的语法</span><span class="sxs-lookup"><span data-stu-id="f4f90-115">Syntax for Importing a Root Key</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="f4f90-116">语法说明</span><span class="sxs-lookup"><span data-stu-id="f4f90-116">Syntax Description</span></span>  
 <span data-ttu-id="f4f90-117">下表介绍了 CertWizard 实用工具使用的语法的每个部分。</span><span class="sxs-lookup"><span data-stu-id="f4f90-117">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|<span data-ttu-id="f4f90-118">**语法**</span><span class="sxs-lookup"><span data-stu-id="f4f90-118">**Syntax**</span></span>|<span data-ttu-id="f4f90-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4f90-119">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="f4f90-120">**Privatekey**</span><span class="sxs-lookup"><span data-stu-id="f4f90-120">**Privatekey**</span></span>|<span data-ttu-id="f4f90-121">用于导入私钥。</span><span class="sxs-lookup"><span data-stu-id="f4f90-121">Used to import a private key.</span></span>|  
|<span data-ttu-id="f4f90-122">**Publickey**</span><span class="sxs-lookup"><span data-stu-id="f4f90-122">**Publickey**</span></span>|<span data-ttu-id="f4f90-123">用于导入公钥。</span><span class="sxs-lookup"><span data-stu-id="f4f90-123">Used to import a public key.</span></span>|  
|<span data-ttu-id="f4f90-124">**Rootkey**</span><span class="sxs-lookup"><span data-stu-id="f4f90-124">**Rootkey**</span></span>|<span data-ttu-id="f4f90-125">用于导入根钥 — 从证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="f4f90-125">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="f4f90-126">**filename.pfx （或.cer）**</span><span class="sxs-lookup"><span data-stu-id="f4f90-126">**filename.pfx (or .cer)**</span></span>|<span data-ttu-id="f4f90-127">.Pfx （私钥） 或.cer （公钥） 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f4f90-127">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="f4f90-128">**Filepassword**</span><span class="sxs-lookup"><span data-stu-id="f4f90-128">**Filepassword**</span></span>|<span data-ttu-id="f4f90-129">若要解锁的.pfx 文件所需的密码。</span><span class="sxs-lookup"><span data-stu-id="f4f90-129">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="f4f90-130">**Useridentity**</span><span class="sxs-lookup"><span data-stu-id="f4f90-130">**Useridentity**</span></span>|<span data-ttu-id="f4f90-131">一个或多个 BizTalk 主机使用的服务标识。</span><span class="sxs-lookup"><span data-stu-id="f4f90-131">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="f4f90-132">如果不想指定主机，但想要导入用户帐户下的证书，请输入用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f4f90-132">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="f4f90-133">**注意：** 如果不添加**Useridentity**切换，实用程序导入，并为所有用户设置的证书。</span><span class="sxs-lookup"><span data-stu-id="f4f90-133">**Note:**  If you do not add the **Useridentity** switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="f4f90-134">**注意：** 如果您将添加**Useridentity**开关，但不要输入一个值，WMI 会自动生成的用户标识。</span><span class="sxs-lookup"><span data-stu-id="f4f90-134">**Note:**  If you add the **Useridentity** switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="f4f90-135">**密码**</span><span class="sxs-lookup"><span data-stu-id="f4f90-135">**Password**</span></span>|<span data-ttu-id="f4f90-136">服务标识用户的密码。</span><span class="sxs-lookup"><span data-stu-id="f4f90-136">The password for the service identity user.</span></span>|  
|<span data-ttu-id="f4f90-137">**Thumbprint**</span><span class="sxs-lookup"><span data-stu-id="f4f90-137">**Thumbprint**</span></span>|<span data-ttu-id="f4f90-138">用例文件中的特定证书的指纹包含多个证书。</span><span class="sxs-lookup"><span data-stu-id="f4f90-138">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="f4f90-139">**注意：** 对于公共证书文件，如果该文件包含多个证书，并且不指定指纹，实用工具将导入该文件中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="f4f90-139">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="f4f90-140">对于私用证书文件，该实用工具会提示您选择要导入的证书。</span><span class="sxs-lookup"><span data-stu-id="f4f90-140">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="f4f90-141">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f4f90-141">**Usage**</span></span>|<span data-ttu-id="f4f90-142">导入私钥证书的预期使用情况。</span><span class="sxs-lookup"><span data-stu-id="f4f90-142">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="f4f90-143">可以为 sign （表示用作签名证书）、 decrypt （表示用作解密证书）、 both （表示为签名证书和解密证书的证书），或 none （也用于签名的证书和解密证书的证书).</span><span class="sxs-lookup"><span data-stu-id="f4f90-143">Can be sign (for a signing certificate), decrypt (for a decryption certificate), both (for a certificate that is both a signing certificate and a decryption certificate), or none (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="f4f90-144">**注意：** 如果您设置 **/Usage**切换为无，该向导将 BizTalk 主机或 BizTalk 组上设置证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="f4f90-144">**Note:**  If you set the **/Usage** switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="f4f90-145">**Exportable**</span><span class="sxs-lookup"><span data-stu-id="f4f90-145">**Exportable**</span></span>|<span data-ttu-id="f4f90-146">可以是`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="f4f90-146">Can be `True` or `False`.</span></span> <span data-ttu-id="f4f90-147">如果`True`，私钥可重新导出。</span><span class="sxs-lookup"><span data-stu-id="f4f90-147">If `True`, the private key can be re-exported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4f90-148">备注</span><span class="sxs-lookup"><span data-stu-id="f4f90-148">Remarks</span></span>  
 <span data-ttu-id="f4f90-149">CertWizard 将私钥从.pfx 文件导入到个人存储中，并将公钥从.cer 文件导入公共存储。</span><span class="sxs-lookup"><span data-stu-id="f4f90-149">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="f4f90-150">在导入私钥，证书可以是传入消息的解密证书或传出消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="f4f90-150">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="f4f90-151">如果您不要在命令提示符处提供完整的命令，CertWizard 会提示你提供所需的值。</span><span class="sxs-lookup"><span data-stu-id="f4f90-151">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f90-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4f90-152">See Also</span></span>  
 <span data-ttu-id="f4f90-153">[实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="f4f90-153">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="f4f90-154">使用 CertWizard 实用程序导入证书</span><span class="sxs-lookup"><span data-stu-id="f4f90-154">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
