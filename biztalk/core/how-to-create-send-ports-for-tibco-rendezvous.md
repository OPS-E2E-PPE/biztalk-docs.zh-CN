---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c3fe43f5ec5f69c84d9f679325a7437d84f2b7d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338923"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>如何创建 TIBCO Rendezvous 的发送端口
请遵循以下步骤创建发送端口使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCORV`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO Rendezvous**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从**发送管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。 从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  单击**配置**可配置的发送端口。  
  
4.  在中**TIBCO Rendezvous 传输属性**对话框框中，执行以下操作：  
  
    1.  输入的属性。  
  
         不需要设置的登录信息。  
  
    2.  在列表中，选择为表示 TIBCO Rendezvous 系统所创建的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  单击“确定” 。  
  
5.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)