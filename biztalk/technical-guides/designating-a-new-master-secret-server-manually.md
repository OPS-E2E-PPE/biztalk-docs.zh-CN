---
title: "手动指定新主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="0cf9d-102">手动指定新主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="0cf9d-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="0cf9d-103">群集硬件可能很昂贵。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="0cf9d-104">如果硬件成本是个问题，你可以考虑手动指定另一台企业单一登录 (SSO) 服务器的主密钥服务器期间出现故障。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="0cf9d-105">使用此选项，SSO 组中的任何其他 SSO 服务器可以提升到的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="0cf9d-106">当主已关闭时，你可以手动将提升是主密钥服务器的 SSO 服务器之一。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="0cf9d-107">此技术的最大缺点是，您不能编辑现有的部署，重新启动现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务，或部署新的 BizTalk 应用程序，直到将提升新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="0cf9d-108">为了使无缝的过程，你将需要实现某些监视机制，以便将尽可能快地发现失败。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="0cf9d-109">你可以使用 System Center Operations Manager 等监视应用程序，以自动升级过程。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="0cf9d-110">有关手动移动的主密钥服务器的详细信息，请参阅[如何移动主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156841)(http://go.microsoft.com/fwlink/?LinkId=156841) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="0cf9d-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (http://go.microsoft.com/fwlink/?LinkId=156841) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf9d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cf9d-111">See Also</span></span>  
 [<span data-ttu-id="0cf9d-112">群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="0cf9d-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)