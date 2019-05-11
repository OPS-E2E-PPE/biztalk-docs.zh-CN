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
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous 事件和接收位置
任何 TIBCO Rendezvous 系统可以将消息发送到选择其使用者名称。 这一概念*事件*是消息的其他 TIBCO Rendezvous 程序生成。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  接收位置创建。  
  
2.  接收位置是与主机关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置必须具有唯一的名称。 两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
> 
> [!IMPORTANT]
>  建议您设置加强的访问控制列表 (ACL) 中接收位置的存放位置。 例如，您必须设置加强的目录的 Acl 文件接收位置从其中提取消息，以便只有经过授权的用户可以在此位置中存放消息。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)