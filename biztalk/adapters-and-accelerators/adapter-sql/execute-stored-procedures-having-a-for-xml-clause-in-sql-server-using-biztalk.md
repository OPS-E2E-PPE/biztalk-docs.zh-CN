---
title: 执行存储的过程具有 FOR XML 子句中使用 BizTalk Server 的 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d8fe927-90bf-48fc-a418-63b920b409ed
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68473929852b8a57acb25317656fd52a38880b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369645"
---
# <a name="execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk-server"></a>执行存储的过程中使用 BizTalk Server 的 SQL Server 具有 FOR XML 子句
一个 SQL SELECT 语句可以以 XML 形式返回查询结果，而不是行集的 FOR XML 子句。 您还可以具有带 FOR XML 子句的 SELECT 语句的存储的过程。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)提供了更多信息。
  
 可以使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行此类存储过程。  
  
> [!IMPORTANT]
>  "本机"附带的 SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]要求存储的过程以具有 FOR XML 子句的 SELECT 语句的一部分。 可以使用此类存储的过程与基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]而无需对存储的过程定义进行任何更改。  
> 
>  您始终可以使用使用与早期版本的提供的 'native' SQL 适配器生成的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[使用 FOR XML 查询与 WCF SQL 适配器](http://go.microsoft.com/fwlink/?LinkId=223428)(<http://go.microsoft.com/fwlink/?LinkId=223428>)。  
  
## <a name="how-to-invoke-stored-procedures-with-for-xml-clause"></a>如何调用存储的过程与 FOR XML 子句  
 使用 FOR XML 子句中 SQL Server Management Studio 或使用附带 SQL 适配器为存储的过程的调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，输出是一条 xml 消息的形式。 若要使用这些过程与基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，必须具有输出消息的架构。 基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行带 FOR XML 子句的存储的过程后，从 SQL Server 接收响应消息时需要此架构。 请注意，请求消息来调用此存储的过程将生成的适配器本身。  
  
 除了将响应消息架构，您还必须执行某些任务，以调用存储的过程与 FOR XML 子句中使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
1. 生成具有 FOR XML 子句的存储过程的响应消息的架构。 如果已有适用于"本机"的 SQL 适配器生成的响应架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以跳过此步骤。  
  
2. 创建 BizTalk 项目，并将生成的架构添加到项目。  
  
3. 生成架构的存储过程与 FOR XML 子句中使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 这提供了请求消息，适配器将发送到 SQL Server 来调用存储的过程的架构。  
  
4. 要发送和接收消息，从 SQL Server 的 BizTalk 项目中创建消息。 请求消息必须符合由适配器生成的请求消息的架构。 响应消息必须符合架构的使用"本机"的 SQL 适配器获得的响应消息或通过在 SQL Server Management Studio 中执行 FOR XML 子句的存储的过程。  
  
5. 创建一个业务流程调用的 SQL Server 数据库中的存储的过程。  
  
6. 生成并部署 BizTalk 项目。  
  
7. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
8. 启动 BizTalk 应用程序。  
  
##  <a name="BKMK_RespSchema"></a> 存储过程的响应消息生成架构  
  
> [!NOTE]
>  不需要执行此步骤中，如果有适用于 SQL 适配器生成的响应架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 提供的存储过程中的 SELECT 语句，可以生成该存储过程，响应消息的架构`xmlschema`子句与`for xml`子句。 在本主题中，我们使用给定的员工 id 检索员工详细信息的 GET_EMP_DETAILS_FOR_XML 存储过程 若要执行存储的过程检索该架构，SELECT 语句所示如下所示：  
  
```  
SELECT [Employee_ID] ,[Name] ,[DOJ] ,[Designation] ,[Job_Description] ,[Photo] ,cast([Rating] as varchar(100)) as Rating ,[Salary] ,[Last_Modified] ,[Status] ,[Address]   
FROM [Adapt_Doc].[dbo].[Employee] for xml auto, xmlschema  
```  
  
 执行此存储的过程以获取响应消息的架构。 请注意，从存储过程的响应包含架构，以及执行存储的过程中的数据。 必须从响应中复制的架构，并将其保存到文本板。 对于此示例中，可以命名为此架构**ResponseSchema.xsd**。 现在必须创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并将此架构添加到项目。  
  
> [!IMPORTANT]
>  请确保删除`xmlschema`子句后执行存储的过程生成的架构。 如果您不能这样做，在最后执行 BizTalk 通过该存储的过程，您将再次响应消息中生成架构。 因此，若要获取响应消息作为 xml 必须删除`xmlschema`子句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>若要将架构添加到 BizTalk 项目  
  
1. 创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2. 将添加到 BizTalk 项目的存储过程生成的响应架构。 右键单击解决方案资源管理器中的 BizTalk 项目，指向**外**，然后单击**现有项**。 在添加现有项对话框中，导航到保存的架构和单击的位置**添加**。  
  
3. 打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并进行以下更改。  
  
   1.  将节点添加到架构，并将此新添加的节点下的现有根节点。 为根节点名称。 本主题中，重命名的根节点**根**。  
  
   2.  生成的存储的过程引用 sqltypes.xsd 的响应架构。 可以获取从 sqltypes.xsd 架构[ http://go.microsoft.com/fwlink/?LinkId=131087 ](http://go.microsoft.com/fwlink/?LinkId=131087)。 将 sqltypes.xsd 架构添加到 BizTalk 项目。  
  
   3.  在生成的存储过程的架构，将的值更改`import schemaLocation`所示。  
  
       ```  
       import schemaLocation=”sqltypes.xsd”  
       ```  
  
        这样做是因为你已添加到您的 BizTalk 项目 sqltypes.xsd 架构。  
  
   4.  提供架构目标命名空间。 单击**\<架构\>** 节点，并在属性窗格中指定的命名空间中**Target Namespace**属性。 本主题中，为提供的命名空间`http://ForXmlStoredProcs/namespace`。  
  
## <a name="generating-schema-for-the-request-message-to-invoke-the-stored-procedure"></a>生成请求消息来调用存储的过程的架构  
 若要生成可以使用请求消息的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]的 BizTalk 项目中从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 本主题中，生成 GET_EMP_DETAILS_FOR_XML 存储过程的架构。 有关如何生成架构使用的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
> [!IMPORTANT]
>  必须通过选择仅从过程生成的架构**过程**中的节点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到你在上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLProcedure.Procedure_dbo。GET_EMP_DETAILS_FOR_XML*，其中 ForXMLProcedure 是 BizTalk 项目的名称。 Procedure_dbo 是为调用 GET_EMP_DETAILS_FOR_XML 过程生成的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ForXMLProcedure.ResponseSchema*，其中 ResponseSchema 是通过执行存储的过程生成的响应架构的名称下所述[存储过程的响应消息生成架构](#BKMK_RespSchema)。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于在 SQL Server 中执行存储的过程。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 必须包括发送和接收形状将消息发送到 SQL Server 和接收响应，分别。 示例业务流程的调用的过程类似于以下内容：  
  
 ![调用存储的过程的业务流程](../../adapters-and-accelerators/adapter-sql/media/eac6e8b6-f0f4-44af-8218-03ca3864b267.gif "eac6e8b6-f0f4-44af-8218-03ca3864b267")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.FOR_XML。请求*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.FOR_XML。请求*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.FOR_XML。响应*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.FOR_XML。请求*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 有关如何创建发送端口的说明，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
     您必须在发送端口中指定的操作。 有关包含 FOR XML 子句的过程，必须采用以下格式设置操作。  
  
    ```  
    XmlProcedure/<schema_name>/<procedure_name>  
    ```  
  
     因此，本主题中我们执行 GET_EMP_DETAILS_FOR_XML 过程的位置，该操作将：  
  
    ```  
    XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML  
    ```  
  
     有关设置操作的详细信息，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。
  
     执行带 FOR XML 子句的存储的过程时，还必须设置以下绑定属性。  
  
    |绑定属性名称|将此设置为|  
    |---------------------------|-----------------|  
    |XmlStoredProcedureRootNodeName|指定的所述添加到存储过程生成的响应架构的根节点名称[存储过程的响应消息生成架构](#BKMK_RespSchema)。 对于本主题，请将此设置为**根**。|  
    |XmlStoredProcedureRootNodeNamespace|指定存储过程生成的响应架构的目标命名空间下所述[存储过程的响应消息生成架构](#BKMK_RespSchema)。 对于本主题，请将此设置为`http://ForXmlStoredProcs/namespace`。|  
  
     有关指定的绑定属性值的详细信息，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须在 SQL Server 数据库启动过程的调用的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合使用生成的过程的请求架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 例如，要调用 GET_EMP_DETAILS_FOR XML 的请求消息是：  
  
```  
<GET_EMP_DETAILS_FOR_XML xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
  <emp_id>10765</emp_id>  
</GET_EMP_DETAILS_FOR_XML>  
```  
  
 请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)详细了解 SQL Server 中的过程调用的请求消息架构数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Root xmlns="http://ForXmlStoredProcs/namespace">  
  <Adapt_Doc.dbo.Employee Employee_ID="10765" Name="John" Designation="asdfaf" Salary="3434.00" Last_Modified="AAAAAAAANso=" Status="0" xmlns="" />  
</Root>  
```  
  
 请注意，通过执行存储的过程生成相同的架构中收到的响应。 此外请注意，根节点和命名空间是相同的值的形式指定**XmlStoredProcedureRootNodeName**并**XmlStoredProcedureRootNodeNamespace**分别绑定属性。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)