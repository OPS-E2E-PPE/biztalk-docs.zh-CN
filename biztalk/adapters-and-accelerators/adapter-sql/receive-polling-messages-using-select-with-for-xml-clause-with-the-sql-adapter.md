---
title: 接收使用 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句的轮询消息 |Microsoft 文档
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
ms.openlocfilehash: 51cd634d7933f7e25de2e742711b1593bf6b6dc1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967699"
---
# <a name="receive-polling-messages-using-select-statements-with-for-xml-clause-from-sql-using-biztalk-server"></a>接收使用 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句的轮询消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来接收使用 SELECT 语句或存储的过程包含 FOR XML 子句的 SQL Server 表或视图的定期的数据更改消息。 你可以指定这些语句作为适配器执行轮询数据库的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回的结果集。  
  
 有关如何的适配器支持轮询的详细信息，请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。 有关轮询操作的 SOAP 消息结构的信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。 SQL [FOR XML 子句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)提供更多详细信息。
  
> [!NOTE]
>  本主题演示如何使用**XmlPolling**入站操作接收轮询消息。 **XmlPolling**操作用于轮询使用 SELECT 语句或存储的过程包含 FOR XML 子句的 SQL Server 数据库。 有关消息**XmlPolling**操作包括接收在 SQL Server Management Studio 中执行 SELECT 语句或存储的过程的 xml 消息。  
>   
>  适配器还可用于接收不同类型的轮询消息。  
>   
>  -   如果你想要获取弱类型轮询消息，则必须使用轮询操作。 有关详细信息，请参阅[从通过使用 BizTalk Server 的 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  
> -   如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。 你还必须使用**TypedPolling**操作以单个的 BizTalk 应用程序中有多个轮询操作。 有关说明如何执行**TypedPolling**操作，请参阅[接收强类型轮询基于的数据更改消息使用 BizTalk Server 从 SQL Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)。  
  
> [!IMPORTANT]
>  如果你想要单个的 BizTalk 应用程序中有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。 使用唯一连接 URI，你可以创建多个接收轮询同一数据库中或甚至同一个表在数据库中的端口。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]更改消息的接收数据的支持，我们使用 SELECT 语句与 FOR XML 子句轮询 SQL Server 数据库。 调用 SQL Server Management Studio 中的此类的语句时，输出是一条 xml 消息的形式。 若要使用此类语句轮询 SQL Server 数据库，必须具有响应 xml 消息的架构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]需要此架构用于在执行带 FOR XML 子句的 SELECT 语句后接收轮询消息。 因此，若要使用带有 FOR XML 子句的 SELECT 语句轮询 SQL Server 数据库，必须执行以下一组任务。  
  
1.  生成带有 FOR XML 子句的 SELECT 语句的 XML 响应消息的架构。  
  
2.  创建 BizTalk 项目，并将生成的架构添加到项目。  
  
3.  在从 SQL Server 数据库接收 XML 响应消息的 BizTalk 项目中创建一条消息。  
  
4.  创建业务流程的 SQL Server 数据库从接收消息，并将它们保存到一个文件夹。  
  
5.  生成和部署 BizTalk 项目。  
  
6.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
    > [!IMPORTANT]
    >  对于入站的轮询方案，你始终必须配置单向的 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不支持。  
  
7.  启动 BizTalk 应用程序。  
  
##  <a name="BKMK_RespSchema"></a>生成 SELECT 语句的响应消息架构  
 你可以通过包括生成 SELECT 语句的响应消息的架构`xmlschema`子句`for xml`子句。 在本主题中，我们使用 SELECT 语句以给定的员工 id 检索员工详细信息 若要执行的 SELECT 语句检索架构，必须按以下方式编写 SELECT 语句：  
  
```  
SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto, xmlschema  
```  
  
 执行此 SELECT 语句，以获取响应消息的架构。 保存该架构。 你现在必须创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并将此架构添加到项目。 对于此示例，您可以命名此架构作为**PollingResponse.xsd**。  
  
> [!IMPORTANT]
>  请确保你删除`xmlschema`子句后执行 SELECT 语句以生成架构。 如果你没有执行此操作，最后执行 SELECT 语句通过 BizTalk 作为 XmlPolling 操作的一部分时，你将再次生成响应消息中的架构。 因此，若要获取你必须删除的 xml 响应消息`xmlschema`子句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>若要将架构添加到 BizTalk 项目  
  
1.  创建 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  添加到 BizTalk 项目存储过程生成的响应架构。 右键单击解决方案资源管理器中的 BizTalk 项目，指向**添加**，然后单击**现有项**。 在添加现有项对话框中，导航到保存该架构，然后单击的位置**添加**。  
  
3.  打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并进行以下更改。  
  
    1.  将节点添加到架构，并移动现有的根节点，在此新添加的节点下。 为指定的根节点名称。 本主题中，重命名根节点到**根**。  
  
    2.  生成的 SELECT 语句引用 sqltypes.xsd 的响应架构。 你可以从 sqltypes.xsd 架构[http://go.microsoft.com/fwlink/p/?LinkId=131087](http://go.microsoft.com/fwlink/p/?LinkId=131087)。 将 sqltypes.xsd 架构添加到 BizTalk 项目。  
  
    3.  在为 SELECT 语句生成的架构，将的值更改`import schemaLocation`所示。  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         因为你已添加到你的 BizTalk 项目 sqltypes.xsd 架构执行此操作。  
  
    4.  提供架构目标命名空间。 单击**\<架构\>** 节点，然后在属性窗格中，指定的命名空间中**目标 Namespace**属性。 本主题中，为提供的命名空间作为`http://ForXmlPolling/namespace`。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。  
  
 对于本主题中，你必须创建一条消息的 SQL Server 数据库从接收消息。  
  
 执行以下步骤以创建消息并将它们链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**PollingMessage**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLPolling.PollingResponse*，其中*ForXMLPolling*是 BizTalk 项目的名称。 *PollingResponse*是通过在所述执行 SELECT 语句生成的响应架构的名称[接收使用 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句的轮询消息](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于接收基于轮询的数据更改消息从 SQL Server 数据库。 在此业务流程，适配器接收到为指定的 select 语句的响应**PollingStatement**绑定属性。 SELECT 语句的响应保存到文件位置。 将包含轮询 SQL Server 数据库典型业务流程：  
  
-   接收和发送形状来从 SQL Server 接收消息并分别将发送到文件端口。  
  
-   单向接收端口从 SQL Server 接收消息。  
  
    > [!IMPORTANT]
    >  你始终必须配置的入站的轮询方案单向接收端口。 双向接收入站操作不支持端口。  
  
-   单向发送端口将从 SQL Server 数据库的轮询响应发送到的文件夹。  
  
 示例业务流程如下所示。  
  
 ![轮询 SQL Server 数据库的业务流程](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br /><br /> -将设置**激活**到*True*|  
|SaveMessage|Send|-将设置**名称**到*SaveMessage*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|SQLReceivePort|-将设置**标识符**到*SQLReceivePort*<br /><br /> -将设置**类型**到*SQLReceivePortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*接收*|  
|SaveMessagePort|-将设置**标识符**到*SaveMessagePort*<br /><br /> -将设置**类型**到*SaveMessagePortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*SQLReceivePort.XmlPolling.Request*|  
|SaveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*SaveMessagePort.XmlPolling.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和其中 BizTalk 业务流程将消息从数据库中删除 SQL Server 的相应文件端口上定义的位置。 这些消息将以响应接收端口指定轮询语句。  
  
    -   定义一个物理 WCF 自定义或 WCF SQL 单向接收端口。 此端口轮询作为端口号指定的轮询语句的 SQL Server 数据库。 有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
        > [!IMPORTANT]
        >  不需要执行此步骤中，如果指定在设计时绑定属性。 在这种情况下，你可以创建 WCF 自定义或 WCF SQL 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
        |绑定属性|值|  
        |----------------------|-----------|  
        |**InboundOperationType**|请确保将此设置为**XmlPolling**。|  
        |**PolledDataAvailableStatement**|请确保指定的 SQL 语句。 对于本主题中，指定：<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|请确保你提供的相同语句，而不`xmlschema`子句中所述生成架构时指定[接收使用 FOR XML 子句中使用 BizTalk Server的SQLSELECT语句的轮询消息](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).<br /><br /> `SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto`<br /><br /> **注意：** 请注意，SELECT 语句不包含`xmlschema`子句。|  
        |**XmlStoredProcedureRootNodeName**|指定在所述添加到 SELECT 语句中，为生成的响应架构的根节点名称[生成 SELECT 语句的响应消息的架构](#BKMK_RespSchema)。 对于本主题中，请将此设置为**根**。|  
        |**XmlStoredProcedureRootNodeNamespace**|指定用于 SELECT 语句中，生成的响应架构的目标命名空间下所述[生成 SELECT 语句的响应消息的架构](#BKMK_RespSchema)。 对于本主题中，请将此设置为`http://ForXmlPolling/namespace`。|  
  
         有关不同的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
        > [!NOTE]
        >  我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以执行以便通过将服务添加行为配置 WCF 自定义或 WCF SQL 时接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 SQL Server 数据库从接收消息的 BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF SQL 单向接收端口，从而轮询使用为指定的语句的 SQL Server 数据库**PollingStatement**绑定属性，正在运行。  
  
-   文件发送端口，从而从 SQL Server 接收消息，正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，下面的一组操作需要置于相同的序列：  
  
-   适配器执行**PolledDataAvailableStatement**对员工表并确定表具有进行轮询的记录。  
  
-   适配器执行轮询语句，并接收来自 SQL Server 数据库的轮询消息。 轮询语句包含带有 FOR XML 子句的 SELECT 语句，因为该适配器接收的轮询消息如下所示：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Root xmlns="http://ForXmlPolling/namespace">  
      <Employee Employee_ID="10765" Name="John" Designation="Tester" xmlns="" />   
      <Employee Employee_ID="10766" Name="Sam" Designation="Manager" xmlns="" />   
      .....  
      .....  
    </Root>  
    ```  
  
     请注意，生成使用执行 SELECT 语句时，相同的架构收到轮询消息**xmlschema**子句。 此外需要注意的根节点和命名空间是相同的值为指定**XmlStoredProcedureRootNodeName**和**XmlStoredProcedureRootNodeNamespace**分别绑定属性。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询除非你显式禁用接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
 [与 BizTalk Server 使用的 SQL 适配器轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)