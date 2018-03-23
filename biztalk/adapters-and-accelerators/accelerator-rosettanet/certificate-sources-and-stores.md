---
title: 源和存储的证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="certificate-sources-and-stores"></a><span data-ttu-id="0d724-102">证书源和存储</span><span class="sxs-lookup"><span data-stu-id="0d724-102">Certificate Sources and Stores</span></span>
<span data-ttu-id="0d724-103">本主题介绍导入和存储证书的位置。</span><span class="sxs-lookup"><span data-stu-id="0d724-103">This topic describes where to import certificates from, and where to store certificates.</span></span>  
  
## <a name="certificate-sources"></a><span data-ttu-id="0d724-104">证书源</span><span class="sxs-lookup"><span data-stu-id="0d724-104">Certificate Sources</span></span>  
 <span data-ttu-id="0d724-105">从以下文件导入证书：</span><span class="sxs-lookup"><span data-stu-id="0d724-105">You import certificates from the following files:</span></span>  
  
-   <span data-ttu-id="0d724-106">从 .pfx 或 .p12 文件导入私用证书。</span><span class="sxs-lookup"><span data-stu-id="0d724-106">Private certificates from .pfx or .p12 files.</span></span> <span data-ttu-id="0d724-107">在导入证书后，对这些文件进行安全的存储。</span><span class="sxs-lookup"><span data-stu-id="0d724-107">After importing the certificates, store these files securely.</span></span> <span data-ttu-id="0d724-108">如果使用 CertWizard 实用工具将私钥证书导入，则可以设置**/可导出**切换到`False`，这是默认设置，以便私有证书无法从存储区导出到文件。</span><span class="sxs-lookup"><span data-stu-id="0d724-108">If you import the private certificates using the CertWizard utility, you can set the **/Exportable** switch to `False`, which is the default setting, so that the private certificates cannot be exported from the store into a file.</span></span> <span data-ttu-id="0d724-109">如果你设置**/可导出**切换到`True`，你可以从证书将这些证书导出到文件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="0d724-109">If you set the **/Exportable** switch to `True`, you can export these certificates to a file from the Certificates [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span>  
  
-   <span data-ttu-id="0d724-110">从 .cer 或 .der 文件导入公用证书。</span><span class="sxs-lookup"><span data-stu-id="0d724-110">Public certificates from .cer or .der files.</span></span> <span data-ttu-id="0d724-111">合作伙伴用这些文件将其证书发送给您。</span><span class="sxs-lookup"><span data-stu-id="0d724-111">Partners send their certificates to you in these files.</span></span>  
  
-   <span data-ttu-id="0d724-112">从 .cer 或 .der 文件导入根证书。</span><span class="sxs-lookup"><span data-stu-id="0d724-112">Root certificates from .cer or .der files.</span></span> <span data-ttu-id="0d724-113">证书授权机构用这些文件将其根证书发送给您。</span><span class="sxs-lookup"><span data-stu-id="0d724-113">Certification authorities send their root certificates to you in these files.</span></span>  
  
## <a name="certificate-storage"></a><span data-ttu-id="0d724-114">证书存储</span><span class="sxs-lookup"><span data-stu-id="0d724-114">Certificate Storage</span></span>  
 <span data-ttu-id="0d724-115">您将证书导入本地计算机的两个证书存储区之一。</span><span class="sxs-lookup"><span data-stu-id="0d724-115">You import certificates into one of two Certificates stores on the local computer.</span></span> <span data-ttu-id="0d724-116">存储中的公共证书**证书 （本地计算机）**存储。</span><span class="sxs-lookup"><span data-stu-id="0d724-116">You store public certificates in the **Certificates (Local Computer)** store.</span></span> <span data-ttu-id="0d724-117">你可以通过打开打开的此存储节点**证书 （本地计算机）**中的节点[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0d724-117">You can open the nodes of this store by opening the **Certificates (Local Computer)** node in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="0d724-118">你可以访问**证书 （本地计算机）**存储如果您的计算机上具有管理权限。</span><span class="sxs-lookup"><span data-stu-id="0d724-118">You can access the **Certificates (Local Computer)** store if you have administrative permissions on the computer.</span></span> <span data-ttu-id="0d724-119">将公用证书存储在以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0d724-119">Store public certificates in the following folders:</span></span>  
  
-   <span data-ttu-id="0d724-120">主页中的个人文件夹中的公共证书**证书 （本地计算机）**存储</span><span class="sxs-lookup"><span data-stu-id="0d724-120">Home public certificates in the Personal folder in the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="0d724-121">合作伙伴的其他人文件夹中的公共证书**证书 （本地计算机）**存储</span><span class="sxs-lookup"><span data-stu-id="0d724-121">Partner public certificates in the Other People folder of the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="0d724-122">从的受信任根证书颁发机构文件夹中的证书颁发机构的证书**证书 （本地计算机）**存储</span><span class="sxs-lookup"><span data-stu-id="0d724-122">Certificates from certification authorities in the Trusted Root Certification Authority folder of the **Certificates (Local Computer)** store</span></span>  
  
 <span data-ttu-id="0d724-123">存储中的私有证书**证书-当前用户**存储。</span><span class="sxs-lookup"><span data-stu-id="0d724-123">You store private certificates in the **Certificates - Current User** store.</span></span> <span data-ttu-id="0d724-124">你可以通过打开管理控制台使用打开的此存储节点**runas**命令和主机服务帐户用户。</span><span class="sxs-lookup"><span data-stu-id="0d724-124">You can open the nodes of this store by opening the Management Console using the **runas** command with the host service account user.</span></span> <span data-ttu-id="0d724-125">有关详细信息，请参阅[导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="0d724-125">For more information, see [Importing Certificates](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d724-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d724-126">See Also</span></span>  
 <span data-ttu-id="0d724-127">[导入证书使用 CertWizard 实用工具](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0d724-127">[Importing Certificates Using the CertWizard Utility](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span></span>  
 <span data-ttu-id="0d724-128">[导入证书使用 MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="0d724-128">[Importing Certificates Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span></span>  
 [<span data-ttu-id="0d724-129">导入证书&#91;RN3&#93;</span><span class="sxs-lookup"><span data-stu-id="0d724-129">Importing Certificates &#91;RN3&#93;</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)