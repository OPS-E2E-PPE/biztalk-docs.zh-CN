---
title: 生成和启用证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, enabling
- private process tutorial, creating certificates
- private process tutorial, enabling certificates
ms.assetid: a36d9725-d57c-499d-948d-558096709d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faf4218919ec2c47729ce1002f17d73ac79584ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283684"
---
# <a name="generating-and-enabling-certificates"></a><span data-ttu-id="a9b2f-102">生成和启用证书</span><span class="sxs-lookup"><span data-stu-id="a9b2f-102">Generating and Enabling Certificates</span></span>
<span data-ttu-id="a9b2f-103">本教程使用证书进行签名和加密由 Contoso 和 Fabrikam 组织发送的消息。</span><span class="sxs-lookup"><span data-stu-id="a9b2f-103">This tutorial uses certificates to sign and encrypt messages sent by the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="a9b2f-104">如果你已经完成了双操作教程，你可能会跳过此步骤并转到[创建 Contoso 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b2f-104">If you have already completed the Double Action Tutorial, you may skip this step and move on to [Creating the Contoso Solution](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span></span> <span data-ttu-id="a9b2f-105">若要生成并使用本教程中的证书，请执行以下主题中的过程：</span><span class="sxs-lookup"><span data-stu-id="a9b2f-105">To generate and use certificates for this tutorial, follow the procedures in the following topics:</span></span>  
  
-   [<span data-ttu-id="a9b2f-106">步骤 1：创建证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="a9b2f-106">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="a9b2f-107">步骤 2：创建公用和私用证书</span><span class="sxs-lookup"><span data-stu-id="a9b2f-107">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="a9b2f-108">步骤 3：导入公用和私用证书</span><span class="sxs-lookup"><span data-stu-id="a9b2f-108">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="a9b2f-109">步骤 4：在 IIS 中启用安全套接字层</span><span class="sxs-lookup"><span data-stu-id="a9b2f-109">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9b2f-110">这些步骤是在双操作教程。</span><span class="sxs-lookup"><span data-stu-id="a9b2f-110">These steps are in the Double Action Tutorial.</span></span> <span data-ttu-id="a9b2f-111">完成每个步骤后，返回到本主题并继续专用流程教程。</span><span class="sxs-lookup"><span data-stu-id="a9b2f-111">After completing each step, return to this topic to continue the Private Process Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b2f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b2f-112">See Also</span></span>  
 [<span data-ttu-id="a9b2f-113">创建 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="a9b2f-113">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)