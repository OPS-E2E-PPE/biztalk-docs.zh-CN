---
title: "插入、 更新、 删除或选择 BizTalk Server 使用的 SQL 适配器的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d411b1a-a36d-4e3e-a56a-91804a5d69b9
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688c4a192a77dbc01de438c20be709dc4b3c378c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-the-sql-adapter"></a>插入、 更新、 删除或选择 BizTalk Server 使用的 SQL 适配器的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]呈现一组的 SQL Server 数据库表和视图上的标准操作。 这些行为称为数据操作语言 (DML) 操作。 通过使用 DML 操作，可以执行简单的 Insert、 Update、 选择和删除表和视图上的操作。 有关如何适配器支持这些操作的详细信息，请参阅[插入、 更新、 删除和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。 有关这些操作的 SOAP 消息结构的信息，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
> [!NOTE]
>  如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。  
  
## <a name="how-to-perform-basic-operations-on-a-sql-server-database"></a>如何对 SQL Server 数据库执行基本操作  
 通过使用执行 SQL Server 数据库上的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要在 SQL Server 中执行插入、 更新、 删除或 Select 操作对表和视图，这些任务包括：  
  
1.  创建 BizTalk 项目，并为你想要在 SQL Server 数据库表或视图上调用操作生成架构。  
  
2.  在发送和接收消息从 SQL Server 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程来调用 SQL Server 数据库表或视图上的操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SelectTable，基于本主题提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何通过从 SQL Server 数据库中的员工表中选择记录执行基本的 DML 操作。 运行这些示例以创建员工表提供的脚本。 有关这些示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 为了演示如何选择记录，将为员工表的选择操作生成架构。 您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
> [!IMPORTANT]
>  如果正在生成具有用户定义类型 (Udt) 的列的表上的操作的元数据，请确保提供与相同的位置中可以找到 Udt 的相应程序集[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件、 devenv.exe。 可执行文件位于通常`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`。 在此示例中，员工表中有 UDT （点） 列。 请确保将复制各自的程序集的位置相同[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件。  
>   
>  有关如何创建一个 UDT 的信息，请参阅[创建用户定义类型](https://msdn.microsoft.com/library/ms131106.aspx)。 有关如何在 SQL Server 中注册一个 UDT 的信息，请参阅[在 SQL Server 中的 Registering User-Defined 类型](https://msdn.microsoft.com/library/eybzcxe6(v=vs.85).aspx)。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在，你必须创建业务流程的消息，并将它们链接到你在上一步中生成的架构。  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectTable.TableOperation_dbo_Employee.Select*，其中 SelectTable 是 BizTalk 项目的名称。 TableOperation_dbo_Employee 是为员工表上的选择操作生成的架构。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectTable.TableOperation_dbo_Employee.SelectResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 SQL Server 上执行操作。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 你必须包括发送和接收形状将消息发送到 SQL Server，并接收响应，分别。 选择操作示例业务流程如下所示：  
  
 ![SQL Server 上的选择操作的业务流程](../../adapters-and-accelerators/adapter-sql/media/e74e342f-ba66-41fe-bd34-d45cd8767ef8.gif "e74e342f-ba66-41fe-bd34-d45cd8767ef8")  
  
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
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.Select.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.Select.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.Select.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.Select.Request*|  
  
 指定这些属性后，消息形状和端口将连接，并且您的业务流程已完成。  
  
 现在，你必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到的 SQL Server 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序以便从 SQL Server 数据库表中选择记录。 有关启动 BizTalk 应用程序的步骤，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   正在运行的 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。  
  
-   BizTalk 业务流程操作正在运行。  
  
> [!IMPORTANT]
>  如果您正在执行对表具有用户定义类型 (Udt) 的列的操作，请确保提供与相同的位置中可以找到 Udt 的相应程序集[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可执行文件、 btsntsvc.exe。 可执行文件位于通常`<installation drive>:\Program Files\Microsoft BizTalk Server <version>`。 在此示例中，员工表中有 UDT （点） 列。 请确保将复制各自的程序集的位置相同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可执行文件。  
>   
>  有关如何创建一个 UDT 的信息，请参阅[创建用户定义类型](https://msdn.microsoft.com/library/ms131106.aspx)。 有关如何在 SQL Server 中注册一个 UDT 的信息，请参阅[在 SQL Server 中的 Register User-Defined 类型](https://msdn.microsoft.com/library/ms131079.aspx)。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 选择你先前生成的操作的架构必须符合请求消息的架构。 例如，要从员工表中选择的所有记录的请求消息是：  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>*</Columns>  
  <Query>where Employee_ID=10001</Query>  
</Select>  
```  
  
 此请求消息将从员工表满足中指定的条件检索记录`<Query>`元素。 如果你想要从该表中检索特定列，则必须指定在 < 列\>与其在表定义中出现用逗号进行分隔，相同的序列中以分隔的元素。 如果您不想要指定一个条件，用于检索数据，保留`<Query>`元素为空。 请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)有关执行 SQL Server 上的基本 DML 操作的请求消息架构的详细信息数据库表和视图使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 业务流程使用该消息，并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置中。 例如，来自 SQL Server 数据库中的前面的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SelectResponse xmlns="mssql://Microsoft.LobServices.Sql/2008/01/TVOp/dbo/Employee">  
  <SelectResult>  
    <Employee xmlns="mssql://Microsoft.LobServices.Sql/2008/01/Types/Tables/dbo">  
      <Employee_ID>10001</Employee_ID>  
      <Name>John</Name>  
      <DOJ>1983-12-31T00:00:00Z</DOJ>  
      <Designation>Manager</Designation>  
      <Job_Description>Management</Job_Description>  
      <Photo>EjRVYzRFVQ==</Photo>  
      <Rating>1,2</Rating>  
      <Salary>100000.00</Salary>  
      <Last_Modified>AAAAAAAAD6I=</Last_Modified>  
    </Employee>  
  </SelectResult>  
</SelectResponse>  
```  
  
## <a name="best-practices"></a>最佳实践  
  
-   已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
-   如果你要插入的更新，或删除大量数据使确保您正确的超时值为 WCF 适配器和设置 MSDTC 事务。 有关详细信息，请参阅"适配器无法插入、 更新或删除单个操作使用 BizTalk Server 中的数据的大型卷"中的问题[解决与 SQL 适配器的操作问题](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)