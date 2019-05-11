---
title: 网络负载平衡 |Microsoft Docs
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
ms.openlocfilehash: 2e3bf3e2aba5d02fd6424ebb95493b798de1546c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377251"
---
# <a name="network-load-balancing"></a><span data-ttu-id="700f1-102">网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="700f1-102">Network Load Balancing</span></span>
<span data-ttu-id="700f1-103">分布式的 A4SWIFT 部署可能包含消息传递、 业务流程中，SharePoint 服务器到主机 MRSR 站点或 SQL Server 数据库的 BizTalk Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="700f1-103">A distributed A4SWIFT deployment may contain BizTalk Server computers for messaging, orchestration, SharePoint Servers to host MRSR site, or SQL Server databases.</span></span> <span data-ttu-id="700f1-104">如果使用配置文件和业务需求是足够大，可能需要设置网络负载平衡 (NLB) 的两个或多个 BizTalk HTTP 前端 （MRSR），站点服务器或两个或多个 BizTalk 消息传送服务器。</span><span class="sxs-lookup"><span data-stu-id="700f1-104">If your usage profile and business needs are great enough, you may need to set up network load balancing (NLB) for two or more BizTalk HTTP front-end (MRSR site) servers or two or more BizTalk messaging servers.</span></span> <span data-ttu-id="700f1-105">需要网络负载平衡的多个服务器的示例，请参阅中的"示例的完整 A4SWIFT 部署"关系图[物理示意图](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)。</span><span class="sxs-lookup"><span data-stu-id="700f1-105">For an example of multiple servers in need of network load balancing, see the "Example of a full A4SWIFT deployment" diagram in [Physical Diagram](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md).</span></span>  
  
 <span data-ttu-id="700f1-106">网络负载平衡的详细信息，请参阅 BizTalk Server 部署指南，和[步骤 2:在服务器上配置 NLB](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="700f1-106">For more information on network load balancing, see the BizTalk Server Deployment Guide, and [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700f1-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="700f1-107">See Also</span></span>  
 [<span data-ttu-id="700f1-108">步骤 2：在服务器上配置 NLB</span><span class="sxs-lookup"><span data-stu-id="700f1-108">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)