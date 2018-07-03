---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 8fc76fb212d343bcafa67c5ea76f62899847b40e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984262"
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="40de7-101">TIBCO Rendezvous 事件和接收位置</span><span class="sxs-lookup"><span data-stu-id="40de7-101">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="40de7-102">任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="40de7-102">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="40de7-103">这一概念*事件*是消息的其他 TIBCO Rendezvous 程序生成。</span><span class="sxs-lookup"><span data-stu-id="40de7-103">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="40de7-104">以下步骤描述了接收位置的生命周期：</span><span class="sxs-lookup"><span data-stu-id="40de7-104">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="40de7-105">创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="40de7-105">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="40de7-106">将接收位置与主机相关联。</span><span class="sxs-lookup"><span data-stu-id="40de7-106">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="40de7-107">接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="40de7-107">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="40de7-108">接收位置启用。</span><span class="sxs-lookup"><span data-stu-id="40de7-108">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="40de7-109">接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="40de7-109">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="40de7-110">每个接收位置都必须具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="40de7-110">Each receive location must have a unique name.</span></span> <span data-ttu-id="40de7-111">同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="40de7-111">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="40de7-112">建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="40de7-112">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="40de7-113">例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="40de7-113">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40de7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="40de7-114">See Also</span></span>  
 [<span data-ttu-id="40de7-115">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="40de7-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)