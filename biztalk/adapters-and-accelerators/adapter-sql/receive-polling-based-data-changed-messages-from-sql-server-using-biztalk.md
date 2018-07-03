---
title: 从 SQL Server 使用 BizTalk Server 接收基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ecaf6f7-974b-4487-8c65-d1ab628cbfeb
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 168a7421aee7a33f1f400815153f5f217bb914b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972886"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>从 SQL Server 使用 BizTalk Server 接收基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收定期的数据更改消息的 SQL Server 表或视图。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。  

  
 适配器如何支持轮询的详细信息，请参阅[支持的轮询](https://msdn.microsoft.com/library/dd788416.aspx)。 轮询操作的 SOAP 消息结构的信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。  
  
> [!NOTE]
>  本主题演示如何使用**轮询**的入站操作使用轮询消息。 轮询操作的消息不是强类型化并与在运行时消息一起检索的轮询的对象的架构。 如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。 此外必须使用**TypedPolling**操作在一个 BizTalk 应用程序中有多个轮询操作。 有关如何执行的说明**TypedPolling**操作，请参阅[接收强类型基于轮询的数据更改消息从 SQL Server 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)。  
  
> [!IMPORTANT]
>  如果想要在单个 BizTalk 应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。 使用唯一连接 URI，可以创建多个接收端口的同一个数据库或甚至同一个表在数据库中的轮询一次。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收数据更改消息、 创建 BizTalk 项目和生成架构**轮询**操作。 如果你想要指定轮询相关属性绑定在设计时，指定**PolledDataAvailableStatement**作为：  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**必须返回的结果集包含正值的第一个单元格。 如果第一个单元格不包含正值，适配器将不会执行轮询语句。  
  
 轮询语句的一部分，请执行以下操作：  
  
- 从 Employee 表选择所有行。  
  
- 执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。  
  
- 执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。 此过程将雇员姓名、 designation 和薪金作为参数。  
  
  若要执行这些操作，必须指定以下**PollingStatement**绑定属性：  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 执行轮询语句后，会选择从 Employee 表的所有记录，并从 SQL Server 的消息放到接收位置。 一旦 MOVE_EMP_DATA 存储过程执行适配器，所有记录都移动到 EmployeeHistory 表。 然后，执行 ADD_EMP_DETAILS 存储过程以将新记录添加到 Employee 表。 下一次轮询执行将仅返回一条记录。 此循环将一直继续，直到你禁用接收轮询 SQL Server 的端口。  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>使用 SQL 适配器的绑定属性中配置轮询查询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  您可以选择生成的架构时指定这些绑定属性**轮询**操作，即使并不总是这样。 如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。 稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF SQL 属性已设置对绑定接收端口。 有关创建使用该绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
|         绑定属性         |                                                                                                                                                                                                                                         Description                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                             指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。 默认值是**轮询**。                                                                                                                                                                              |
| **PolledDataAvailableStatement** |                                                                                       指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 SQL 语句必须返回的结果集由行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。                                                                                       |
|   **PollingIntervalInSeconds**   |                         指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。                          |
|       **PollingStatement**       | 指定要轮询 SQL Server 数据库表的 SQL 语句。 您可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 null。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。 可以指定任意数量的以分号分隔的 SQL 语句。 |
|      **PollWhileDataFound**      |                            指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。                             |
  
 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读更多。  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a>如何从 SQL Server 数据库中接收数据更改消息  
 使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要配置要接收数据更改消息的适配器，这些任务包括：  
  
1. 创建 BizTalk 项目，然后生成的架构**轮询**操作。 或者，您可以指定的值**PolledDataAvailableStatement**并**PollingStatement**绑定属性。  
  
2. 在从 SQL Server 数据库接收消息的 BizTalk 项目中创建一条消息。  
  
3. 创建业务流程从 SQL Server 数据库接收消息并将它们保存到一个文件夹。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
   > [!IMPORTANT]
   >  对于入站的轮询方案始终必须配置一个单向 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不受支持。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**轮询**操作。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果不想指定绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**PolledDataAvailableStatement**并**PollingStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
     有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
2.  选择作为协定类型**服务 （入站操作）**。  
  
3.  生成架构**轮询**操作。  
  
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
    |Identifier|类型**接收**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*PollingQuery.Polling*，其中*PollingQuery*是 BizTalk 项目的名称。 *轮询*是为生成的架构**轮询**操作。|  
  
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
|ReceiveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*SQLReceivePort.Polling.Request*|  
|SaveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*SaveMessagePort.Polling.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。 
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应的 BizTalk 业务流程将消息从数据库中删除 SQL Server 的文件端口上定义的位置。 这些消息将以响应接收端口中指定的轮询语句。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 单向接收端口。 此端口将轮询指定的端口的轮询语句与 SQL Server 数据库。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果指定在设计时的绑定属性。 在这种情况下，您可以创建 WCF 自定义或 WCF SQL 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|请确保将其设置为**轮询**。|  
    |**PolledDataAvailableStatement**|请确保指定的 SQL 语句。 对于本主题中，指定：<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|请确保指定的轮询语句。 对于本主题中，指定：<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
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
  
- 适配器将执行**PolledDataAvailableStatement**对 Employee 上表，确定此表具有用于轮询的记录。  
  
- 适配器执行轮询语句。 轮询语句包含 SELECT 语句和存储的过程，因为该适配器将在它们执行所有语句一个。  
  
  - 适配器首先执行 SELECT 语句中的 Employee 表返回所有记录。  
  
  - 然后，适配器执行将所有数据从 Employee 表都移动到 EmployeeHistory 表 MOVE_EMP_DATA 存储过程。 此存储的过程不返回任何值。  
  
  - 然后，适配器执行将一条记录添加到 Employee 表的 ADD_EMP_DETAILS 存储过程。 此存储的过程返回插入的记录的员工 ID。  
  
    因此，从 SQL Server 收到的消息将包含多个结果集 （对于 SELECT 语句和 ADD_EMP_DETAILS 存储过程），并将如下所示：  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling/">  
    <PolledData>  
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
              <Employee_ID>10001</Employee_ID>   
              <Name>John</Name>   
              <Designation>Tester</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF34=</Last_Modified>   
            </NewTable>  
            ........  
            ........  
            <NewTable>  
              <Employee_ID>10005</Employee_ID>   
              <Name>Wilson</Name>   
              <Designation>Tester3</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF4E=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
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
              <Employee_ID>10006</Employee_ID>  
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </PolledData>  
  </Polling>  
  ```  
  
   上面的响应包含两个数据集。 第一个数据集包含 SELECT 语句的响应。 SELECT 语句中的 Employee 表选择所有记录。 第二个数据集是 ADD_EMP_DETAILS 存储过程。 此存储的过程将一条记录添加到 Employee 表，并返回新的记录的雇员 ID。  
  
  > [!NOTE]
  >  MOVE_EMP_DATA 存储过程不返回结果集。 因此，响应消息中是没有相应的数据集。  
  
- 当适配器执行**PollDataAvailableStatement**再次，找到一条记录所插入的 ADD_EMP_DETAILS 存储过程。 然后适配器将执行为指定的所有三个语句**PollingStatement**属性绑定。 这次，来自 SQL Server 的响应包含 SELECT 语句只是一条记录，并且一条记录 ADD_EMP_DETAILS 存储过程。 所有后续轮询将返回类似的响应。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
 [使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)