---
title: 调用 Trfc 在 SAP 中使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking using BizTalk Server
ms.assetid: 9489adca-cf2c-4e15-8573-445acd7ebf73
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baebf2a3f1723265612974f4728797bca7a070a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989744"
---
# <a name="invoke-trfcs-in-sap-using-biztalk-server"></a>调用 Trfc SAP 使用 BizTalk Server 中
事务性远程函数调用 (Trfc) 保证 SAP 系统上的 RFC 有且只有一个时执行。 您可以调用任何显示的 Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 tRFC。 调用 tRFC 是类似于调用 RFC (请参阅[调用中使用 BizTalk server 的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)) 具有以下差异：  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc 不同节点下的图面 (**TRFC**) 与 Rfc (**RFC**)。  
  
- tRFC 操作包括映射到由 tRFC SAP 事务 ID 的 GUID 参数[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 调用 tRFC 后，必须调用 RfcConfirmTransID 操作以确认 （提交） tRFC SAP 系统上。 此操作显示正下方**TRFC**中的节点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持调用 tRFC，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 对于用于调用 tRFC 消息的 SOAP 结构有关的详细信息，请参阅[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="how-to-invoke-a-trfc-in-an-sap-system-using-biztalk-server"></a>调用 tRFC SAP 系统使用 BizTalk Server 中的方式？  
 对 SAP 系统使用执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要调用 tRFC SAP 系统中，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要在 SAP 系统中调用的 tRFC 生成架构。 您还必须生成的架构**RfcConfirmTransID**提交 TID SAP 系统中的操作。  
  
2. 用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。  
  
3. 创建一个业务流程调用 tRFC SAP 系统中，然后提交以响应由 tRFC 调用在 SAP 系统中创建 TID [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，tRFCClient，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[示例从 SAP 适配器](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用 tRFC 使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，我们将生成的架构：  
  
- *BAPI_SALESORDER_CREATEFROMDAT2* tRFC。  
  
- RfcConfirmTransID 操作。 必须使用此操作来提交创建 SAP 系统中 TID。 SAP 系统收到此调用后它从系统中删除 TID。  
  
  请参阅[浏览、 搜索和获取 tRFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-trfc-operations-in-sap.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须从 BizTalk 项目的业务流程视图中的消息链接你生成的架构。  
  
 对于本主题中，您必须创建四个消息，设置才能调用 tRFC 和另一个请求-响应消息的请求-响应消息设置为调用 RfcConfirmTransID 操作。  
  
 执行以下步骤来创建消息并将其链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，并选择消息类型。 例如，选择*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2*，其中*tRFC_Client*是 BizTalk 项目的名称。 *SAPBindingSchema1*是为生成的架构*BAPI_SALESORDER_CREATEFROMDAT2*。|  
  
5.  重复上述步骤创建三个更多的消息。 在中**属性**窗格中的新消息，执行以下操作。  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |响应|*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |TIDRequest|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransID*|  
    |TIDResponse|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransIDResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于调用 Trfc SAP 系统中。 在此业务流程中删除时的请求消息定义接收位置。 业务流程使用此消息，并将其传递到 SAP 系统。 响应从 SAP 收到并保存在另一个位置。 响应消息包含的 GUID。 业务流程包括**构造消息**形状，可从响应中提取 GUID 并构造一条消息，符合的架构**RfcConfirmTransID**操作。 要调用的消息**RfcConfirmTransID**操作发送到 SAP 系统具有 GUID 作为参数 _ 用于调用 Trfc 在 SAP 系统中后, 跟一个典型的业务流程**RfcConfirmTransID**操作将包含：  
  
- 发送和接收形状来将消息发送到 SAP 系统和接收响应。  
  
- 构造消息形状和中的消息赋值形状构造的消息**RfcConfirmTransID**操作。  
  
- 一个单向接收端口接收请求消息发送到 SAP 系统以调用 tRFC。  
  
- 一个双向发送端口以发送消息来调用 tRFC 并接收响应。  
  
- 一个双向发送端口以发送消息来调用**RfcConfirmTransID**操作和接收响应。  
  
- 两个单向发送端口以从 SAP 系统将响应发送到的文件夹。  
  
  示例业务流程如下所示：  
  
  ![用于发出 tRFC 客户端调用业务流程](../../adapters-and-accelerators/adapter-sap/media/369d62dd-9ae4-4673-b346-03d2acfb453a.gif "369d62dd-9ae4-4673-b346-03d2acfb453a")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveXml|Receive|-设置**名称**到*ReceiveXml*<br />-设置**激活**到 *，则返回 True*|  
|SendToLOB|Send|-设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
|SendTIDMsg|Send|-设置**名称**到*SendTIDMsg*|  
|ReceiveTIDRsp|Receive|-设置**名称**到*ReceiveTIDRsp*<br />-设置**激活**到*False*|  
|SendTIDRsp|Send|-设置**名称**到*SendTIDRsp*|  
  
### <a name="adding-the-construct-message-shape"></a>添加构造消息形状  
 TRFC 调用该 SAP 系统的响应包含的 GUID。 若要提交 tRFC 调用，必须将相同的 GUID 传递给 RfcConfirmTransID 操作。 若要执行此操作，必须包含构造消息形状，并在其中消息赋值形状，在业务流程中。 在这里，构造消息形状的目的是：  
  
- 若要从 tRFC 调用该 SAP 系统从收到的响应中提取 GUID。  
  
- 若要构造一条消息，符合 RfcConfirmTransID 操作的消息架构。  
  
  对于构造消息形状中，您必须设置**构造的消息**属性设置为**TIDRequest**。  
  
  必须将以下代码段添加到消息赋值形状：  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<RfcConfirmTransID xmlns='http://Microsoft.LobServices.Sap/2007/03/RfcApi/'><TransactionalRfcOperationIdentifier /></RfcConfirmTransID>");  
TIDRequest = XmlDoc;  
TIDRequest.TransactionalRfcOperationIdentifier = xpath(Response,"string(/*[local-name()='BAPI_SALESORDER_CREATEFROMDAT2Response']/*[local-name()='TransactionalRfcOperationIdentifier']/text())");  
```  
  
 若要使用上述代码摘录中，您必须具有：  
  
-   创建了一个变量**XmlDoc**、 在 BizTalk 项目，并将其类型设置为 System.Xml.XmlDocument。 有关创建变量的详细信息，请参阅[业务流程中使用变量](../../core/using-variables-in-orchestrations.md)。
  
-   提升**TransactionalRfcOperationIdentifier** RfcConfirmTransID 操作的架构中的属性。 有关升级属性的详细信息，请参阅[升级属性](../../core/promoting-properties.md)。
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInPortType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|tRFC_Port|-设置**标识符**到*tRFC_Port*<br />-设置**类型**到*tRFC_PortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SavetRFCResponse|-设置**标识符**到*SavetRFCResponse*<br />-设置**类型**到*SavetRFCResponsePortType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
|TID_Port|-设置**标识符**到*TID_Port*<br />-设置**类型**到*TIDPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveTIDResponse|-设置**标识符**到*SaveTIDResponse*<br />-设置**类型**到*SaveTIDResponsePortType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，以前的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveXml|-设置**消息**到*请求*<br />-设置**操作**到*FileIn.tRFC.Request*|  
|SendToLOB|-设置**消息**到*请求*<br />-设置**操作**到*tRFC_Port.tRFC.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*tRFC_Port.tRFC.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SavetRFCResponse.tRFC.Request*|  
|SendTIDMsg|-设置**消息**到*TIDRequest*<br />-设置**操作**到*TID_Port.TID.Request*|  
|ReceiveTIDRsp|-设置**消息**到*TIDResponse*<br />-设置**操作**到*TID_Port.TID.Response*|  
|SendTIDRsp|-设置**消息**到*TIDResponse*<br />-设置**操作**到*SaveTIDResponse.TID.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息发送到 SAP 系统。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义物理 WCF 自定义或 WCF SAP 发送端口 （分别用于 tRFC 请求消息和 RfcConfirmTransID 消息） 将消息发送到 SAP 系统。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动调用 Trfc SAP 系统中的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须删除该业务流程的请求消息。 请参阅[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)需要了解的有关为 SAP 系统中调用 tRFC 的请求消息的架构。 例如，要调用 tRFC 作为 BAPI_SALEASORDER_CREATEFROMDAT2 的请求消息是：  
  
```  
<BAPI_SALESORDER_CREATEFROMDAT2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
  <ORDER_HEADER_IN>  
    <DOC_TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">TA</DOC_TYPE>  
    <SALES_ORG xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_ORG>  
    <DISTR_CHAN xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">10</DISTR_CHAN>  
    <DIVISION xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">00</DIVISION>  
    <SALES_OFF xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_OFF>  
    <REQ_DATE_H xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-09-01T23:50:00</REQ_DATE_H>  
    <PURCH_DATE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-08-25T23:50:00</PURCH_DATE>  
    <PURCH_NO_C xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">Cust PO</PURCH_NO_C>  
    <CURRENCY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">EUR</CURRENCY>  
  </ORDER_HEADER_IN>  
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <MATERIAL>P-109</MATERIAL>  
      <PLANT>1000</PLANT>  
      <TARGET_QU>ST</TARGET_QU>  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>  
      <PARTN_NUMB>0000001390</PARTN_NUMB>  
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
  <RETURN/>  
  <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
</BAPI_SALESORDER_CREATEFROMDAT2>  
```  
  
 业务流程将使用消息、 将其传递到 SAP 系统，并接收来自 SAP 系统的响应。 响应消息保存在指定的业务流程一部分的其他文件位置。 从 SAP 系统的响应包含的 GUID。 然后，业务流程从响应中生成另一个请求消息，并将其传递到 SAP 系统，以执行 RfcConfirmTransID。 从 SAP 系统 RfcConfirmTransID 操作收到响应后，它被复制到文件位置。 总之，该操作已成功执行后：  
  
-   用于调用 tRFC 来自 SAP 的响应消息复制到文件位置。 这包含已发送到 SAP 系统的 GUID 相同。 调用 tRFC 原样 BAPI_SALESORDER_CREATEFROMDAT2 响应消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
      <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
    </BAPI_SALESORDER_CREATEFROMDAT2Response>  
    ```  
  
-   RfcConfirmTransID 的响应消息复制到同一位置。 这是一个空响应。 RfcConfirmTransID 的响应消息是：  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <RfcConfirmTransIDResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/RfcApi/"></RfcConfirmTransIDResponse>  
    ```  
  
> [!NOTE]
>  可以使用**ConvertGuidToTid()** 由要检索 TID 映射到 GUID SAP 系统中的 SAP 适配器程序集公开的公共方法。 有关详细信息，请参阅[特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)。  
  
## <a name="possible-exceptions"></a>可能的异常  
 在 SAP 系统中使用 BizTalk Server 调用 tRFC 时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)