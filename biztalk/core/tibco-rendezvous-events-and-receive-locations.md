---
title: "TIBCO 集合事件和接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="4da64-102">TIBCO 集合事件和接收位置</span><span class="sxs-lookup"><span data-stu-id="4da64-102">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="4da64-103">任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="4da64-103">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="4da64-104">这一概念*事件*是代的其他 TIBCO 会合程序的消息。</span><span class="sxs-lookup"><span data-stu-id="4da64-104">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="4da64-105">以下步骤描述了接收位置的生命周期：</span><span class="sxs-lookup"><span data-stu-id="4da64-105">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="4da64-106">创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="4da64-106">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="4da64-107">将接收位置与主机相关联。</span><span class="sxs-lookup"><span data-stu-id="4da64-107">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="4da64-108">接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="4da64-108">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="4da64-109">接收位置已启用。</span><span class="sxs-lookup"><span data-stu-id="4da64-109">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="4da64-110">接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="4da64-110">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4da64-111">每个接收位置都必须具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="4da64-111">Each receive location must have a unique name.</span></span> <span data-ttu-id="4da64-112">同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="4da64-112">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4da64-113">建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="4da64-113">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="4da64-114">例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="4da64-114">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da64-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4da64-115">See Also</span></span>  
 [<span data-ttu-id="4da64-116">创建 TIBCO 会合接收处理程序</span><span class="sxs-lookup"><span data-stu-id="4da64-116">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)