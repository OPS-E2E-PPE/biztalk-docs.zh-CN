---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: cd807abafe2cf8769bf4816143facdaf37607d5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400150"
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="af0f8-101">TIBCO Rendezvous 事件和接收位置</span><span class="sxs-lookup"><span data-stu-id="af0f8-101">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="af0f8-102">任何 TIBCO Rendezvous 系统可以将消息发送到选择其使用者名称。</span><span class="sxs-lookup"><span data-stu-id="af0f8-102">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="af0f8-103">这一概念*事件*是消息的其他 TIBCO Rendezvous 程序生成。</span><span class="sxs-lookup"><span data-stu-id="af0f8-103">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="af0f8-104">以下步骤描述了接收位置的生命周期：</span><span class="sxs-lookup"><span data-stu-id="af0f8-104">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="af0f8-105">接收位置创建。</span><span class="sxs-lookup"><span data-stu-id="af0f8-105">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="af0f8-106">接收位置是与主机关联。</span><span class="sxs-lookup"><span data-stu-id="af0f8-106">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="af0f8-107">接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="af0f8-107">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="af0f8-108">接收位置启用。</span><span class="sxs-lookup"><span data-stu-id="af0f8-108">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="af0f8-109">接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="af0f8-109">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af0f8-110">每个接收位置必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="af0f8-110">Each receive location must have a unique name.</span></span> <span data-ttu-id="af0f8-111">两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="af0f8-111">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="af0f8-112">建议您设置加强的访问控制列表 (ACL) 中接收位置的存放位置。</span><span class="sxs-lookup"><span data-stu-id="af0f8-112">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="af0f8-113">例如，您必须设置加强的目录的 Acl 文件接收位置从其中提取消息，以便只有经过授权的用户可以在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="af0f8-113">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0f8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="af0f8-114">See Also</span></span>  
 [<span data-ttu-id="af0f8-115">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="af0f8-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)