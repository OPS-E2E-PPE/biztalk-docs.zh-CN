---
title: 提供高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e482709ae5a9c6b1ea67446773eaadcdc26a25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395108"
---
# <a name="providing-high-availability"></a><span data-ttu-id="a2394-102">提供高可用性</span><span class="sxs-lookup"><span data-stu-id="a2394-102">Providing High Availability</span></span>
<span data-ttu-id="a2394-103">为提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在环境中实现冗余，以便每个功能组件的环境。</span><span class="sxs-lookup"><span data-stu-id="a2394-103">High availability is provided for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by implementing redundancy for each functional component in the environment.</span></span> <span data-ttu-id="a2394-104">BizTalk 主机的冗余，可以通过安装运行的多台计算机实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的 BizTalk 组，然后配置要在多个运行的计算机上运行的主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="a2394-104">Redundancy for a BizTalk Host can be accomplished by installing multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a BizTalk group and then configuring instances of the host to run on more than one of the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="a2394-105">中的其他组件的冗余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，可以通过为中的资源配置的组件实现[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="a2394-105">Redundancy for other components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment can be accomplished by configuring the components as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a2394-106">也适合于在配置 BizTalk 主机中的资源作为[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集，建议对于某些 BizTalk 适配器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="a2394-106">also accommodates configuring BizTalk Hosts as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, which is recommended to provide high availability for certain BizTalk adapters.</span></span>  
  
 <span data-ttu-id="a2394-107">本部分介绍如何为中的功能组件提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="a2394-107">This section describes how to provide high availability for the functional components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2394-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a2394-108">In This Section</span></span>  
  
-   [<span data-ttu-id="a2394-109">规划高 Availability2</span><span class="sxs-lookup"><span data-stu-id="a2394-109">Planning for High Availability2</span></span>](../technical-guides/planning-for-high-availability2.md)  
  
-   [<span data-ttu-id="a2394-110">BizTalk 主机的高可用性</span><span class="sxs-lookup"><span data-stu-id="a2394-110">High Availability for BizTalk Hosts</span></span>](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="a2394-111">数据库的高可用性</span><span class="sxs-lookup"><span data-stu-id="a2394-111">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)  
  
-   [<span data-ttu-id="a2394-112">主密钥服务器的高可用性</span><span class="sxs-lookup"><span data-stu-id="a2394-112">High Availability for the Master Secret Server</span></span>](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a2394-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2394-113">See Also</span></span>  
 [<span data-ttu-id="a2394-114">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="a2394-114">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)