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
ms.openlocfilehash: 96dd45cb6a4f973b98a0a7a4a0c32c2d8452c0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283655"
---
# <a name="importing-certificates"></a><span data-ttu-id="a7451-102">导入证书</span><span class="sxs-lookup"><span data-stu-id="a7451-102">Importing Certificates</span></span>
<span data-ttu-id="a7451-103">本部分介绍如何导入证书，包括从其导入的位置、 它们的存储的位置和使用导入它们何种工具。</span><span class="sxs-lookup"><span data-stu-id="a7451-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="a7451-104">有两种方法来导入证书。</span><span class="sxs-lookup"><span data-stu-id="a7451-104">There are two ways to import certificates.</span></span> <span data-ttu-id="a7451-105">可以使用 CertWizard 工具或证书管理单元中的 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="a7451-105">You can use the CertWizard tool or the Certificates snap-in for Microsoft Management Console (MMC).</span></span>  
  
- <span data-ttu-id="a7451-106">CertWizard 为分步式命令行，用于配置基于开关设置的证书的使用。</span><span class="sxs-lookup"><span data-stu-id="a7451-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="a7451-107">此工具现已推出 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7451-107">This tool is available in the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
- <span data-ttu-id="a7451-108">证书管理单元在 MMC 中，您可导入证书的证书存储中。</span><span class="sxs-lookup"><span data-stu-id="a7451-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="a7451-109">但是，此手动过程需要您单独配置证书的使用。</span><span class="sxs-lookup"><span data-stu-id="a7451-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="a7451-110">若要导入或使用私用证书 MMC 中，登录的用户必须具有 BizTalk 主机的用户标识。</span><span class="sxs-lookup"><span data-stu-id="a7451-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="a7451-111">如果不是，您必须运行**runas**与用户开关和主机服务帐户，以启动证书 MMC，例如，命令**runas /user: hostsvc mmc**。</span><span class="sxs-lookup"><span data-stu-id="a7451-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="a7451-112">通过运行以下命令，您假定 BizTalk 主机 （BizTalkServerApplication 和 BizTalkServerIsolatedHost） 的用户标识。</span><span class="sxs-lookup"><span data-stu-id="a7451-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7451-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="a7451-113">In This Section</span></span>  
  
-   [<span data-ttu-id="a7451-114">证书源和证书存储</span><span class="sxs-lookup"><span data-stu-id="a7451-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="a7451-115">使用 CertWizard 实用程序导入证书</span><span class="sxs-lookup"><span data-stu-id="a7451-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="a7451-116">使用 MMC 导入证书</span><span class="sxs-lookup"><span data-stu-id="a7451-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)