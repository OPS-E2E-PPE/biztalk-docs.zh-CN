---
title: "执行存储的过程具有 FOR XML 子句中使用 BizTalk Server 的 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d8fe927-90bf-48fc-a418-63b920b409ed
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c1b69c522f01f2561ea8145c11dec3e36b5cd4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk-server"></a>执行具有 FOR XML 子句中使用 BizTalk Server 的 SQL Server 中的存储的过程
SQL SELECT 语句可以有一个 FOR XML 子句，而不是行集以 XML 形式返回查询结果。 你还可以具有带 FOR XML 子句的 SELECT 语句的存储的过程。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)提供了更多信息。
  
 你可以使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行如存储过程。  
  
> [!IMPORTANT]
>  适用于"本机"的 SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]需要能够 FOR XML 子句的 SELECT 语句的一部分的存储的过程。 你可以使用此类存储的过程基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]而不必对存储的过程定义中进行任何更改。  
>   
>  您可以始终使用架构生成使用本机提供的早期版本的 SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[使用 FOR XML 查询与 WCF SQL 适配器](http://go.microsoft.com/fwlink/?LinkId=223428)(http://go.microsoft.com/fwlink/?LinkId=223428)。  
  
## <a name="how-to-invoke-stored-procedures-with-for-xml-clause"></a>如何以调用存储的过程与 FOR XML 子句  
 使用 SQL Server Management Studio 或使用适用于 SQL 适配器中的 FOR XML 子句为存储的过程的调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，输出为一条 xml 消息的形式。 若要使用这些过程基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须具有输出消息的架构。 基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在执行使用 FOR XML 子句为存储的过程后，从 SQL Server 接收响应消息时需要此架构。 请注意，将通过适配器本身生成要调用此存储的过程的请求消息。  
  
 除了具有响应消息的架构，你还必须执行某些任务要使用基于 WCF 的 FOR XML 子句调用存储的过程[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
1.  生成具有 FOR XML 子句的存储过程的响应消息的架构。 如果你已有由"本机"的 SQL 适配器适用于生成的响应架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则可以跳过此步骤。  
  
2.  创建 BizTalk 项目，并将生成的架构添加到项目。  
  
3.  使用基于 WCF 的 FOR XML 子句生成的存储过程的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 这提供了请求消息，该适配器将发送到 SQL Server 来调用存储的过程的架构。  
  
4.  在 BizTalk 项目发送和接收消息从 SQL Server 中创建消息。 请求消息必须符合的适配器由生成的请求消息架构。 响应消息必须符合该架构的使用"本机"的 SQL 适配器获取响应消息或通过在 SQL Server Management Studio 执行 FOR XML 子句的存储的过程。  
  
5.  创建业务流程来调用 SQL Server 数据库中存储的过程。  
  
6.  生成和部署 BizTalk 项目。  
  
7.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
8.  启动 BizTalk 应用程序。  
  
##  <a name="BKMK_RespSchema"></a>生成存储过程的响应消息架构  
  
> [!NOTE]
>  不需要执行此步骤中，如果必须由 SQL 适配器适用于生成的响应架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 你可以生成的存储过程，响应消息的架构，提供存储过程中的 SELECT 语句具有`xmlschema`子句`for xml`子句。 在本主题中，我们将使用给定的员工 id 检索员工详细信息的 GET_EMP_DETAILS_FOR_XML 存储过程 若要执行存储的过程检索架构，SELECT 语句如下所示：  
  
```  
SELECT [Employee_ID] ,[Name] ,[DOJ] ,[Designation] ,[Job_Description] ,[Photo] ,cast([Rating] as varchar(100)) as Rating ,[Salary] ,[Last_Modified] ,[Status] ,[Address]   
FROM [Adapt_Doc].[dbo].[Employee] for xml auto, xmlschema  
```  
  
 执行此存储的过程以获取响应消息的架构。 请注意，存储过程的响应包含架构，以及执行存储的过程中的数据。 你必须从响应中复制架构并将其保存到一个文本簿。 对于此示例，您可以命名此架构作为**ResponseSchema.xsd**。 你现在必须创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并将此架构添加到项目。  
  
> [!IMPORTANT]
>  请确保你删除`xmlschema`子句后执行存储的过程以生成架构。 如果你没有执行此操作，最后执行 BizTalk 通过存储的过程时，你将再次生成响应消息中的架构。 因此，若要获取你必须删除的 xml 响应消息`xmlschema`子句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>若要将架构添加到 BizTalk 项目  
  
1.  创建 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  添加到 BizTalk 项目存储过程生成的响应架构。 右键单击解决方案资源管理器中的 BizTalk 项目，指向**添加**，然后单击**现有项**。 在添加现有项对话框中，导航到保存该架构，然后单击的位置**添加**。  
  
3.  打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并进行以下更改。  
  
    1.  将节点添加到架构，并移动现有的根节点，在此新添加的节点下。 为指定的根节点名称。 本主题中，重命名根节点到**根**。  
  
    2.  存储过程生成的响应架构引用 sqltypes.xsd。 你可以从 sqltypes.xsd 架构[http://go.microsoft.com/fwlink/?LinkId=131087](http://go.microsoft.com/fwlink/?LinkId=131087)。 将 sqltypes.xsd 架构添加到 BizTalk 项目。  
  
    3.  在存储过程生成的架构，将的值更改`import schemaLocation`所示。  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         因为你已添加到你的 BizTalk 项目 sqltypes.xsd 架构执行此操作。  
  
    4.  提供架构目标命名空间。 单击**\<架构\>**节点，然后在属性窗格中，指定的命名空间中**目标 Namespace**属性。 本主题中，为提供的命名空间作为`http://ForXmlStoredProcs/namespace`。  
  
## <a name="generating-schema-for-the-request-message-to-invoke-the-stored-procedure"></a>生成请求消息来调用存储的过程的架构  
 若要生成可以使用的请求消息架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 本主题中，为生成 GET_EMP_DETAILS_FOR_XML 存储过程的架构。 有关如何生成架构使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
> [!IMPORTANT]
>  必须通过选择只能从过程中生成的架构**过程**中的节点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，为其类型由相应的架构定义。 你现在必须创建消息业务流程，并将它们链接到你在上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLProcedure.Procedure_dbo。GET_EMP_DETAILS_FOR_XML*，其中 ForXMLProcedure 是 BizTalk 项目的名称。 Procedure_dbo 是为调用 GET_EMP_DETAILS_FOR_XML 过程生成的架构。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLProcedure.ResponseSchema*，其中 ResponseSchema 是通过执行所在的存储的过程生成的响应架构的名称描述[生成的存储过程的响应消息的架构](#BKMK_RespSchema)。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在 SQL Server 中执行存储的过程。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 你必须包括发送和接收形状来将消息发送到 SQL Server 和接收响应，分别。 调用过程示例业务流程如下所示：  
  
 ![业务流程来调用存储的过程](../../adapters-and-accelerators/adapter-sql/media/eac6e8b6-f0f4-44af-8218-03ca3864b267.gif "eac6e8b6-f0f4-44af-8218-03ca3864b267")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>对于操作形状，指定消息并将其连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.FOR_XML。请求*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.FOR_XML。请求*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.FOR_XML。响应*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.FOR_XML。请求*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 SQL Server 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SQL 发送端口将消息发送到 SQL Server 数据库。 有关如何创建发送端口的说明，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
         你必须在发送端口中指定的操作。 有关包含 FOR XML 子句的过程，必须采用以下格式设置操作。  
  
        ```  
        XmlProcedure/<schema_name>/<procedure_name>  
        ```  
  
         因此，本主题中，我们正在其中执行 GET_EMP_DETAILS_FOR_XML 过程，操作为：  
  
        ```  
        XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML  
        ```  
  
         有关设置操作的详细信息，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。
  
         执行带 FOR XML 子句的存储的过程时，还必须设置以下绑定属性。  
  
        |绑定属性名称|将其设置为|  
        |---------------------------|-----------------|  
        |XmlStoredProcedureRootNodeName|指定在所述添加到存储过程，生成的响应架构的根节点名称[生成的存储过程的响应消息的架构](#BKMK_RespSchema)。 对于本主题中，请将此设置为**根**。|  
        |XmlStoredProcedureRootNodeNamespace|指定的存储过程，生成的响应架构的目标命名空间下所述[生成的存储过程的响应消息的架构](#BKMK_RespSchema)。 对于本主题中，请将此设置为`http://ForXmlStoredProcs/namespace`。|  
  
         有关指定的绑定属性值的详细信息，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须在 SQL Server 数据库中启动过程的调用的 BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   正在运行的 WCF 自定义或 WCF SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须符合使用生成过程的请求架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 例如，要调用 GET_EMP_DETAILS_FOR XML 的请求消息是：  
  
```  
<GET_EMP_DETAILS_FOR_XML xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
  <emp_id>10765</emp_id>  
</GET_EMP_DETAILS_FOR_XML>  
```  
  
 请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)有关调用 SQL Server 中的过程的请求消息架构的详细信息数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 业务流程使用该消息，并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置中。 例如，来自 SQL Server 数据库中的前面的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Root xmlns="http://ForXmlStoredProcs/namespace">  
  <Adapt_Doc.dbo.Employee Employee_ID="10765" Name="John" Designation="asdfaf" Salary="3434.00" Last_Modified="AAAAAAAANso=" Status="0" xmlns="" />  
</Root>  
```  
  
 请注意，通过执行存储的过程生成时，相同的架构收到响应。 此外需要注意的根节点和命名空间是相同的值为指定**XmlStoredProcedureRootNodeName**和**XmlStoredProcedureRootNodeNamespace**分别绑定属性。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)