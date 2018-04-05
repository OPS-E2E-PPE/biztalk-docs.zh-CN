---
title: 调用中使用 BizTalk Server SAP Rfc |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking using BizTalk Server
ms.assetid: cc859ca2-aa9a-48fd-a941-ae28bee96f06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3db5180d8b4183a2a48c726fd5e73b3347f82dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a>调用中使用 BizTalk Server SAP Rfc
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现作为适配器客户端可以调用的操作公开 SAP 系统的 Rfc。 本部分说明了通过使用调用中某个 SAP 系统的 RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 RFC 调用在 SAP 系统中，请参阅[操作中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。 有关用于调用 RFC 的 SOAP 消息的结构的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a>如何在某个 SAP 系统调用 RFC？  
 执行对 SAP 系统使用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要调用 RFC SAP 系统中，这些任务包括：  
  
1.  创建 BizTalk 项目，并为你想要调用 SAP 系统中的 RFC 生成架构。  
  
2.  在发送和接收消息从 SAP 系统的 BizTalk 项目中创建消息。  
  
3.  创建业务流程来调用 RFC SAP 系统中。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，若要演示如何调用 RFC 在 SAP 系统中，我们生成的架构*RFC_CUSTOMER_GET*。 请参阅[浏览，搜索，并为 SAP 中的 RFC 操作获取元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须从 BizTalk 项目的业务流程视图来链接到消息的你生成的架构。  
  
 对于本主题中，你必须创建两条消息，另一个用于将请求发送到 SAP 系统，另一个用于接收响应。  
  
 执行以下步骤以创建消息并将它们链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果不是已打开。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*，其中*InvokeRFC*是 BizTalk 项目的名称。  *SAPBindingSchema*是为生成的架构*RFC_CUSTOMER_GET*。|  
  
5.  重复上述步骤以创建新的消息。 在**属性**窗格中，为新的消息中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用 Rfc SAP 系统中。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。 从 SAP 系统的响应保存到另一个位置。 将包含 SAP 系统中的调用 Rfc 典型业务流程：  
  
-   发送和接收形状来将消息发送到 SAP 系统并接收响应。  
  
-   单向接收端口接收请求消息将发送到 SAP 系统。  
  
-   双向发送端口将请求消息发送到 SAP 系统和接收响应。  
  
-   单向发送端口将响应从 SAP 系统发送到的文件夹。  
  
 示例业务流程如下所示：  
  
 ![与连接端口的协调](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|Receive_Request|Receive|-将设置**名称**到*Receive_Request*<br />-将设置**激活**到*True*|  
|Send_LOB|Send|-将设置**名称**到*Send_LOB*|  
|Receive_LOB|Receive|-将设置**名称**到*Receive_LOB*<br />-将设置**激活**到*False*|  
|Send_Response|Send|-将设置**名称**到*Send_Response*|  
  
### <a name="adding-ports"></a>添加端口  
 为每个逻辑端口指定以下属性。 中列出的名称*端口*列是业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|ReceiveMsgPort|-将设置**标识符**到*ReceiveMsgPort*<br />-将设置**类型**到*ReceiveMsgPortType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|SendToLOBPort|-将设置**标识符**到*SendToLOBPort*<br />-将设置**类型**到*SendToLOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|SendMsgPort|-将设置**标识符**到*SendMsgPort*<br />-将设置**类型**到*SendMsgPortType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|Receive_Request|-将设置**消息**到*请求*<br />-将设置**操作**到*ReceiveMsgPort.Operation_1.Request*|  
|Send_LOB|-将设置**消息**到*请求*<br />-将设置**操作**到*SendToLOBPort.Operation_1.Request*|  
|Receive_LOB|-将设置**消息**到*响应*<br />-将设置**操作**到*SendToLOBPort.Operation_1.Response*|  
|Send_Response|-将设置**消息**到*响应*<br />-将设置**操作**到*SendMsgPort.Operation_1.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动调用 RFC SAP 系统中的 BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须在预定义位置删除业务流程的请求消息。 请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)需要了解的有关调用 RFC SAP 系统中的请求消息的架构。 例如，要调用 RFC_CUSTOMER_GET 的请求消息是：  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 业务流程使用该消息，并将其发送到 SAP 系统。 从 SAP 系统的响应保存在定义为业务流程的一部分的其他文件位置中。 例如，来自以上的请求消息的 SAP 系统的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RFC_CUSTOMER_GETResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <CUSTOMER_T>  
    <RFCCUST xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <KUNNR>0000001390</KUNNR>   
      <ANRED>Firma</ANRED>   
      <NAME1>Contoso, Ltd.</NAME1>   
      <PFACH />   
      <STRAS>4567 Main Street</STRAS>   
      <PSTLZ>98052</PSTLZ>   
      <ORT01>USA</ORT01>   
      <TELF1>555-0101</TELF1>   
      <TELFX>555-0102</TELFX>   
    </RFCCUST>  
  </CUSTOMER_T>  
</RFC_CUSTOMER_GETResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 调用中使用 BizTalk Server 某个 SAP 系统的 RFC 时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)