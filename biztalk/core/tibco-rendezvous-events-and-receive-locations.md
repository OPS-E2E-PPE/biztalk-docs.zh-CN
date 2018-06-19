---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: b93e747cdc665fb5a8407ca2a3d052b880236378
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013036"
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO 集合事件和接收位置
任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。 这一概念*事件*是代的其他 TIBCO 会合程序的消息。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  创建接收位置。  
  
2.  将接收位置与主机相关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置已启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置都必须具有唯一名称。 同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。  
  
> [!IMPORTANT]
>  建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。 例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)