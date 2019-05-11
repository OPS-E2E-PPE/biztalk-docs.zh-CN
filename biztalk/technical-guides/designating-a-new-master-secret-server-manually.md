---
title: 手动指定新的主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e198d5aa82b22170fe4ed52115bf7c72b0c55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305787"
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="3d5e2-102">手动指定新的主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3d5e2-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="3d5e2-103">群集硬件可能成本高昂。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="3d5e2-104">如果硬件成本是一个问题，则可以考虑手动指定另一个企业单一登录 (SSO) 服务器，在故障情况下保持在主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="3d5e2-105">使用此选项，可以为主密钥服务器升级 SSO 组中的任何其他 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="3d5e2-106">主机关闭时，你可以手动升级是主密钥服务器与 SSO 服务器之一。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="3d5e2-107">此技术的最大缺点是，不能编辑现有部署，重新启动现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务，或部署新的 BizTalk 应用程序，直到您提升新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="3d5e2-108">若要使该过程无缝，您需要实现某些监视机制，以便将尽可能快地发现失败。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="3d5e2-109">此外可以通过使用 System Center Operations Manager 等监视应用程序自动升级过程。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="3d5e2-110">有关手动移动主密钥服务器的详细信息，请参阅[如何移动主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156841)(<http://go.microsoft.com/fwlink/?LinkId=156841>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="3d5e2-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (<http://go.microsoft.com/fwlink/?LinkId=156841>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5e2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d5e2-111">See Also</span></span>  
 [<span data-ttu-id="3d5e2-112">聚类分析主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3d5e2-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)