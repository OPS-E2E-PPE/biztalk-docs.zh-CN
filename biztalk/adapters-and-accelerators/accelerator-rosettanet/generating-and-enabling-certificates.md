---
title: "生成并启用证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, enabling
- private process tutorial, creating certificates
- private process tutorial, enabling certificates
ms.assetid: a36d9725-d57c-499d-948d-558096709d67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93293939ae509dcb2af04e17fcdd35e9cf6d03cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generating-and-enabling-certificates"></a><span data-ttu-id="d30cc-102">生成并启用证书</span><span class="sxs-lookup"><span data-stu-id="d30cc-102">Generating and Enabling Certificates</span></span>
<span data-ttu-id="d30cc-103">本教程将使用证书对 Contoso 和 Fabrikam 组织发送的消息进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="d30cc-103">This tutorial uses certificates to sign and encrypt messages sent by the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="d30cc-104">如果你已经完成 Double 操作教程，你可能会跳过此步骤并转到[创建 Contoso 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="d30cc-104">If you have already completed the Double Action Tutorial, you may skip this step and move on to [Creating the Contoso Solution](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md).</span></span> <span data-ttu-id="d30cc-105">若要生成和使用本教程中的证书，请执行以下主题中介绍的过程：</span><span class="sxs-lookup"><span data-stu-id="d30cc-105">To generate and use certificates for this tutorial, follow the procedures in the following topics:</span></span>  
  
-   [<span data-ttu-id="d30cc-106">步骤 1： 创建证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="d30cc-106">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="d30cc-107">步骤 2： 创建公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="d30cc-107">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="d30cc-108">步骤 3： 导入公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="d30cc-108">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="d30cc-109">步骤 4： 启用安全套接字在 IIS 中的层</span><span class="sxs-lookup"><span data-stu-id="d30cc-109">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)  
  
> [!IMPORTANT]
>  <span data-ttu-id="d30cc-110">这些步骤可在双操作教程。</span><span class="sxs-lookup"><span data-stu-id="d30cc-110">These steps are in the Double Action Tutorial.</span></span> <span data-ttu-id="d30cc-111">完成各个步骤以后，请返回到本主题继续学习专用流程教程。</span><span class="sxs-lookup"><span data-stu-id="d30cc-111">After completing each step, return to this topic to continue the Private Process Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30cc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d30cc-112">See Also</span></span>  
 [<span data-ttu-id="d30cc-113">创建 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="d30cc-113">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)