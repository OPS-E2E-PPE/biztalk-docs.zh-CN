---
title: 演练： 使用标头和尾的平面文件反汇编 |Microsoft 文档
description: 使用平面文件架构向导创建标头架构、 电影预告片架构和正文架构，然后反汇编 BizTalk Server 中的平面文件
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c1406367f047794c6d8931352104bb59e6ca5b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a>演练：使用头部和尾部拆装平面文件

## <a name="overview"></a>概述
本演练演示了如何使用平面文件架构向导创建的架构，对包含一个头部、一个尾部和一个重复消息正文的文件执行平面文件拆装。 在本演练中，您将参与开发一个虚构的错误跟踪系统，它满足以下要求：  
  
-   错误消息记录在公司内部不同的物理地点，并发送到一个中央位置，供各种后端系统进行处理。  
  
-   错误消息以平面文件格式写入，该平面文件格式包含一个指明其位置的头部、含有一个或多个错误消息的正文，以及一个指明批号的尾部。  
  
-   如果消息不包含头部、正文和尾部，则被视为无效。  
  
 本演练结束时，会创建一个 BizTalk Server 应用程序，它可处理平面文件，并将其输出为 XML 格式，以供后端系统处理。  
  
## <a name="prerequisites"></a>先决条件  
 对于本示例，您需要熟悉以下操作：创建 BizTalk Server 项目、签署程序集、使用 BizTalk Server 管理控制台查看应用程序和端口。 你还应与中提供的想法[演练： 将基本的 BizTalk 应用程序部署](../core/walkthrough-deploying-a-basic-biztalk-application.md)。 对平面文件架构向导有个基本了解也有帮助，但不是必需的。  
  
## <a name="what-this-example-does"></a>此示例的执行  
 本示例使用自定义管道和平面文件拆装器组件来处理入站平面文件消息。 解析消息使用头部、尾部和正文架构，然后将消息写到一个发送位置，以进行后端处理。  
  
## <a name="example"></a>示例  
 若要创建该示例，请按照下述步骤进行操作。  
  
### <a name="create-a-new-biztalk-project"></a>创建新 BizTalk 项目  
 生成解决方案前，需要先创建一个 BizTalk 项目，确保要对其进行强命名，并为其指定一个应用程序名。 指定应用程序名可防止 BizTalk Server 将该解决方案部署到默认 BizTalk 应用程序中。  
  
1.  使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]创建新的 BizTalk 项目。 调用项目 **FFDisassemblerWalkthrough**。  
  
2.  生成密钥文件，并将其分配给该项目。 有关此任务的详细信息，请参阅 [签名页上，项目设计器](http://go.microsoft.com/fwlink/?LinkId=125876)。  
  
3.  在项目的部署属性，设置 **应用程序名称** 到"FlatFileExample"和集 **重新启动主机实例** 到 `True`。 设置此标志的作用是通知主机清除该程序集的所有缓存的实例。  
  
### <a name="create-the-sample-data-file"></a>创建示例数据文件  
生成架构前，您需要创建测试文件。   
  
1.  启动记事本或其他文本编辑器。  
  
2.  创建测试文件示例。 该文件由头部、尾部和正文组成，头部用来指明报告错误的位置，尾部含有此批的批 ID，正文包含一个或多个错误记录。 该文件的格式如下：  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    标记有文本"错误"错误记录并将其用分隔"&#124;"字符 （而非位置）。 下表对 ERROR 记录的数据元素进行了描述。  
  
    |元素|数据类型|Description|  
    |---|---|---|  
    |ID|integer|此错误 ID。|  
    |类型|integer|错误类型。|  
    |Priority|string|优先级指示器：低、中或高。|  
    |Description|string|错误的说明。|  
    |ErrorDateTime|DateTime|发生错误的日期和时间。|  
  
    该文件可拥有一个或多个 ERROR 记录。  
  
     **-- OR --  **
  
     将下面的示例数据复制到新文件。 最后一行包含尾随的换行符：
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  将新示例文件保存到项目目录中。 请使用带有说明性的名称，如“ErrorFile.txt”，以便查找。  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a>创建头部、尾部和正文架构并进行测试  
 创建示例数据文件后，下一步就是创建头部、尾部和正文架构。 平面文件拆装器接收管道组件使用这些架构来处理接收到的消息。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a>使用平面文件架构向导创建的标头架构  
  
1.  向项目添加新架构。 在解决方案资源管理器，右键单击 **FFDisassemblerWalkthrough**, ，指向 **添加**, ，然后单击 **新项**。  
  
2.  在 **添加新项** 对话框中，单击 **架构文件** 和选择 **平面文件架构向导**。 将新架构"Header.xsd"，然后单击 **添加**。  
  
3.  上 **欢迎 BizTalk 平面文件架构向导** 页上，单击 **下一步**。  
  
4.  上 **平面文件架构信息** 页上，单击 **浏览** 并找到之前创建的示例数据文件。 更改 **记录名称** to"标头"，验证的代码页;，然后单击 **下一步**。  
  
    > [!NOTE]
    >  如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。 这不会对该示例产生不利影响。  
  
5.  然后，选择文档数据。 上 **选择文档数据** 页上，突出显示的第一个行的数据，包括新行字符 {CR} 和 {LF} 所示︰  
  
     ![标头架构用于所选数据](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")  
  
     单击“下一步” 。  
  
6.  上 **选择记录格式** 页上，单击 **下一步** 以接受默认值。 您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。  
  
7.  上 **分隔记录** 页上，单击 **下一步**。  
  
8.  现在，您可以指定子元素了。 头部包含一个名为“Location”的元素：  
  
     ![标头定义的位置节点](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")  
  
     单击 **“下一步”** 继续。  
  
9. 上 **架构视图** 页上，验证架构。  
  
     ![架构视图显示完成标头架构](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")  
  
     当满足要求，单击 **完成** 以完成向导。  
  
10. 单击**\<架构\>**在标头的架构窗格中的节点。 在属性窗格中，更改 **元素 FormDefault** 到 **合格**。 这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a>使用平面文件架构向导创建尾部架构  
  
1.  向项目添加新架构。 在解决方案资源管理器，右键单击 **FFDisassemblerWalkthrough**, ，指向 **添加** , ，然后单击 **新项**。  
  
2.  在 **添加新项** 对话框中，单击 **架构文件** 和选择 **平面文件架构向导**。 将新架构"Trailer.xsd"，然后单击 **添加**。  
  
3.  上 **欢迎 BizTalk 平面文件架构向导** 页上，单击 **下一步**。  
  
4.  上 **平面文件架构信息** 页上，单击 **浏览** 并找到之前创建的示例数据文件。 更改 **记录名称** 到"预告片"，验证的代码页;，然后单击 **下一步**。  
  
    > [!NOTE]
    >  如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。 这不会对该示例产生不利影响。  
  
5.  然后，选择文档数据。 上 **选择文档数据** 页上，突出显示的最后一行的数据，包括新行字符 {CR} 和 {LF} 所示︰  
  
     ![尾部架构用于所选数据](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")  
  
     单击“下一步” 。  
  
6.  上 **选择记录格式** 页上，单击 **下一步** 以接受默认值。 您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。  
  
7.  上 **分隔记录** 页上，单击 **下一步**。  
  
8.  现在，您可以指定子元素了。 头部包含一个名为“BatchID”的元素：  
  
     ![位置节点为预告片定义](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")  
  
     单击 **“下一步”** 继续。  
  
9. 上 **架构视图** 页上，验证架构。  
  
     ![架构视图显示完成预告片架构](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")  
  
     当满足要求，单击 **完成** 以完成向导。  
  
10. 单击**\<架构\>**预告片架构窗格中的节点。 在属性窗格中，更改 **elementFormDefault** 到 **合格**。 这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a>使用平面文件架构向导创建正文架构  
  
1.  向项目添加新架构。 在解决方案资源管理器，右键单击 **FFDisassemblerWalkthrough**, ，指向 **添加**, ，然后单击 **新项**。  
  
2.  在 **添加新项** 对话框中，单击 **架构文件** 和选择 **平面文件架构向导**。 将新架构"Body.xsd"，然后单击 **添加**。  
  
3.  上 **欢迎 BizTalk 平面文件架构向导** 页上，单击 **下一步**。  
  
4.  上 **平面文件架构信息** 页上，单击 **浏览** 并找到之前创建的示例数据文件。 更改 **记录名称** 到"正文"中，验证的代码页;，然后单击 **下一步**。  
  
    > [!NOTE]
    >  如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。 这不会对该示例产生不利影响。  
  
5.  然后，选择文档数据。 上 **选择文档数据** 页上，突出显示两个和第三行的数据，包括新行字符 {CR} 和 {LF} 所示︰  
  
     ![正文架构用于所选数据](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")  
  
     单击“下一步” 。  
  
6.  上 **选择记录格式** 页上，单击 **下一步** 以接受默认值。 您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。  
  
7.  上 **分隔记录** 页上，选择 **下一步**。  
  
8.  下面定义子元素。 更改 **Body_Child1** 到 **错误**并将其元素类型设置为 **重复记录**。 设置 **Body_Child2** 元素记录类型设置为 **忽略**。  
  
9. 上 **架构视图** 页上，单击 **下一步** 定义的错误记录的子元素。  
  
10. 上 **选择文档数据** 页上，单击 **下一步**。 该向导可正确地选择记录定义的数据。  
  
11. 上 **选择记录格式** 页上，单击 **下一步**。 由分隔符设置数据格式。  
  
12. 上 **分隔记录** 页上，选择 **&#124;** 为 **子分隔符**。 接下来，选择 **记录带有标记标识符** 复选框，并键入 **错误** 的标记值。  
  
     ![配置分隔记录具有标记标识符](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")  
  
     单击“下一步” 。  
  
13. 现在，定义错误记录的子元素。  
  
     ![使用五个元素定义的错误记录](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")  
  
     单击“下一步” 。  
  
14. 上 **架构视图** 页上，验证架构。  
  
     ![架构视图显示完成正文架构](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")  
  
     如果所做的任何错误，请单击 **回** 并进行必要的更正。 当满足要求，单击 **完成** 以完成向导。  
  
15. 单击**\<架构\>**正文架构窗格中的节点。 在属性窗格中，更改 **元素 FormDefault** 到 **合格**。 这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。  
  
16. 单击**\<错误\>**正文架构窗格上的节点。 在属性窗格中，更改 **Max Occurs** 到 **1**。 这将使平面文件拆装器把每个错误拆分到各自的消息中。  
  
##### <a name="test-the-schemas-using-ffdasm"></a>测试使用 FFDasm 的架构  
  
1.  打开命令提示符，将目录改到您的项目目录。  
  
2.  在命令提示符下，运行 FFDasm.exe，如下所示。  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     有关此产品及其他管道工具的位置的信息，请参阅[管道工具](../core/pipeline-tools.md)。  
  
3.  FFDasm.exe 将产生两个名称为 {GUID}.xml 的输出文件，分别对应测试文件中的每个 ERROR 记录。 高优先级错误记录与以下类似：  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a>创建自定义接收管道  
 现在已定义了平面文件架构，下面需要创建一个使用平面文件拆装器组件的自定义管道。 然后，就可将平面文件拆装器组件配置为使用头部、正文和尾部架构来分解消息。    
 
1.  向项目添加新接收管道。 在解决方案资源管理器，右键单击 **FFDisassemblerWalkthrough** 项目，指向 **添加**, ，然后单击 **新项**。  
  
2.  在 **添加新项** 对话框中，指向 **管道文件** ，然后单击 **接收管道**。 命名新管道"FFReceivePipeline"，再单击 **添加**。  
  
3.  通过将平面文件拆装器组件从“工具箱”窗格拖至“拆装”步骤来配置新管道。  
  
4.  在属性窗格中，设置 **文档架构** 到 **FFDisassemblerWalkthrough.Body**, 、 **标头架构** 到 **FFDisassemblerWalkthrough.Header** 和 **尾部架构** 到 **FFDisassemblerWalkthrough.Trailer**。  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a>部署应用程序并配置发送端口和接收端口  
 创建了架构和自定义接收管道后，需要编译和部署项目。 部署完毕后，就可使用 BizTalk Server 管理控制台来配置发送端口和接收端口。  

##### <a name="deploy"></a>部署  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过右键单击项目，然后单击部署解决方案**部署**。  
  
2.  使用 BizTalk Server 管理控制台中，展开 **应用程序** 组以便确认 **FlatFileExample** 显示为自定义应用程序。  
  
##### <a name="configure-the-receive-port"></a>配置接收端口  
  
1.  使用 Windows 资源管理器下创建一个名为"接收"目录 **FFDisassemblerWalkthrough** 项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开 **FlatFileExample** 应用程序中，右键单击 **接收端口**, ，指向 **新建**, ，然后单击 **单向接收端口**。  
  
3.  在 **接收端口属性** 对话框框中，设置为"ReceiveError"的端口的名称。  
  
4.  单击 **接收位置**, ，然后单击 **新建** 添加接收位置。 将新的接收位置命名为“ReceiveErrorLocation”。 设置 **接收管道** 到 **FFReceivePipeline**。 有关 **传输类型**, ，选择 **文件**, ，然后单击 **配置**。 选择接收目录创建，并将 **文件掩码** 到 *.txt。  
  
5.  单击 **“确定”**。 现在接收端口配置完毕。 单击 **确定** 关闭。  
  
##### <a name="configure-the-send-port"></a>配置发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"发送"目录 **FFDisassemblerWalkthrough** 项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开 **FlatFileExample** 应用程序中，右键单击 **发送端口**, ，指向 **新建**, ，然后单击 **静态单向发送端口..**。  
  
3.  在 **发送端口属性** 对话框框中，设置"发送"的端口的名称。  
  
4.  对于传输类型，选择 **文件**, ，然后单击 **配置**。 将目标文件夹设置为前面创建的发送目录。  
  
5.  现在配置筛选器。 单击 **筛选器** 并添加一个表达式︰  
  
    -   BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**  
  
6.  单击 **确定** 以完成发送端口配置。 现在发送端口配置完毕。  
  
### <a name="run-the-example"></a>运行示例  
 现在该运行示例了。 使用 BizTalk Server 管理控制台中启动应用程序之后, 将测试文件复制到接收位置和观察在发送位置生成的内容。  
  
1.  在 BizTalk Server 管理控制台中，右键单击**FlatFileExample**应用程序，，然后单击**启动**。 这登记和启动发送和接收端口。  
  
2.  将示例 Errorfile.txt 的副本放入接收目录中。 应有两个输出文件写入到发送目录中。  
  
