---
title: "BizTalk Server 中的 RosettaNet Double 操作教程的先决条件 |Microsoft 文档"
description: "单步执行双操作教程 RosettaNet 快捷键 (BTARN) BizTalk Server 中的先决条件"
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc247aa1ab9ec7cb6f056cd45df54bc324990ad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="prepare-for-the-double-action-tutorial"></a><span data-ttu-id="92cb2-103">对于双操作教程准备</span><span class="sxs-lookup"><span data-stu-id="92cb2-103">Prepare for the Double Action tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92cb2-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="92cb2-104">Prerequisites</span></span>
<span data-ttu-id="92cb2-105">在开始本教程： 之前</span><span class="sxs-lookup"><span data-stu-id="92cb2-105">Before starting the tutorial:</span></span>
  
-   <span data-ttu-id="92cb2-106">执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。</span><span class="sxs-lookup"><span data-stu-id="92cb2-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="92cb2-107">有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="92cb2-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="92cb2-108">请确保你完全配置 RosettaNet 快捷键，包括起始 BTARN 业务流程。</span><span class="sxs-lookup"><span data-stu-id="92cb2-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="92cb2-109">请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="92cb2-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
-   <span data-ttu-id="92cb2-110">本教程使用两台计算机而不是一台具有环回协议的计算机来模拟现实方案。</span><span class="sxs-lookup"><span data-stu-id="92cb2-110">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loopback agreement.</span></span> <span data-ttu-id="92cb2-111">本教程用占位符作为计算机名。</span><span class="sxs-lookup"><span data-stu-id="92cb2-111">Whenever this tutorial uses computer names, it uses a placeholder.</span></span> <span data-ttu-id="92cb2-112">该占位符替换为你选择的实际计算机名称。</span><span class="sxs-lookup"><span data-stu-id="92cb2-112">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="92cb2-113">例如，如果计算机运行 Contoso 解决方案命名为**Contoso**，任何匹配项替换的教程中\\ \\< contoso**_** *计算机*\>具有该计算机名称。</span><span class="sxs-lookup"><span data-stu-id="92cb2-113">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso**_***computer*\> with that computer name.</span></span>  
  
-   <span data-ttu-id="92cb2-114">本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="92cb2-114">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="92cb2-115">你必须生成任何证书要求，以及在其各自的计算机上安装它们。</span><span class="sxs-lookup"><span data-stu-id="92cb2-115">You must generate any certificates you require, and install them on their respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="92cb2-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="92cb2-116">Next steps</span></span> 
  
-   [<span data-ttu-id="92cb2-117">步骤 1：创建证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="92cb2-117">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="92cb2-118">步骤 2：创建公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="92cb2-118">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="92cb2-119">步骤 3：导入公共和私有证书</span><span class="sxs-lookup"><span data-stu-id="92cb2-119">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="92cb2-120">步骤 4：在 IIS 中启用安全套接字层</span><span class="sxs-lookup"><span data-stu-id="92cb2-120">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)