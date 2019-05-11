---
title: 证书源和存储 |Microsoft Docs
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d099afcc6cecf229771e20551470027bf6bfe65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284772"
---
# <a name="certificate-sources-and-stores"></a><span data-ttu-id="c40c5-102">证书源和证书存储</span><span class="sxs-lookup"><span data-stu-id="c40c5-102">Certificate Sources and Stores</span></span>
<span data-ttu-id="c40c5-103">本主题介绍，从中导入证书的位置和存储证书的位置。</span><span class="sxs-lookup"><span data-stu-id="c40c5-103">This topic describes where to import certificates from, and where to store certificates.</span></span>  
  
## <a name="certificate-sources"></a><span data-ttu-id="c40c5-104">证书源</span><span class="sxs-lookup"><span data-stu-id="c40c5-104">Certificate Sources</span></span>  
 <span data-ttu-id="c40c5-105">从以下文件中导入证书：</span><span class="sxs-lookup"><span data-stu-id="c40c5-105">You import certificates from the following files:</span></span>  
  
- <span data-ttu-id="c40c5-106">私用证书从.pfx 或.p12 文件。</span><span class="sxs-lookup"><span data-stu-id="c40c5-106">Private certificates from .pfx or .p12 files.</span></span> <span data-ttu-id="c40c5-107">导入证书之后, 安全地存储这些文件。</span><span class="sxs-lookup"><span data-stu-id="c40c5-107">After importing the certificates, store these files securely.</span></span> <span data-ttu-id="c40c5-108">如果您导入私用证书使用 CertWizard 实用工具，可以设置 **/可导出**切换到`False`，这是默认设置，以便私用证书不能从存储区导出到一个文件。</span><span class="sxs-lookup"><span data-stu-id="c40c5-108">If you import the private certificates using the CertWizard utility, you can set the **/Exportable** switch to `False`, which is the default setting, so that the private certificates cannot be exported from the store into a file.</span></span> <span data-ttu-id="c40c5-109">如果您设置 **/可导出**切换到`True`，您可以将这些证书导出到文件从证书 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="c40c5-109">If you set the **/Exportable** switch to `True`, you can export these certificates to a file from the Certificates Microsoft Management Console (MMC).</span></span>  
  
- <span data-ttu-id="c40c5-110">从.cer 或.der 文件的公共证书。</span><span class="sxs-lookup"><span data-stu-id="c40c5-110">Public certificates from .cer or .der files.</span></span> <span data-ttu-id="c40c5-111">合作伙伴将其证书发送给您，这些文件中。</span><span class="sxs-lookup"><span data-stu-id="c40c5-111">Partners send their certificates to you in these files.</span></span>  
  
- <span data-ttu-id="c40c5-112">从.cer 或.der 文件的根证书。</span><span class="sxs-lookup"><span data-stu-id="c40c5-112">Root certificates from .cer or .der files.</span></span> <span data-ttu-id="c40c5-113">证书颁发机构这些文件中，向你发送其根证书。</span><span class="sxs-lookup"><span data-stu-id="c40c5-113">Certification authorities send their root certificates to you in these files.</span></span>  
  
## <a name="certificate-storage"></a><span data-ttu-id="c40c5-114">证书存储</span><span class="sxs-lookup"><span data-stu-id="c40c5-114">Certificate Storage</span></span>  
 <span data-ttu-id="c40c5-115">证书导入本地计算机上的两个证书存储之一。</span><span class="sxs-lookup"><span data-stu-id="c40c5-115">You import certificates into one of two Certificates stores on the local computer.</span></span> <span data-ttu-id="c40c5-116">中的公用证书**证书 （本地计算机）** 存储。</span><span class="sxs-lookup"><span data-stu-id="c40c5-116">You store public certificates in the **Certificates (Local Computer)** store.</span></span> <span data-ttu-id="c40c5-117">可以通过打开打开此存储区的节点**证书 （本地计算机）** Microsoft 中的节点[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c40c5-117">You can open the nodes of this store by opening the **Certificates (Local Computer)** node in the Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="c40c5-118">您可以访问**证书 （本地计算机）** 存储如果计算机上拥有管理权限。</span><span class="sxs-lookup"><span data-stu-id="c40c5-118">You can access the **Certificates (Local Computer)** store if you have administrative permissions on the computer.</span></span> <span data-ttu-id="c40c5-119">将公用证书存储在以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="c40c5-119">Store public certificates in the following folders:</span></span>  
  
- <span data-ttu-id="c40c5-120">本组织中的个人文件夹中的公用证书**证书 （本地计算机）** 存储</span><span class="sxs-lookup"><span data-stu-id="c40c5-120">Home public certificates in the Personal folder in the **Certificates (Local Computer)** store</span></span>  
  
- <span data-ttu-id="c40c5-121">合作伙伴的其他人文件夹中的公用证书**证书 （本地计算机）** 存储</span><span class="sxs-lookup"><span data-stu-id="c40c5-121">Partner public certificates in the Other People folder of the **Certificates (Local Computer)** store</span></span>  
  
- <span data-ttu-id="c40c5-122">从证书颁发机构的受信任的根证书颁发机构文件夹中的证书**证书 （本地计算机）** 存储</span><span class="sxs-lookup"><span data-stu-id="c40c5-122">Certificates from certification authorities in the Trusted Root Certification Authority folder of the **Certificates (Local Computer)** store</span></span>  
  
  <span data-ttu-id="c40c5-123">存储中的专用证书**证书-当前用户**存储。</span><span class="sxs-lookup"><span data-stu-id="c40c5-123">You store private certificates in the **Certificates - Current User** store.</span></span> <span data-ttu-id="c40c5-124">可以通过打开管理控制台使用打开此存储区的节点**runas**命令和主机服务帐户用户。</span><span class="sxs-lookup"><span data-stu-id="c40c5-124">You can open the nodes of this store by opening the Management Console using the **runas** command with the host service account user.</span></span> <span data-ttu-id="c40c5-125">有关详细信息，请参阅[导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="c40c5-125">For more information, see [Importing Certificates](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40c5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c40c5-126">See Also</span></span>  
 <span data-ttu-id="c40c5-127">[使用 CertWizard 实用工具导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c40c5-127">[Importing Certificates Using the CertWizard Utility](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span></span>  
 <span data-ttu-id="c40c5-128">[使用 MMC 导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="c40c5-128">[Importing Certificates Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span></span>  
 [<span data-ttu-id="c40c5-129">导入证书&#91;RN3&#93;</span><span class="sxs-lookup"><span data-stu-id="c40c5-129">Importing Certificates &#91;RN3&#93;</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)