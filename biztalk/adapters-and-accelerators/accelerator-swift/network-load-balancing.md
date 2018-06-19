---
title: 网络负载平衡 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- NLB
- deploying, network configuration
ms.assetid: 27dc95be-8069-4cbf-b7b0-77657ce22189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66147720f810fb4ec8b8c4b0d387073f188ec844
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213989"
---
# <a name="network-load-balancing"></a><span data-ttu-id="01928-102">网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="01928-102">Network Load Balancing</span></span>
<span data-ttu-id="01928-103">分布式的 A4SWIFT 部署可能包含消息传递、 业务流程、 SharePoint 服务器到主机 MRSR 站点或 SQL Server 数据库的 BizTalk Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="01928-103">A distributed A4SWIFT deployment may contain BizTalk Server computers for messaging, orchestration, SharePoint Servers to host MRSR site, or SQL Server databases.</span></span> <span data-ttu-id="01928-104">如果你使用配置文件和业务需要足够大，可能需要设置网络负载平衡 (NLB) 为两个或多个 BizTalk HTTP 前端 （MRSR 站点） 服务器或两个或多个 BizTalk 消息传送服务器。</span><span class="sxs-lookup"><span data-stu-id="01928-104">If your usage profile and business needs are great enough, you may need to set up network load balancing (NLB) for two or more BizTalk HTTP front-end (MRSR site) servers or two or more BizTalk messaging servers.</span></span> <span data-ttu-id="01928-105">需要网络负载平衡的多个服务器的示例，请参阅中的"示例的完整 A4SWIFT 部署"关系图[物理图](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)。</span><span class="sxs-lookup"><span data-stu-id="01928-105">For an example of multiple servers in need of network load balancing, see the "Example of a full A4SWIFT deployment" diagram in [Physical Diagram](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md).</span></span>  
  
 <span data-ttu-id="01928-106">有关网络负载平衡的详细信息，请参阅 BizTalk Server 部署指南中，和[步骤 2： 在服务器上配置 NLB](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="01928-106">For more information on network load balancing, see the BizTalk Server Deployment Guide, and [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01928-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01928-107">See Also</span></span>  
 [<span data-ttu-id="01928-108">步骤 2： 在服务器上配置 NLB</span><span class="sxs-lookup"><span data-stu-id="01928-108">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)