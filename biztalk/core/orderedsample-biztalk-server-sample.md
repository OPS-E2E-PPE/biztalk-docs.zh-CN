---
title: OrderedSample （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84490c48cc4f43f226cc65d4baa90ce7bca347f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322252"
---
# <a name="orderedsample-biztalk-server-sample"></a>OrderedSample （BizTalk Server 示例）
OrderedSample 示例演示如何使用业务流程接收和发送往返过程方式中的一系列有序的消息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例假定它从中接收消息的 MQSeries 队列中有消息。 当适配器读取来自 MQSeries 队列的消息时，它按顺序读取消息，并将其提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 在业务流程，接收端口**mqreceive**，具有其**按序送达**属性设置为**True**。  
  
 为发送方，业务流程发送一条消息，然后等待发送下一条消息之前送达通知。 发送端口**mqsend**具有其**送达通知**属性设置为**传输**。 若要简化该示例，该业务流程使用无限循环。  
  
 业务流程可以接收消息批和单个消息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|----------|-----------------|  
|OrderedReceiveSend.btproj,<br /><br /> OrderedReceiveSend.sln|应用程序的项目和解决方案文件。|  
|OrderedReceiveSendOrchestration.odx|应用程序的业务流程。|  
|OrderedSample.snk|强名称密钥文件。|  
|**Setup.bat**|生成并初始化本示例。|  
  
## <a name="building-and-running-the-sample"></a>构建和运行示例  
  
#### <a name="to-build-and-deploy-the-sample"></a>若要生成并部署示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   1.  创建项目的强名称密钥。  
  
   2.  编译并部署业务流程项目。  
  
   如果必须为 MQSeries Server for Windows 安装所需的权限，您可以创建 MQSeries 队列通过适配器对话框，并可以跳过下一步的过程。 如果还没有这样的访问权限，可以创建使用 IBM WebSphere MQ Explorer 的队列。 若要创建的队列通过 WebSphere MQ Explorer，请完成以下步骤。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>创建通过 WebSphere MQ Explorer MQSeries 队列  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>通过 WebSphere MQ Explorer 创建 MQSeries 队列  
  
1.  单击**启动**，依次指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  
  
2.  双击**队列管理器**，然后双击**默认队列管理器**。 默认的队列管理器通常命名为的 QM_ < m a c h > 其中是您的计算机的名称。  
  
3.  右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  
  
4.  在中**创建本地队列**对话框中**队列名称**，类型 **"queue1"**，然后单击**确定**。  
  
5.  右键单击**队列**，单击**新建**，然后单击**本地队列**。  
  
6.  在中**创建本地队列**对话框中**队列名称**，类型 **"queue2"**，然后单击**确定**。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
 此过程创建发送端口和接收位置发送到消息并接收来自 MQSeries 的相关消息。 时创建的接收位置，如果不是已创建，也可创建 MQSeries 队列。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
4.  在中**单向接收端口属性**对话框框中，键入，在**名称**框中，键入**OrderedSampleReceive**然后单击**确定**。  
  
5.  在左窗格中，单击**接收位置**选项卡，然后依次**新建**。  
  
6.  在中**接收位置属性**对话框中**名称**框中，键入"**OrderedSampleReceiveLocation**"。  
  
7.  在中**传输类型**框中，选择**MQSeries**。  
  
8.  在中**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
9. 在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
10. 单击**配置**。  
  
11. 在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入 **"10"**。  
  
12. 在中**队列定义**框中，单击**省略号 （...）** 按钮。  
  
13. 在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
14. 在中**队列管理器**框中，选择**默认队列管理器**。  
  
15. 在中**队列**框中，键入" **queue1**"，然后单击**导出**。  
  
16. 在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>若要创建的发送端口和 MQSeries 队列  
  
1.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在中**静态端口属性**对话框框中，键入，在**名称**框中，键入"**OrderedSampleSend**"。  
  
3.  在中**传输类型**框中，选择**MQSeries**。  
  
4.  在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
5.  单击**配置**。  
  
6.  在中**MQSeries 传输属性**对话框中**队列定义**框中，单击**省略号 （...）** 按钮。  
  
7.  在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
8.  在中**队列管理器**框中，选择**默认队列管理器**。  
  
9. 在中**队列**框中，键入" **queue2**"，然后单击**导出**。  
  
10. 在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置并启动发送端口  
  
1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  
  
2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  
  
3.  在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**  
  
#### <a name="to-bind-and-start-the-orchestration"></a>绑定和启动业务流程  
  
1.  在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。  
  
2.  双击**OrderedSampleOrchestration**业务流程，并单击**绑定**。  
  
3.  将业务流程端口绑定到以下发送端口和接收位置：  
  
    |业务流程端口|消息传送端口 / 接收位置|  
    |------------------------|----------------------------------------|  
    |mqreceive|OrderedSampleReceive|  
    |mqsend|OrderedSampleSend|  
  
4.  单击**主机**。  
  
5.  在中**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。  
  
6.  右键单击**业务流程**然后单击**启动**。  
  
#### <a name="to-run-the-sample"></a>若要运行示例  
  
1.  启动业务流程。  
  
2.  将消息放入已从其配置接收位置读取 MQSeries 队列。  
  
3.  已向其配置发送端口以发送消息的发送队列中在 WebSphere MQ Explorer 中查看的消息。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)