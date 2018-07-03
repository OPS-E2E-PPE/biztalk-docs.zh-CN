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
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous 事件和接收位置
任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。 这一概念*事件*是消息的其他 TIBCO Rendezvous 程序生成。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  创建接收位置。  
  
2.  将接收位置与主机相关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置都必须具有唯一名称。 同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。  
> 
> [!IMPORTANT]
>  建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。 例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)