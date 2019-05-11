---
title: 创建 FRR 接收位置从 SWIFT 接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1912187c299e959c1a4f56c6650201efc5b37246
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378405"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a>创建 FRR 接收位置从 SWIFT 接收
若要执行 FIN 响应对帐，您需要创建到 A4SWIFT 从 SWIFT 网络接收消息的接收位置。  
  
> [!NOTE]
>  建议您设置两个接收位置接收来自 SAA 的消息： 一个用于接收平移/Nan，另一个用于接收其他消息。 若要设置两个接收位置，你必须从位于 SAA 的两个 MQSeries 队列接收消息： 一个用于平移/Nan，一个为所有其他消息类型。  
  
 **摘要**  
  
 创建接收位置具有以下属性和组件：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|接收端口|单向端口|  
|传输类型|MQSeries|  
|队列定义 (MQSeries)|MQSeries 服务器<br />队列管理器<br />队列|  
|接收处理程序|BizTalkServerApplication|  
|接收管道|A4SWIFT 接收的 FRR 创建的管道|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a>若要添加 FRR 接收位置以便接收来自 SWIFT  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。  
  
2.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
3.  在接收端口属性对话框中，在**名称**框中，键入接收端口，例如 FRRSWIFTReceivePort 的名称。  
  
4.  单击**Apply**以绑定端口，然后单击**确定**。  
  
5.  在管理控制台中，右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
6.  在选择接收端口对话框中，选择接收端口刚刚创建，然后依次**确定**。  
  
7.  在接收位置属性对话框中，在**名称**框中，键入接收位置，例如 FRRSWIFTReceiveLocation 的名称。  
  
8.  在中**传输**部分中，对于**类型**文本框中，选择**MQSeries**。  
  
9. 单击**配置**。  
  
10. 在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 (**...**) 按钮。  
  
11. 在中**队列定义**对话框中，输入的 MQSeries 服务器、 队列管理器和队列。 单击“确定” 。  
  
12. 在中**MQSeries 传输属性**对话框框中，验证属性是否根据需要。 单击“确定” 。  
  
    > [!NOTE]
    >  MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。  
  
13. 在接收位置属性对话框中，对于**接收处理程序**，选择**BizTalkServerApplication**。  
  
14. 有关**接收管道**部分中，选择此项 A4SWIFT 接收的 FRR 创建管道。  
  
15. 单击**Apply**，然后单击**确定**  
  
16. 在 BizTalk 浏览器中，右键单击您刚接收位置创建，然后依次**启用**。