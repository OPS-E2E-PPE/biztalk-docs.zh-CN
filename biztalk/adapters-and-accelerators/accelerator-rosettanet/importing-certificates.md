---
title: 导入证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96bdc2a681cf3632f6393a3fef05ec275f60f82f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006078"
---
# <a name="importing-certificates"></a><span data-ttu-id="9b4ea-102">导入证书</span><span class="sxs-lookup"><span data-stu-id="9b4ea-102">Importing Certificates</span></span>
<span data-ttu-id="9b4ea-103">本节介绍如何导入证书，包括从何处导入证书、将证书存储在何处以及使用何工具来导入证书。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="9b4ea-104">有两种方法可导入证书。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-104">There are two ways to import certificates.</span></span> <span data-ttu-id="9b4ea-105">可以使用 CertWizard 工具或证书管理单元中的 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-105">You can use the CertWizard tool or the Certificates snap-in for Microsoft Management Console (MMC).</span></span>  
  
- <span data-ttu-id="9b4ea-106">CertWizard 为分步式命令行工具，基于开关设置来配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="9b4ea-107">此工具现已推出 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-107">This tool is available in the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
- <span data-ttu-id="9b4ea-108">使用 MMC 中的证书管理单元，可将证书导入到证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="9b4ea-109">但是，该手动过程需要您单独配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="9b4ea-110">要在 MMC 中导入或使用私用证书，已登录的用户必须具有 BizTalk 主机的用户标识。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="9b4ea-111">如果不是，您必须运行**runas**与用户开关和主机服务帐户，以启动证书 MMC，例如，命令**runas /user: hostsvc mmc**。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="9b4ea-112">通过运行此命令，您可获得 BizTalk 主机（BizTalkServerApplication 和 BizTalkServerIsolatedHost）的用户标识。</span><span class="sxs-lookup"><span data-stu-id="9b4ea-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b4ea-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="9b4ea-113">In This Section</span></span>  
  
-   [<span data-ttu-id="9b4ea-114">证书源和证书存储</span><span class="sxs-lookup"><span data-stu-id="9b4ea-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="9b4ea-115">使用 CertWizard 实用程序导入证书</span><span class="sxs-lookup"><span data-stu-id="9b4ea-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="9b4ea-116">使用 MMC 导入证书</span><span class="sxs-lookup"><span data-stu-id="9b4ea-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)