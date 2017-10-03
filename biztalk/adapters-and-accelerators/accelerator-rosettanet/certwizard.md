---
title: "CertWizard |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d9daf4ea1ea996680088c7a7a1333e9d26906b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="certwizard"></a><span data-ttu-id="51132-102">CertWizard</span><span class="sxs-lookup"><span data-stu-id="51132-102">CertWizard</span></span>
<span data-ttu-id="51132-103">CertWizard 实用程序用于从.pfx 或.cer 文件的证书导入到的与一起使用的私有或公用存储区[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51132-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="51132-104">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="51132-104">Location in SDK</span></span>  
 <span data-ttu-id="51132-105">\<*驱动器*> \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\ 快捷键</span><span class="sxs-lookup"><span data-stu-id="51132-105">\<*drive*>\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\\</span></span>  
  
## <a name="running-certwizard"></a><span data-ttu-id="51132-106">运行 CertWizard</span><span class="sxs-lookup"><span data-stu-id="51132-106">Running CertWizard</span></span>  
  
#### <a name="to-run-certwizard"></a><span data-ttu-id="51132-107">运行 CertWizard</span><span class="sxs-lookup"><span data-stu-id="51132-107">To run CertWizard</span></span>  
  
1.  <span data-ttu-id="51132-108">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="51132-108">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="51132-109">将移动到\<*驱动器*> \ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="51132-109">Move to \<*drive*>\ Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="51132-110">在命令提示符处，键入**CertWizard**，键入必选和相应的交换机，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="51132-110">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press ENTER.</span></span>  
  
## <a name="syntax-for-certwizard"></a><span data-ttu-id="51132-111">CertWizard 的语法</span><span class="sxs-lookup"><span data-stu-id="51132-111">Syntax for CertWizard</span></span>  
 <span data-ttu-id="51132-112">下面给出了用于启动此命令行实用工具的语法：</span><span class="sxs-lookup"><span data-stu-id="51132-112">The following shows the syntax that you use to start this command-line utility:</span></span>  
  
### <a name="syntax-for-importing-a-private-key"></a><span data-ttu-id="51132-113">导入私钥的语法</span><span class="sxs-lookup"><span data-stu-id="51132-113">Syntax for Importing a Private Key</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a><span data-ttu-id="51132-114">导入公钥的语法</span><span class="sxs-lookup"><span data-stu-id="51132-114">Syntax for Importing a Public Key</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a><span data-ttu-id="51132-115">导入根钥的语法</span><span class="sxs-lookup"><span data-stu-id="51132-115">Syntax for Importing a Root Key</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="51132-116">语法说明</span><span class="sxs-lookup"><span data-stu-id="51132-116">Syntax Description</span></span>  
 <span data-ttu-id="51132-117">下表介绍了 CertWizard 实用工具使用的语法的每个部分。</span><span class="sxs-lookup"><span data-stu-id="51132-117">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|<span data-ttu-id="51132-118">**语法**</span><span class="sxs-lookup"><span data-stu-id="51132-118">**Syntax**</span></span>|<span data-ttu-id="51132-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="51132-119">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="51132-120">**Privatekey**</span><span class="sxs-lookup"><span data-stu-id="51132-120">**Privatekey**</span></span>|<span data-ttu-id="51132-121">用于导入私钥。</span><span class="sxs-lookup"><span data-stu-id="51132-121">Used to import a private key.</span></span>|  
|<span data-ttu-id="51132-122">**Publickey**</span><span class="sxs-lookup"><span data-stu-id="51132-122">**Publickey**</span></span>|<span data-ttu-id="51132-123">用于导入公钥。</span><span class="sxs-lookup"><span data-stu-id="51132-123">Used to import a public key.</span></span>|  
|<span data-ttu-id="51132-124">**根主键**</span><span class="sxs-lookup"><span data-stu-id="51132-124">**Rootkey**</span></span>|<span data-ttu-id="51132-125">用于导入根钥（来自证书颁发机构）。</span><span class="sxs-lookup"><span data-stu-id="51132-125">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="51132-126">**filename.pfx （或.cer）**</span><span class="sxs-lookup"><span data-stu-id="51132-126">**filename.pfx (or .cer)**</span></span>|<span data-ttu-id="51132-127">.pfx（私钥）或 .cer（公钥）文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="51132-127">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="51132-128">**Filepassword**</span><span class="sxs-lookup"><span data-stu-id="51132-128">**Filepassword**</span></span>|<span data-ttu-id="51132-129">对 .pfx 文件进行解锁所需的密码。</span><span class="sxs-lookup"><span data-stu-id="51132-129">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="51132-130">**用户身份**</span><span class="sxs-lookup"><span data-stu-id="51132-130">**Useridentity**</span></span>|<span data-ttu-id="51132-131">一个或多个 BizTalk 主机使用的服务标识。</span><span class="sxs-lookup"><span data-stu-id="51132-131">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="51132-132">如果不想指定主机，而想以用户帐户导入证书，请输入一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="51132-132">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="51132-133">**注意：**如果不希望添加**用户身份**开关，实用程序导入，并且将证书设置的所有用户。</span><span class="sxs-lookup"><span data-stu-id="51132-133">**Note:**  If you do not add the **Useridentity** switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="51132-134">**注意：**如果添加**用户身份**开关，但不是输入一个值，WMI 自动生成的用户标识。</span><span class="sxs-lookup"><span data-stu-id="51132-134">**Note:**  If you add the **Useridentity** switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="51132-135">**密码**</span><span class="sxs-lookup"><span data-stu-id="51132-135">**Password**</span></span>|<span data-ttu-id="51132-136">服务标识用户的口令。</span><span class="sxs-lookup"><span data-stu-id="51132-136">The password for the service identity user.</span></span>|  
|<span data-ttu-id="51132-137">**指纹**</span><span class="sxs-lookup"><span data-stu-id="51132-137">**Thumbprint**</span></span>|<span data-ttu-id="51132-138">特定证书的指纹（如果证书文件包含多个证书）。</span><span class="sxs-lookup"><span data-stu-id="51132-138">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="51132-139">**注意：**对于公共证书文件，如果该文件包含多个证书且未指定指纹，该实用程序导入文件中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="51132-139">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="51132-140">对于私用证书文件，实用工具会提示你选择要导入的证书。</span><span class="sxs-lookup"><span data-stu-id="51132-140">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="51132-141">**用法**</span><span class="sxs-lookup"><span data-stu-id="51132-141">**Usage**</span></span>|<span data-ttu-id="51132-142">导入的私用证书的预期用途。</span><span class="sxs-lookup"><span data-stu-id="51132-142">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="51132-143">可以为 sign（表示用作签名证书）、decrypt（表示用作解密证书）、both（表示既用作签名证书也用作解密证书）或者 none（同样表示既用作签名证书也用作解密证书）。</span><span class="sxs-lookup"><span data-stu-id="51132-143">Can be sign (for a signing certificate), decrypt (for a decryption certificate), both (for a certificate that is both a signing certificate and a decryption certificate), or none (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="51132-144">**注意：**如果你设置**/Usage**交换机为 none，向导将 BizTalk 主机或 BizTalk 组上设置证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="51132-144">**Note:**  If you set the **/Usage** switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="51132-145">**可导出**</span><span class="sxs-lookup"><span data-stu-id="51132-145">**Exportable**</span></span>|<span data-ttu-id="51132-146">可以为 `True` 或 `False`。</span><span class="sxs-lookup"><span data-stu-id="51132-146">Can be `True` or `False`.</span></span> <span data-ttu-id="51132-147">如果`True`，可以重新导出私钥。</span><span class="sxs-lookup"><span data-stu-id="51132-147">If `True`, the private key can be re-exported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51132-148">注释</span><span class="sxs-lookup"><span data-stu-id="51132-148">Remarks</span></span>  
 <span data-ttu-id="51132-149">CertWizard 将私钥从 .pfx 文件导入到个人存储区中，将公钥从 .cer 文件导入到公用存储区中。</span><span class="sxs-lookup"><span data-stu-id="51132-149">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="51132-150">导入私钥时，证书可为传入消息的解密证书或传出消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="51132-150">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="51132-151">如果在命令提示符处提供的命令不完整，CertWizard 会提示你提供必需的值。</span><span class="sxs-lookup"><span data-stu-id="51132-151">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51132-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51132-152">See Also</span></span>  
 <span data-ttu-id="51132-153">[实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="51132-153">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="51132-154">导入证书使用 CertWizard 实用工具</span><span class="sxs-lookup"><span data-stu-id="51132-154">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)