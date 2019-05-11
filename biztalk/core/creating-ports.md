---
title: 创建端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9370442e6f24222a361aa2a6c9901dca0772f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353632"
---
# <a name="creating-ports"></a>创建端口
使用以下过程创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口的单一登录。  
  
## <a name="creating-a-send-port"></a>创建发送端口  
  
#### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SSOSendToPeopleSoft`。  
  
    2.  从**类型**下拉列表中，选择**PeopleSoft**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  单击**配置**可配置的发送端口。  
  
4.  在中**PeopleSoft 传输属性**对话框框中，执行以下操作：  
  
    1.  展开**适配器所需的属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和用于连接到 Peoplesoft 系统的 Jar 文件。  
  
         不需要设置的登录信息。  
  
    2.  在列表中，选择创建为表示 PeopleSoft 系统的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  单击“确定” 。  
  
5.  单击“确定” 。  
  
## <a name="creating-a-receive-port"></a>创建接收端口  
  
#### <a name="to-create-a-receive-port"></a>若要创建的接收端口  
  
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
  
## <a name="see-also"></a>请参阅  
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)