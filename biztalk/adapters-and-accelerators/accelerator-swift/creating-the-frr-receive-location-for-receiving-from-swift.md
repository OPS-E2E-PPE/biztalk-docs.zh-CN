---
title: "创建 FRR 接收位置用于接收从 SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43ac2ac0fab9b2a29a44784032f9d3369833ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a>创建 FRR 来接收来自 SWIFT 接收位置
若要执行 FIN 响应对帐，你需要创建到 A4SWIFT 从 SWIFT 网络接收消息的接收位置。  
  
> [!NOTE]
>  建议你设置两个接收从 SAA 接收消息的位置： 一个用于接收平移/Nan，另一个为接收其他消息。 若要设置两个接收位置，你必须从在 SAA 的两个 MQSeries 队列接收消息： 一个用于平移/Nan，一个对于所有其他消息类型。  
  
 **摘要**  
  
 创建具有以下属性和组件接收位置：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|接收端口|单向端口|  
|传输类型|MQSeries|  
|队列定义 (MQSeries)|MQSeries 服务器<br />队列管理器<br />队列|  
|接收处理程序|BizTalkServerApplication|  
|接收管道|A4SWIFT 接收为 FRR 创建的管道|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a>若要添加 FRR 接收位置用于接收从 SWIFT  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。  
  
2.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在接收端口属性对话框中，在**名称**框中，键入接收端口，如 FRRSWIFTReceivePort 的名称。  
  
4.  单击**应用**以绑定端口，然后单击**确定**。  
  
5.  在管理控制台中，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
6.  在选择接收端口对话框中，选择你刚接收端口创建，，然后单击**确定**。  
  
7.  在接收位置属性对话框中，在**名称**框中，键入接收位置，如 FRRSWIFTReceiveLocation 的名称。  
  
8.  在**传输**部分中，为**类型**文本框中，选择**MQSeries**。  
  
9. 单击**配置**。  
  
10. 在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 (**...**) 按钮。  
  
11. 在**队列定义**对话框中，输入 MQSeries 服务器，队列管理器，并排入队列。 单击 **“确定”**。  
  
12. 在**MQSeries 传输属性**对话框框中，验证属性是否根据需要。 单击 **“确定”**。  
  
    > [!NOTE]
    >  有关 MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。  
  
13. 在接收位置属性对话框中，为**接收处理程序**，选择**BizTalkServerApplication**。  
  
14. 有关**接收管道**部分中，选择 A4SWIFT 接收为 FRR 创建的管道。  
  
15. 单击**应用**，然后单击**确定**  
  
16. 在 BizTalk 资源管理器，右键单击你刚接收位置创建，并依次**启用**。