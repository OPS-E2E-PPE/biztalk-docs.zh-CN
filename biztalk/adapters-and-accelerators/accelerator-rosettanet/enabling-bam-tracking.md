---
title: 启用 BAM 跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e7260ed387ae5bb09e229c8721f5c40c61d4e80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971558"
---
# <a name="enabling-bam-tracking"></a><span data-ttu-id="c87c3-102">启用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="c87c3-102">Enabling BAM Tracking</span></span>
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]<span data-ttu-id="c87c3-103"> 使用 BizTalk 活动监视 (BAM) 增强了跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="c87c3-103"> supports enhanced tracking using BizTalk Activity Monitoring (BAM).</span></span> <span data-ttu-id="c87c3-104">启用跟踪是 BTARN 配置的全局属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="c87c3-104">You enable tracking as part of the global properties of the BTARN configuration.</span></span> <span data-ttu-id="c87c3-105">启用跟踪后，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将跟踪所有协议的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c87c3-105">After you enable tracking, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracks all messages for all agreements.</span></span> <span data-ttu-id="c87c3-106">默认情况下，跟踪是启用的。</span><span class="sxs-lookup"><span data-stu-id="c87c3-106">By default, tracking is enabled.</span></span>  
  
 <span data-ttu-id="c87c3-107">有关跟踪的详细信息，请参阅[增强跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="c87c3-107">For more information about tracking, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="c87c3-108">启用或禁用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="c87c3-108">To enable or disable BAM tracking</span></span>  
  
1. <span data-ttu-id="c87c3-109">单击**启动**，依次指向**程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="c87c3-109">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="c87c3-110">右键单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]节点在作用域窗格中，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c87c3-110">Right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node in the scope pane, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="c87c3-111">在中**全局属性**对话框中，选择**启用 BAM 跟踪**启用跟踪，或清除此选项以禁用它。</span><span class="sxs-lookup"><span data-stu-id="c87c3-111">In the **Global Properties** dialog box, select **Enable BAM Tracking** to enable tracking, or clear this option to disable it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c87c3-112">在启用或禁用跟踪时，一旦更改了启用标志，必须重新启动运行公用流程和 HTTP 适配器的所有服务。</span><span class="sxs-lookup"><span data-stu-id="c87c3-112">Whenever you change the enable flag to enable or disable tracking, you have to restart all services on which the public processes and the HTTP adapter are running.</span></span> <span data-ttu-id="c87c3-113">包括主机服务和独立主机服务。</span><span class="sxs-lookup"><span data-stu-id="c87c3-113">This includes the host service and the isolated host service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87c3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c87c3-114">See Also</span></span>  
 <span data-ttu-id="c87c3-115">[管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="c87c3-115">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 <span data-ttu-id="c87c3-116">[增强的跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="c87c3-116">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="c87c3-117">管理 BTARN 配置</span><span class="sxs-lookup"><span data-stu-id="c87c3-117">Administering the BTARN Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)