---
title: 接收轮询消息使用包含 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65c629c1-9ef7-4aa1-8ec1-f94a3cb41cb0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 967279b93be393d38d220d487e383beb73d91b4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014126"
---
# <a name="receive-polling-messages-using-select-statements-with-for-xml-clause-from-sql-using-biztalk-server"></a>接收轮询消息使用包含 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过使用 SELECT 语句或包含 FOR XML 子句的存储的过程接收定期的数据更改消息的 SQL Server 表或视图。 您可以指定这些语句作为适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。  
  
 适配器如何支持轮询的详细信息，请参阅[支持的轮询](https://msdn.microsoft.com/library/dd788416.aspx)。 轮询操作的 SOAP 消息结构的信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。 SQL [FOR XML 子句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)提供了更多详细信息。
  
> [!NOTE]
>  本主题演示如何使用**XmlPolling**的入站操作接收轮询消息。 **XmlPolling**操作用于轮询 SQL Server 数据库使用 SELECT 语句或包含 FOR XML 子句的存储的过程。 消息**XmlPolling**操作包括通过 SQL Server Management Studio 中执行 SELECT 语句或存储的过程接收的 xml 消息。  
> 
>  适配器还可用于接收不同类型的轮询消息。  
> 
> - 如果你想要获取弱类型的轮询消息，则必须使用轮询操作。 有关详细信息，请参阅[从 SQL Server 使用 BizTalk server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  
>   -   如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。 此外必须使用**TypedPolling**操作在一个 BizTalk 应用程序中有多个轮询操作。 有关如何执行的说明**TypedPolling**操作，请参阅[接收强类型基于轮询的数据更改消息使用 BizTalk Server 从 SQL Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)。  
> 
> [!IMPORTANT]
>  如果想要在单个 BizTalk 应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。 使用唯一连接 URI，可以创建多个接收端口的同一个数据库或甚至同一个表在数据库中的轮询一次。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何将[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收数据更改消息，我们使用 SELECT 语句与 FOR XML 子句来轮询 SQL Server 数据库。 当您调用此类语句在 SQL Server Management Studio 中的时，输出是一条 xml 消息的形式。 若要使用此类语句轮询 SQL Server 数据库，必须具有响应 xml 消息的架构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]需要此架构后执行带 FOR XML 子句的 SELECT 语句接收轮询消息。 因此，若要使用带 FOR XML 子句的 SELECT 语句轮询 SQL Server 数据库，你必须执行以下一组任务。  
  
1.  生成 SELECT 语句与 FOR XML 子句的 XML 响应消息的架构。  
  
2.  创建 BizTalk 项目，并将生成的架构添加到项目。  
  
3.  在接收来自 SQL Server 数据库的 XML 响应消息的 BizTalk 项目中创建一条消息。  
  
4.  创建业务流程从 SQL Server 数据库接收消息并将它们保存到一个文件夹。  
  
5.  生成并部署 BizTalk 项目。  
  
6.  配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
    > [!IMPORTANT]
    >  对于入站的轮询方案始终必须配置一个单向 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不受支持。  
  
7.  启动 BizTalk 应用程序。  
  
##  <a name="BKMK_RespSchema"></a> SELECT 语句的响应消息生成架构  
 可以通过包括生成 SELECT 语句的响应消息的架构`xmlschema`子句与`for xml`子句。 在本主题中，我们使用 SELECT 语句以给定的员工 id 检索员工的详细信息 若要执行的 SELECT 语句检索该架构，必须按以下方式编写 SELECT 语句：  
  
```  
SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto, xmlschema  
```  
  
 执行此 SELECT 语句，以获取响应消息的架构。 保存该架构。 现在必须创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并将此架构添加到项目。 对于此示例中，可以命名为此架构**PollingResponse.xsd**。  
  
> [!IMPORTANT]
>  请确保删除`xmlschema`子句执行 SELECT 语句生成的架构后。 如果未能这样做，在最后执行 SELECT 语句通过 BizTalk XmlPolling 操作的一部分，您将再次生成响应消息中的架构。 因此，若要获取响应消息作为 xml 必须删除`xmlschema`子句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>若要将架构添加到 BizTalk 项目  
  
1. 创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2. 将添加到 BizTalk 项目的存储过程生成的响应架构。 右键单击解决方案资源管理器中的 BizTalk 项目，指向**外**，然后单击**现有项**。 在添加现有项对话框中，导航到保存的架构和单击的位置**添加**。  
  
3. 打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并进行以下更改。  
  
   1.  将节点添加到架构，并将此新添加的节点下的现有根节点。 为根节点名称。 本主题中，重命名的根节点**根**。  
  
   2.  生成的 SELECT 语句引用 sqltypes.xsd 的响应架构。 可以获取从 sqltypes.xsd 架构[ http://go.microsoft.com/fwlink/p/?LinkId=131087 ](http://go.microsoft.com/fwlink/p/?LinkId=131087)。 将 sqltypes.xsd 架构添加到 BizTalk 项目。  
  
   3.  在 SELECT 语句生成的架构，将的值更改`import schemaLocation`所示。  
  
       ```  
       import schemaLocation=”sqltypes.xsd”  
       ```  
  
        这样做是因为你已添加到您的 BizTalk 项目 sqltypes.xsd 架构。  
  
   4.  提供架构目标命名空间。 单击**\<架构\>** 节点，并在属性窗格中指定的命名空间中**Target Namespace**属性。 本主题中，为提供的命名空间`http://ForXmlPolling/namespace`。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，必须创建一条消息从 SQL Server 数据库接收消息。  
  
 执行以下步骤创建消息并将其链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**PollingMessage**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLPolling.PollingResponse*，其中*ForXMLPolling*是 BizTalk 项目的名称。 *PollingResponse*是通过下面所述执行 SELECT 语句生成的响应架构的名称[接收轮询消息使用包含 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于接收基于轮询的数据更改消息从 SQL Server 数据库。 在此业务流程，适配器将接收 $ select 语句为指定的响应**PollingStatement**属性绑定。 SELECT 语句的响应保存到文件位置。 用于轮询 SQL Server 数据库的典型业务流程将包含：  
  
- 接收和发送形状从 SQL Server 接收消息并将发送给 FILE 端口，分别。  
  
- 一个单向接收端口以接收来自 SQL Server 的消息。  
  
  > [!IMPORTANT]
  >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  
  
- 单向发送端口将从 SQL Server 数据库轮询响应发送到的文件夹。  
  
  示例业务流程如下所示。  
  
  ![用于轮询 SQL Server 数据库的业务流程](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveMessage|Send|-设置**名称**到*SaveMessage*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|SQLReceivePort|-设置**标识符**到*SQLReceivePort*<br /><br /> -设置**类型**到*SQLReceivePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|SaveMessagePort|-设置**标识符**到*SaveMessagePort*<br /><br /> -设置**类型**到*SaveMessagePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*SQLReceivePort.XmlPolling.Request*|  
|SaveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*SaveMessagePort.XmlPolling.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应的 BizTalk 业务流程将消息从数据库中删除 SQL Server 的文件端口上定义的位置。 这些消息将以响应接收端口中指定的轮询语句。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 单向接收端口。 此端口将轮询指定的端口的轮询语句与 SQL Server 数据库。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果指定在设计时的绑定属性。 在这种情况下，您可以创建 WCF 自定义或 WCF SQL 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|请确保将其设置为**XmlPolling**。|  
    |**PolledDataAvailableStatement**|请确保指定的 SQL 语句。 对于本主题中，指定：<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|请确保提供相同的语句，不带`xmlschema`子句，如中所述生成架构时指定[接收轮询消息使用包含 FOR XML 子句中使用 BizTalk Server的SQLSELECT语句](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).<br /><br /> `SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto`<br /><br /> **注意：** 请注意，SELECT 语句不包含`xmlschema`子句。|  
    |**XmlStoredProcedureRootNodeName**|指定的所述添加到 SELECT 语句生成的响应架构的根节点名称[SELECT 语句的响应消息生成架构](#BKMK_RespSchema)。 对于本主题，请将此设置为**根**。|  
    |**XmlStoredProcedureRootNodeNamespace**|指定 SELECT 语句生成的响应架构的目标命名空间，如下面所述[SELECT 语句的响应消息生成架构](#BKMK_RespSchema)。 对于本主题，请将此设置为`http://ForXmlPolling/namespace`。|  
  
     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以执行以便通过将服务添加行为时配置 WCF 自定义或 WCF SQL 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和使用 SQL 事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 SQL Server 数据库中接收消息的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF-SQL 单向接收端口，轮询 SQL Server 数据库使用为指定的语句**PollingStatement**绑定属性，正在运行。  
  
-   FILE 发送端口，从 SQL Server 接收消息，正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，以下组操作需要置于相同的序列：  
  
-   适配器将执行**PolledDataAvailableStatement**对 Employee 上表，确定此表具有用于轮询的记录。  
  
-   适配器执行轮询语句，并从 SQL Server 数据库接收轮询消息。 由于轮询语句包含带 FOR XML 子句的 SELECT 语句，则接收适配器的轮询消息如下所示：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Root xmlns="http://ForXmlPolling/namespace">  
      <Employee Employee_ID="10765" Name="John" Designation="Tester" xmlns="" />   
      <Employee Employee_ID="10766" Name="Sam" Designation="Manager" xmlns="" />   
      .....  
      .....  
    </Root>  
    ```  
  
     请注意，由使用执行 SELECT 语句生成相同的架构中接收轮询消息**xmlschema**子句。 此外请注意，根节点和命名空间是相同的值的形式指定**XmlStoredProcedureRootNodeName**并**XmlStoredProcedureRootNodeNamespace**分别绑定属性。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
 [通过使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)