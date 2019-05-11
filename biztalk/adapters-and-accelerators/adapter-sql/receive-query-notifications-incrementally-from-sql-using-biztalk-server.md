---
title: 从使用 BizTalk Server 的 SQL 查询通知以增量方式接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43616dd0cb8b70d8363c39e897f81e59832ccf8e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368308"
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a>从使用 BizTalk Server 的 SQL 查询通知以增量方式接收
> [!IMPORTANT]
>  为了简洁起见，本主题仅介绍如何以增量方式接收通知。 在业务方案中，业务流程在理想情况下必须包括用于提取收到通知消息的类型，然后执行任何后续操作的逻辑。 换而言之，本主题中所述的业务流程必须基于业务流程中所述[处理通知消息，以完成特定任务中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。  
  
 本主题演示如何配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以从 SQL Server 数据库中接收增量查询通知消息。 若要演示增量通知，请考虑表中的，员工，"状态"列。 一条新记录插入到此表时，状态列的值设置为 0。 可以配置适配器后，通过执行以下接收增量通知：  
  
- 注册通知使用 SQL 语句检索所有记录为 0 的状态列。 您可以通过指定的 SQL 语句来实现**NotificationStatement**属性绑定。  
  
- 对于已接收的通知消息的行，更新为 1 的状态列。  
  
  本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>使用 SQL 适配器的绑定属性中配置通知  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置 SQL Server 从接收通知的属性。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  您可以选择生成的架构时指定这些绑定属性**通知**操作，即使并不总是这样。 如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。 稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF SQL 属性已设置对绑定接收端口。 有关创建使用该绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationStatement**|指定的 SQL 语句 (SELECT 或 EXEC\<存储过程\>) 用于对查询通知注册。 仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取通知消息。|  
|**NotifyOnListenerStart**|指定适配器是否启动侦听器时在向适配器客户端发送了通知。|  
  
 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要从 SQL Server 中接收通知，请阅读更多。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>如何本主题演示如何接收通知消息  
 若要演示如何将[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持从 SQL Server 中接收通知消息，本主题将演示如何将适配器配置为接收到的雇员表更改通知。 假设 Employee 表包含列 Employee_ID、 名称和状态。 每当添加新员工时，状态列的值设置为 0。  
  
 为了演示通知的接收，执行以下操作：  
  
-   生成架构**通知**（入站操作），并**选择**（出站操作） 上的 Employee 表。  
  
-   创建具有以下业务流程：  
  
    -   接收位置接收通知消息。 可以通过指定 SELECT 语句作为通知进行配置：  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  具体而言，必须指定在此所示的语句中的列名称的 SELECT 语句。 此外，您必须始终指定表名称以及架构名称。 例如，`dbo.Employee`。  
  
    -   要更新的行已为其发送通知的发送端口。 通过将值设置为 1 的状态列中执行此操作。 您可以为此选择操作的一部分，将显示以下消息发送到适配器。  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         在此消息中，作为的一部分`<Query>`元素中，指定要更新状态列的 UPDATE 语句。 请注意接收通知消息，以便将更新已处理的行后，必须执行此操作。 若要使用正在等待获取通知响应，然后手动将请求消息，若要更新的行的开销即可执行操作，将生成为更新的行在业务流程本身内的请求消息。 可以通过使用执行操作**构造消息**形状在业务流程中的。  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>如何从 SQL Server 数据库中接收通知消息  
 使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要配置要接收通知消息的适配器，这些任务包括：  
  
1. 创建 BizTalk 项目，然后生成的架构**通知**（入站操作） 和**选择**（出站操作） 上的 Employee 表。 或者，您可以指定的值**InboundOperationType**并**NotificationStatement**绑定属性。  
  
2. 用于从 SQL Server 数据库中接收通知的 BizTalk 项目中创建一条消息。  
  
3. 在 SQL Server 数据库上执行的选择信息并接收响应消息的 BizTalk 项目中创建消息。  
  
4. 创建业务流程中执行以下任务：  
  
   -   从 SQL Server 中接收通知消息。  
  
   -   创建消息，以选择和更新为其接收通知的行。  
  
   -   将此消息发送到 SQL Server 以更新这些行，并接收响应。  
  
5. 生成并部署 BizTalk 项目。  
  
6. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
   > [!NOTE]
   >  对于入站操作，如接收通知消息，你必须仅配置一个单向 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不受支持。  
  
7. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，IncrementalNotification，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**通知**操作并**选择**Employee 表上的操作。 请参阅[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果您不想要在设计时指定的绑定属性，跳过的第一步。  
  
1.  为指定值**InboundOperationType**并**NotificationStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
2.  选择作为协定类型**服务 （入站操作）**。  
  
3.  生成架构**通知**操作。  
  
4.  选择作为协定类型**客户端 （出站操作）**。  
  
5.  生成架构**选择**上的操作**员工**表。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，您必须创建三个消息 — 一个用于从 SQL Server 数据库，另一个执行选择操作，以接收选择操作的响应中接收通知。  
  
 执行以下步骤创建消息并将其链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|键入 `NotifyReceive`。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SQLNotify.Notification*，其中*SQLNotify*是 BizTalk 项目的名称。 *通知*是为生成的架构**通知**操作。|  
  
6.  重复步骤 3 以创建两条新消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |选择|*SQLNotify.TableOperation_dbo_Employee.Select*，其中*TableOperation_dbo_Employee*是为生成的架构**选择**操作|  
    |SelectResponse|*SQLNotify.TableOperation_dbo_Employee.SelectResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 SQL Server 数据库中接收通知消息，然后更新的行已收到通知。 在此业务流程，适配器将接收通知消息根据 SELECT 语句为指定**NotificationStatement**属性绑定。 在文件位置接收通知消息。 一旦收到响应，该业务流程将构造一条消息，将用于更新为其接收通知的行。 在相同的文件位置还收到此消息的响应。  
  
 因此，您的业务流程必须包含以下信息：  
  
- 一个单向接收端口以接收通知消息。  
  
- 一个双向发送端口以发送要更新的行和对同一接收响应消息。  
  
- 一个**构造消息**形状以构造消息，以执行更新操作，在业务流程内的。  
  
- FILE 发送端口以保存更新操作的响应。  
  
- 接收和发送形状。  
  
  示例业务流程如下所示。  
  
  ![用于接收 SQL Server 通知的业务流程](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-设置**名称**到*ReceiveNotification*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveNotification|Send|-设置**名称**到*SaveNotification*|  
|SendSelectMessage|Send|-设置**名称**到*SendSelectMessage*|  
|ReceiveSelectResponse|Receive|-设置**名称**到*ReceiveSelectResponse*|  
|SaveSelectResponse|Send|-设置**名称**到*SaveSelectResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 可以使用**构造消息**形状中，以生成操作中的请求消息执行选择操作。 若要执行此操作，必须添加**构造消息**形状，并在其中**消息赋值**向业务流程的形状。 对于本例，请**消息赋值**形状调用生成一条消息，发送到 SQL Server 执行选择操作的代码。 **消息赋值**形状也设置为要发送到 SQL Server 的消息的操作。  
  
 对于构造消息形状，请设置**构造的消息**属性设置为**选择**。  
  
 若要生成响应的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 用于生成响应消息的示例代码如下所示。  
  
```  
namespace SampleMessageCreator  
{  
    public class SampleMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\CreateMessage";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 对于上述摘录的代码可以生成请求消息，您必须具有 XML 请求消息 （适用于员工表上的选择操作），为指定的位置中`XmlFileLocation`变量。  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 SampleMessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。 此外，必须将 SampleMessageCreator.dll 添加为 BizTalk 项目中的引用。  
  
 添加以下表达式来调用此代码从**消息赋值**形状，以及设置用于消息的操作。 若要添加一个表达式，请双击**消息赋值**形状以打开表达式编辑器。  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|SQLNotifyPort|-设置**标识符**到*SQLNotifyPort*<br /><br /> -设置**类型**到*SQLNotifyPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|SaveMessagePort|-设置**标识符**到*SaveMessagePort*<br /><br /> -设置**类型**到*SaveMessagePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*<br /><br /> -创建一个操作*通知*。 此操作用于通知消息。<br /><br /> -创建一个操作*选择*。 此操作用于选择响应消息。|  
|SQLOutboundPort|-设置**标识符**到*SQLOutboundPort*<br /><br /> -设置**类型**到*SQLOutboundPortType*<br /><br /> -设置**通信模式**到*请求-响应*<br /><br /> -设置**通信方向**到*发送接收*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*SQLNotifyPort.Notify.Request*|  
|SaveNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*SaveMessagePort.Notify.Request*|  
|SendSelectMessage|-设置**消息**到*选择*<br /><br /> -设置**操作**到*SQLOutboundPort.Select.Request*|  
|ReceiveSelectResponse|-设置**消息**到*SelectResponse*<br /><br /> -设置**操作**到*SQLOutboundPort.Select.Response*|  
|SaveSelectResponse|-设置**消息**到*SelectResponse*<br /><br /> -设置**操作**到*SaveMessagePort.Select.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 单向接收端口。 此端口侦听来自 SQL Server 数据库的通知。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果在设计时指定的绑定属性。 在这种情况下，您可以创建 WCF 自定义或 WCF SQL 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|将此设置为**通知**。|  
    |**NotificationStatement**|将此设置为：<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注意：** 具体而言，必须指定在此所示的语句中的列名称的 SELECT 语句。 此外，您必须始终指定表名称以及架构名称。 例如，`dbo.Employee`。|  
    |**NotifyOnListenerStart**|将此设置为 **，则返回 True**。|  
  
     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以执行以便通过将服务添加行为时配置 WCF 自定义或 WCF SQL 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和使用 SQL 事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。  
  
  - 硬盘和相应的 BizTalk 业务流程将消息从数据库中删除 SQL Server 的文件端口上定义的位置。 这些将是从 SQL Server 收到的通知消息和消息进行，请选择和更新操作执行通过 WCF 自定义或 WCF-SQL 发送端口。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序从 SQL Server 数据库中接收通知消息并执行后续的 Select 和 Update 操作。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF-SQL 单向接收端口，从 SQL Server 数据库运行时接收通知消息。  
  
-   要执行的 WCF 自定义或 WCF-SQL 发送端口选择并运行 Employee 表更新操作。  
  
-   FILE 发送端口，从 SQL Server 接收消息，正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 若要执行此操作，必须将一条记录插入到 Employee 表中。 让我们假设插入具有以下详细信息的记录：  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 此外，请确保要执行的 XML 消息选择和更新操作，请参阅 C:\TestLocation\MessageIn。 XML 文件应如下所示：  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 后插入记录时，以下组操作需要置于相同的序列：  
  
-   适配器接收一条通知消息，如下所示：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     此消息会通知员工表中已插入一条记录。 请注意，对于值`<Info>`元素为"Insert"。  
  
-   适配器将执行选择操作。 因为选择操作 XML 还包括了 Update 语句，也会执行更新语句。 SQL Server 的下一步响应是 Select 语句。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult>  
        <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10006</Employee_ID>   
          <Name>John</Name>   
          <Status>0</Status>  
        </Employee>  
      </SelectResult>  
    </SelectResponse>  
    ```  
  
     此响应将显示一条记录插入到 Employee 表，并且该记录的状态为 0。  
  
-   作为 Select 语句的一部分，也会执行更新语句和新的记录的状态列更改为 1。 这会再次触发从 SQL Server 的另一条通知和适配器接收相应的通知消息，类似于下面：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     此消息会通知员工表中已更新记录。 请注意，对于值`<Info>`元素是"更新"。  
  
-   第二个通知之后, 适配器执行 Select 语句。 但是，因为没有记录现在的有状态为 0，适配器将获取类似于以下的响应为空。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
 [接收使用 BizTalk Server 的 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)