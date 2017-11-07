---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: e31246cf90f42206de6a22fcc32338fcb2936db3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a>如何创建 在 TIBCO Enterprise Message Service 中创建接收端口
请遵循以下步骤创建一个接收端口。  
  
### <a name="to-create-a-receive-port"></a>若要创建接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在**接收端口属性**窗口，请在**常规**页上，执行以下操作：  
  
    1.  在**名称**字段中，键入`ReceiveFromTIBCOEMS`。  
  
    2.  在**身份验证**组框中，指定使用身份验证时处理消息的方式。  
  
    3.  选择**启用路由失败消息**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择接收管道。  
  
    5.  上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。  
  
    6.  选择**启用服务窗口**复选框。  
  
    7.  单击 **“确定”**。  
  
5.  上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击 **“确定”**。  
  
