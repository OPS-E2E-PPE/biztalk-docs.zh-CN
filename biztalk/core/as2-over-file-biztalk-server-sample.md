---
title: AS2 over File （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b604db858e6ad2826ece6c1a925b1ec80d45c6c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528632"
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 over File （BizTalk Server 示例）
AS2 Over File 示例演示如何通过 FILE 接收 AS2 消息接收位置。 这使您可以使用 FILE 适配器以接收 AS2 消息，而不是通常使用的 HTTP 适配器。 若要执行此操作，此解决方案将 HTTP 标头 AS2 消息中写入 InboundHTTPHeaders 上下文属性，所需的 AS2 解码器。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何处理 AS2 消息中的 HTTP 标头，而无需 HTTP 适配器。 具体而言，此示例执行以下任务：  

1.  当测试消息放入输入文件夹时，文件接收位置提取该消息。  

2.  自定义管道组件中的自定义 AS2 接收管道处理消息，其 HTTP 标头写入 InboundHTTPHeaders 上下文属性。  

    > [!NOTE]
    >  如果处理的自定义管道组件的下游消息失败，则可能难以恢复消息处理的消息，因为它将具有已经转换为 XML 编码。  

3.  自定义接收管道中的 AS2 解码器处理消息，读取 InboundHTTPHeaders 上下文属性以进行处理中的属性。  

4.  发送端口订阅由接收管道生成的 XML 消息，将其通过直通发送管道，并将其放入输出文件夹。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File。  

 下表显示了本示例中的文件及其用途说明：  

|文件|Description|  
|---------------|-----------------|  
|AS2OverFile.csproj|包含自定义管道组件代码的项目。|  
|AS2OverFile.sln|包含 AS2OverFile.btproj 项目的解决方案。|  
|Program.cs|包括表示标头数据的类。|  
|SampleMessage.txt|包含 HTTP 标头的示例消息。|  

## <a name="implementing-and-running-this-sample"></a>实现和运行本示例  
 若要实现 AS2 Over File 示例，需要执行以下操作：  

-   生成和部署本示例中，创建自定义管道组件的 BizTalk 项目  

-   创建使用自定义管道组件的自定义管道并生成和部署具有该自定义管道的项目  

-   创建输入和输出文件文件夹  

-   配置接收端口和位置，并启用接收位置  

-   配置发送端口并启动发送端口  

-   创建的参与方发送示例消息  

#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>若要生成的自定义管道使用 AS2 通过 File Emulator 管道组件  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开中的 AS2OverFile 项目[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 文件夹。  

2. 创建强名称密钥文件，打开 AS2OverFile 项目的属性对话框并将密钥文件分配到项目。  

3. 生成项目。  

4. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建一个名为 AS2OverFile_Pipeline 的新 BizTalk 项目。  

5. 右键单击 AS2OverFile_Pipeline 项目，指向**外**，然后单击**新项**。  

6. 在中**添加新项**对话框中，选择**管道文件**在左侧窗格中，选择**接收管道**在右侧窗格中，命名管道 AS2OverFile_Receive.btp，并单击**添加**。  

7. 单击**视图**在菜单栏中，然后单击**工具箱**，显示工具箱。  

8. 在工具箱中，右键单击**BizTalk 管道组件**，然后单击**选择项**。  

9. 在中**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡。单击**AS2 Over File Emulator**，然后单击**确定**。  

10. 通过打开将 AS2OverFile.dll 文件添加到全局程序集缓存[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符处，并执行命令`gacutil /if "<file name and path>"`上 Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll \AS2 Over File\obj\Debug 文件夹中。  

11. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，将 AS2 Over File Emulator 管道组件从工具箱拖到**解码**自定义管道阶段。  

12. AS2 解码器将组件拖至**解码**自定义管道，AS2 Over File 组件之后阶段。  

    > [!NOTE]
    >  如果你想要生成 MDN，将 AS2 拆装器添加到自定义管道的拆装阶段。 如果不返回 MDN，则不需要 AS2 拆装器。  

13. 创建强名称密钥文件，打开 AS2OverFile_Pipeline 项目的属性对话框并将密钥文件分配到项目。  

14. 生成和部署自定义管道。  

15. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，将自定义管道添加到管道节点中，通过单击管道节点，然后单击**刷新**。  

#### <a name="to-implement-the-solution-for-this-sample"></a>若要实现此示例的解决方案  

1. 在 Windows 资源管理器中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 文件夹中，创建一个 In 输入的文件夹和一个 Out 输出文件夹。  

2. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个单向接收端口名为 AS2OverFile_Receive。 在接收端口中创建具有以下属性的接收位置：  


   |     属性     |                                                 设置                                                  |
   |------------------|----------------------------------------------------------------------------------------------------------|
   |       “属性”       |                                           AS2OverFile_Receive                                            |
   |       类型       |                                                   FILE                                                   |
   |  接收文件夹  | [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/In |
   |    文件掩码     |                                                  \*.txt                                                  |
   | 接收管道 |                                               AS2OverFile                                                |


3. 在接收位置节点，右键单击 AS2OverFile_Receive 接收位置，然后单击**启用**。  

4. 在发送端口节点中，创建具有以下属性的静态单向发送端口:  


   |    属性    |                                                  设置                                                  |
   |----------------|-----------------------------------------------------------------------------------------------------------|
   |      “属性”      |                                             AS2OverFile_Send                                              |
   |      类型      |                                                   FILE                                                    |
   | 接收文件夹 | [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 输入/输出 |
   |   文件掩码    |                                              %MessageID%.xml                                              |
   | 发送管道  |                                                 Passthru                                                  |
   |     “筛选器”     |                                BTS.REceivePortName == AS2OverFile_Receive                                 |


5. 在发送端口节点中，右键单击 AS2OverFile_Send 发送端口，然后依次**启动**。  

6. 在参与方节点中，创建名为"合作伙伴"参与方。 到别名列表中，添加一个别名**名称**的**EDIINT-AS2 From 值**即**限定符**的**AS2-从**，和一个**值**的**合作伙伴**。  

   BizTalk Server 现在已准备好可使用本示例。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 AS2 Over File 示例。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1. 复制该 SampleMessage.txt 文件从[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 文件夹复制到 \AS2 Over File\In 文件夹。  

2. 验证已将输出 XML 消息放入 \AS2 Over File\Out 输出文件夹。  

3. 在文本编辑器中，打开输入的消息 SampleMessage.txt，打开输出消息\<GUID\>在文本编辑器中的.xml。 验证 SampleMessage.txt 输入的消息具有 HTTP （和 AS2） 标头以及输出消息不具有 HTTP 标头。  

## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 None  

## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 （BizTalk Server 示例文件夹）](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)