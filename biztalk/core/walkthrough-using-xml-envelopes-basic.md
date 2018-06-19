---
title: 演练： 使用 XML 信封 (Basic) |Microsoft 文档
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
ms.openlocfilehash: 9090c4ee7d576bb7ab610cd81637680d837b2cae
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975748"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a>演练： 使用 XML 信封 (Basic)
本示例通过实现部分虚构的错误跟踪系统来演示基本的 XML 信封拆装。 该示例要满足以下条件：  
  
1.  错误消息记录在公司内部不同的物理地点，并发送到一个中央位置，供各种后端系统进行处理。  
  
2.  错误信息以 XML 格式编写。  
  
3.  可不用信封就将错误消息发送出去，也可以包含在一个信封中，成批发送出去。  
  
## <a name="prerequisites"></a>先决条件  
 对于本示例，您需要熟悉以下操作：创建 BizTalk 项目、签署程序集、使用 BizTalk Server 管理控制台查看应用程序和端口。 你还应与中提供的想法[演练： 将基本的 BizTalk 应用程序部署](../core/walkthrough-deploying-a-basic-biztalk-application.md)。  
  
## <a name="what-this-example-does"></a>此示例的执行  
 该示例通过定义一个信封架构并使用 XmlDisassembler 管道来处理包含单个错误消息或一批错误消息的入站消息。  
  
## <a name="example"></a>示例  
 若要创建该示例，请按照下述步骤进行操作。  
  
### <a name="create-a-new-biztalk-project"></a>创建新 BizTalk 项目  
 生成解决方案前，需要先创建一个 BizTalk 项目，确保要对其进行强命名，并为其指定一个应用程序名。 指定应用程序名可防止 BizTalk Server 将该解决方案部署到默认 BizTalk 应用程序中。  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a>创建并配置新的 BizTalk 项目  
  
1.  使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]创建新的 BizTalk 项目。 调用项目**BasicXMLEnvelope**。  
  
2.  生成密钥文件，并将其分配给该项目。 有关此任务的详细信息，请参阅[如何配置一个强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
3.  在项目的部署配置属性，将分配**应用程序名称**并设置**重新启动主机实例**到`True`。 设置此标志的作用是通知主机清除该程序集的所有缓存的实例。  
  
### <a name="create-the-error-schema"></a>创建架构时出现错误  
 在此步骤中，您将创建 Error（错误）架构。 该架构定义系统的重要消息。  
  
##### <a name="to-create-the-error-schema"></a>若要创建错误架构  
  
1.  向项目中添加名称为“Error”的新架构。  
  
2.  更改到架构的目标命名空间**http://BasicXMLEnvelope**。  
  
3.  更改架构属性**元素 FormDefault**下**高级**类别与**合格**。 这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。  
  
4.  重命名根节点“Error”，并创建 5 个子元素，类型如下：  
  
    -   ID xs:int  
  
    -   类型 xs:int  
  
    -   优先级，xs: string  
  
    -   说明，xs: string  
  
    -   ErrorDateTime，xs: string  
  
     您所创建的架构应基本如下：  
  
     ![架构已完成时出现错误](../core/media/error-schema.gif "error_schema")  
  
5.  为此架构创建一个示例消息。 此消息用于检验对信封外的单个消息的处理是否正确。 下面是一个示例消息：  
  
    ```  
    <Error xmlns="http://BasicXMLEnvelope">  
      <ID>1</ID>  
      <Type>5</Type>  
      <Priority>Low</Priority>  
      <Description>Sprocket widget prints reports slowly.</Description>  
      <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
    </Error>  
    ```  
  
     将此消息保存到项目目录下的文件中。  
  
### <a name="create-the-envelope-schema"></a>创建信封架构  
 该信封包含一个或多个错误消息。 在本基本示例中，信封没有自己的属性和元素。  
  
##### <a name="to-create-the-envelope-schema"></a>若要创建信封架构  
  
1.  向项目 BasicXMLEnvelope 添加名称为“Envelope”的新架构。  
  
2.  更改到的目标命名空间**http://BasicXMLEnvelope**。  
  
3.  将根节点的名称从“Root”改为“Envelope”。  
  
4.  现在，将该架构标记为信封架构。 单击**\<架构\>** 节点。 在属性窗格中，将架构引用属性设置**信封**到`OK`。  
  
5.  设置**正文 XPath**属性。 若要执行此操作，请单击**信封**节点。 在属性窗口中，单击省略号 (**...**) 按钮**正文 XPath**属性中，选择**信封**，然后单击**确定**。  
  
6.  向“Envelope”节点任意添加一个“任何元素”子级。 错误信息将包含在此元素中。 您所创建的架构应基本如下：  
  
     ![已完成的信封架构](../core/media/envelope-schema.gif "envelope_schema")  
  
7.  创建一个包含一个信封、一个或多个示例消息的示例消息。 示例消息为：  
  
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
  
     将此消息保存到项目目录下的文件中。  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a>部署并配置发送和接收端口  
 创建架构后，还需要编译和部署项目。 部署完毕后，就可使用 BizTalk Server 管理控制台来配置发送端口和接收端口。  
  
##### <a name="to-deploy-basicxmlenvelope"></a>若要部署 BasicXMLEnvelope  
  
1.  从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**部署 BasicXMLEnvelope**从生成菜单。 这将生成“BasicXMLEnvelope”并将其作为应用程序部署到 BizTalk Server。  
  
2.  在 BizTalk Server 管理控制台中，展开**应用程序**组以便确认**BasicXMLEnvelope**显示为自定义应用程序。  
  
##### <a name="to-configure-the-receive-port"></a>若要配置接收端口  
  
1.  使用 Windows 资源管理器下创建一个名为"接收"目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在**接收端口属性**对话框框中，设置"接收"的端口的名称。  
  
4.  右击接收位置，然后单击**新建**将接收端口添加。 将新端口命名为“ReceiveError”。 设置**接收管道**到**XMLReceive**。 有关**传输类型**，选择**文件**，然后单击**配置**。  
  
5.  选择上面创建的接收目录，然后单击**确定**。 现在接收端口配置完毕。 单击**确定**关闭。  
  
##### <a name="to-configure-the-send-port"></a>若要配置发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"发送"目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在**发送端口属性**对话框框中，设置"发送"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 到前面创建的发送目录设置的目标文件夹，然后单击**确定**。  
  
5.  单击**筛选器**并添加单个筛选器：  
  
    -   BTS。MessageType = = **http://BasicXMLEnvelope#Error**  
  
6.  单击**确定**以完成发送端口配置。 现在发送端口配置完毕。  
  
### <a name="run-the-example"></a>运行示例  
 现在该运行示例了。 使用 BizTalk Server 管理控制台启动 BasicXMLEnvelope 应用程序后，您应将测试文件复制到接收位置，然后观察发送位置生成的内容。  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a>若要运行 BasicXMLEnvelope 示例  
  
1.  在 BizTalk Server 管理控制台中，右键单击**BasicXMLEnvelope**应用程序，然后单击**启动**。 此时将登记并启动发送端口和接收端口。  
  
2.  将所有示例文件放入接收目录中。 如果您使用前面给出的示例，则操作完毕时，应在发送位置找到三个单个错误消息。  
  
## <a name="extending-the-example"></a>扩展示例  
 您可扩展该示例以满足其他要求。 此处主要介绍两种常见方案：  
  
-   如果一批错误是装入信封中提交的，则单个消息的拆装错误不应阻止其他无错误消息的进一步处理。  
  
-   应根据错误优先级，将错误发送到不同位置。 高优先级的消息应迅速处理，而其他优先级的消息应按照常规方式进行处理。  
  
 以下部分扩展了该示例，以处理这些要求。  
  
### <a name="recoverable-interchange-processing"></a>可恢复的交换处理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持可恢复的交换处理。 借助此功能，您可确保成批消息的拆装中只会单个消息失败，而不会整批单位。  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a>若要配置可恢复的交换处理的示例  
  
1.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，单击**接收端口**，然后双击接收端口。 它是您先前创建的端口。  
  
2.  在**接收端口属性**对话框中，单击**接收位置**。 单击**属性**弹出**ReceiveError 接收位置属性**对话框。 单击省略号 (**...**) 按钮**接收管道**。  
  
3.  在**配置管道-XMLReceive**对话框中，设置**可恢复交换处理**属性`True`，然后单击**确定**。  
  
4.  单击**确定**关闭**接收位置属性**对话框中，然后单击**确定**关闭**接收端口属性**对话框框。  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a>若要创建示例文件并运行此示例  
  
1.  若要创建示例文件，请复制在示例中创建的信封示例文件，并向其中一个“Error”实例添加一个并不存在的命名空间，然后保存该文件：  
  
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
  
3.  将该消息放入接收位置。 操作完毕后，您应在发送位置找到第一条消息，并在挂起队列中找到优先级较低的第二条消息。  
  
### <a name="content-based-routing-cbr"></a>基于内容的路由 (CBR)  
 借助基于内容的路由，您可根据消息的内容来路由消息。 在本方案中，路由是基于优先级进行的，高优先级的消息路由到一个发送位置，低优先级和中优先级的消息路由到另一个发送位置。  
  
 若要扩展该示例，必须完成以下任务：  
  
1.  将提升**优先级**BasicXMLEnvelope 项目中的错误架构字段。 基于内容的路由依靠升级的属性来路由消息。 有关详细信息，请参阅[提升属性](../core/promoting-properties.md)。  
  
2.  创建并配置其他两个发送端口。 这些端口使用筛选器来确保其接收正确的消息。  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a>若要将提升错误架构中的优先级字段  
  
1.  与**BasicXMLEnvelope**中打开项目后[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**错误**架构和展开**错误**节点。  
  
2.  右键单击**优先级**元素，指向**Promote**，然后单击**快速提升**。  
  
3.  单击**确定**以确认添加提升的属性的新属性架构。  
  
4.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，打开新的属性架构 PropertySchema.xsd。 从架构中删除"Field1"。  
  
5.  现在重新编译并重新部署该解决方案。 在“生成”菜单中，选择“部署 BasicXMLEnvelope”。  
  
6.  该项目原本配置为在重新部署解决方案时，重置主机实例。 如果您对此进行了更改，则需要停止并重新启动主机。  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a>若要配置的低和中等优先级发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"SendLowMediumPriority"目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在**发送端口属性**对话框框中，设置为"SendLowMediumPriority"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 将目标文件夹设置为前面创建的目录。 单击**确定**关闭。  
  
5.  单击**筛选器**并添加三个筛选表达式：  
  
    -   BTS。MessageType = = http://BasicXMLEnvelope#Error 和  
  
    -   BasicXMLEnvelope.PropertySchema.Priority = = 低或  
  
    -   BasicXMLEnvelope.PropertySchema.Priority = = 介质  
  
6.  单击**确定**以完成低和中等优先级发送端口配置。  
  
##### <a name="to-configure-the-high-priority-send-port"></a>若要配置的优先级较高发送端口  
  
1.  使用 Windows 资源管理器下创建一个名为"SendHighPriority"目录**BasicXMLEnvelope**项目目录。  
  
2.  在 BizTalk Server 管理控制台中，展开**BasicXMLEnvelope**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向**。  
  
3.  在**发送端口属性**对话框框中，设置为"SendHighPriority"的端口的名称。  
  
4.  有关**传输类型**，选择**文件**，然后单击**配置**。 将目标文件夹设置为前面创建的目录。 单击**确定**关闭。  
  
5.  单击**筛选器**并添加两个筛选表达式：  
  
    -   BTS。MessageType = = http://BasicXMLEnvelope#Error 和  
  
    -   BasicXMLEnvelope.PropertySchema.Priority = = 高  
  
6.  单击**确定**以完成优先级较高发送端口配置。  
  
##### <a name="to-test-the-routing-solution"></a>若要测试路由解决方案  
  
1.  在 BizTalk Server 管理控制台中，展开**应用程序**组中，右键单击**BasicXMLEnvelope**应用程序，，然后单击**启动**。 当系统提示确认，请单击**启动**。 这将登记新发送端口。  
  
2.  将测试消息放入接收位置。 请注意错误消息是如何被路由到不同的发送位置的：  
  
    -   错误消息，不论其优先级是高、中还是低，只要消息处理没有失败，都会路由到两个位置：原始发送位置（在核心示例中配置）和相应优先级的发送位置。 对于低优先级和中优先级的消息，原始发送位置和低/中优先级发送位置均会出现该消息。  
  
    -   如果启用了可恢复的交换处理，则不会路由失败的错误消息，而没有失败的消息将按预期正确路由。 不路由失败消息的原因是，其消息类型与所配置的筛选器的类型不匹配。  
  
## <a name="see-also"></a>另请参阅  
 [可恢复的交换处理](../core/recoverable-interchange-processing.md)   
 [提升属性](../core/promoting-properties.md)   
 [CBRSample（BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)