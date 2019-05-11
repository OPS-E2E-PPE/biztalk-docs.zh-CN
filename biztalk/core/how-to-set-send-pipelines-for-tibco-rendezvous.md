---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 062194b411096af3e03afee826b73efad09c2036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383899"
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a>如何设置 TIBCO Rendezvous 的发送管道
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器要求你选择 XMLTransmit 和 XMLReceive 的发送和接收管道，分别。  
  
### <a name="to-set-pipelines"></a>若要设置管道  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCORV`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO Rendezvous**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
4.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)