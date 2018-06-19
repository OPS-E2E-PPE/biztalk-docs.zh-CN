---
title: OrderedSample （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: 1b9e93c7bb9cb59088e465dc53dd992ffd5f1c11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974747"
---
# <a name="orderedsample-biztalk-server-sample"></a>OrderedSample（BizTalk Server 示例）
OrderedSample 示例演示如何使用业务流程以往返过程方式接收和发送一系列有序消息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例假设发送消息的 MQSeries 队列中存在消息。 当适配器读取来自 MQSeries 队列的消息时，适配器将按顺序读取消息，并将其提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 在业务流程，接收端口**mqreceive**，具有其**按序送达**属性设置为**True**。  
  
 对于发送端，业务流程将发送一个消息并等待传送通知，然后再发送下一个消息。 发送端口**mqsend**具有其**传递通知**属性设置为**传输**。 为了使此示例尽量简单，业务流程使用无限循环。  
  
 业务流程可接收消息批和单个消息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|----------|-----------------|  
|OrderedReceiveSend.btproj、<br /><br /> OrderedReceiveSend.sln|应用程序的项目和解决方案文件。|  
|OrderedReceiveSendOrchestration.odx|应用程序的业务流程。|  
|OrderedSample.snk|强命名密钥文件。|  
|**Setup.bat**|生成并初始化本示例。|  
  
## <a name="building-and-running-the-sample"></a>生成和运行示例  
  
#### <a name="to-build-and-deploy-the-sample"></a>生成和部署示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    1.  为项目创建强名称密钥。  
  
    2.  编译并部署业务流程项目。  
  
 如果您具有安装 MQSeries Server for Windows 的必需权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过下一过程。 如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer 来创建队列。 若要通过 WebSphere MQ Explorer 创建队列，请完成下列步骤。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>创建通过 WebSphere MQ 资源管理器的 MQSeries 队列  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>若要创建 MQSeries 队列通过 WebSphere MQ 资源管理器  
  
1.  单击**启动**，指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ 资源管理器**。  
  
2.  双击**队列管理器**，然后双击**默认队列管理器**。 默认的队列管理器通常命名为的 QM_ < machine_name > machine_name 所在计算机的名称。  
  
3.  右键单击**队列**，指向**新建**，然后单击**本地队列**。  
  
4.  在**创建本地队列**对话框中，在**队列名称**，类型 **"queue1"**，然后单击**确定**。  
  
5.  右键单击**队列**，单击**新建**，然后单击**本地队列**。  
  
6.  在**创建本地队列**对话框中，在**队列名称**，类型 **"queue2"**，然后单击**确定**。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
 此过程将创建发送端口和接收位置，以便向 MQSeries 发送消息以及接收来自 MQSeries 的相关消息。 创建接收位置时，还将创建 MQSeries 队列（如果尚未创建）。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>若要创建接收位置和 MQSeries 队列  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
4.  在**单向接收端口属性**对话框框中，键入，在**名称**框中，键入**OrderedSampleReceive**单击**确定**。  
  
5.  在左窗格中，单击**接收位置**选项卡上，并依次**新建**。  
  
6.  在**接收位置属性**对话框中，在**名称**框中，键入"**OrderedSampleReceiveLocation**"。  
  
7.  在**传输类型**框中，选择**MQSeries**。  
  
8.  在**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
9. 在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
10. 单击**配置**。  
  
11. 在**MQSeries 传输属性**对话框中，在**轮询间隔**框中，键入 **"10"**。  
  
12. 在**队列定义**框中，单击**省略号 （...）** 按钮。  
  
13. 在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。  
  
14. 在**队列管理器**框中，选择**默认队列管理器**。  
  
15. 在**队列**框中，键入" **queue1**"，然后单击**导出**。  
  
16. 在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>若要创建的发送端口和 MQSeries 队列  
  
1.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在**静态端口属性**对话框框中，键入，在**名称**框中，键入"**OrderedSampleSend**"。  
  
3.  在**传输类型**框中，选择**MQSeries**。  
  
4.  在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
5.  单击**配置**。  
  
6.  在**MQSeries 传输属性**对话框中，在**队列定义**框中，单击**省略号 （...）** 按钮。  
  
7.  在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。  
  
8.  在**队列管理器**框中，选择**默认队列管理器**。  
  
9. 在**队列**框中，键入" **queue2**"，然后单击**导出**。  
  
10. 在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置和启动发送端口  
  
1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  
  
2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  
  
3.  在细节窗格中，右键单击**MQOut**发送端口和单击**启动。**  
  
#### <a name="to-bind-and-start-the-orchestration"></a>若要将绑定和启动业务流程  
  
1.  在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。  
  
2.  双击**OrderedSampleOrchestration**业务流程，，然后单击**绑定**。  
  
3.  将业务流程端口绑定到下列发送端口和接收位置：  
  
    |业务流程端口|消息传送端口/接收位置|  
    |------------------------|----------------------------------------|  
    |mqreceive|OrderedSampleReceive|  
    |mqsend|OrderedSampleSend|  
  
4.  单击**主机**。  
  
5.  在**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。  
  
6.  右键单击**Orchestration**单击**启动**。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  启动业务流程。  
  
2.  将消息放置到 MQSeries 队列中，已将接收位置配置为从此队列进行读取。  
  
3.  在 WebSphere MQ Explorer 中查看发送队列中的消息，已将发送端口配置为向此队列发送消息。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)