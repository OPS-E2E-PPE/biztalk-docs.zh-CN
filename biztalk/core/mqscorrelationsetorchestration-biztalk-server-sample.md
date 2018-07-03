---
title: MQSCorrelationSetOrchestration （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0057e9a9276de5eb3724f1af298822b03065a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011774"
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a>MQSCorrelationSetOrchestration（BizTalk Server 示例）
MQSCorrelationSetOrchestration 示例演示如何使用 MQSeries 相关标识符将发送至 MQSeries 队列的消息重新与正在运行的业务流程关联。 业务流程设置 MQSeries 相关标识符和消息使用的标识符值**MQMD_CorrelId**并**MQMD_MsgID**属性。 MQSeries 队列管理器将 MessageID 值复制到消息的 CorrelationID 属性。  

## <a name="prerequisites"></a>必要條件  
 此示例假定已在正在运行的同一服务器上安装 IBM WebSphere MQSeries [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="what-this-sample-does"></a>本示例的用途  
 本示例将演示如何在发送至 IBM WebSphere MQSeries 服务器的消息中设置消息标识符和相关标识符。 这是一种可用于将消息重新与正在运行的业务流程实例关联的方法。 当 MQSeries 队列管理器收到消息时，它会将 MessageID 值复制到消息的 CorrelationID 属性。 此 CorrelationID (**MQMD_CorrelId**) 然后使用在业务流程中将 MQSeries 上的响应消息与用来将消息发送到 MQSeries 的实例相关联。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本示例将演示一个方案，在该方案中可以将业务流程正在处理的文档发送至 MQSeries 队列（可能用于其他处理），然后返回正在运行的业务流程。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration  

 下表显示了本示例中的文件及其用途说明：  

|**File**|**Description**|  
|--------------|---------------------|  
|**MQSCorrelationSetOrchestration.btproj，**<br /><br /> **MQSCorrelationSetOrchestration.sln**|应用程序的项目和解决方案文件。|  
|**MQSCorrelationSetOrchestration.odx**|应用程序的业务流程。|  
|**MQSCorrelationSetOrchestration.snk**|强命名密钥文件。|  
|**Setup.bat**|生成并初始化本示例。|  

## <a name="how-to-use-this-sample"></a>如何使用本示例  
 如果作为整个工作流的其中一个步骤，您需要将消息发送至 MQSeries 服务器，请引入本示例中采用的逻辑。  

### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a>通过 WebSphere MQ Explorer 创建 MQSeries 队列  

1.  单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。  

2.  双击**队列管理器**，然后双击默认的队列管理器。 默认的队列管理器通常命名为**QM_ < m a c h >** 其中*machine_name*是您的计算机的名称。  

3.  右键单击**队列**，依次指向**新建**，然后单击**本地队列**。  

4.  在中**创建本地队列**对话框中**队列名称**，键入"MQCorrelation"，然后单击**确定**。  

### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>创建接收位置和 MQSeries 队列  

1.  打开 BizTalk Server 管理控制台。  

2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  

3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  

4.  在中**单向接收端口属性**对话框中**名称**框中，键入"MQIn"，然后单击**确定**。  

5.  在左窗格中，单击**接收位置**选项卡，然后依次**新建**。  

6.  在中**接收位置属性**对话框中**名称**框中，键入"MQIn"。  

7.  在中**传输类型**框中，选择**MQSeries**。  

8.  在中**接收处理程序**框中，选择**BizTalkServerApplication**。  

9. 在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  

10. 单击**配置**。  

11. 在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入"10"。  

12. 在中**队列定义**框中，单击省略号 （...） 按钮。  

13. 在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  

14. 在中**队列管理器**框中，选择默认的队列管理器。  

15. 在中**队列**框中，键入"MQCorrelation"，然后单击**导出**。  

16. 在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。  

### <a name="to-create-the-send-port-to-mqseries"></a>创建到 MQSeries 的发送端口  

1.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2.  在中**发送端口属性**对话框中**名称**框中，键入"MQOut"。  

3.  在中**传输类型**框中，选择**MQSeries**。  

4.  在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  

5.  单击**配置**。  

6.  在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 （...） 按钮。  

7.  在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。  

8.  在中**队列管理器**框中，选择默认的队列管理器。  

9. 在中**队列**框中，键入"MQCorrelation"，然后单击**确定**。  

10. 单击**确定**直到您退出所有对话框为止。  

### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>若要启用接收位置并启动发送端口  

1.  在 BizTalk Server 管理控制台中，单击**接收端口**。  

2.  在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。  

3.  在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**  

### <a name="to-create-the-folders-used-by-the-application"></a>创建应用程序使用的文件夹  

1.  在你**c:\\** 驱动器中，创建名为"temp"如果尚不存在的文件夹。  

2.  下**C:\temp**目录中，创建名为"Pickup"和"dropit 的文件夹"的文件夹。  

### <a name="building-and-deploying-this-sample"></a>生成和部署此示例  

1.  在命令窗口中，导航到下面的文件夹：  

     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  

2.  运行 Setup.bat 文件，该文件将执行以下操作：  

    1.  为项目创建强名称密钥。  

    2.  编译并部署业务流程项目。  

    3.  使用文件适配器创建发送端口和接收端口。  

### <a name="bind-and-start-the-orchestration"></a>绑定和启动业务流程  

1.  在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。  

2.  在细节窗格中，右键单击**MQSCorrelationSetOrchestration**业务流程，并单击**绑定**。  

3.  将业务流程端口绑定到下列发送端口和接收位置：  

    |**业务流程端口**|**消息传送端口 / 接收位置**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSetOrchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQIn|  
    |MQSeriesRequestSendPort|MQOut|  
    |FileSendPort|MQSCorrelationSetOrchestration.FileSendPort|  

4.  单击**主机**。  

5.  在中**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。  

6.  在中**发送端口**，右键单击**MQSCorrelationSetOrchestration.FileSendPort**，然后选择**启动**。  

7.  在中**接收位置**，右键单击**MQSCorrelationSetOrchestration.FileReceivePort** ，然后选择**启用**。  

8.  右键单击该业务流程，然后单击**启动**。  

    > [!NOTE]
    >  启动业务流程还将自动登记该业务流程。  

### <a name="to-test-the-application"></a>测试应用程序  

1.  Put 将文件放**C:\Temp\Pickup**文件夹。  

2.  查看中的文件**C:\Temp\Dropit**文件夹。  

    > [!NOTE]
    >  如果禁用**MQIn**接收位置，您可以检查在 WebSphere MQ Explorer 中的消息，请参阅设置消息和相关标识符。 若要执行此操作，启动**WebSphere MQ Explorer**并查看放置在消息**MQCorrelation**队列。 消息和相关标识符显示在**标识符**选项卡**消息属性**对话框。  

    > [!NOTE]
    >  在生产方案中，您将希望为发送到 MQSeries 队列的每个消息分配一个唯一 ID。 可以通过修改业务流程中的表达式形状完成该操作。 更改以下行以将这些属性设置为唯一的 24 字节 ID：  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  如果你想要设置唯一的 24 字节 ID，有关这些属性，请参阅明**创建唯一的 24 字节 ID 发送到 MQSeries 的消息**。  

### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a>为发送到 MQSeries 的消息创建唯一的 24 字节 ID  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中新建一个 C# 类库项目。  

2. 将以下代码粘贴到该类的 .cs 文件中：  

   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Text;  
   using System.Security.Cryptography;  

   namespace MQId  
   {[Serializable]  
       public class GetId  
       {  
           RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  

           public string getGuidstr()  
           {  
               byte[] newGuid = GetRandomData(24);  
               return ConvertToHex(newGuid);  
           }  

           private byte[] GetRandomData(int keySize)  
           {  
               byte[] randomData = new byte[keySize];  
               randomCryptoString.GetBytes(randomData);  
               return randomData;  
           }  

           private string ConvertToHex(byte[] key)  
           {  
               StringBuilder hexString = new StringBuilder();  
               for (int i = 0; i < key.Length; ++i)  
               {  
                   hexString.Append(String.Format("{0:X2}", key[i]));  
               }  
               return hexString.ToString();  
           }  
       }  
   }  
   ```  

3. 指定**默认命名空间**的**MQId**和一个**程序集名称**的**GetId**的项目属性**应用程序**页。  

4. 指定一个强名称密钥文件的项目属性为程序集签名**签名**页上，然后生成项目。  

5. 使用全局程序集缓存工具 (gacutil.exe) 已编译的程序集加载到 GAC (gacutil /i \<*已编译的 dll 文件的名称*\>)。  

6. 对于本示例，在 BizTalk 项目中添加对 GetId 程序集的引用。  

7. 向本示例中使用的业务流程中添加两个变量：  


   | 变量名（标识符） |     类型      |
   |----------------------------|---------------|
   |           GetId            |  MQId.GetId   |
   |          strGuid           | System.String |


8. 将以下代码粘贴到本示例的业务流程中使用的表达式形状，该代码应该覆盖现有代码：  

   ```  
   GetId = new MQId.GetId();  
   strGuid = GetId.getGuidstr();  
   MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
   ```  

9. 停止并移动到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的业务流程（如果已部署该业务流程）。 然后按照部分中的步骤**构建和部署此示例**，**绑定和启动业务流程**并**测试应用程序**。  

    > [!NOTE]
    >  使用此方法为发送到 MQSeries 的消息创建唯一的 24 字节 ID 并不能够百分百保证所有发送的消息的 ID 唯一，但出现重复消息 ID 的可能性非常低。 如果业务需要百分百保证消息 ID 不重复，则您将需要使用另一个自定义代码来确保此功能。  

## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 本示例不显式使用任何类或方法。  

## <a name="see-also"></a>请参阅  
 [使用请求-答复相关消息](../core/correlating-messages-using-request-reply.md)   
 [MQSeries 适配器示例](../core/mqseries-adapter-samples.md)