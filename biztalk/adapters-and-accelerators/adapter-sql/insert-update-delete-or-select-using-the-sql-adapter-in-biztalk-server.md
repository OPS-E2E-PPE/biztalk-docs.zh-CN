---
title: 插入、 更新、 删除或选择将 BizTalk Server 与 SQL 适配器的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d411b1a-a36d-4e3e-a56a-91804a5d69b9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e81cf843473a544b915d185e4609d0748fc2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982022"
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-the-sql-adapter"></a>插入、 更新、 删除或选择将 BizTalk Server 与 SQL 适配器的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]显示一组的 SQL Server 数据库表和视图上的标准操作。 这些称为数据操作语言 (DML) 操作。 通过使用 DML 操作，可以执行简单的 Insert、 Update、 Select 和删除表和视图上的操作。 有关适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。 有关这些操作的 SOAP 消息结构的信息，请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="how-to-perform-basic-operations-on-a-sql-server-database"></a>如何对 SQL Server 数据库执行基本操作  
 使用执行 SQL Server 数据库上的操作的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要在 SQL Server 中执行插入、 更新、 删除或选择表和视图操作，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要在 SQL Server 数据库表或视图上调用该操作生成架构。  
  
2. 在发送和接收消息，从 SQL Server 数据库的 BizTalk 项目中创建的消息。  
  
3. 创建一个业务流程调用上的 SQL Server 数据库表或视图的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，SelectTable，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何通过从 SQL Server 数据库中的 EMPLOYEE 表中选择记录执行基本的 DML 操作。 运行提供的示例创建员工表的脚本。 有关示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 若要演示如何选择记录，用于为 EMPLOYEE 表选择操作生成架构。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
> [!IMPORTANT]
>  如果生成具有用户定义类型 (Udt) 的列的表操作的元数据，请确保提供与相同的位置中可以找到相应的程序集的 Udt[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件，devenv.exe。 可执行文件是通常位于`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`。 在此示例中，EMPLOYEE 表有一个 UDT （点） 列。 请确保将复制各自的程序集与在同一位置[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件。  
> 
>  有关如何创建 UDT 的信息，请参阅[创建用户定义类型](https://msdn.microsoft.com/library/ms131106.aspx)。 有关如何在 SQL Server 中注册 UDT 的信息，请参阅[SQL Server 中的 Registering User-Defined 类型](https://msdn.microsoft.com/library/eybzcxe6(v=vs.85).aspx)。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在必须为该业务流程创建消息并将其链接到上一步中生成的架构。  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectTable.TableOperation_dbo_Employee.Select*，其中 SelectTable 是 BizTalk 项目的名称。 TableOperation_dbo_Employee 是为 EMPLOYEE 表上的选择操作生成的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectTable.TableOperation_dbo_Employee.SelectResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 SQL Server 上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 您必须包括发送和接收形状将消息发送到 SQL Server 并将它们分别收到答复。 选择操作的示例业务流程如下所示：  
  
 ![用于 SQL Server 上的选择操作的业务流程](../../adapters-and-accelerators/adapter-sql/media/e74e342f-ba66-41fe-bd34-d45cd8767ef8.gif "e74e342f-ba66-41fe-bd34-d45cd8767ef8")  
  
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
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.Select.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.Select.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.Select.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.Select.Request*|  
  
 指定这些属性后，连接的消息形状和端口，并在业务流程已完成。  
  
 现在，必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 SQL Server 数据库表中选择记录的 BizTalk 应用程序。 启动 BizTalk 应用程序的步骤，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
> [!IMPORTANT]
>  如果您正在执行对表具有用户定义类型 (Udt) 的列的操作，请确保提供与相同的位置中可以找到相应的程序集的 Udt[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可执行文件，btsntsvc.exe。 可执行文件是通常位于`<installation drive>:\Program Files\Microsoft BizTalk Server <version>`。 在此示例中，EMPLOYEE 表有一个 UDT （点） 列。 请确保将复制各自的程序集与在同一位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可执行文件。  
> 
>  有关如何创建 UDT 的信息，请参阅[创建用户定义类型](https://msdn.microsoft.com/library/ms131106.aspx)。 有关如何在 SQL Server 中注册 UDT 的信息，请参阅[SQL Server 中的 Register User-Defined 类型](https://msdn.microsoft.com/library/ms131079.aspx)。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 选择先前生成的操作的架构必须符合请求消息的架构。 例如，要从 EMPLOYEE 表中选择的所有记录的请求消息是：  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>*</Columns>  
  <Query>where Employee_ID=10001</Query>  
</Select>  
```  
  
 此请求消息将从满足中指定的条件的员工表中检索记录`<Query>`元素。 如果你想要从表中检索特定列，则必须指定在 < 列\>元素，用逗号分隔的相同顺序出现在表定义。 如果您不想要指定一个条件，用于检索数据，请将保留`<Query>`元素为空。 请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)有关执行 SQL Server 上的基本 DML 操作的请求消息架构的详细信息的数据库表和视图使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
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
  
-   部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
-   如果插入、 更新或删除大量数据进行确保您正确超时值为 WCF 适配器和设置 MSDTC 事务。 有关详细信息，请参阅"适配器无法插入、 更新或删除在单个操作中使用 BizTalk Server 的数据量很大"中的问题[与 SQL 适配器进行故障排除操作问题](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)