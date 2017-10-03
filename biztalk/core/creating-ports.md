---
title: "创建端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb7ff7d93b754285e9ed0eb627ca24b113bd2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-ports"></a>创建端口
使用以下过程可创建单一登录的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收端口。  
  
## <a name="creating-a-send-port"></a>创建发送端口  
  
#### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SSOSendToPeopleSoft`。  
  
    2.  从**类型**下拉列表中，选择**PeopleSoft**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  单击**配置**配置发送端口。  
  
4.  在**PeopleSoft 传输属性**对话框框中，执行以下操作：  
  
    1.  展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。  
  
         您不必设置登录信息。  
  
    2.  在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  单击 **“确定”**。  
  
5.  单击 **“确定”**。  
  
## <a name="creating-a-receive-port"></a>创建接收端口  
  
#### <a name="to-create-a-receive-port"></a>若要创建接收端口  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on2.md)