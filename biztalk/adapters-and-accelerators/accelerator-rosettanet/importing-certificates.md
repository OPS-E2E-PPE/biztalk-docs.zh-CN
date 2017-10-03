---
title: "导入证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78773d6eb1fc7e51ca80afadfd282d54def80b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates"></a><span data-ttu-id="1f3f3-102">导入证书</span><span class="sxs-lookup"><span data-stu-id="1f3f3-102">Importing Certificates</span></span>
<span data-ttu-id="1f3f3-103">本节介绍如何导入证书，包括从何处导入证书、将证书存储在何处以及使用何工具来导入证书。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="1f3f3-104">有两种方法可导入证书。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-104">There are two ways to import certificates.</span></span> <span data-ttu-id="1f3f3-105">你可以使用 CertWizard 工具或证书管理单元接[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-105">You can use the CertWizard tool or the Certificates snap-in for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span>  
  
-   <span data-ttu-id="1f3f3-106">CertWizard 为分步式命令行工具，基于开关设置来配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="1f3f3-107">此工具可用于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-107">This tool is available in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
-   <span data-ttu-id="1f3f3-108">使用 MMC 中的证书管理单元，可将证书导入到证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="1f3f3-109">但是，该手动过程需要您单独配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1f3f3-110">要在 MMC 中导入或使用私用证书，已登录的用户必须具有 BizTalk 主机的用户标识。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="1f3f3-111">如果没有，你必须运行**runas**用户交换机和主机服务帐户，以启动证书 MMC，例如，命令**runas /user:hostsvc mmc**。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="1f3f3-112">通过运行此命令，您可获得 BizTalk 主机（BizTalkServerApplication 和 BizTalkServerIsolatedHost）的用户标识。</span><span class="sxs-lookup"><span data-stu-id="1f3f3-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f3f3-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f3f3-113">In This Section</span></span>  
  
-   [<span data-ttu-id="1f3f3-114">证书源和存储</span><span class="sxs-lookup"><span data-stu-id="1f3f3-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="1f3f3-115">导入证书使用 CertWizard 实用工具</span><span class="sxs-lookup"><span data-stu-id="1f3f3-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="1f3f3-116">导入证书使用 MMC</span><span class="sxs-lookup"><span data-stu-id="1f3f3-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)