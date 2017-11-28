---
title: "启用或禁用 BAM 跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-or-disabling-bam-tracking"></a><span data-ttu-id="dd29c-102">启用或禁用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="dd29c-102">Enabling or Disabling BAM Tracking</span></span>
<span data-ttu-id="dd29c-103">你可以启用或禁用 BAM 跟踪任何时候，即使在消息修复和新的传输进程的进程中的事务。</span><span class="sxs-lookup"><span data-stu-id="dd29c-103">You can enable or disable BAM tracking at any point, even while the Message Repair and New Transmission process has transactions in process.</span></span> <span data-ttu-id="dd29c-104">但是，如果你禁用 BAM 跟踪进程事务时，BAM 数据可能不完整的这些事务。</span><span class="sxs-lookup"><span data-stu-id="dd29c-104">However, if you disable BAM tracking while transactions are in process, the BAM data may be incomplete for those transactions.</span></span> <span data-ttu-id="dd29c-105">如果发生这种情况，历史记录表将仍然包含所有实例的准确的数据。</span><span class="sxs-lookup"><span data-stu-id="dd29c-105">If this occurs, the history table will still contain accurate data for all instances.</span></span>  
  
 <span data-ttu-id="dd29c-106">有关启用或禁用 BAM 跟踪 A4SWIFT 组件配置过程的一部分的信息，请参阅[设置 A4SWIFT 属性](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="dd29c-106">For information about enabling or disabling BAM tracking as part of the A4SWIFT component configuration process, see [Setting A4SWIFT Properties](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="dd29c-107">若要启用或禁用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="dd29c-107">To enable or disable BAM Tracking</span></span>  
  
1.  <span data-ttu-id="dd29c-108">在配置文件的 Web 客户端中，右键单击**BizTalk Accelerator for SWIFT**在控制台树中，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="dd29c-108">In the Profile Web Client, right-click **BizTalk Accelerator for SWIFT** in the console tree, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="dd29c-109">在全局属性对话框中，禁用通过取消选择跟踪的 BAM**启用 BAM 跟踪**，或启用 BAM 跟踪通过选择它。</span><span class="sxs-lookup"><span data-stu-id="dd29c-109">In the Global Properties dialog box, disable BAM tracking by deselecting **Enable BAM Tracking**, or enable BAM tracking by selecting it.</span></span>  
  
3.  <span data-ttu-id="dd29c-110">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="dd29c-110">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="dd29c-111">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，，然后**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="dd29c-111">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, and then **Platform Settings**.</span></span> <span data-ttu-id="dd29c-112">单击**托管实例**。</span><span class="sxs-lookup"><span data-stu-id="dd29c-112">Click **Host Instances**.</span></span>  
  
5.  <span data-ttu-id="dd29c-113">在细节窗格中，右键单击主机实例，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="dd29c-113">In the details pane, right-click the host instance , and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd29c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd29c-114">See Also</span></span>  
 [<span data-ttu-id="dd29c-115">设置 A4SWIFT 属性</span><span class="sxs-lookup"><span data-stu-id="dd29c-115">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)