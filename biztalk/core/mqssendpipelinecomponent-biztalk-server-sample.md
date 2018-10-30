---
title: MQSSendPipelineComponent （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc89b19f1e493c46e6128d390774479eb59bc6b0
ms.sourcegitcommit: e172dedfd00d4de3a40c8289f3a97ef65cdadd3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "36975910"
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a>MQSSendPipelineComponent（BizTalk Server 示例）
本示例演示如何写入从 XML 文件读取一组 MQSeries 属性值并将其应用到消息的管道组件。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包含两种[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目、 管道组件项目和一个进行的管道项目使用的管道组件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
  
- *\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent  
  
- *\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline  
  
  下表显示了本示例中的文件及其用途说明：  
  
|                                                                              **File**                                                                               |                                         **Description**                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln、<br /><br /> SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj |                    管道组件的项目和解决方案文件。                    |
|                                              SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs                                              |                      管道组件的 Visual C#® 源文件。                      |
|                                                      SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml                                                      |                 由管道组件读取和使用的 MQSeries 属性。                 |
|   SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj、<br /><br /> SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln   |                     BizTalk 管道的项目和解决方案文件。                     |
|                                               SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk                                               |                   BizTalk 管道项目的强名称密钥文件。                   |
|                                               SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp                                               | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道。 |
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 若要创建应用程序，必须完成以下步骤：  
  
1. 为应用程序创建文件夹。  
  
2. 修改和编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]管道组件项目。  
  
3. 将编译的程序集和头文件复制到相应文件夹。  
  
4. 修改 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。  
  
5. 编译和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道项目。  
  
6. 设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置。  
  
7. 创建 MQSeries 队列。  
  
8. 设置发送端口。  
  
9. 启用接收位置并启动发送端口。  
  
## <a name="creating-the-folders-for-the-application"></a>为应用程序创建文件夹  
 此过程将为应用程序创建相应文件夹。  
  
#### <a name="to-create-the-folders-for-the-application"></a>若要创建的应用程序的文件夹  
  
1.  创建名为的文件夹**temp**如果尚不存在在 C:\ 驱动器上。  
  
2.  在中创建文件夹**C:\temp**名为目录**Pickup3**。  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a>修改和编译管道组件的项目  
 此过程修改和编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]管道组件项目。  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a>修改和编译管道组件的项目  
  
1. 双击解决方案文件**SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln**以打开中的解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 双击类文件**CSetMQSeriesHeaderPropertyComponent.cs**以打开中的类文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
3. 找到变量**samplesDir**，验证此变量设置为位置**C:\temp**。  
  
4. 右键单击解决方案资源管理器中的解决方案，然后单击**生成**。 这会将项目编译到 dll 位于**SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** 目录。  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a>将程序集和头文件复制到相应文件夹  
 此过程将编译的程序集和头文件复制到相应文件夹。  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a>将编译的程序集和头文件复制到相应文件夹  
  
1. 将已编译的程序集复制**setmqseriesheaderpropertycomponent.dll 复制**到 BizTalk 管道组件文件夹。 BizTalk 管道组件文件夹的默认位置是 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 管道组件。  
  
2. 将 MQHeader 属性文件复制**setmqsmqmdhdrprops.xml 复制**到**C:\temp**目录。  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a>修改 BizTalk Server 管道项目  
 此过程修改 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a>修改 BizTalk Server 管道的项目  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过双击解决方案文件中，打开解决方案**SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln**。  
  
2. 为项目创建强名称密钥文件。 若要这样做，请执行以下操作：  
  
   1. 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符。  
  
   2. 将目录更改为\<示例路径\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent。  
  
   3. 键入以下命令：  
  
       `sn -k MQSSendPipelineComponent.snk`  
  
   4. 按 Enter。 这样将创建密钥文件。  
  
3. 在中**解决方案资源管理器**，右键单击项目，然后单击**属性**（在中心窗口中） 中的项目启动项目设计器。  
  
   1.  在项目设计器中，单击**签名**选项卡。  
  
   2.  在右侧窗格中，选择**为程序集签名**选项...  
  
   3.  单击下拉列表**选择强名称密钥文件**选项，然后单击**浏览**。  
  
   4.  浏览到\<\adaptersusage\mqseriesadapter\mqssendpipelinecomponent\mqssendpipelinecomponent.snk\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk，单击**打开**。  
  
4. 前面创建的管道组件已添加到**预组装**此管道项目阶段。 如果尚未添加此组件，则需要完成以下步骤来添加它：  
  
   1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]IDE 中，单击**工具箱**左侧和右侧的选项卡。  
  
   2. 右键单击**工具箱**，然后单击**选择项**。  
  
   3. 在中**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡上，选择**自定义组件以设置 MQseries 标头属性**组件，并然后单击**确定**。  
  
   4. 拖动**自定义组件以设置 MQseries 标头属性**组件**预组装**此管道阶段。  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a>编译和部署管道项目  
 此过程编译和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道项目。  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a>若要编译和部署管道项目  
  
1.  在解决方案资源管理器窗口中，右键单击该解决方案，然后单击**部署解决方案**。 这样会生成解决方案，并将程序集部署到 BizTalk 管理数据库。  
  
2.  验证程序集是否已部署到 BizTalk 管理数据库：  
  
    1.  打开 BizTalk 管理控制台。  
  
    2.  单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，然后单击以展开**程序集**文件夹。  
  
         已部署的管道程序集应在下可见**程序集**文件夹。  
  
## <a name="creating-the-receive-location"></a>创建接收位置  
 此过程创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置。  
  
#### <a name="to-create-the-receive-location"></a>若要创建接收位置  
  
1.  在 BizTalk Server 管理控制台中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
2.  在中**单向接收端口属性**对话框中**名称**框中，键入"MQReply"，然后单击**确定**。  
  
3.  在左窗格中，单击**接收位置**选项卡，然后依次**新建**。  
  
4.  在中**接收位置属性**对话框中**名称**字段中，键入"ReceiveFile"。  
  
5.  在中**传输类型**框中，选择**文件**。  
  
6.  在中**接收处理程序**字段中，选择**BizTalkServerApplication**。  
  
7.  在中**接收管道**字段中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
8.  在中**接收文件夹**字段中，键入"C:\temp\Pickup3"。  
  
9. 在中**文件掩码**字段中，键入"*。\*"。  
  
10. 单击**确定**，然后单击**确定**再次以退出**接收位置属性**对话框。  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a>创建通过 MQSeries Explorer MQSeries 队列  
 如果您拥有安装 MQSeries Server for Windows 所需的权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过接下来的过程。  
  
 如果您没有这样的访问权限，则可以通过以下过程使用 IBM WebSphere MQ Explorer 创建队列。  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a>通过 MQSeries Explorer 创建 MQSeries 队列  
  
1.  单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  
  
2.  双击**队列管理器**，然后双击默认的队列管理器。 默认的队列管理器通常命名为**QM_**\<*m a c h* \>其中*m a c h*是您的计算机的名称。  
  
3.  右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  
  
4.  在中**创建本地队列**对话框中**队列名称**，类型**SETHEADER**，然后单击**确定**。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>创建发送端口和 MQSeries 队列  
 此过程创建输出消息的发送端口。 创建发送端口时，如果尚未创建 MQSeries 队列，也将创建该队列。  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>若要创建的发送端口和 MQSeries 队列  
  
1.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在中**发送端口属性**对话框中**名称**框中，键入"MQSolicitResponse"。  
  
3.  在中**传输类型**框中，选择**MQSeries**。  
  
4.  在中**发送管道**框中，选择**SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**。  
  
5.  在中**筛选器**，添加具有以下名称/值对的新条目：  
  
    -   设置**属性**到"BTS。ReceivePortName"。  
  
    -   设置**运算符**到"= ="。  
  
    -   设置**值**为"ReceiveFile"。  
  
        > [!NOTE]
        >  这样会将发送端口设置为订阅在 ReceiveFile 接收端口上到达的消息。  
  
6.  单击**传输**。  
  
7.  在中**地址 (URI)** 字段中，单击省略号 （...） 按钮。  
  
8.  在中**MQSeries 传输属性**对话框中**队列定义**字段中，单击省略号 （...） 按钮。  
  
9. 在中**队列定义**对话框中**服务器名称**字段中，键入您的计算机名称。  
  
10. 在中**队列管理器**字段中，选择默认的队列管理器。  
  
11. 在队列字段中，键入"SETHEADER"，然后单击**导出**。  
  
12. 在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>启用接收位置和启动发送端口  
 此过程将启用接收位置并启动发送端口。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置并启动发送端口  
  
1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  
  
2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  
  
3.  在细节窗格中，右键单击**SetMQHeader**发送端口，然后单击**启动**。  
  
## <a name="testing-the-application"></a>测试应用程序  
 此过程将测试应用程序。  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1.  Put 将文件放**C:\Temp\Pickup3**文件夹。  
  
2.  启动 WebSphere MQ Explorer，双击 SETHEADER 队列以检查 SETHEADER 队列中的消息。  
  
     若要查看 SETHEADER 队列中的所有消息上下文属性，请完成以下步骤：  
  
    1.  双击**SETHEADER**队列以显示**消息浏览器**对话框。  
  
    2.  在中**消息浏览器**对话框中，单击**列**以显示**消息的显示/隐藏列**对话框。  
  
    3.  下**可用的列**，双击每个条目，以将其显示在**消息浏览器**对话框中，然后单击**确定**。  
  
3.  每条消息的消息上下文属性应会显示在**消息浏览器**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)