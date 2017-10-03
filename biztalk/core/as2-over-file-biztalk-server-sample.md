---
title: "AS2 over File （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84e497579b2f3b8465f7a30677dae6920e2750c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 over File （BizTalk Server 示例）
AS2 Over File 示例演示了如何通过 FILE 接收位置接收 AS2 消息。 这样，便可使用 FILE 适配器接收 AS2 消息，而不是通常使用的 HTTP 适配器。 若要完成该操作，此解决方案会按照 AS2 解码器的要求，将 AS2 消息中的 HTTP 标头写入 InboundHTTPHeaders 上下文属性。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示如何在没有 HTTP 适配器的情况下处理 AS2 消息中的 HTTP 标头。 具体而言，本示例执行下列操作：  
  
1.  当将测试消息放入输入文件夹时，FILE 接收位置将提取该消息。  
  
2.  自定义 AS2 接收管道中的自定义管道组件处理该消息，将其 HTTP 标头写入 InboundHTTPHeaders 上下文属性中。  
  
    > [!NOTE]
    >  如果在自定义管道组件的下游消息处理失败，则可能难以恢复消息处理，因为该消息已经转换为 XML 编码。  
  
3.  自定义接收管道中的 AS2 解码器处理消息，读取 InboundHTTPHeaders 上下文属性中的属性以进行处理。  
  
4.  发送端口订阅由接收管道生成的 XML 消息，将其通过直通发送管道传递，并将其放入输出文件夹。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 通过文件。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AS2OverFile.csproj|包含自定义管道组件代码的项目。|  
|AS2OverFile.sln|包含 AS2OverFile.btproj 项目的解决方案。|  
|Program.cs|包括表示标头数据的类。|  
|SampleMessage.txt|包含 HTTP 标头的示例消息。|  
  
## <a name="implementing-and-running-this-sample"></a>实现和运行本示例  
 若要实现 AS2 Over File 示例，需要执行以下操作：  
  
-   生成并部署本示例的 BizTalk 项目，创建自定义管道组件  
  
-   使用自定义管道组件创建自定义管道，并且用该自定义管道生成和部署项目  
  
-   创建输入和输出文件夹  
  
-   配置接收端口和位置，并且启用接收位置  
  
-   配置发送端口并启动发送端口  
  
-   创建发送示例消息的参与方  
  
#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>生成具有 AS2 Over File Emulator 管道组件的自定义管道  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\Samples\AS2\AS2 Over File 文件夹中的 AS2OverFile 项目。  
  
2.  创建强名称密钥文件，打开 AS2OverFile 项目的“属性”对话框，并将该密钥文件分配给此项目。  
  
3.  生成此项目。  
  
4.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建名为 AS2OverFile_Pipeline 的新 BizTalk 项目。  
  
5.  右键单击 AS2OverFile_Pipeline 项目，指向**添加**，然后单击**新项**。  
  
6.  在**添加新项**对话框中，选择**管道文件**在左侧窗格中，选择**接收管道**在右侧窗格中，命名管道 AS2OverFile_Receive.btp，，然后单击**添加**。  
  
7.  单击**视图**在菜单栏上，然后单击**工具箱**，显示工具箱。  
  
8.  在工具箱中，右键单击**BizTalk 管道组件**，然后单击**选择项**。  
  
9. 在**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡。单击**AS2 通过文件模拟器**，然后单击**确定**。  
  
10. 通过打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符，并对 \AS2 Over File\obj\Debug 文件夹中的 Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll 执行命令 `gacutil /if "<file name and path>"`，将 AS2OverFile.dll 文件添加到全局程序集缓存中。  
  
11. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，从到工具箱中拖动文件模拟器通过 AS2 管道组件**解码**自定义管道的阶段。  
  
12. 将组件拖到 AS2 解码器组件**解码**自定义管道之后 AS2 通过文件组件, 的阶段。  
  
    > [!NOTE]
    >  如果要生成 MDN，请将 AS2 拆装器添加到自定义管道的“拆装”阶段。 如果不返回 MDN，则不需要 AS2 拆装器。  
  
13. 创建强名称密钥文件，打开 AS2OverFile_Pipeline 项目的“属性”对话框，并将该密钥文件分配给此项目。  
  
14. 生成并部署自定义管道。  
  
15. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，通过单击管道节点，然后单击向管道节点中添加自定义管道**刷新**。  
  
#### <a name="to-implement-the-solution-for-this-sample"></a>实现本示例的解决方案  
  
1.  在 Windows 资源管理器中的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Samples\AS2\AS2 Over File 文件夹中，创建一个 In 输入文件夹和一个 Out 输出文件夹。  
  
2.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个名为 AS2OverFile_Receive 的单向接收端口。 在此接收端口中，创建具有下列属性的接收位置：  
  
    |属性|设置|  
    |--------------|-------------|  
    |Name|AS2OverFile_Receive|  
    |类型|FILE|  
    |接收文件夹|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/In|  
    |文件掩码|*.txt|  
    |接收管道|AS2OverFile|  
  
3.  在接收位置节点中，右键单击 AS2OverFile_Receive 接收位置，然后单击**启用**。  
  
4.  在“发送端口”节点中，创建具有下列属性的静态单向发送端口：  
  
    |属性|设置|  
    |--------------|-------------|  
    |Name|AS2OverFile_Send|  
    |类型|FILE|  
    |接收文件夹|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/Out|  
    |文件掩码|%MessageID%.xml|  
    |发送管道|Passthru|  
    |“筛选器”|BTS.REceivePortName == AS2OverFile_Receive|  
  
5.  在发送端口节点中，右键单击 AS2OverFile_Send 发送端口，并依次**启动**。  
  
6.  在“参与方”节点中，创建名为“伙伴”的参与方。 将与别名添加到别名列表中，**名称**的**EDIINT AS2 从值**、**限定符**的**AS2-从**，和一个**值**的**合作伙伴**。  
  
 BizTalk Server 现在已准备好使用此示例。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 AS2 Over File 示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将该 SampleMessage.txt 文件从 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 文件夹复制到 \AS2 Over File\In 文件夹。  
  
2.  验证是否已将输出 XML 消息放入 \AS2 Over File\Out 输出文件夹中。  
  
3.  在文本编辑器中，打开输入的消息 SampleMessage.txt 并打开输出消息\<GUID > 在文本编辑器中的.xml。 验证 SampleMessage.txt 输入消息是否具有 HTTP（和 AS2）标头以及输出消息是否不具有 HTTP 标头。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 无  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 （BizTalk Server 的示例文件夹）](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)