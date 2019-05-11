---
title: 运行 SQL Server 使用 BizTalk Server 上的复合操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a229918f677c3cd0949a961d3fc12c5ad92705e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367969"
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a>运行 SQL Server 使用 BizTalk Server 上的复合操作
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端能够执行复合操作上的 SQL Server 数据库。 复合操作可能包括：  
  
- 插入、 更新和删除操作。 选择操作不支持复合操作的一部分。  
  
- 作为操作执行的存储的过程。  
  
  单个复合操作可能具有任意数量的这些操作，按任何顺序。 例如，您可以跟一个删除操作，以及存储的过程执行最后两个插入操作。 此外，您可以以不同的数据库表或视图为目标的不同操作。 有关如何在适配器支持复合操作的详细信息，请参阅[在使用 SQL 适配器的 SQL Server 中运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)。 复合操作的 SOAP 消息结构的信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a>如何执行 SQL Server 上的复合操作  
 使用 SQL Server 上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要执行复合操作上的 SQL Server 数据库，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要调用的所有操作生成架构。  
  
2. 手动创建一个包含对你在上一步中生成的所有架构的引用的架构文件。  
  
3. 在发送和接收消息，从 SQL Server 数据库的 BizTalk 项目中创建的消息。 这些消息必须符合在上一步中创建的请求和响应架构。  
  
4. 创建一个业务流程调用上的 SQL Server 数据库的复合操作。  
  
5. 生成并部署 BizTalk 项目。  
  
6. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
7. 启动 BizTalk 应用程序。  
  
   本主题提供有关如何执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，CompositeOperations，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，若要演示如何执行复合操作，执行以下任务将指定的顺序：  
  
- EMPLOYEE 表中插入记录。  
  
- 通过调用 GET_LAST_EMP_DATA 存储过程检索最后一个插入记录的所有列。  
  
- 从 EMPLOYEE 表中删除的记录。  
  
  运行提供的示例创建员工表的脚本。 有关示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
  必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成这些操作的架构。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="creating-a-composite-schema-definition"></a>创建复合架构定义  
 现在必须创建一个复合架构引用为单个操作创建的架构。 执行以下步骤来创建复合架构定义。  
  
#### <a name="to-add-a-composite-schema-definition"></a>若要添加的复合架构定义  
  
1. 将架构文件添加到 BizTalk 项目。 右键单击项目名称，指向**外**，然后单击**新项**。 在中**添加新项**对话框中，从**类别**框中，单击**架构文件**。 从**模板**框中，单击**架构**。 指定的架构文件的名称，然后单击**确定**。  
  
    对于此示例中，指定的架构文件名称作为`CompositeSchema.xsd`。  
  
2. 添加对生成适用于你想要执行的不同操作的架构的引用。 在此示例中，为操作生成的不同架构是：  
  
   - TableOperation.dbo.Employee.xsd，对于 Insert 和 Delete 操作。  
  
   - 有关 GET_LAST_EMP_DATA Procedure.dbo.xsd，存储过程。  
  
     若要添加的引用：  
  
   1.  右键单击根**\<架构\>** 节点，CompositeSchema.xsd，然后单击**属性**。  
  
   2.  在中**属性**框中，单击省略号按钮 **（...）** 针对**导入**属性。  
  
        ![导入架构定义](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  
  
   3.  在中**导入**对话框中，从**作为导入新架构**列表中，选择**XSD 导入**，然后单击**添加**。  
  
   4.  在中**BizTalk 类型选取器**对话框框中，展开 BizTalk 项目名称节点，展开**架构**，然后选择你想要导入的架构。 对于此示例中，选择 < BizTalk_project_name >。TableOperation_dbo_Employee。 单击“确定” 。  
  
        重复此步骤以导入 < BizTalk_project_name >。Procedure_dbo 过。  
  
   5.  在中**导入**对话框中，单击**确定**。  
  
3. 将两个子节点添加到的根架构节点。 一个子节点对应于执行复合操作的请求架构。 另一个子节点对应的响应架构。 对应于请求架构的节点可以具有任何名称。 < Request_schema_node > 响应，必须调用到响应架构相对应的节点。 对于此示例中，我们将调用请求架构节点作为**请求**。 因此，响应架构节点称为**RequestResponse**。  
  
   > [!NOTE]
   >  默认情况下**根**节点也会添加到新的架构文件。 您可以重命名**根**节点到节点**请求**。 若要重命名节点，右键单击节点名称，然后单击**重命名**。  
  
    若要添加的节点下**\<架构\>** 节点：  
  
   1.  右键单击**\<架构\>** 节点，指向**插入 Schema 节点**，然后单击**子记录**。  
  
   2.  重命名的新节点**RequestResponse**。  
  
4. 添加下的子节点**请求**对应于将执行复合操作的一部分的每个操作的请求架构的节点。 对于此示例中，必须添加对应于以下的子节点：  
  
   -   插入和删除 EMPLOYEE 表上的操作。  
  
   -   GET_LAST_EMP_DATA 存储过程。  
  
   > [!IMPORTANT]
   >  必须在想要执行的操作的顺序来添加节点。 例如，如果你想要插入的记录，然后执行存储的过程，然后删除必须首先添加的节点插入操作的记录后, 接存储过程，一个节点，最后删除操作的节点。  
  
    若要添加到的子节点**请求**节点：  
  
   1.  右键单击**请求**节点，指向**插入 Schema 节点**，然后单击**子记录**。  
  
        ![插入架构的子节点](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  
  
   2.  重命名要与复合操作的一部分执行的操作请求架构相对应的记录。 例如，重命名为"Insert"节点。  
  
   3.  地图**插入**为 EMPLOYEE 表上的插入操作的请求架构的节点。 为此，请右键单击**插入**节点，然后单击**属性**。 在中**属性**框中，从**Data Structure Type**列表中，选择**插入 （参考）**。  
  
        ![将子节点映射到请求架构](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")  
  
   4.  重复这些步骤以添加 GET_LAST_EMP_DATA 存储过程和删除操作的请求架构的节点。 指定节点名称，并将它们映射到相应的架构，如下表中所述。  
  
       |节点名称|映射到架构|  
       |---------------|----------------------|  
       |GET_LAST_EMP_DATA|GET_LAST_EMP_DATA （参考）|  
       |DELETE|删除 （参考）|  
  
5. 添加下的子节点**RequestResponse**对应于将执行复合操作的一部分的每个操作的响应架构的节点。 对于此示例中，必须添加对应于以下的子节点：  
  
   -   插入和删除 EMPLOYEE 表上的操作。  
  
   -   GET_LAST_EMP_DATA 存储过程。  
  
   > [!IMPORTANT]
   >  必须添加子节点下的子节点的顺序相同**请求**节点。  
  
    若要添加到的子节点**RequestResponse**节点：  
  
   1.  右键单击**RequestResponse**节点，指向**插入 Schema 节点**，然后单击**子记录**。  
  
   2.  重命名要与复合操作的一部分执行的操作的响应架构相对应的记录。 例如，重命名为"InsertResponse"节点。  
  
   3.  地图**InsertResponse**为 EMPLOYEE 表上的插入操作的响应架构的节点。 为此，请右键单击**InsertResponse**节点，然后单击**属性**。 在中**属性**框中，从**Data Structure Type**列表中，选择**InsertResponse （参考）**。  
  
   4.  重复这些步骤以添加 GET_LAST_EMP_DATA 存储过程和删除操作的响应架构的节点。 指定节点名称，并将它们映射到相应的架构，如下表中所述。  
  
       |节点名称|映射到架构|  
       |---------------|----------------------|  
       |GET_LAST_EMP_DATAResponse|GET_LAST_EMP_DATAResponse （参考）|  
       |DeleteResponse|DeleteResponse （参考）|  
  
6. 保存**CompositeSchema.xsd**文件。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 在最后一步中创建复合架构描述了在业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到上一步中创建的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*CompositeOp.CompositeSchema.Request*，其中 CompositeOp 是 BizTalk 项目的名称。 CompositeSchema 是手动创建的复合操作的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*CompositeOp.CompositeSchema.RequestResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行 SQL Server 上的复合操作。 在将请求消息放在此业务流程，定义接收位置。 请求消息必须符合前面创建的复合架构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 必须包括发送和接收形状将消息发送到 SQL Server 和接收响应，分别。 用于执行复合操作的基本业务流程如下所示：  
  
 ![用于执行复合操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  
  
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
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.CompositeOp.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.CompositeOp.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.CompositeOp.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 因为操作是与复合操作的一部分执行在单个事务中，请确保**UseAmbientTransaction**绑定属性设置为**True**。  
  
     您必须在发送端口中指定的操作。 复合操作的操作是"**CompositeOperation**"。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 有关如何指定端口的操作的详细信息，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。 如果此绑定文件导入，WCF 自定义或 WCF-SQL 发送端口上的操作设置为涉及中选择的所有操作的动态操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构时。 对于复合操作，必须将为"CompositeOperation"包含的动态操作。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动执行复合操作的 SQL Server 数据库上的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合前面创建的复合操作的架构。 例如，员工表中插入一条记录，调用 GET_LAST_EMP_DATA 存储过程，并从 EMPLOYEE 表中删除记录的请求消息是：  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)详细了解请求消息架构执行复合操作的 SQL Server 上的数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      <xs:element minOccurs="0" name="Name" type="xs:string" />   
                      <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="">  
            <NewTable>  
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 上面的响应包含多个对应复合操作的一部分执行的不同操作的结果集。 例如，`InsertResult`元素包含 10080，这是新添加的记录的唯一标识符。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)