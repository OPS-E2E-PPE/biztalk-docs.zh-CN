---
title: "轮询使用存储的过程、 函数或打包的过程和函数的 Oracle 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c34843a-d02b-4941-baf6-6bc80b5821ad
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0646f1c447cfc4949edafe94d634a6c651083307
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-database-using-stored-procedures-functions-or-packaged-procedures-and-functions"></a>使用存储的过程、 函数或打包的过程和函数的轮询 Oracle 数据库
你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收定期的数据更改消息通过使用存储的过程、 函数或打包的过程和函数以定期轮询 Oracle 数据库。 你可以指定存储的过程、 函数或打包的过程和函数与适配器执行定期轮询 Oracle 数据库的轮询语句。  
  
 若要启用此功能，必须指定某些绑定属性上[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你还可以通过设置修改 POLLINGSTMT 操作的目标命名空间**PollingId**连接 URI 中的属性。 有关详细信息，请参阅[支持基于接收轮询的 Oracle 数据库中的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)和[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。 有关轮询操作的 SOAP 消息结构的信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。  
  
## <a name="configuring-a-polling-operation-with-oracle-database-adapter-binding-properties"></a>使用 Oracle 数据库适配器绑定属性中配置的轮询操作  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行轮询查询和在事务内的任何后轮询 PL/SQL 代码块。 下表总结了[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]更改消息的绑定属性，用于配置适配器，以接收数据。 你必须指定配置 WCF 自定义或 WCF OracleDB 时这些绑定属性接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定是否想要执行的轮询或通知入站操作。 默认值是**轮询**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 仅当一条记录时，存储的过程指定为**PollingStatement**将执行绑定属性。|  
|**PollingInterval**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 500 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。 默认值是`SELECT 1 FROM DUAL`，这表明是否，适配器必须继续而不考虑轮询表是否具有数据的轮询。|  
|**PollingStatement**|指定的轮询语句。 若要轮询使用存储的过程、 函数，或打包的过程或函数，必须在此绑定属性中指定相应的操作的整个请求消息。 请求消息必须相同，你将发送到适配器作为出站操作调用相应的操作。 默认值为 null。<br /><br /> 必须指定的值**PollingStatement**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。|  
|**PollingAction**|指定轮询操作的操作。 你可以确定从元数据生成操作使用特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。|  
|**PostPollStatement**|指定在指定的语句之后执行的语句块**PollingStatement**绑定属性执行。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。|  
  
 有关这些属性的更完整说明，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要轮询的 Oracle 数据库，进一步阅读。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何可以轮询使用存储的过程的 Oracle 数据库。 创建 BizTalk 项目，并生成你想要用于轮询 Oracle 数据库的存储过程的架构。 在本主题中，我们使用 GET_ACTIVITYS 存储过程来轮询 ACCOUNTACTIVITY 表。 此存储的过程时使用 SCOTT 架构中的 ACCOUNT_PKG 包。 你可以运行这些示例数据库中创建这些对象提供的 SQL 脚本。  
  
> [!NOTE]
>  此主题轮询 ACCOUNTACTIVITY 表，其中数据库表创建通过使用示例运行提供的脚本中业务流程。 本主题以轮询任何其他表中所述，你必须执行类似的过程。  
  
 为了演示轮询操作，我们执行以下操作：  
  
-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中表轮询 (ACCOUNTACTIVITY) 有任何数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     这可确保仅当 ACCOUNTACTIVITY 表具有某些记录时，适配器都将执行轮询语句。  
  
-   通过提供作为的一部分的请求消息执行存储的过程，GET_ACTIVITYS， **PollingStatement**绑定属性。 此存储的过程将检索 ACCOUNTACTIVITY 表中的所有行，并且你将获得该适配器的响应消息。  
  
-   作为的一部分执行一个 PL/SQL 块**PostPollStatement**绑定属性。 此语句将所有数据从 ACCOUNTACTIVITY 表都移到数据库中的另一个表。 一旦发生这种情况下, 一次**PollingStatement**将执行，它将不提取任何数据，因此 GET_ACTIVITYS 存储过程将返回一个空响应消息。  
  
-   更多的数据添加到 ACCOUNTACTIVITY 表，直到你将继续获取空响应消息。 因此，你必须重新填充的新记录所在 ACCOUNTACTIVITY 的表。 你可以通过运行这些示例使用提供的 more_activity_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。  
  
## <a name="how-to-receive-data-change-messages-from-oracle"></a>如何从 Oracle 接收数据更改消息  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及以下过程任务中所述[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要配置的适配器轮询 Oracle 数据库使用的存储的过程：  
  
1.  创建 BizTalk 项目，并生成你想要使用进行轮询的存储过程的架构。  
  
2.  在从 Oracle 数据库接收消息的 BizTalk 项目中创建一条消息。  
  
3.  创建业务流程从 Oracle 数据库接收消息并将它们保存到文件夹。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
    > [!IMPORTANT]
    >  你始终必须配置的入站的轮询方案单向接收端口。 双向接收入站操作不支持端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 你必须生成 GET_ACTIVITYS 操作的架构。 生成架构使用时执行以下任务[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
-   选择与具有协定类型**服务 （入站操作）**。  
  
-   生成架构**GET_ACTIVITYS**过程。  
  
 有关如何生成架构的详细信息，请参阅[浏览、 搜索和 get 元数据的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。  
  
 对于本主题中，你必须创建一条消息，用于从 Oracle 接收消息。  
  
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
    |消息类型|从下拉列表中，展开**架构**，然后选择*Polling.OracleEBSBindingSchema*，其中*轮询*是 BizTalk 项目的名称。 *OracleEBSBindingSchema*是为生成的响应架构**GET_ACTIVITYS**存储过程。<br /><br /> **重要说明：**因为轮询是单向操作，生成适配器的架构不包含响应节点中，并且因此没有只有一个根节点在架构中。 如果此类架构用于消息类型，必须通过生成的架构的文件名来标识的架构。<br /><br /> 例如，如果你创建双向操作的架构，架构中的节点使用文件名称`OracleEBSBindingSchema`可能看起来像"请求"和"响应"。 如果你想要在业务流程映射到的请求架构中创建一条消息，你可以通过查找来确定在列表中的架构`OracleEBSBindingSchema.Request`。 但是，在轮询操作时，因为的唯一节点的"轮询"，它不是轻松地标识你想要映射到，因为具有单个节点的架构不会作为列出的架构\<schemafilename >。\<rootnodename >。 相反，此类架构仅的文件名按列出。 在这种情况下，唯一的方法来识别的架构是架构文件名，例如，OracleEBSBindingSchema。|  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] GET_ACTIVITYS 的入站和出站操作存储过程生成架构。 入站操作，必须使用架构：  
  
    -   业务流程的一部分创建将消息映射。  
  
    -   若要检索你必须为指定的操作**PollingAction**属性绑定在运行时。  
  
     必须使用出站操作的架构来获取请求消息必须指定作为的一部分**PollingStatement**绑定属性。  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 Oracle 接收基于轮询的数据更改消息。 在此业务流程，适配器将通过执行存储的过程的一部分的请求消息指定为其接收响应**PollingStatement**绑定属性。 存储过程的响应消息保存到文件位置。 将包含轮询 Oracle 数据库典型业务流程：  
  
-   接收和发送形状从 Oracle 接收消息并分别将发送到文件端口。  
  
-   单向接收端口从 Oracle 数据库接收消息。  
  
    > [!IMPORTANT]
    >  你始终必须配置的入站的轮询方案单向接收端口。 双向接收入站操作不支持端口。  
  
-   要从 Oracle 数据库发送轮询响应单向发送端口。  
  
 示例业务流程如下所示。  
  
 ![适用于 Oracle 轮询查询的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3.gif "6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3")  
  
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
|OracleReceivePort|-将设置**标识符**到*OracleReceivePort*<br /><br /> -将设置**类型**到*OracleReceivePortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*接收*|  
|SaveMessagePort|-将设置**标识符**到*SaveMessagePort*<br /><br /> -将设置**类型**到*SaveMessagePortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*OracleReceivePort.Polling.Request*|  
|SaveMessage|-将设置**消息**到*接收*<br /><br /> -将设置**操作**到*SaveMessagePort.Polling.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md))。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和其中 BizTalk 业务流程将从 Oracle 丢弃消息的相应文件端口上定义的位置。 这些消息将以响应接收端口指定轮询语句。  
  
    -   定义一个物理 WCF 自定义或 WCF OracleDB 单向接收端口。 此端口轮询 Oracle 数据库。 有关如何创建接收端口，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
        |绑定属性|值|  
        |----------------------|-----------|  
        |**InboundOperationType**|将其设置为**轮询**。|  
        |**PolledDataAvailableStatement**|此示例中，此绑定属性设置为：<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> 这可确保仅当 ACCOUNTACTIVITY 表具有某些记录时，适配器都将执行轮询语句。|  
        |**PollingAction**|从为 GET_ACTIVITYS 过程的入站消息生成的架构中检索轮询操作。 对于此示例中，此绑定属性设置为**http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/PollingPackage//ACCOUNT_PKG/GET_ACTIVITYS**。|  
        |**PollingStatement**|此绑定属性，指定要调用 GET_ACTIVITYS 的请求消息存储过程。 你可以获取请求消息从架构生成的出站操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 你必须为此绑定属性作为输入提供整个 XML 消息。 此示例中，此绑定属性设置为：<br /><br /> `<GET_ACTIVITYS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY">   <INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS> </GET_ACTIVITYS>`<br /><br /> GET_ACTIVITYS 参数作为存储过程采用输入的 REF CURSOR。|  
        |**PostPollStatement**|指定要从 ACCOUNTACTIVITY 表的所有数据都移到另一个表的后期轮询声明。 此示例中，此绑定属性设置为：<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`|  
  
         有关不同的绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
        > [!NOTE]
        >  我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你可以这样做通过配置接收端口时添加的服务行为。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动轮询 Oracle 数据库的 BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleDB 单向接收端口，从而轮询使用为指定的存储的过程的 Oracle **PollingStatement**绑定属性，正在运行。  
  
-   文件发送端口，从而从 Oracle 数据库中接收消息，正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，下面的一组操作需要置于相同的序列：  
  
-   适配器执行**PolledDataAvailableStatement**它返回一个正值，该值指示要执行的语句，为指定的适配器**PollingStatement**绑定属性。  
  
-   适配器执行为指定的存储的 GET_ACTIVITYS 过程**PollingStatement** ACCOUNTACTIVITY 表中的绑定属性，并返回所有行。 从 Oracle 数据库响应如下所示：  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <GET_ACTIVITYS xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/PollingPackage/ACCOUNT_PKG">  
      <OUTRECS>  
        <OUTRECSRecord xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/ReferencedRecordTypes/SCOTT/ACCOUNT_PKG/GET_ACTIVITYS/SCOTT/GET_ACTIVITYS">  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </OUTRECSRecord>  
        <OUTRECSRecord xmlns=" http://Microsoft.LobServices.OracleDB/2007/03/ReferencedRecordTypes/SCOTT/ACCOUNT_PKG/GET_ACTIVITYS/SCOTT/GET_ACTIVITYS">  
          ......  
          ......   
        </OUTRECSRecord>  
        ......  
        ......  
      </OUTRECS>  
    </GET_ACTIVITYS>  
    ```  
  
-   适配器执行后轮询语句，它将所有数据从 ACCOUNTACTIVITY 表都移动到另一个表。  
  
-   轮询间隔后，该适配器再次执行**PolledDataAvailableStatement**。 因为 ACCOUNTACTIVITY 表中不有任何记录现在， **PolledDataAvailableStatement**不返回一个正值，并且因此适配器不执行为指定的语句**PollingStatement**绑定属性。 因此，适配器客户端不会获取任何轮询消息。  
  
-   适配器客户端不会获得更多的轮询消息，直到某些记录显式插入 ACCOUNTACTIVITY 表。 要插入更多的记录，你可以运行这些示例使用提供的 more_activity_data.sql 脚本。 运行此脚本下, 一次后**PolledDataAvailableStatement**是执行，返回一个正值。 因此，适配器执行轮询的语句，适配器客户端可能再次收到轮询消息。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将继续轮询除非你显式禁用接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)