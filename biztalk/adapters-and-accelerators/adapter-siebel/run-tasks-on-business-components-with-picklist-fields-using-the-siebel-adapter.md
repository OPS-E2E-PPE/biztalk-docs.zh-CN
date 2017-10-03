---
title: "使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, perform operations with picklist fields by using BizTalk Server
- business components, performing operations with picklist fields by using BizTalk Server
ms.assetid: b62d32fa-903a-442b-951b-2343ef719bd0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 823c2959f10bbd836bd0154b2e59f07fffcc6a96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-picklist-fields-using-biztalk-server-and-the-siebel-adapter"></a>使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作
Siebel 选择列表字段类型构成的可能的值集合从哪种客户端可以指定要传递到 Siebel 系统的某些值。 换而言之，选择列表字段包含字段接受的值的列表。 有关选择列表和它们的类型的详细信息，请参阅 Siebel 文档。 有关详细信息，如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]上与选择列表字段的业务组件支持操作请参阅[Siebel 业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。  
  
 在生成包含静态绑定的选择列表字段 （一种选择列表） 的业务组件元数据时，还作为元数据的一部分发布的选择列表可接受的值。 如果你在选择列表字段中插入一个值，你必须指定一个值，在元数据中发布。  
  
## <a name="how-to-perform-operations-on-business-components-with-picklist-fields"></a>如何执行与选择列表字段的业务组件上的操作？  
 Siebel 系统使用上执行操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[使用 Siebel 适配器创建 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。 
 
 若要完成选择列表字段的业务组件上的操作，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成架构，以对在业务组件包含选择列表字段执行操作。  
  
2.  在发送和接收消息从 Siebel 系统的 BizTalk 项目中创建消息。  
  
3.  创建要在 Siebel 系统调用操作的业务流程。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SiebelPicklist，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，来演示如何调用操作与选择列表字段的业务组件我们将生成架构**插入**操作**帐户**在业务组件。 **帐户**在业务组件具有静态选择列表中，*调查类型*。  
  
 请参阅[检索用于 Siebel 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
 生成的 Insert 操作的元数据时**帐户**在业务组件，你将获取包含选择列表字段和其可能的值的单独.xsd 文件。 请注意，.xsd 仅包含值的静态选择列表，包括*调查类型*。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您从生成的架构中的第一步的邮件 BizTalk 项目的业务流程视图。  
  
 对于本主题中，你必须创建两条消息，另一个用于将请求发送到 Siebel 系统，另一个用于接收响应。  
  
 执行以下步骤以创建消息并将它们链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果不是已打开。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.Insert*，其中*SiebelPicklist*是 BizTalk 项目的名称。 *SiebelBindingSchema*是为调用生成的架构*插入*操作*帐户*在业务组件。|  
  
5.  重复上述步骤以创建新的消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.InsertResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行插入操作在选择列表字段具有 Siebel 业务组件上的。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用此消息并将其传递到 Siebel 系统。 Siebel 系统的响应保存到另一个位置。 将包含在 Siebel 业务组件上执行操作的典型业务流程：  
  
-   发送和接收形状来将消息发送到 Siebel 和接收响应。  
  
-   单向接收端口接收请求消息将发送到 Siebel。  
  
-   双向发送端口将请求消息发送到 Siebel 和接收响应。  
  
-   单向发送端口将响应从 Siebel 发送到的文件夹。  
  
 示例业务流程*插入*操作*帐户*在业务组件如下所示：  
  
 ![业务流程用于 Siebel 插入选择列表值](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-将设置**名称**到*ReceiveXML*<br />-将设置**激活**到*True*|  
|SendToLOB|Send|-将设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 中列出的名称*端口*列是业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|文件|-将设置**标识符**到*文件*<br />-将设置**类型**到*FileInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|SaveResponse|-将设置**标识符**到*SaveResponse*<br />-将设置**类型**到*SaveResponseType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveXml|-将设置**消息**到*请求*<br />-将设置**操作**到*FileIn.Picklist.Request*|  
|SendToLOB|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.Picklist.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.Picklist.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse.Picklist.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[如何构建业务流程](../../core/how-to-build-orchestrations.md)和[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF Siebel 发送端口将消息发送到 Siebel 系统。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序用于执行*插入*操作*帐户*Siebel 中的业务组件。 有关启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF Siebel 发送端口将消息发送到 Siebel 系统正在运行  
  
-   运行该操作 BizTalk 业务流程  
  
## <a name="executing-the-operation"></a>执行该操作  
 你必须放到该文件的请求消息接收位置。 本主题前面的生成的架构必须符合的请求消息架构。 请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关的请求消息架构的详细信息。  
  
 若要插入到选择列表字段的值，请查看生成的架构，以确定可接受值的列表选择列表。 请确保请求消息具有要插入到选择列表字段的值的元素。 例如，请求消息必须包含以下元素插入到值*调查类型*选择列表。  
  
 `<Survey_x0020_Type>1</Survey_x0020_Type>`  
  
 在这里，"1"是调查类型选取列表的可接受值。  
  
 包含的选择列表参数示例请求消息，则：  
  
```  
<Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <ArrayOfAccountInsertRecord>  
    <AccountInsertRecord xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">  
      <Currency_x0020_Code>usd</Currency_x0020_Code>  
      <Current_x0020_Volume>9</Current_x0020_Volume>  
      <Customer_x0020_Account_x0020_Group>Sold-To Party</Customer_x0020_Account_x0020_Group>  
      <Location>Location_1</Location>  
      <Main_x0020_Phone_x0020_Number>4256543212</Main_x0020_Phone_x0020_Number>  
      <Name>Name_Surname</Name>  
      <Party_x0020_Name>test_party</Party_x0020_Name>  
      <Primary_x0020_Address_x0020_Id>1212 street</Primary_x0020_Address_x0020_Id>  
      <Survey_x0020_Type>1</Survey_x0020_Type>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 业务流程使用请求消息，并将其传递到 Siebel 系统。 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。  
  
> [!NOTE]
>  你还可以选择列表中尝试插入一个无效值。 在这种情况下，你必须获取`TargetSystemException`。  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到与使用的选择列表字段执行在业务组件上的操作时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理，并在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。
  
## <a name="see-also"></a>另请参阅  
[开发使用 Siebel 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)