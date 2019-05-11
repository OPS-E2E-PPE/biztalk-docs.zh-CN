---
title: 设置 BTARN 发送和接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, modifying
- modifying, send pipelines
- receive pipelines, modifying
- modifying, receive pipelines
ms.assetid: 00960de0-3763-40aa-9e4b-1fedc7f1eea6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c195747a5c5501a3ac9ef57602f5bbdd5e0c0bfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281834"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a><span data-ttu-id="0cb9f-102">设置 BTARN 发送和接收管道</span><span class="sxs-lookup"><span data-stu-id="0cb9f-102">Setting BTARN Send and Receive Pipelines</span></span>
<span data-ttu-id="0cb9f-103">默认情况下，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用标准[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发送管道 (Microsoft.Solutions.BTARN.Pipelines.Send) 和标准[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]创建合作伙伴时，接收管道 (Microsoft.Solutions.BTARN.Pipelines.Receive)发送端口。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-103">By default, Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline (Microsoft.Solutions.BTARN.Pipelines.Send) and the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline (Microsoft.Solutions.BTARN.Pipelines.Receive) when you create partner send ports.</span></span> <span data-ttu-id="0cb9f-104">但是，可以更改[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]配置以使用现有的 BizTalk 管道或已创建的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-104">However, you can change the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration to use an existing BizTalk pipeline or a custom pipeline that you have created.</span></span> <span data-ttu-id="0cb9f-105">所有贸易合作伙伴协议、 合作伙伴和本组织都使用相同的发送管道和相同的接收管道。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-105">All trading partner agreements, and all partners and home organizations, use the same send pipeline and the same receive pipeline.</span></span>  
  
 <span data-ttu-id="0cb9f-106">当你首次创建合作伙伴，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]创建为该合作伙伴使用，一个异步的两个发送端口，另一个同步： \<*合作伙伴名称*\>。异步发送端口并\<*合作伙伴名称*\>。同步的发送端口。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-106">When you first create a partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] creates two send ports for that partner to use, one asynchronous and one synchronous: \<*partner name*\>.Async send port and \<*partner name*\>.Sync send port.</span></span> <span data-ttu-id="0cb9f-107">这些发送端口默认为标准[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发送管道和同步发送端口接收管道默认为标准[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收管道。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-107">These send ports default to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline, and the sync send port receive pipeline defaults to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cb9f-108">更改[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管道中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台可能会重置直接在 BizTalk 浏览器中更改的属性。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-108">Changing the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console might reset properties that you changed directly in BizTalk Explorer.</span></span>  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a><span data-ttu-id="0cb9f-109">若要更改发送或接收管道，BTARN 使用</span><span class="sxs-lookup"><span data-stu-id="0cb9f-109">To change the send or receive pipeline that BTARN uses</span></span>  
  
1. <span data-ttu-id="0cb9f-110">单击**启动**，依次指向**程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-110">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="0cb9f-111">在 BTARN 管理控制台中，右键单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]节点，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-111">In the BTARN Management Console, right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="0cb9f-112">在全局属性对话框中，从下拉列表中，选择不同的管道，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-112">In the Global Properties dialog box, select a different pipeline from the drop-down list, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="0cb9f-113">在中**主机实例**节点下的[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**节点，停止，然后重新启动主机。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-113">In the **Host Instances** node under the [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration** node, stop and then restart the host.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0cb9f-114">如果重新启动 BizTalk Server 对管道更改只会生效。</span><span class="sxs-lookup"><span data-stu-id="0cb9f-114">The changes to the pipelines will only take effect if you restart the BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb9f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb9f-115">See Also</span></span>  
 <span data-ttu-id="0cb9f-116">[管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="0cb9f-116">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 [<span data-ttu-id="0cb9f-117">启用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="0cb9f-117">Enabling BAM Tracking</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)