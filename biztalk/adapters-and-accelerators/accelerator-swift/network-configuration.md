---
title: 网络配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="network-configuration"></a><span data-ttu-id="a4ca8-102">网络配置</span><span class="sxs-lookup"><span data-stu-id="a4ca8-102">Network Configuration</span></span>
<span data-ttu-id="a4ca8-103">本部分提供在你的部署中配置网络的规范性指引。</span><span class="sxs-lookup"><span data-stu-id="a4ca8-103">This section provides prescriptive guidance for configuring the network in your deployment.</span></span> <span data-ttu-id="a4ca8-104">有关详细信息，请参阅[为部署做好准备](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ca8-104">For more information, see [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span>  
  
 <span data-ttu-id="a4ca8-105">你定义在交换机中的虚拟局域网 (Vlan)，然后连接适当的电缆。</span><span class="sxs-lookup"><span data-stu-id="a4ca8-105">You define virtual local area networks (VLANs) in the switch and then connect the appropriate cables.</span></span> <span data-ttu-id="a4ca8-106">通过定义 Vlan，指定为每个网络段或层交换机上的端口。</span><span class="sxs-lookup"><span data-stu-id="a4ca8-106">By defining the VLANs, you are designating ports on the switch for each network segment or tier.</span></span> <span data-ttu-id="a4ca8-107">为每个以下的环境，必须创建 VLAN:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-107">You must create a VLAN for each of the following environments:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a4ca8-108">接收和发送层</span><span class="sxs-lookup"><span data-stu-id="a4ca8-108"> receive and send tier</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a4ca8-109">业务流程和数据库层</span><span class="sxs-lookup"><span data-stu-id="a4ca8-109"> orchestration and database tier</span></span>  
  
-   <span data-ttu-id="a4ca8-110">企业网络</span><span class="sxs-lookup"><span data-stu-id="a4ca8-110">Corporate network</span></span>  
  
 <span data-ttu-id="a4ca8-111">定义 Vlan 后，你可以连接的网络电缆从服务器到交换机上的相应端口。</span><span class="sxs-lookup"><span data-stu-id="a4ca8-111">After you have defined the VLANs, you can connect the network cables from the servers to the appropriate ports on the switch.</span></span>  
  
 <span data-ttu-id="a4ca8-112">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="a4ca8-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="a4ca8-113">物理关系图</span><span class="sxs-lookup"><span data-stu-id="a4ca8-113">Physical Diagram</span></span>](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [<span data-ttu-id="a4ca8-114">网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="a4ca8-114">Network Load Balancing</span></span>](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)