---
title: 使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息 |Microsoft 文档
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
ms.openlocfilehash: 2251ec6f5019fab4eecff36ac35314183f9a7d61
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967869"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来接收 SQL Server 表或视图的定期的数据更改消息。 你可以指定适配器执行轮询数据库轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回的结果集。  

  
 有关如何的适配器支持轮询的详细信息，请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。 有关轮询操作的 SOAP 消息结构的信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。  
  
> [!NOTE]
>  本主题演示如何使用**轮询**入站操作人员使用轮询消息。 轮询操作的消息不是强类型，以及在运行时消息检索轮询的对象的架构。 如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。 你还必须使用**TypedPolling**操作以单个的 BizTalk 应用程序中有多个轮询操作。 有关说明如何执行**TypedPolling**操作，请参阅[接收强类型轮询基于的数据更改消息从 SQL Server 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)。  
  
> [!IMPORTANT]
>  如果你想要单个的 BizTalk 应用程序中有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。 使用唯一连接 URI，你可以创建多个接收轮询同一数据库中或甚至同一个表在数据库中的端口。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收数据的支持更改消息、 创建 BizTalk 项目和生成架构**轮询**操作。 如果你想要指定轮询相关在设计时绑定属性，指定**PolledDataAvailableStatement**作为：  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**必须返回具有包含正值的第一个单元格的结果集。 如果第一个单元格不包含是正数值，该适配器将不会执行轮询语句。  
  
 作为轮询语句的一部分，请执行以下操作：  
  
-   从员工表中选择所有行。  
  
-   执行存储的过程 (MOVE_EMP_DATA) 将从员工表到 EmployeeHistory 表的所有记录。  
  
-   执行存储的过程 (ADD_EMP_DETAILS) 将一条新记录添加到员工表。 此过程使用雇员姓名、 名称以及薪金作为参数。  
  
 若要执行这些操作，必须指定以下项作为**PollingStatement**绑定属性：  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 执行轮询语句后，选择从 Employee 表的所有记录，并从 SQL Server 消息拖放到接收位置。 一旦 MOVE_EMP_DATA 存储过程执行适配器，所有记录都移动到 EmployeeHistory 表。 然后，执行 ADD_EMP_DETAILS 存储过程将一条新记录添加到员工表。 下一次轮询执行将只返回单个记录。 此循环将持续，直到您禁用接收轮询 SQL Server 的端口。  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>配置与 SQL 适配器绑定属性的轮询查询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  你可以选择在生成的架构时指定这些绑定属性**轮询**操作，即使它不是强制性。 如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。 你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF SQL 接收属性已设置对绑定的端口。 有关创建使用绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
|绑定属性|Description|  
|---|---|  
|**InboundOperationType**|指定是否想要执行**轮询**， **TypedPolling**，或**通知**入站操作。 默认值是**轮询**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 SQL 语句必须返回的结果集行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行绑定属性。|  
|**PollingIntervalInSeconds**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器将等待的间隔中的剩余时间。|  
|**PollingStatement**|指定要轮询的 SQL Server 数据库表的 SQL 语句。 你可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 null。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。 你可以指定任意数量的以分号分隔的 SQL 语句。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，进一步阅读。  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a>如何从 SQL Server 数据库中接收数据更改消息  
 使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要配置接收数据更改消息的适配器，这些任务包括：  
  
1.  创建 BizTalk 项目，然后生成架构**轮询**操作。 （可选） 你可以为指定值**PolledDataAvailableStatement**和**PollingStatement**绑定属性。  
  
2.  在从 SQL Server 数据库中接收消息的 BizTalk 项目中创建一条消息。  
  
3.  创建业务流程的 SQL Server 数据库从接收消息，并将它们保存到一个文件夹。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
    > [!IMPORTANT]
    >  对于入站的轮询方案，你始终必须配置单向的 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不支持。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**轮询**操作。 请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果你不想要指定的绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**PolledDataAvailableStatement**和**PollingStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
     有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
2.  选择与具有协定类型**服务 （入站操作）**。  
  
3.  生成架构**轮询**操作。  
  
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
    |Identifier|类型**接收**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*PollingQuery.Polling*，其中*PollingQuery*是 BizTalk 项目的名称。 *轮询*是为生成的架构**轮询**操作。|  
  
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
|ReceiveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*SQLReceivePort.Polling.Request*|  
|SaveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*SaveMessagePort.Polling.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。 
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和其中 BizTalk 业务流程将消息从数据库中删除 SQL Server 的相应文件端口上定义的位置。 这些消息将以响应接收端口指定轮询语句。  
  
    -   定义一个物理 WCF 自定义或 WCF SQL 单向接收端口。 此端口轮询作为端口号指定的轮询语句的 SQL Server 数据库。 有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
        > [!IMPORTANT]
        >  不需要执行此步骤中，如果指定在设计时绑定属性。 在这种情况下，你可以创建 WCF 自定义或 WCF SQL 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
        |绑定属性|值|  
        |----------------------|-----------|  
        |**InboundOperationType**|请确保将此设置为**轮询**。|  
        |**PolledDataAvailableStatement**|请确保指定的 SQL 语句。 对于本主题中，指定：<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|请确保指定轮询语句。 对于本主题中，指定：<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
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
  
-   适配器执行轮询语句。 轮询语句包含 SELECT 语句和存储的过程，因为该适配器后将不执行所有语句一个其他。  
  
    -   适配器首先执行 SELECT 语句返回员工表中的所有记录。  
  
    -   然后，适配器执行将从员工表的所有数据都移动到 EmployeeHistory 表 MOVE_EMP_DATA 存储过程。 此存储的过程不返回任何值。  
  
    -   适配器然后执行 ADD_EMP_DETAILS 存储过程，将一条记录添加到员工表。 此存储的过程返回插入的记录的员工 ID。  
  
     因此，从 SQL Server 接收的消息将包含多个结果集 （SELECT 语句和 ADD_EMP_DETAILS 存储过程），并将如下所示：  
  
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
  
     前面的响应包含两个数据集。 第一个数据集包含 SELECT 语句的响应。 SELECT 语句员工表中选择的所有记录。 第二个数据集是 ADD_EMP_DETAILS 存储过程。 此存储的过程将记录添加到员工表，并返回新的记录的员工 ID。  
  
    > [!NOTE]
    >  MOVE_EMP_DATA 存储过程不返回结果集。 因此，在响应消息中，如果没有相应的数据集。  
  
-   当适配器执行**PollDataAvailableStatement**再次，它找到一个记录所插入的 ADD_EMP_DETAILS 存储过程。 适配器然后执行为指定的所有三个语句**PollingStatement**绑定属性。 此时，来自 SQL Server 的响应包含 SELECT 语句只是一条记录，并且一条记录 ADD_EMP_DETAILS 存储过程。 所有后续轮询将返回类似的响应。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询除非你显式禁用接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
 [与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)