---
title: 在 BizTalk Server 中 RosettaNet 专用流程教程的先决条件 |Microsoft Docs
description: 单步执行 BizTalk Server 中的 RosettaNet 加速器 (BTARN) 的专用流程教程的先决条件
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 4f2a218063bc7f8d90205480887c90c6f6be78d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282719"
---
# <a name="prepare-for-the-private-process-tutorial"></a><span data-ttu-id="25282-103">准备专用流程教程</span><span class="sxs-lookup"><span data-stu-id="25282-103">Prepare for the Private Process tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25282-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="25282-104">Prerequisites</span></span>
<span data-ttu-id="25282-105">教程： 开始前</span><span class="sxs-lookup"><span data-stu-id="25282-105">Before starting the tutorial:</span></span>
  
- <span data-ttu-id="25282-106">执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。</span><span class="sxs-lookup"><span data-stu-id="25282-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="25282-107">有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="25282-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="25282-108">请确保您完全配置 RosettaNet 加速器，包括启动 BTARN 业务流程。</span><span class="sxs-lookup"><span data-stu-id="25282-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="25282-109">请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="25282-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span> <span data-ttu-id="25282-110">您可能还需要添加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到 Microsoft Windows® SharePoint™ Services 管理的路径排除列表 （包括 btarnhttpreceive） 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="25282-110">You may also have to add the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] virtual directories (including btarnhttpreceive) to the Microsoft Windows® SharePoint™ Services managed path exclusion list.</span></span> 
  
- <span data-ttu-id="25282-111">本教程通过使用两台计算机而不一台具有环回协议来模拟真实方案。</span><span class="sxs-lookup"><span data-stu-id="25282-111">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loop-back agreement.</span></span> <span data-ttu-id="25282-112">每当本教程使用计算机名称，它会使用与计算机名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="25282-112">Whenever this tutorial uses computer names, it uses a placeholder as the computer name.</span></span> <span data-ttu-id="25282-113">该占位符替换为你选择的实际计算机名称。</span><span class="sxs-lookup"><span data-stu-id="25282-113">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="25282-114">例如，如果计算机运行你的 Contoso 解决方案命名为**Contoso**，在本教程的中替换任何出现\\ \\< contoso<strong>_</strong> *计算机*\>具有该计算机名称。</span><span class="sxs-lookup"><span data-stu-id="25282-114">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso<strong>_</strong>*computer*\> with that computer name.</span></span>  
  
  <span data-ttu-id="25282-115">本教程将升级通过 Contoso 和 Fabrikam 之间的证书的安全通信。</span><span class="sxs-lookup"><span data-stu-id="25282-115">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="25282-116">必须生成所有证书要求，并在各自计算机上安装它们。</span><span class="sxs-lookup"><span data-stu-id="25282-116">You must generate any certificates you require, and install them on the respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="25282-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="25282-117">Next steps</span></span>
  
-   [<span data-ttu-id="25282-118">还原 Contoso 数据库</span><span class="sxs-lookup"><span data-stu-id="25282-118">Restoring the Contoso Database</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [<span data-ttu-id="25282-119">生成和启用证书</span><span class="sxs-lookup"><span data-stu-id="25282-119">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)