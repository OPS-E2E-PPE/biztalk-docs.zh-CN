---
title: "MQSCorrelationSetOrchestrationWithSolicitResponse （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2665967e27cf708fcdbbddf61a7b66c619757223
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a>MQSCorrelationSetOrchestrationWithSolicitResponse（BizTalk Server 示例）
MQSCorrelationSetOrchestrationWithSolicitResponse 示例将演示如何使用 MQSeries Server 而非 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的相关标识符。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 业务流程将具有空值的消息发送**MQMD_MsgID**消息标头中的属性。 MQSeries 生成 MessageID 和 CorrelationID 和返回值分配给消息**MQMD_MsgID**和**MQMD_CorrelId**请求-响应中的响应的一部分发送的适配器的端口. 业务流程使用生成的相关标识符来初始化相关集和关联集在后续的如下所示通过检查接收位置**MQMD_CorrelId**消息的属性。 适配器还会将分配到的相关标识符**BizTalk_CorrelationID**，你还可以使用它在业务流程。 有关使用了该适配器的相关性标识符的详细信息，请参阅[关联消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。  
  
> [!IMPORTANT]
>  如果来自 MQSeries Server 的消息在相关标识符之前到达，则使用此方法的业务流程可能出现问题。 确保将您的业务流程设计为允许 MQSeries Server 具有足够的时间返回相关标识符。 此示例未考虑可能出现争用情况。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**文件**|**Description**|  
|--------------|---------------------|  
|**MQSCorrelationSolicitResponse.btproj，**<br /><br /> **MQSCorrelationSolicitResponse.sln**|应用程序的项目和解决方案文件。|  
|**MQSCorrelationSolicitResponse.odx**|应用程序的 BizTalk 业务流程文件。|  
|**MQSCorrelationSolicitResponse.snk**|强命名密钥文件。|  
|Setup.bat|生成并初始化本示例。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 若要创建应用程序，必须完成以下步骤：  
  
-   创建两个 MQSeries 队列。  
  
-   设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的接收位置和发送端口。  
  
-   启用接收位置。  
  
-   开始发送端口。  
  
-   创建相应文件夹。  
  
-   修改业务流程。  
  
-   部署、绑定并启动业务流程。  
  
 如果您具有安装 MQSeries Server for Windows 的必需权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过下一过程。 如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer 来创建队列。 若要通过 WebSphere MQ Explorer 创建队列，请完成下列步骤。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>创建通过 WebSphere MQ 资源管理器的 MQSeries 队列  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>若要创建 MQSeries 队列通过 WebSphere MQ 资源管理器  
  
1.  单击**启动**，指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ 资源管理器**。  
  
2.  双击**队列管理器**，然后双击默认队列管理器。 默认的队列管理器通常命名为**QM_***< machine_name >*其中*machine_name*是你的计算机的名称。  
  
3.  右键单击**队列**，指向**新建**，然后单击**本地队列**。  
  
4.  在**创建本地队列**对话框中，在**队列名称**，键入"REPLYTOQ"，然后单击**确定**。  
  
5.  右键单击**队列**，单击**新建**，然后单击**本地队列**。  
  
6.  在**创建本地队列**对话框中，在**队列名称**，键入"SOLICITRESPONSEQ"，然后单击**确定**。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
 此过程将创建发送端口和接收位置，以便向 MQSeries 发送消息以及接收来自 MQSeries 的相关消息。 创建接收位置时，还将创建 MQSeries 队列（如果尚未创建）。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>若要创建接收位置和 MQSeries 队列  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
4.  在**单向接收端口属性**对话框中，在**名称**框中，键入"MQReply"，然后单击**确定**。  
  
5.  在左窗格中，单击**接收位置**选项卡上，并依次**新建**。  
  
6.  在**接收位置属性**对话框中，在**名称**框中，键入"MQReply"。  
  
7.  在**传输类型**框中，选择**MQSeries**。  
  
8.  在**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
9. 在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
10. 单击**配置**。  
  
11. 在**MQSeries 传输属性**对话框中，在**轮询间隔**框中，键入"10"。  
  
12. 在**队列定义**框中，单击省略号 （…） 按钮。  
  
13. 在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。  
  
14. 在**队列管理器**框中，选择默认的队列管理器。  
  
15. 在**队列**框中，键入"REPLYTOQ"，然后单击**导出**。  
  
16. 在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>若要创建的发送端口和 MQSeries 队列  
  
1.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在**发送端口属性**对话框中，在**名称**框中，键入"MQSolicitResponse"。  
  
3.  在**传输类型**框中，选择**MQSeries**。  
  
4.  在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
5.  在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
6.  单击**配置**。  
  
7.  在**MQSeries 传输属性**对话框中，在**队列定义**框中，单击省略号 （…） 按钮。  
  
8.  在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。  
  
9. 在**队列管理器**框中，选择默认的队列管理器。  
  
10. 在**队列**框中，键入"SOLICITRESPONSEQ"，然后单击**导出**。  
  
11. 在导出对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>启用接收位置和启动发送端口  
 此过程创建在业务流程中接收文件所需的文件夹，并向输出文件夹发送相关消息和响应消息。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置和启动发送端口  
  
1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  
  
2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  
  
3.  在细节窗格中，右键单击**MQOut**发送端口和单击**启动。**  
  
## <a name="creating-the-folders-used-by-the-application"></a>创建应用程序使用的文件夹  
  
#### <a name="to-create-the-folders-used-by-the-application"></a>创建应用程序使用的文件夹  
  
1.  如果没有应用程序使用的文件夹，请在 C:\ 驱动器上创建一个名为“temp”的文件夹。  
  
2.  下创建文件夹**C:\temp**目录名称为"Pickup2"、"Dropit2"和"MoveIt"。  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a>修改应用程序使用业务流程  
 此过程将修改应用程序使用的业务流程。  
  
||  
|-|  
|修改应用程序使用的业务流程|  
|-在 Microsoft 中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，双击解决方案文件， **MQSCorrelationSolicitResponse.sln**，若要打开解决方案。<br /><br /> -从解决方案资源管理器窗格中，双击业务流程**MQSCorrelationSolicitResponse.odx**查看业务流程。<br /><br /> -双击消息赋值形状**MessageAssignment_1**若要启动 BizTalk 表达式编辑器。<br /><br /> -输入下面的表达式的相应 MQSeries 队列管理器名称：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> -如果您要用于从 BizTalk 发送到包含原始消息而不是第一个 100 个字节的全部内容的响应消息，修改以下行中使用 BizTalk 表达式编辑器。<br /><br /> -原始行：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> 将更改为：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> -在 BizTalk 表达式编辑器中，单击**确定**以保存修改后的表达式。<br /><br /> -在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**文件**，然后选择**保存所有**。|  
  
## <a name="building-and-deploying-the-sample"></a>构建和部署示例  
 此过程将生成并部署包含在此应用程序中使用的业务流程的解决方案。  
  
#### <a name="to-build-and-deploy-the-sample"></a>生成和部署示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    1.  为项目创建强名称密钥。  
  
    2.  编译并部署业务流程项目。  
  
    3.  使用文件适配器创建发送端口和接收端口。  
  
    > [!NOTE]
    >  由于此业务流程指定了使用文件适配器收发文件的绑定，因此，在部署业务流程时，将创建所需的发送端口、接收端口和接收位置，以便接收文件并将其放置到业务流程中，并输出相关消息和响应消息。  
  
## <a name="binding-and-starting-the-orchestration"></a>绑定和启动业务流程  
 此过程将业务流程绑定到主机以及相应的发送端口和接收位置。  
  
#### <a name="to-bind-and-start-the-orchestration"></a>绑定和启动业务流程的步骤  
  
1.  在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。  
  
2.  在细节窗格中，右键单击**MQSCorrelationSolicitResponse**业务流程和单击**绑定**。  
  
3.  将业务流程端口绑定到下列发送端口和接收位置：  
  
    |**业务流程端口**|**消息端口 / 接收位置**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSolicitResponse.Orchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQReply|  
    |SolicitResponsePort|MQSolicitResponse|  
    |TempPort|MQSCorrelationSolicitResponse.Orchestration.TempPort|  
    |FileSendPort|MQSCorrelationSolicitResponse.Orchestration.FileSendPort|  
  
4.  单击**主机**。  
  
5.  在**主机**框中，选择**BizTalkServerApplication**单击**确定**。  
  
6.  在**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.TempPort**，然后选择**启动**。  
  
7.  在**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileSendPort**，然后选择**启动**。  
  
8.  在**接收位置**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**，然后选择**启用**。  
  
9. 右键单击业务流程和单击**启动**。  
  
    > [!NOTE]
    >  启动业务流程还将自动登记该业务流程。  
  
## <a name="testing-the-application"></a>测试应用程序  
 此过程将测试应用程序。  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1.  将文件放入**C:\Temp\Pickup2**文件夹。  
  
2.  检查中的文件**C:\Temp\Dropit2**文件夹和**C:\Temp\Moveit**文件夹。  
  
    -   **C:\Temp\Dropit2**文件夹应包含最初已由身份选取消息的副本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    -   **C:\Temp\Moveit**文件夹应包含带有消息标识符 (MQMD_MsgId) 和相关标识符 (MQMD_CorrelId) 的响应文档。  
  
    > [!NOTE]
    >  如果禁用**MQReply**接收位置，你可以检查 WebSphere MQ 资源管理器中的消息，并查看是否设置的消息和关联的标识符。 若要执行此操作，启动**WebSphere MQ 资源管理器**和检查消息放入**REPLYTOQ**队列。 上显示的消息和相关标识符**标识符**选项卡**Messageproperties**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [使消息使用请求-答复关联](../core/correlating-messages-using-request-reply.md)   
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)