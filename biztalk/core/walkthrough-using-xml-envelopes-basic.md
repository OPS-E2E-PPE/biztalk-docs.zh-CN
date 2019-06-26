---
title: 演练：使用 XML 信封 （基础） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f614a1400631a1bae36a1f15dc4b1f6916b45916
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279641"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a>演练：使用 XML 信封 （基础）
此示例演示通过实现部分虚构的错误跟踪系统的基本 XML 信封拆装。 该示例要满足以下要求：  
  
1.  错误消息记录在公司内的各种物理站点，并发送到中央位置进行到各种后端系统的处理。  
  
2.  错误消息以 XML 格式编写。  
  
3.  不使用信封或作为批处理包含在一个信封可以成批发送一条错误消息。  
  
## <a name="prerequisites"></a>先决条件  
 对于此示例，您需要熟悉创建 BizTalk 项目，为程序集签名并使用 BizTalk Server 管理控制台查看应用程序和端口。 您还应熟悉中列出的观点与[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。  
  
## <a name="what-this-example-does"></a>此示例的用途  
 示例进程的入站通过定义信封架构并使用 XmlDisassembler 管道包含单个错误消息或一批错误消息的消息。  
  
## <a name="example"></a>示例  
 若要创建该示例，请执行以下各节中所述的步骤。  
  
### <a name="create-a-new-biztalk-project"></a>创建新的 BizTalk 项目  
 在生成解决方案之前需要创建 BizTalk 项目，请确保它具有强名称，并将其分配应用程序名称。 指定应用程序名可防止 BizTalk Server 将解决方案部署到默认 BizTalk 应用程序。  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a>若要创建和配置新的 BizTalk 项目  
  
1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]若要创建新的 BizTalk 项目。 调用项目**BasicXMLEnvelope**。  
  
2. 生成密钥文件并将其分配到项目。 有关此任务的详细信息，请参阅[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
3. 在项目的部署配置属性，将分配**应用程序名称**并设置**重新启动主机实例**到`True`。 设置此标志指示要清除的程序集的所有缓存的实例的主机。  
  
### <a name="create-the-error-schema"></a>创建架构时出现错误  
 在此步骤中创建架构时出现错误。 它定义系统的重要消息。  
  
##### <a name="to-create-the-error-schema"></a>若要创建错误架构  
  
1. 添加到项目名称为"Error"的新架构。  
  
2. 更改到架构的目标命名空间 **http://BasicXMLEnvelope** 。  
  
3. 更改架构属性**Element FormDefault**下**高级**到类别**限定**。 这表示必须在实例文档中的目标命名空间限定本地声明的元素。  
  
4. 重命名根节点"Error"，并与所指示的类型创建 5 个子元素：  
  
   - ID、 xs: int  
  
   - 类型 xs: int  
  
   - 优先级，xs: string  
  
   - 说明，xs: string  
  
   - ErrorDateTime，xs: string  
  
     您的架构应如以下所示：  
  
     ![架构已完成时出现错误](../core/media/error-schema.gif "error_schema")  
  
5. 创建此架构的示例消息。 这用于验证对信封外的单个消息处理正确。 是一个示例消息：  
  
   ```  
   <Error xmlns="http://BasicXMLEnvelope">  
     <ID>1</ID>  
     <Type>5</Type>  
     <Priority>Low</Priority>  
     <Description>Sprocket widget prints reports slowly.</Description>  
     <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
   </Error>  
   ```  
  
    将此消息保存在项目目录中的文件。  
  
### <a name="create-the-envelope-schema"></a>创建信封架构  
 信封包含一个或多个错误消息。 在此基本示例中，信封没有自己的属性和元素。  
  
##### <a name="to-create-the-envelope-schema"></a>若要创建信封架构  
  
1.  添加到 BasicXMLEnvelope 项目名称为"Envelope"的新架构。  
  
2.  更改到的目标命名空间 **http://BasicXMLEnvelope** 。  
  
3.  更改从"Root"改为"Envelope"的根节点名称。  
  
4.  现在将此架构标记为信封架构。 单击 **\<架构\>** 节点。 在属性窗格中，将架构引用属性设置**信封**到`OK`。  
  
5.  设置**正文 XPath**属性。 若要执行此操作，请单击**信封**节点。 在属性窗口中，单击省略号 ( **...** ) 按钮**正文 XPath**属性中，选择**信封**，然后单击**确定**。  
  
6.  向 Envelope 节点中添加任何元素子级。 将此元素中包含错误消息。 您的架构应如以下所示：  
  
     ![已完成的信封架构](../core/media/envelope-schema.gif "envelope_schema")  
  
7.  创建包含一个信封、 一个或多个示例消息的示例消息。 示例消息为：  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     将此消息保存在项目目录中的文件。  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a>部署并配置发送和接收端口  
 创建架构后，您需要编译和部署项目。 在部署后，可以使用 BizTalk Server 管理控制台来配置发送和接收端口。  
  
##### <a name="to-deploy-basicxmlenvelope"></a>若要部署 BasicXMLEnvelope  
  
1. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**部署 BasicXMLEnvelope**从生成菜单。 这将生成并将其部署到 BizTalk Server，作为应用程序"BasicXMLEnvelope"。  
  
2. 在 BizTalk Server 管理控制台中，展开**应用程序**组，以验证**BasicXMLEnvelope**是显示为自定义应用程序。  
  
##### <a name="to-configure-the-receive-port"></a>若要配置接收端口  
  
1.  使用 Windows 资源管理器下创建一个名为"Receive"目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在中**接收端口属性**对话框框中，设置为"Receive"的端口的名称。  
  
4.  右键单击接收位置，然后单击**新建**添加接收端口。 新的端口"为 ReceiveError"的名称。 设置**接收管道**到**XMLReceive**。 有关**传输类型**，选择**文件**，然后单击**配置**。  
  
5.  选择上面创建的接收目录，然后单击**确定**。 在接收端口应现在已配置。 单击**确定**关闭。  
  
##### <a name="to-configure-the-send-port"></a>若要配置的发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"发送" **BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在中**发送端口属性**对话框框中，设置为"Send"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 目标文件夹设置为前面创建的发送目录，然后单击**确定**。  
  
5.  单击**筛选器**并添加一个筛选器：  
  
    -   BTS.MessageType == **http://BasicXMLEnvelope#Error**  
  
6.  单击**确定**完成发送端口配置。 应配置您的发送端口。  
  
### <a name="run-the-example"></a>运行示例  
 它现在是要运行该示例的时间。 使用 BizTalk Server 管理控制台启动 BasicXMLEnvelope 应用程序之后, 将测试文件复制到接收位置，并观察在发送位置生成的内容。  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a>若要运行 BasicXMLEnvelope 示例  
  
1.  在 BizTalk Server 管理控制台中，右键单击**BasicXMLEnvelope**应用程序，然后单击**启动**。 这将登记并启动发送和接收端口。  
  
2.  放入接收目录中的每个示例文件。 如果您使用前面给出的示例，应完成处理后发送位置找到三个单独的错误消息。  
  
## <a name="extending-the-example"></a>扩展示例  
 您可以扩展该示例以满足其他要求。 本部分解决了两种常见方案：  
  
- 如果在一个信封提交一批错误时，单个消息失败的反汇编应不会妨碍其他无错误消息进一步处理。  
  
- 错误应传递到不同的位置根据错误优先级。 而其他优先级的处理按照常规方式将加快高优先级的消息。  
  
  以下各节将扩展以处理这些要求的示例。  
  
### <a name="recoverable-interchange-processing"></a>可恢复交换处理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持可恢复交换处理。 通过使用此功能，可以确保消息批的拆装和不是作为一批单独故障。  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a>若要配置可恢复交换处理的示例  
  
1.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，单击**接收端口**，然后双击接收端口。 这是你之前创建的端口。  
  
2.  在中**接收端口属性**对话框中，单击**接收位置**。 单击**属性**以打开**ReceiveError 接收位置属性**对话框。 单击省略号 ( **...** ) 按钮**接收管道**。  
  
3.  在中**配置管道-XMLReceive**对话框中，将**可恢复交换处理**属性设置为`True`，然后单击**确定**。  
  
4.  单击**确定**以关闭**接收位置属性**对话框中，然后单击**确定**以关闭**接收端口属性**对话框框。  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a>若要创建示例文件并运行示例  
  
1.  若要创建示例文件，制作一份示例中创建的信封示例文件，将不存在命名空间添加到其中一个错误实例中，然后保存该文件：  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  在 BizTalk Server 管理控制台中，单击**应用程序**并确认**BasicXMLEnvelope**运行应用程序。  
  
3.  该消息放入接收位置。 在处理后，应在发送位置和挂起队列中的第二个、 低优先级消息中找到的第一个消息。  
  
### <a name="content-based-routing-cbr"></a>基于内容的路由 (CBR)  
 可以使用基于内容的路由来路由消息根据其内容。 在此方案中，路由基于优先级，具有高消息路由到一个发送位置和低和中的消息路由到不同的发送位置。  
  
 若要扩展该示例，必须完成以下任务：  
  
1.  将提升**优先级**字段 BasicXMLEnvelope 项目中的错误架构中。 基于内容的路由都依赖于将消息路由到已升级属性。 有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
2.  创建并配置两个其他发送端口。 端口使用筛选器来确保其接收相应的消息。  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a>若要升级错误架构中的优先级字段  
  
1. 与**BasicXMLEnvelope**中打开项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**错误**架构和展开**错误**节点。  
  
2. 右键单击**优先级**元素，指向**Promote**，然后单击**Quick Promote**。  
  
3. 单击**确定**以确认添加的新属性架构的已升级属性。  
  
4. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中打开新的属性架构 PropertySchema.xsd。 从架构中删除"Field1"。  
  
5. 现在重新编译和重新部署解决方案。 在生成菜单上选择部署 BasicXMLEnvelope。  
  
6. 该项目已配置为重新部署解决方案时重置主机实例。 如果已更改此，需要停止并重新启动主机。  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a>若要配置的低和中优先级发送端口  
  
1.  使用 Windows 资源管理器下创建名为"SendLowMediumPriority"的目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在中**发送端口属性**对话框框中，设置为"SendLowMediumPriority"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 将目标文件夹设置为前面创建的目录。 单击**确定**关闭。  
  
5.  单击**筛选器**然后添加三个筛选器表达式：  
  
    -   BTS。MessageType == http://BasicXMLEnvelope#Error 和  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Low Or  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Medium  
  
6.  单击**确定**，完成低和中优先级发送端口配置。  
  
##### <a name="to-configure-the-high-priority-send-port"></a>若要配置高优先级发送端口  
  
1.  使用 Windows 资源管理器下创建名为"SendHighPriority"的目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在中**发送端口属性**对话框框中，设置为"SendHighPriority"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 将目标文件夹设置为前面创建的目录。 单击**确定**关闭。  
  
5.  单击**筛选器**和添加两个筛选器表达式：  
  
    -   BTS。MessageType == http://BasicXMLEnvelope#Error 和  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == High  
  
6.  单击**确定**完成高优先级发送端口配置。  
  
##### <a name="to-test-the-routing-solution"></a>若要测试路由解决方案  
  
1.  在 BizTalk Server 管理控制台中，展开**应用程序**组中，右键单击**BasicXMLEnvelope**应用程序，，然后单击**启动**。 当系统提示你确认，单击**启动**。 这将登记新发送端口。  
  
2.  测试消息放入接收位置。 请注意如何将错误消息路由到不同的发送位置：  
  
    -   具有低、 中或高优先级和消息处理没有失败的错误消息被路由到原始发送位置 （在核心示例中配置） 和发送位置两个按优先级别。 对于具有较低或中等优先级的消息，副本会显示在原始发送位置和低/中发送位置中。  
  
    -   如果启用可恢复交换处理，则不会路由失败的错误消息，并按预期正确路由没有失败的消息。 因为其消息类型不匹配的已配置的筛选器中使用的类型，不路由失败的消息。  
  
## <a name="see-also"></a>请参阅  
 [可恢复交换处理](../core/recoverable-interchange-processing.md)   
 [升级属性](../core/promoting-properties.md)   
 [CBRSample（BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)