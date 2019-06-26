---
title: 演练：使用标头和尾部拆装平面文件 |Microsoft Docs
description: 使用平面文件架构向导创建标头架构、 尾部架构和正文架构，然后拆装平面文件在 BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a3e2739b50d19c867fa05744ab98735ffc90646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395338"
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a>演练：使用标头和尾部拆装平面文件

## <a name="overview"></a>概述
本演练演示如何将执行包含头部、 尾部和重复的消息正文的文件的平面文件拆装平面文件架构向导创建的架构。 在本演练中，我们将开发一个虚构的错误跟踪系统，满足以下要求的一部分：  
  
- 错误消息记录在公司内的各种物理站点，并发送到中央位置进行到各种后端系统的处理。  
  
- 错误消息写入到包含标头指示的位置，正文，其中包含一个或多个错误消息和一个指明批号的尾部的平面文件格式。  
  
- 消息将被视为无效，如果它们没有标头、 正文和尾部。  
  
  在本演练结束时必须处理平面文件并将其输出为 XML 进行处理后端系统的 BizTalk Server 应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 对于此示例，您需要熟悉创建 BizTalk Server 项目中，为程序集签名并使用 BizTalk Server 管理控制台查看应用程序和端口。 您还应熟悉中列出的观点与[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。 平面文件架构向导的基本熟悉也是有所帮助，但并不是必需的。  
  
## <a name="what-this-example-does"></a>此示例的用途  
 此示例中处理入站平面文件消息使用自定义管道和平面文件拆装器组件。 使用头部、 尾部和正文架构分析消息，然后写出到发送位置进行后端处理。  
  
## <a name="example"></a>示例  
 若要创建该示例，请执行以下各节中所述的步骤。  
  
### <a name="create-a-new-biztalk-project"></a>创建新的 BizTalk 项目  
 在生成解决方案之前需要创建 BizTalk 项目，请确保它具有强名称，并将其分配应用程序名称。 指定应用程序名可防止 BizTalk Server 将解决方案部署到默认 BizTalk 应用程序。  
  
1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]若要创建新的 BizTalk 项目。 调用项目**FFDisassemblerWalkthrough**。  
  
2. 生成密钥文件并将其分配到项目。 有关此任务的详细信息，请参阅[签名页，项目设计器](http://go.microsoft.com/fwlink/?LinkId=125876)。  
  
3. 在项目的部署属性，设置**应用程序名称**为"FlatFileExample"，将**重新启动主机实例**到`True`。 设置此标志指示要清除的程序集的所有缓存的实例的主机。  
  
### <a name="create-the-sample-data-file"></a>创建示例数据文件  
生成架构前，需要创建一个测试文件。   
  
1.  启动记事本或其他文本编辑器。  
  
2.  创建测试文件示例。 该文件由头部用来指明报告错误，尾部含有此批和正文包含一个或多个错误记录的批 ID 的位置。 文件的格式如下所示：  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    使用文本"ERROR"标记错误记录并将其与分隔"&#124;"字符 （而不是位置）。 下表所述的错误记录的数据元素。  
  
    |元素|数据类型|Description|  
    |---|---|---|  
    |ID|integer|此错误的 ID。|  
    |类型|integer|错误的类型。|  
    |Priority|string|优先级指示器：低、 中或高。|  
    |Description|string|错误的说明。|  
    |ErrorDateTime|DateTime|日期和时间，出现了错误。|  
  
    该文件可以具有一个或多个错误记录。  
  
     \* *--或者-* *
  
     将下面的示例数据复制到新的文件。 最后一行包含一个尾随的换行符：
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  将新的示例文件保存在项目目录。 使用一个描述性名称，如"ErrorFile.txt"，因此它能轻松地找到。  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a>创建和测试头部、 尾部和正文架构  
 创建示例数据文件后下, 一步是创建头部、 尾部和正文架构。 使用平面文件拆装器使用这些架构来接收管道组件处理接收的消息。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a>使用平面文件架构向导创建头部架构  
  
1.  向项目添加新架构。 在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。 命名新的架构"为 Header.xsd"，然后单击**添加**。  
  
3.  上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。  
  
4.  上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。 更改**记录名称**为"Header"，验证代码页，然后单击**下一步**。  
  
    > [!NOTE]
    >  如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。 这不会产生负面影响的示例。  
  
5.  接下来选择文档数据。 上**选择文档数据**页上，突出显示的第一个行的数据，包括新行字符 {CR} 和 {LF} 所示：  
  
     ![选用于头部架构的数据](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")  
  
     单击“下一步”  。  
  
6.  上**选择记录格式**页上，单击**下一步**接受默认值。 你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。  
  
7.  上**分隔记录**页上，单击**下一步**。  
  
8.  现在，您指定子元素。 标头包含一个名为"位置"元素：  
  
     ![标头定义的位置节点](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")  
  
     单击 **“下一步”** 继续。  
  
9. 上**架构视图**页上，验证架构。  
  
     ![已完成的架构视图显示标头架构](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")  
  
     完成后，单击**完成**以完成向导。  
  
10. 单击 **\<架构\>** 标头架构窗格中的节点。 在属性窗格中更改**Element FormDefault**到**限定**。 这表示必须在实例文档中的目标命名空间限定本地声明的元素。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a>使用平面文件架构向导创建尾部架构  
  
1.  向项目添加新架构。 在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。 命名新架构"Trailer.xsd"，然后单击**添加**。  
  
3.  上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。  
  
4.  上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。 更改**记录名称**为"Trailer"，验证代码页，然后单击**下一步**。  
  
    > [!NOTE]
    >  如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。 这不会产生负面影响的示例。  
  
5.  接下来选择文档数据。 上**选择文档数据**页上，突出显示的最后一行的数据，包括新行字符 {CR} 和 {LF} 所示：  
  
     ![选用于尾部架构的数据](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")  
  
     单击“下一步”  。  
  
6.  上**选择记录格式**页上，单击**下一步**接受默认值。 你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。  
  
7.  上**分隔记录**页上，单击**下一步**。  
  
8.  现在，您指定子元素。 标头包含一个名为"BatchID"元素：  
  
     ![为尾部定义的位置节点](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")  
  
     单击 **“下一步”** 继续。  
  
9. 上**架构视图**页上，验证架构。  
  
     ![架构视图显示完成尾部架构](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")  
  
     完成后，单击**完成**以完成向导。  
  
10. 单击 **\<架构\>** 尾部架构窗格中的节点。 在属性窗格中更改**elementFormDefault**到**限定**。 这表示必须在实例文档中的目标命名空间限定本地声明的元素。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a>使用平面文件架构向导创建正文架构  
  
1.  向项目添加新架构。 在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。 命名新架构"Body.xsd"，然后单击**添加**。  
  
3.  上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。  
  
4.  上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。 更改**记录名称**为"Body"，验证代码页，然后单击**下一步**。  
  
    > [!NOTE]
    >  如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。 这不会产生负面影响的示例。  
  
5.  接下来选择文档数据。 上**选择文档数据**页上，突出显示两个和第三行的数据，包括新行字符 {CR} 和 {LF} 所示：  
  
     ![为正文架构选择的数据](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")  
  
     单击“下一步”  。  
  
6.  上**选择记录格式**页上，单击**下一步**接受默认值。 你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。  
  
7.  上**分隔记录**页上，选择**下一步**。  
  
8.  接下来定义的子元素。 更改**Body_Child1**到**错误**并将其元素类型设置为**重复记录**。 设置**Body_Child2**元素记录类型设置为**忽略**。  
  
9. 上**架构视图**页上，单击**下一步**定义的错误记录的子元素。  
  
10. 上**选择文档数据**页上，单击**下一步**。 该向导将正确地选择记录定义的数据。  
  
11. 上**选择记录格式**页上，单击**下一步**。 按分隔符符号设置数据的格式。  
  
12. 上**分隔记录**页上，选择 **&#124;** 有关**子分隔符**。 接下来，选择**记录带有标记标识符**复选框，键入**错误**标记值。  
  
     ![配置分隔记录具有标记标识符](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")  
  
     单击“下一步”  。  
  
13. 现在定义的错误记录的子元素。  
  
     ![使用五个元素定义的错误记录](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")  
  
     单击“下一步”  。  
  
14. 上**架构视图**页上，验证架构。  
  
     ![架构视图显示完成正文架构](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")  
  
     如果所做的任何错误，请单击**回**并进行必要的更正。 完成后，单击**完成**以完成向导。  
  
15. 单击 **\<架构\>** 正文架构窗格中的节点。 在属性窗格中更改**Element FormDefault**到**限定**。 这表示必须在实例文档中的目标命名空间限定本地声明的元素。  
  
16. 单击 **\<错误\>** 正文架构窗格上的节点。 在属性窗格中更改**Max Occurs**到**1**。 这将导致平面文件拆装器将每个错误拆分为其自己的消息。  
  
##### <a name="test-the-schemas-using-ffdasm"></a>测试使用 FFDasm 架构  
  
1.  打开命令提示符处，并将目录更改为你的项目目录。  
  
2.  从命令提示符处，运行 FFDasm.exe，如下所示。  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     此文档及其他管道工具的位置有关的信息，请参阅[管道工具](../core/pipeline-tools.md)。  
  
3.  FFDasm.exe 将产生两个名为 {GUID}.xml，一个用于测试文件中每个错误记录的输出文件。 高优先级错误记录看起来如下所示：  
  
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
 现在，定义平面文件架构，您需要创建自定义管道使用平面文件拆装器组件。 然后可以配置平面文件拆装器组件为使用头部、 正文和尾部架构来分解消息。    
 
1.  向项目添加新的接收管道。 在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**项目，指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，依次指向**管道文件**，然后单击**接收管道**。 命名新管道"FFReceivePipeline"，然后单击**添加**。  
  
3.  通过将平面文件拆装器组件从工具箱窗格拖至拆装步骤中配置新的管道。  
  
4.  在属性窗格中设置**文档架构**到**FFDisassemblerWalkthrough.Body**，则**标头架构**到**FFDisassemblerWalkthrough.Header**并**尾部架构**到**FFDisassemblerWalkthrough.Trailer**。  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a>部署应用程序并配置发送和接收端口  
 接收管道创建架构和自定义，您需要编译和部署项目。 在部署后，可以使用 BizTalk Server 管理控制台来配置发送和接收端口。  

##### <a name="deploy"></a>部署  
1. 从内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，右键单击项目，然后单击部署解决方案**部署**。  
  
2. 使用 BizTalk Server 管理控制台中，展开**应用程序**组，以验证**FlatFileExample**是显示为自定义应用程序。  
  
##### <a name="configure-the-receive-port"></a>配置接收端口  
  
1.  使用 Windows 资源管理器下创建一个名为"Receive"目录**FFDisassemblerWalkthrough**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在中**接收端口属性**对话框框中，设置为"ReceiveError"的端口的名称。  
  
4.  单击**接收位置**，然后单击**新建**添加接收位置。 新的接收位置"命名为 ReceiveErrorLocation"。 设置**接收管道**到**FFReceivePipeline**。 有关**传输类型**，选择**文件**，然后单击**配置**。 选择接收目录创建，并将**文件掩码**到 *.txt。  
  
5.  单击“确定”  。 在接收端口应现在已配置。 单击**确定**关闭。  
  
##### <a name="configure-the-send-port"></a>配置发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"发送" **FFDisassemblerWalkthrough**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口...** .  
  
3.  在中**发送端口属性**对话框框中，设置为"Send"的端口的名称。  
  
4.  对于传输类型，选择**文件**，然后单击**配置**。 将目标文件夹设置为前面创建的发送目录。  
  
5.  现在配置筛选器。 单击**筛选器**并添加下面的表达式：  
  
    -   BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**  
  
6.  单击**确定**完成发送端口配置。 应配置您的发送端口。  
  
### <a name="run-the-example"></a>运行示例  
 它现在是要运行该示例的时间。 使用 BizTalk Server 管理控制台启动应用程序之后, 将测试文件复制到接收位置和观察发送位置生成的内容。  
  
1.  在 BizTalk Server 管理控制台中，右键单击**FlatFileExample**应用程序，，然后单击**启动**。 这将登记并启动发送和接收端口。  
  
2.  拖放入接收目录将示例 Errorfile.txt 的复制。 两个输出文件应写入到的发送目录。  
  
