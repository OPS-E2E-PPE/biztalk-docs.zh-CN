---
title: MQSCorrelationSetOrchestrationWithSolicitResponse （BizTalk Server 示例） |Microsoft Docs
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
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a41d62b7c8e578f7e89e7802ed5eaecd0e2b61
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443394"
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a>MQSCorrelationSetOrchestrationWithSolicitResponse（BizTalk Server 示例）
MQSCorrelationSetOrchestrationWithSolicitResponse 示例将演示如何使用 MQSeries Server 而非 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的相关标识符。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 业务流程发送一条消息为空值与**MQMD_MsgID**消息标头中的属性。 MQSeries 生成 MessageID 和 CorrelationID，并返回一条消息分配给的值与**MQMD_MsgID**并**MQMD_CorrelId**要求-响应中的响应的一部分发送的适配器的端口. 沿用相关集在后面的通过检查接收位置和业务流程使用生成的相关标识符初始化相关集**MQMD_CorrelId**消息属性。 适配器还将分配到的相关标识符**BizTalk_CorrelationID**，您还可以使用它在业务流程中。 有关与适配器配合使用相关标识符的详细信息，请参阅[关联的消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。  
  
> [!IMPORTANT]
>  如果来自 MQSeries Server 的消息在相关标识符之前到达，则使用此方法的业务流程可能出现问题。 确保将您的业务流程设计为允许 MQSeries Server 具有足够的时间返回相关标识符。 此示例未考虑可能出现争用情况。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**File**|**说明**|  
|--------------|---------------------|  
|**MQSCorrelationSolicitResponse.btproj,**<br /><br /> **MQSCorrelationSolicitResponse.sln**|应用程序的项目和解决方案文件。|  
|**MQSCorrelationSolicitResponse.odx**|应用程序的 BizTalk 业务流程文件。|  
|**MQSCorrelationSolicitResponse.snk**|强命名密钥文件。|  
|Setup.bat|生成并初始化本示例。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 若要创建应用程序，必须完成以下步骤：  
  
- 创建两个 MQSeries 队列。  
  
- 设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的接收位置和发送端口。  
  
- 启用接收位置。  
  
- 启动发送端口。  
  
- 创建相应文件夹。  
  
- 修改业务流程。  
  
- 部署、绑定并启动业务流程。  
  
  如果您具有安装 MQSeries Server for Windows 的必需权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过下一过程。 如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer 来创建队列。 若要通过 WebSphere MQ Explorer 创建队列，请完成下列步骤。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>创建通过 WebSphere MQ Explorer MQSeries 队列  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>通过 WebSphere MQ Explorer 创建 MQSeries 队列  
  
1.  单击**启动**，依次指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  
  
2.  双击**队列管理器**，然后双击默认的队列管理器。 默认的队列管理器通常命名为**QM_**_< m a c h >_ 其中*m a c h*是您的计算机的名称。  
  
3.  右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  
  
4.  在中**创建本地队列**对话框中**队列名称**，键入"REPLYTOQ"，然后单击**确定**。  
  
5.  右键单击**队列**，单击**新建**，然后单击**本地队列**。  
  
6.  在中**创建本地队列**对话框中**队列名称**，键入"SOLICITRESPONSEQ"，然后单击**确定**。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
 此过程将创建发送端口和接收位置，以便向 MQSeries 发送消息以及接收来自 MQSeries 的相关消息。 创建接收位置时，还将创建 MQSeries 队列（如果尚未创建）。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
4.  在中**单向接收端口属性**对话框中**名称**框中，键入"MQReply"，然后单击**确定**。  
  
5.  在左窗格中，单击**接收位置**选项卡，然后依次**新建**。  
  
6.  在中**接收位置属性**对话框中**名称**框中，键入"MQReply"。  
  
7.  在中**传输类型**框中，选择**MQSeries**。  
  
8.  在中**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
9. 在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
10. 单击**配置**。  
  
11. 在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入"10"。  
  
12. 在中**队列定义**框中，单击省略号 （...） 按钮。  
  
13. 在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
14. 在中**队列管理器**框中，选择默认的队列管理器。  
  
15. 在中**队列**框中，键入"REPLYTOQ"，然后单击**导出**。  
  
16. 在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>若要创建的发送端口和 MQSeries 队列  
  
1.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在中**发送端口属性**对话框中**名称**框中，键入"MQSolicitResponse"。  
  
3.  在中**传输类型**框中，选择**MQSeries**。  
  
4.  在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
5.  在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
6.  单击**配置**。  
  
7.  在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 （...） 按钮。  
  
8.  在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  
  
9. 在中**队列管理器**框中，选择默认的队列管理器。  
  
10. 在中**队列**框中，键入"SOLICITRESPONSEQ"，然后单击**导出**。  
  
11. 在导出对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>启用接收位置和启动发送端口  
 此过程创建在业务流程中接收文件所需的文件夹，并向输出文件夹发送相关消息和响应消息。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置并启动发送端口  
  
1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  
  
2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  
  
3.  在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**  
  
## <a name="creating-the-folders-used-by-the-application"></a>创建应用程序使用的文件夹  
  
#### <a name="to-create-the-folders-used-by-the-application"></a>创建应用程序使用的文件夹  
  
1.  如果没有应用程序使用的文件夹，请在 C:\ 驱动器上创建一个名为“temp”的文件夹。  
  
2.  下创建文件夹**C:\temp**目录名称为"Pickup2"、"Dropit2"和"MoveIt"。  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a>修改应用程序使用的业务流程  
 此过程将修改应用程序使用的业务流程。  
  
||  
|-|  
|修改应用程序使用的业务流程|  
|-在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，双击解决方案文件中， **MQSCorrelationSolicitResponse.sln**，若要打开该解决方案。<br /><br /> -从解决方案资源管理器窗格中，双击业务流程**MQSCorrelationSolicitResponse.odx**查看业务流程。<br /><br /> -双击消息赋值形状**MessageAssignment_1**以启动 BizTalk 表达式编辑器。<br /><br /> -输入下面的表达式的相应 MQSeries 队列管理器名称：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> -如果您要用于从 BizTalk 发送包含原始消息而不是仅前 100 个字节的全部内容的响应消息，修改以下行在 BizTalk 表达式编辑器。<br /><br /> 的原始行：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> 将更改为：<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> -在 BizTalk 表达式编辑器中，单击**确定**保存修改后的表达式。<br /><br /> -在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**文件**，然后选择**全部保存**。|  
  
## <a name="building-and-deploying-the-sample"></a>生成和部署示例  
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
  
2.  在细节窗格中，右键单击**MQSCorrelationSolicitResponse**业务流程，并单击**绑定**。  
  
3.  将业务流程端口绑定到下列发送端口和接收位置：  
  
    |**业务流程端口**|**消息传送端口 / 接收位置**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSolicitResponse.Orchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQReply|  
    |SolicitResponsePort|MQSolicitResponse|  
    |TempPort|MQSCorrelationSolicitResponse.Orchestration.TempPort|  
    |FileSendPort|MQSCorrelationSolicitResponse.Orchestration.FileSendPort|  
  
4.  单击**主机**。  
  
5.  在中**主机**框中，选择**BizTalkServerApplication**然后单击**确定**。  
  
6.  在中**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.TempPort**，然后选择**启动**。  
  
7.  在中**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileSendPort**，然后选择**启动**。  
  
8.  在中**接收位置**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**，然后选择**启用**。  
  
9. 右键单击该业务流程，然后单击**启动**。  
  
    > [!NOTE]
    >  启动业务流程还将自动登记该业务流程。  
  
## <a name="testing-the-application"></a>测试应用程序  
 此过程将测试应用程序。  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1. 将文件放入**C:\Temp\Pickup2**文件夹。  
  
2. 检查中的文件**C:\Temp\Dropit2**文件夹并**C:\Temp\Moveit**文件夹。  
  
   - **C:\Temp\Dropit2**文件夹应包含最初所提取的消息的副本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
   - **C:\Temp\Moveit**文件夹应包含带有消息标识符 (MQMD_MsgId) 和相关标识符 (MQMD_CorrelId) 的响应文档。  
  
   > [!NOTE]
   >  如果禁用**MQReply**接收位置，您可以检查在 WebSphere MQ Explorer 中的消息，请参阅设置消息和相关标识符。 若要执行此操作，启动**WebSphere MQ Explorer**并查看放置在消息**REPLYTOQ**队列。 消息和相关标识符显示在**标识符**选项卡**Messageproperties**对话框。  
  
## <a name="see-also"></a>请参阅  
 [使用请求-答复相关消息](../core/correlating-messages-using-request-reply.md)   
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)
