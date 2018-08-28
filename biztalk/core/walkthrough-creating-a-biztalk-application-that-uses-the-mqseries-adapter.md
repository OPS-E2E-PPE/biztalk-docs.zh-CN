---
title: 演练： 创建 BizTalk 应用程序使用 MQSeries 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c086c69dee4318b9ab15f8746291594a815870
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024523"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a>演练： 创建使用 MQSeries 适配器的 BizTalk 应用程序
本部分将指导您创建使用 MQSeries 适配器的简单 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。  
  
> [!NOTE]
>  该应用程序假定您已在安装 BizTalk Server 的计算机上安装了 IBM WebSphere MQ（面向 Windows 平台的服务器组件）。 并假定您尚未创建任何发送端口或接收位置。 如果已存在发送端口或接收位置，请在执行以下步骤时替换相应的名称。  
  
 该应用程序是一个简单的基于内容的路由应用程序，仅使用一个接收位置和一个发送端口。 接收位置从 IBM WebSphere MQ 队列读取消息。 发送端口从接收位置获取消息，然后将其发送到其他 IBM WebSphere MQ 队列。  
  
 若要创建该应用程序，必须创建 IBM WebSphere MQ 队列，设置 BizTalk Server 接收位置和发送端口，启动发送端口并启用接收位置，并在队列中放入测试消息。  
  
 如果您具有安装 IBM WebSphere MQ 所需的权限，可以通过适配器对话框创建 IBM WebSphere MQ 队列，并可以跳过下一过程。 如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器，面向 Windows 平台的客户端组件）来创建队列。 若要通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）管理单元创建队列，请执行以下步骤。  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a>通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）创建 IBM WebSphere MQ 队列  
 按照以下步骤，通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）创建 IBM WebSphere MQ 队列：  
  
1. 单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  
  
2. 双击**队列管理器**，然后双击默认的队列管理器。 默认的队列管理器通常命名为 **QM_ * * * < m a c h >* 其中*machine_name*是您的计算机的名称。  
  
3. 右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  
  
4. 在中**创建本地队列**对话框中**队列名称**，类型**BTStoMQS**，然后单击**确定**。  
  
5. 右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  
  
6. 在中**创建本地队列**对话框中**队列名称**，类型**MQStoBTS**，然后单击**确定**。  
  
   以下步骤将创建接收位置和发送端口，然后启动该发送端口并启用该接收位置。 还将创建 IBM WebSphere MQ 队列。  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
 按照以下步骤创建接收位置和 MQSeries 队列：  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开默认值应用程序 (**BizTalk Application 1**默认情况下)。  
  
2.  右键单击**接收端口**节点中，单击**新建**，然后选择**单向端口**。  
  
3.  在中**接收端口属性**对话框中**名称**框中，键入**MQStoBTS**。  
  
4.  在左窗格中，单击**接收位置**，然后在右窗格中，单击**新建**。  
  
5.  在中**接收位置属性**对话框中**名称**框中，键入**MQStoBTS**。  
  
6.  选择**MQSeries**下拉列表中下一步**类型**选项。  
  
7.  在中**传输**部分中，单击**配置**。  
  
8.  在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入**1**。  
  
9. 在中**队列定义**框中，单击省略号 (**...**) 按钮。  
  
10. 在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
11. 在中**队列管理器**框中，选择默认的队列管理器。  
  
12. 在中**队列**框中，键入**MQStoBTS**，然后单击**导出**。  
  
13. 在**导出**对话框中，单击**Create Queue**，然后单击**确定**并**确定**再次以返回到**接收位置属性**对话框。  
  
14. 在中**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
15. 在中**接收管道**框中，选择**PassThruReceive**。  
  
16. 单击**确定**以应用更改。  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
 按照以下步骤创建发送端口和 MQSeries 队列：  
  
1.  右键单击**发送端口**，单击**新建**，然后选择**静态单向发送端口**。  
  
2.  在中**发送端口属性**对话框中**名称**框中，键入**BTStoMQS。**  
  
3.  选择**MQSeries**下拉列表中下一步**类型**选项。  
  
4.  在中**传输**部分中，单击**配置**。  
  
5.  在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 (**...**) 按钮。  
  
6.  在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
7.  在中**队列管理器**框中，选择默认的队列管理器。  
  
8.  在中**队列**框中，键入**BTStoMQS**，然后单击**导出**。  
  
9. 在**导出**对话框中，单击**Create Queue**，然后单击**确定**并**确定**再次以返回到**发送端口属性**对话框。  
  
10. 在中**发送管道**框中，选择**PassThruTransmit**。  
  
11. 单击此项可选择**筛选器**在左窗格中，然后在右窗格中配置筛选器选项。  
  
12. 在中**属性**下拉列表中，选择**BTS。ReceivePortName**。  
  
13. 在中**值**框中，键入**MQStoBTS**。  
  
14. 单击**确定**以应用更改。  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置并启动发送端口  
 请遵循以下步骤来启用接收位置和启动发送端口：  
  
1. 右键单击**MQStoBTS**接收位置，然后依次**启用**。  
  
2. 右键单击**BTStoMQS**发送端口，然后依次**启动**。  
  
   下一步将通过向接收队列发送测试消息来测试应用程序。  
  
## <a name="to-test-the-application"></a>测试应用程序  
 按照以下步骤来测试应用程序：  
  
1. 单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  
  
2. 右键单击**MQStoBTS**，然后单击**放置测试消息**。  
  
3. 在中**消息数据**框中，键入测试消息。 单击“确定” 。  
  
   输入数据后**当前深度**有关**MQStoBTS**队列是一 (1)。 当应用程序处理消息时，计数将返回到零 (0) 和**当前深度**有关**BTStoMQS**变为一 （1)。 您还可以查看消息的内容。  
  
## <a name="to-view-the-message"></a>若要查看消息  
 请遵循以下步骤查看消息：  
  
1.  双击**BTStoMQS**队列。  
  
2.  双击该消息，并选择**数据**工作表。 您可以查看中的消息的文本**消息数据**框。  
  
3.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器是什么？](../core/what-is-the-mqseries-adapter.md)   
 [MQSeries 适配器的体系结构](../core/mqseries-adapter-architecture.md)