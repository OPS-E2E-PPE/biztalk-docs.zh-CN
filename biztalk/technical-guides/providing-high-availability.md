---
title: 提供高可用性 |Microsoft 文档
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
ms.openlocfilehash: c4521981bc3df67553c244a55c91c1eb045c8e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302037"
---
# <a name="providing-high-availability"></a><span data-ttu-id="9c79e-102">提供高可用性</span><span class="sxs-lookup"><span data-stu-id="9c79e-102">Providing High Availability</span></span>
<span data-ttu-id="9c79e-103">为提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在环境中实现冗余，以便每个功能的组件的环境。</span><span class="sxs-lookup"><span data-stu-id="9c79e-103">High availability is provided for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by implementing redundancy for each functional component in the environment.</span></span> <span data-ttu-id="9c79e-104">BizTalk 主机的冗余，可以通过安装运行的多台计算机实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组，然后配置要在多个运行的计算机上运行的主机的实例中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="9c79e-104">Redundancy for a BizTalk Host can be accomplished by installing multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a BizTalk group and then configuring instances of the host to run on more than one of the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="9c79e-105">中的其他组件的冗余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，可以通过为中的资源配置组件实现[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="9c79e-105">Redundancy for other components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment can be accomplished by configuring the components as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9c79e-106">此外可以适应 BizTalk 主机配置中的资源为[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集，建议以提供高可用性，对于某些 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="9c79e-106"> also accommodates configuring BizTalk Hosts as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, which is recommended to provide high availability for certain BizTalk adapters.</span></span>  
  
 <span data-ttu-id="9c79e-107">本部分介绍如何为中的功能组件提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="9c79e-107">This section describes how to provide high availability for the functional components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c79e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="9c79e-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9c79e-109">规划高 Availability2</span><span class="sxs-lookup"><span data-stu-id="9c79e-109">Planning for High Availability2</span></span>](../technical-guides/planning-for-high-availability2.md)  
  
-   [<span data-ttu-id="9c79e-110">BizTalk 主机的高可用性</span><span class="sxs-lookup"><span data-stu-id="9c79e-110">High Availability for BizTalk Hosts</span></span>](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="9c79e-111">数据库的高可用性</span><span class="sxs-lookup"><span data-stu-id="9c79e-111">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)  
  
-   [<span data-ttu-id="9c79e-112">主密钥服务器的高可用性</span><span class="sxs-lookup"><span data-stu-id="9c79e-112">High Availability for the Master Secret Server</span></span>](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c79e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c79e-113">See Also</span></span>  
 [<span data-ttu-id="9c79e-114">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="9c79e-114">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)