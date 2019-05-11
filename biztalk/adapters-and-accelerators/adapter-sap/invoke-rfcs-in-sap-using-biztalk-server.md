---
title: 调用中使用 BizTalk Server 的 SAP Rfc |Microsoft Docs
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
ms.openlocfilehash: 35d27d21a147aef162bed6a7920aab2a086f0a00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373291"
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a>调用中使用 BizTalk Server 的 SAP Rfc
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现为可由适配器客户端调用的操作公开的 SAP 系统的 Rfc。 本部分说明了通过使用 SAP 系统中调用 RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 RFC 调用在 SAP 系统中，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。 有关以调用 RFC 的 SOAP 消息的结构的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a>如何调用 RFC，SAP 系统中？  
 对 SAP 系统使用执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要在 SAP 系统中调用 RFC，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要在 SAP 系统中调用的 RFC 生成架构。  
  
2. 用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。  
  
3. 创建一个业务流程调用 RFC，SAP 系统中。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用 RFC 在 SAP 系统中，我们生成的架构*RFC_CUSTOMER_GET*。 请参阅[浏览、 搜索和获取 RFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须从 BizTalk 项目的业务流程视图中的消息链接你生成的架构。  
  
 对于本主题中，您必须创建两条消息，另一个用于将请求发送到 SAP 系统，另一个用于接收响应。  
  
 执行以下步骤来创建消息并将其链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*，其中*InvokeRFC*是 BizTalk 项目的名称。  *SAPBindingSchema*是为生成的架构*RFC_CUSTOMER_GET*。|  
  
5.  重复上述步骤以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于调用 Rfc，SAP 系统中。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。 从 SAP 系统的响应保存到另一个位置。 调用 Rfc，SAP 系统中的一个典型的业务流程将包含：  
  
- 发送和接收形状来将消息发送到 SAP 系统和接收响应。  
  
- 一个单向接收端口接收请求消息发送到 SAP 系统。  
  
- 一个双向发送端口以将请求消息发送到 SAP 系统和接收响应。  
  
- 一个单向发送端口用于从 SAP 系统将响应发送到的文件夹。  
  
  示例业务流程如下所示：  
  
  ![已连接端口的业务流程](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|Receive_Request|Receive|-设置**名称**到*Receive_Request*<br />-设置**激活**到 *，则返回 True*|  
|Send_LOB|Send|-设置**名称**到*Send_LOB*|  
|Receive_LOB|Receive|-设置**名称**到*Receive_LOB*<br />-设置**激活**到*False*|  
|Send_Response|Send|-设置**名称**到*Send_Response*|  
  
### <a name="adding-ports"></a>添加端口  
 为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|ReceiveMsgPort|-设置**标识符**到*ReceiveMsgPort*<br />-设置**类型**到*ReceiveMsgPortType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|SendToLOBPort|-设置**标识符**到*SendToLOBPort*<br />-设置**类型**到*SendToLOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SendMsgPort|-设置**标识符**到*SendMsgPort*<br />-设置**类型**到*SendMsgPortType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|Receive_Request|-设置**消息**到*请求*<br />-设置**操作**到*ReceiveMsgPort.Operation_1.Request*|  
|Send_LOB|-设置**消息**到*请求*<br />-设置**操作**到*SendToLOBPort.Operation_1.Request*|  
|Receive_LOB|-设置**消息**到*响应*<br />-设置**操作**到*SendToLOBPort.Operation_1.Response*|  
|Send_Response|-设置**消息**到*响应*<br />-设置**操作**到*SendMsgPort.Operation_1.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动以调用 RFC，SAP 系统中的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须在预定义的位置删除该业务流程的请求消息。 请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)需要了解的有关为 SAP 系统中调用 RFC 的请求消息的架构。 例如，要调用 RFC_CUSTOMER_GET 的请求消息是：  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 业务流程使用该消息并将其发送到 SAP 系统。 来自 SAP 系统的响应被保存在定义为业务流程的一部分的其他文件位置。 例如，来自 SAP 系统的更高版本的请求消息的响应是：  
  
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
 在 SAP 系统中使用 BizTalk Server 调用 RFC 时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)