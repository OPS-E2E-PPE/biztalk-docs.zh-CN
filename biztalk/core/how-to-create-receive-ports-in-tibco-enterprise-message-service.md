---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4f579df64543ad21d923c37f6d97251d7655f552
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385460"
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a>如何创建 TIBCO Enterprise Message Service 中的接收端口
请按照下列步骤创建接收端口。  
  
### <a name="to-create-a-receive-port"></a>若要创建的接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
3.  在中**接收端口属性**窗口，然后在**常规**页上，执行以下操作：  
  
    1.  在中**名称**字段中，键入`ReceiveFromTIBCOEMS`。  
  
    2.  在中**身份验证**组框中，指定如何处理消息时使用身份验证。  
  
    3.  选择**失败消息启用路由功能**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在中**接收位置**窗口，然后在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择传输类型和从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择接收管道。  
  
    5.  上**计划**页上，选择**开始日期**并**结束日期**以限制接收文档。  
  
    6.  选择**启用服务时段**复选框。  
  
    7.  单击“确定” 。  
  
5.  上**入站映射**页上，选择用于转换所选端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击“确定” 。  
  
