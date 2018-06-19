---
title: BizTalk Server 中的 RosettaNet 私有过程教程的先决条件 |Microsoft 文档
description: 单步执行 RosettaNet 快捷键 (BTARN) BizTalk Server 中私有过程本教程的先决条件
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
ms.openlocfilehash: 580edcc7a8d779067895fb5aac99d81a1ad76872
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963411"
---
# <a name="prepare-for-the-private-process-tutorial"></a><span data-ttu-id="b3a7a-103">对于私有过程教程准备</span><span class="sxs-lookup"><span data-stu-id="b3a7a-103">Prepare for the Private Process tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3a7a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="b3a7a-104">Prerequisites</span></span>
<span data-ttu-id="b3a7a-105">在开始本教程： 之前</span><span class="sxs-lookup"><span data-stu-id="b3a7a-105">Before starting the tutorial:</span></span>
  
-   <span data-ttu-id="b3a7a-106">执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="b3a7a-107">有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b3a7a-108">请确保你完全配置 RosettaNet 快捷键，包括起始 BTARN 业务流程。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="b3a7a-109">请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span> <span data-ttu-id="b3a7a-110">你可能还需要添加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到 Microsoft Windows® SharePoint™ Services 托管的路径的排除列表 （包括 btarnhttpreceive） 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-110">You may also have to add the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] virtual directories (including btarnhttpreceive) to the Microsoft Windows® SharePoint™ Services managed path exclusion list.</span></span> 
  
-   <span data-ttu-id="b3a7a-111">本教程通过使用两台计算机而不环回协议一台计算机来模拟真实世界方案。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-111">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loop-back agreement.</span></span> <span data-ttu-id="b3a7a-112">只要本教程使用计算机名称，它会使用与计算机名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-112">Whenever this tutorial uses computer names, it uses a placeholder as the computer name.</span></span> <span data-ttu-id="b3a7a-113">该占位符替换为你选择的实际计算机名称。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-113">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="b3a7a-114">例如，如果计算机运行 Contoso 解决方案命名为**Contoso**，任何匹配项替换的教程中\\ \\< contoso **_** *计算机*\>具有该计算机名称。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-114">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso **_***computer*\> with that computer name.</span></span>  
  
 <span data-ttu-id="b3a7a-115">本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-115">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="b3a7a-116">你必须生成任何证书要求，以及在各自计算机上安装它们。</span><span class="sxs-lookup"><span data-stu-id="b3a7a-116">You must generate any certificates you require, and install them on the respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b3a7a-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b3a7a-117">Next steps</span></span>
  
-   [<span data-ttu-id="b3a7a-118">还原 Contoso 数据库</span><span class="sxs-lookup"><span data-stu-id="b3a7a-118">Restoring the Contoso Database</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [<span data-ttu-id="b3a7a-119">生成和启用证书</span><span class="sxs-lookup"><span data-stu-id="b3a7a-119">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)