---
title: 使用 SELECT 语句轮询 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling-based notifications, receiving from Oracle
- polling query, configuring a
ms.assetid: d2689eb9-6f17-498f-8a32-07f43a368833
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5d4a540f5a7e3b6cf589bfe247720aef829cc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376257"
---
# <a name="poll-oracle-database-using-the-select-statement"></a>使用 SELECT 语句轮询 Oracle 数据库
你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过使用 SELECT 语句，若要连续轮询的表和视图中 Oracle 的 Oracle 数据库接收定期的数据更改消息。 您可以指定为适配器执行定期轮询 Oracle 数据库的轮询语句的 SELECT 语句。 （可选） 还可以指定如果数据中的更改，则执行适配器后轮询 PL/SQL 代码块。 若要更新目标中的查询记录的字段或将查询的记录移到另一个表或视图，通常使用此块。  

 若要启用此功能，必须指定特定绑定的属性上[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你还可以通过设置修改 POLLINGSTMT 操作的目标命名空间**PollingId**连接 URI 中的属性。 有关详细信息，请参阅[对基于接收轮询的 Oracle 数据库中的数据更改消息的支持](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)并[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。 轮询操作的 SOAP 消息结构的信息，请参阅[轮询 Operations2 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。  

## <a name="configuring-a-polling-operation-with-oracle-database-adapter-binding-properties"></a>使用 Oracle 数据库适配器的绑定属性中配置轮询操作  
 下表总结了[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，用于将适配器配置为接收数据更改消息。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  


|         绑定属性         |                                                                                                                                                                                                                      Description                                                                                                                                                                                                                      |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                       指定是否想要执行轮询或入站操作的通知。 默认值是**轮询**。                                                                                                                                                                        |
| **PolledDataAvailableStatement** |                        指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 仅当一条记录不可用，SELECT 语句指定的**PollingStatement**将执行属性绑定。 默认值是`SELECT 1 FROM DUAL`，这意味着与否，适配器必须继续轮询而不考虑轮询表是否包含数据。                        |
|       **PollingInterval**        | 指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 500 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将休眠的剩余时间间隔中。 |
|       **PollingStatement**       |                 指定的轮询语句。 若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。 默认值为 NULL。<br /><br /> 必须指定的值**PollingStatement**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。                 |
|        **PollingAction**         |                                                                                              指定轮询操作的操作。 您可以确定操作使用生成的元数据中的特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。                                                                                              |
|      **PostPollStatement**       |                                                                                                                                                         指定在指定的语句之后执行的语句块**PollingStatement**执行绑定属性。                                                                                                                                                          |
|      **PollWhileDataFound**      |                                     指定是否[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]忽略的轮询间隔，连续执行轮询语句中，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。                                     |

 有关这些属性的更完整说明，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要轮询 Oracle 数据库，请阅读更多。  

## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收数据的支持更改使用 SELECT 语句的消息、 创建 BizTalk 项目和生成架构**POLLINGSTMT**通过设置操作**PollingStatement**属性绑定到以下：  

```  
SELECT * FROM ACCOUNTACTIVITY FOR UPDATE  
```  

 运行示例，在数据库中创建这些对象提供的 SQL 脚本时创建 ACCOUNTACTIVITY 表。  

> [!NOTE]
>  此主题轮询 ACCOUNTACTIVITY 表，其中基本的数据库表创建示例运行提供的脚本中的业务流程。 本主题来轮询任何其他表中所述，必须执行类似的过程。  

 为了演示轮询操作，我们执行以下操作：  

-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性，以确定其中表正在轮询一次 (ACCOUNTACTIVITY) 有任何数据。 在此示例中，可以设置为此绑定属性：  

    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  

     这可确保只有 ACCOUNTACTIVITY 表有某些记录时，适配器都将执行轮询语句。  

-   指定 SELECT 语句，如前文所述针对**PollingStatement**属性绑定。 此语句检索 ACCOUNTACTIVITY 表中的所有行。  

-   作为的一部分执行一个 PL/SQL 块**PostPollStatement**属性绑定。 此语句将所有数据从 ACCOUNTACTIVITY 表到另一个数据库表中。 一旦发生这种情况下, 一次为指定的语句**PollingStatement**将执行，它将不提取任何数据。  

-   之前更多的数据添加到 ACCOUNTACTIVITY 表，您将无法获得任何轮询消息。 因此，您必须重新填充的新记录所在 ACCOUNTACTIVITY 的表。 可以通过运行这些示例提供的 more_activity_data.sql 脚本执行操作。 在运行此脚本后下, 一个轮询操作将提取新记录插入到表。  

## <a name="how-to-receive-data-change-messages-from-oracle"></a>如何从 Oracle 接收数据更改消息  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及以下过程任务中所述[构建基块来开发 BizTalk 应用程序与 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要配置的适配器轮询 Oracle 数据库使用的 SELECT 语句，这些任务包括：  

1. 创建 BizTalk 项目，并生成的架构**POLLINGSTMT**你想要轮询的表的操作。  

2. 用于从 Oracle 数据库接收消息的 BizTalk 项目中创建一条消息。  

3. 创建业务流程从 Oracle 接收消息并将其保存到的文件夹。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

   > [!IMPORTANT]
   >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="generating-schema"></a>生成架构  
 必须生成的架构**POLLINGSTMT**操作。 执行以下任务，同时生成架构使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

- 为指定值**PollingStatement**属性绑定在生成架构时。 有关此绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 例如，指定以下内容作为轮询语句：  

  ```  
  SELECT * FROM ACCOUNTACTIVITY FOR UPDATE  
  ```  

- 选择作为协定类型**服务 （入站操作）**。  

- 生成架构**POLLINGSTMT**操作。  

  有关如何生成架构的详细信息，请参阅[浏览、 搜索和获取元数据的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  

 对于本主题中，必须创建一条消息用于从 Oracle 接收消息。  

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
    |消息类型|从下拉列表中，展开**架构**，然后选择*TablePolling.OracleDBBinding*，其中*TablePolling*是 BizTalk 项目的名称。 *OracleDBBindingSchema*是为生成的响应架构**POLLINGSTMT** ACCOUNTACTIVITY 表上的操作。<br /><br /> **重要**由于轮询是一种方法的操作，适配器生成的架构不包含响应节点中，因此，没有只有一个根节点在架构中。 如果消息类型使用此类架构，则必须通过生成的架构的文件名标识架构。<br /><br /> 例如，如果创建双向操作的架构，架构中的节点文件的名称`OracleDBBindingSchema`可能看起来像"请求"和"响应"。 如果你想要在业务流程映射到请求架构中创建一条消息，可以通过查找来确定在列表中的架构`OracleDBBindingSchema.Request`。 但是，在执行轮询操作时，唯一的节点是"POLLINGSTMT"，因为它并不容易标识你想要映射到，因为单个节点包含以下架构： 不会作为列出的架构\<schemafilename\>。\<rootnodename\>。 相反，仅文件名，列出了此类架构。 在这种情况下，标识架构的唯一方法是按架构文件名，例如，OracleDBBindingSchema。|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]以便从 Oracle 接收基于轮询的数据更改消息。 在此业务流程，该适配器接收的响应通过执行 SELECT 语句为指定**PollingStatement**属性绑定。 SELECT 语句的响应消息将保存到文件位置。 用于轮询 Oracle 数据库的典型业务流程将包含：  

- 接收和发送形状从 Oracle 接收消息并将发送给 FILE 端口，分别。  

- 一个单向接收端口从 Oracle 数据库接收消息。  

  > [!IMPORTANT]
  >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  

- 用于从 Oracle 数据库发送轮询响应的单向发送端口。  

  示例业务流程如下所示。  

  ![用于 Oracle 轮询查询的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3.gif "6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3")  

### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveMessage|Send|-设置**名称**到*SaveMessage*|  

### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  

|Port|属性|  
|----------|----------------|  
|OracleReceivePort|-设置**标识符**到*OracleReceivePort*<br /><br /> -设置**类型**到*OracleReceivePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|SaveMessagePort|-设置**标识符**到*SaveMessagePort*<br /><br /> -设置**类型**到*SaveMessagePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  

|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*OracleReceivePort.Polling.Request*|  
|SaveMessage|-设置**消息**到*接收*<br /><br /> -设置**操作**到*SaveMessagePort.Polling.Request*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  

  - 硬盘和相应的 BizTalk 业务流程将放置的位置将消息从 Oracle FILE 端口上定义的位置。 这些消息将以响应接收端口中指定的轮询语句。  

  - 定义一个物理 WCF 自定义或 Wcf-oracledb 单向接收端口。 此端口将轮询 Oracle 数据库。 有关如何创建接收端口，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 请确保指定的接收端口的以下绑定属性。  

    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|将此设置为**轮询**。|  
    |**PolledDataAvailableStatement**|对于此示例中，此绑定属性设置为：<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> 这可确保只有 ACCOUNTACTIVITY 表有某些记录时，适配器都将执行轮询语句。|  
    |**PollingStatement**|对于此绑定属性，指定一个 SELECT 语句来从 ACCOUNTACTIVITY 表中检索所有记录。 对于此示例中，此绑定属性设置为：<br /><br /> `SELECT * FROM ACCOUNTACTIVITY FOR UPDATE`|  
    |**PostPollStatement**|指定要将所有数据从 ACCOUNTACTIVITY 表都移到另一个表的轮询后语句。 对于此示例中，此绑定属性设置为：<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`|  

     有关不同的绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  

    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 可以配置接收端口时添加的服务行为来完成此操作。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动轮询 Oracle 数据库的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   WCF 自定义或 Wcf-oracledb 单向接收端口，轮询使用 SELECT 语句为指定的 Oracle **PollingStatement**绑定属性，正在运行。  

-   FILE 发送端口，从 Oracle 数据库接收消息，正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，以下组操作需要置于相同的序列：  

-   适配器将执行**PolledDataAvailableStatement**这会返回正值，指示要执行的语句为指定的适配器**PollingStatement**属性绑定。  

-   适配器执行的 SELECT 语句**PollingStatement** ACCOUNTACTIVITY 表中的绑定属性，并返回所有行。 从 Oracle 数据库的响应类似于以下内容：  

    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <POLLINGSTMT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT">  
      <POLLINGSTMTRECORD>  
        <POLLINGSTMTRECORD>  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-08-03T20:10:28</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        <POLLINGSTMTRECORD>  
      <POLLINGSTMTRECORD>  
          ......  
          ......  
      </POLLINGSTMTRECORD>  
        ......  
        ......  
      </POLLINGSTMTRECORD>  
    </POLLINGSTMT>  
    ```  

-   适配器执行轮询后语句，后者将所有数据从 ACCOUNTACTIVITY 表都移动到另一个表。  

-   轮询间隔后，适配器再次执行**PolledDataAvailableStatement**。 因为 ACCOUNTACTIVITY 表现在，有没有记录**PolledDataAvailableStatement**不会返回正值，因此该适配器不会执行该语句为指定**PollingStatement**绑定属性。 因此，适配器客户端不会获取任何轮询消息。  

-   适配器客户端不会获得更多轮询消息，直到显式向 ACCOUNTACTIVITY 表中插入一些记录。 要插入更多的记录，可以运行这些示例提供的 more_activity_data.sql 脚本。 在运行此脚本中下, 一次后**PolledDataAvailableStatement**是执行，它会返回正值。 因此，适配器将执行轮询语句和适配器客户端再次接收轮询消息。  

> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息在 Oracle 上运行的轮询查询时可能会遇到数据库使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理与 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  

## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)