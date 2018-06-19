---
title: 处理通知消息，以完成使用 BizTalk Server 的 Oracle 数据库中的特定任务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376055a7-98a6-4055-b6cd-2f5971349a6a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 379ef13914d7c6136d39e4a394a9299c709785fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967867"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-database-using-biztalk-server"></a>处理通知邮件完成使用 BizTalk Server 的 Oracle 数据库中的特定任务
你可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收对 Oracle 数据库表的更改的通知。 但是，该适配器仅向你发送通知某些记录已插入、 更新或删除某些数据库表中。 这些记录的任何后续处理必须由客户端应用程序本身进行处理。 本主题提供有关如何处理表根据从 Oracle 数据库接收的通知的类型中记录的基于方案的说明。  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>收到通知后执行后续操作的方案  
 以下是几个适配器客户端必须在其中执行某些后通知任务的场景。  
  
-   **方案 1。** 请考虑适配器客户端必须执行某些任务根据从 Oracle 数据库接收的通知的类型的位置的方案。 例如，如果在表"B"中插入记录客户端应用程序，就必须更新表"A"中的记录。 同样，客户端应用程序必须从表"B"中删除记录如果从表"A"中删除记录。  
  
     收到的通知消息在此方案中，适配器客户端必须提取要决定是否通知已为插入操作或删除操作的通知类型。 一旦查明通知类型是适配器客户端必须执行后续操作来插入或更新相关的表。  
  
-   **方案 2。** 请考虑接收到的表的更改的通知消息的接收位置出现故障的方案。 接收位置停机时，某些记录会添加到表中。 但是，这些记录的适配器客户端不接收任何通知。 备份接收位置时，该适配器将通过发送特定消息来通知客户端，然后客户端应用程序必须查找接收位置已关闭时插入数据库表中的所有记录。  
  
     收到的通知消息在此方案中，适配器客户端必须提取通知是到数据库表的更改或用于接收位置启动有关的信息。 如果通知所针对的接收位置开始，适配器客户端必须实现的逻辑来处理可能已插入、 更新，或接收位置已关闭时删除的记录。  
  
> [!NOTE]
>  这些是只为某些更好地了解如何使用通知功能中的列出的示例方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 但是，提取收到的通知的类型所需的任务的一组基本将为所有应用场景类似。 本主题将说明了如何从一条通知消息中提取通知的类型。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>本主题演示接收通知消息的方式  
 在本主题中，来演示如何处理通知消息，以执行后续任务中，我们假设一个基本方案适配器客户端其中使用 BizTalk 应用程序以接收对 ACCOUNTACTIVITY 表的更改的通知消息。 收到通知后，客户端将筛选器收到的通知的类型，并执行后续操作。 为了演示非常基本的方案，让我们考虑适配器客户端将通知消息复制到不同的文件夹，根据收到的通知的类型。 因此：  
  
-   如果通知消息是针对插入或更新操作，适配器客户端会将该邮件复制到 C:\TestLocation\UpsertNotification 文件夹中。  
  
-   如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。  
  
 若要实现此方法作为 BizTalk 应用程序的一部分，业务流程必须包含以下信息：  
  
-   单向接收端口以接收通知消息。  
  
-   表达式形状包含 xpath 查询来提取有关收到的通知消息的类型的信息。  
  
-   要包含在业务流程中的决策块判定形状。 在此决策块中，应用程序决定要执行的后续操作基于收到的通知消息。  
  
-   两个单向发送最后接收通知消息的端口。  
  
## <a name="configuring-notifications-with-the-oracle-database-binding-properties"></a>与 Oracle 数据库绑定属性中配置通知  
 下表总结了[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，用于配置从 Oracle 数据库接收通知。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  你可以选择在生成的架构时指定这些绑定属性**通知**操作，即使它不是强制性。 如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。 你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF OracleDB 接收属性已设置对绑定的端口。 有关创建使用绑定文件的 WCF 自定义或 WCF OracleDB 端口的详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。|  
|**NotificationStatement**|指定用来注册查询通知的 SELECT 语句。 仅当指定的 SELECT 语句更改的结果集时，适配器获取一条通知消息。|  
|**NotifyOnListenerStart**|指定启动侦听器时，适配器是否发送到适配器客户端通知。|  
  
 有关这些属性的更完整说明，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。 有关如何使用的完整说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要从 Oracle 数据库接收通知，请阅读更多。  
  
## <a name="how-to-receive-notification-messages-from-oracle-database"></a>如何从 Oracle 数据库接收通知消息  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要配置的适配器以接收通知消息，这些任务包括：  
  
1.  创建 BizTalk 项目，然后生成架构**通知**入站操作。 （可选） 你可以为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**绑定属性。  
  
2.  在从 Oracle 数据库接收通知的 BizTalk 项目中创建一条消息。  
  
3.  在前面部分所述创建一个业务流程。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
    > [!NOTE]
    >  对于入站操作，如接收通知消息，你必须仅配置单向的 WCF 自定义或 WCF OracleDB 接收端口。 双向接收入站操作不支持端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**通知**入站操作。 请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果你不想要指定的绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。 有关如何指定绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
2.  选择与具有协定类型**服务 （入站操作）**。  
  
3.  生成架构**通知**操作。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。  
  
 对于本主题中，你必须创建一条消息从 Oracle 数据库接收通知。  
  
 执行以下步骤以创建消息并将它们链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|键入 `NotifyReceive`。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Process_Notification.OracleDBBinding.Notification*，其中*Process_Notification*是的名称你BizTalk 项目。 *OracleDBBinding*是为生成的架构**通知**操作。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为从 Oracle 数据库接收通知消息，然后执行基于收到的通知的类型的任务。 在此业务流程，适配器接收基于 SELECT 语句为指定的通知消息**NotificationStatement**绑定属性。 表达式形状中指定的 xpath 查询提取到变量中，通知的类型假设**NotificationType**。 确定形状使用此变量中的值来确定接收通知的类型和采用的相应"路径"执行后续操作。 如前一部分所述，业务流程将执行以下操作，根据收到的通知消息的类型。  
  
-   如果通知消息是针对插入或更新操作，适配器客户端会将该邮件复制到 C:\TestLocation\UpsertNotification 文件夹中。  
  
-   如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。  
  
 因此，您的业务流程必须包含以下信息：  
  
-   单向接收端口以接收通知消息。  
  
-   包含要提取的收到的通知类型 xpath 查询是表达式形状。  
  
-   要包含在业务流程中的决策块判定形状。 在此决策块中，应用程序决定要执行的后续操作基于收到的通知消息。  
  
-   两个单向发送最后接收通知消息的端口。  
  
-   接收形状。  
  
 示例业务流程如下所示。  
  
 ![业务流程执行 post &#45; 通知任务](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-将设置**名称**到*ReceiveNotification*<br /><br /> -将设置**激活**到*True*|  
  
### <a name="adding-an-expression-shape"></a>添加表达式形状  
 包括表达式形状中业务流程的用途是具有要提取的收到的通知消息的种类的 xpath 查询。 在创建之前 xpath 查询，让我们看一下通知消息的格式。 典型的通知消息如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
  <Details>  
    <NotificationDetails>  
      <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
      <Info>1</Info>   
      <QueryId>0</QueryId>   
    </NotificationDetails>  
  </Details>  
  <Info>Insert</Info>   
  <ResourceNames>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
  </ResourceNames>  
  <Source>Data</Source>   
  <Type>Change</Type>   
</Notification>  
```  
  
 正如您看到的通知类型有关的信息中有可用`<info>`标记，父项中的`<Notification>`标记。 因此，在此表达式形状的你必须：  
  
-   创建包含中的值的变量`<Info>`标记并将其类型设置为 System.String。 有关创建变量的详细信息，请参阅[在业务流程中使用变量](../../core/using-variables-in-orchestrations.md)。  
  
     本主题中，将命名为变量**NotificationType**。  
  
-   创建要提取的值的 xpath 查询\<信息\>标记。 Xpath 查询将如下所示：  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     在此 xpath 查询**NotifyReceive**是创建用于接收通知消息的消息。 中的摘录`string`函数指示查询必须提取的值在`<Info>`标记，又是内`<Notification>`标记。 最后，该查询所提取的值分配给**NotificaitonType**变量。  
  
### <a name="adding-a-decide-shape"></a>添加判定形状  
 添加判定形状的目的是要包含在业务流程来决定要执行的后续操作根据收到的通知消息的类型中的决策块。 默认情况下，决定的值根据**NotificationType**变量。 在本主题中，业务流程做出决策基于收到的通知消息的种类。 因此，规则形状中的条件，如下所示指定：  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 此条件提供的建议，如果值**NotificaitonType**变量是 Insert 或 Update，业务流程将执行一组任务。 如果值**NotificationType**变量是任何其他操作，业务流程将执行另一组任务。  
  
 如前面几节中所述，来演示一种简单方法，业务流程将将消息复制到不同的文件夹，基于通知消息类型。 这样，在规则中和 Else 块，您必须添加发送形状以将消息发送到不同的端口。 本主题中，将命名为规则块中的发送形状**SendUpsertNotification**和作为 Else 块中的发送形状**SendOtherNotification**。  
  
### <a name="adding-ports"></a>添加端口  
 现在，你必须将以下逻辑端口添加到业务流程：  
  
-   单向接收端口从 Oracle 数据库接收通知消息。  
  
-   将 Insert 和 Update 操作的通知消息发送到特定文件夹的单向发送端口。  
  
-   要将任何其他操作的通知消息发送到特定文件夹的单向发送端口。  
  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|OracleNotifyPort|-将设置**标识符**到*OracleNotifyPort*<br /><br /> -将设置**类型**到*OracleNotifyPortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*接收*|  
|NotificationUpsertPort|-将设置**标识符**到*NotificationUpsertPort*<br /><br /> -将设置**类型**到*NotificationUpsertPortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*|  
|OtherNotificationPort|-将设置**标识符**到*OtherNotificationPort*<br /><br /> -将设置**类型**到*OtherNotificationPortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveNotification|-将设置**消息**到*NotifyReceive*<br /><br /> -将设置**操作**到*OracleNotifyPort.Notify.Request*|  
|SendUpsertNotification|-将设置**消息**到*NotifyReceive*<br /><br /> -将设置**操作**到*NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-将设置**消息**到*选择*<br /><br /> -将设置**操作**到*OtherNotificationPort.Other.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   定义一个物理 WCF 自定义或 WCF OracleDB 单向接收端口。 此端口侦听来自 Oracle 数据库的通知。 有关如何创建接收端口，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
        > [!IMPORTANT]
        >  不需要执行此步骤中，如果指定在设计时绑定属性。 在这种情况下，你可以创建 WCF 自定义或 WCF OracleDB 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息，请参阅配置物理端口绑定使用端口绑定文件。  
  
        |绑定属性|值|  
        |----------------------|-----------|  
        |**InboundOperationType**|将其设置为**通知**。|  
        |**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。 将其设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。<br /><br /> **重要说明：** 如果设置为默认值为-1，则你将需要完全禁用 Windows 防火墙，以接收通知消息。|  
        |**NotificationStatement**|将其设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注意：** 必须指定表名称以及架构名称。 例如， `SCOTT.ACCOUNTACTIVITY`。|  
        |**NotifyOnListenerStart**|将其设置为**True**。|  
  
         有关不同的绑定属性的详细信息，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。  
  
        > [!NOTE]
        >  我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你可以执行以便通过将服务添加行为配置 WCF 自定义或 WCF OracleDB 时接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 Oracle 数据库的事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。  
  
    -   硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Oracle 数据库 Insert 和 Update 操作的相应文件端口上定义的位置。 配置此端口，以将通知消息放置到 C:\TestLocation\UpsertNotification 的文件夹。  
  
    -   硬盘和 BizTalk 业务流程将放置的位置的通知消息从所有其他操作的 Oracle 数据库的相应文件端口上定义的位置。 配置此端口，以将通知消息放置到 C:\TestLocation\OtherNotification 的文件夹。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序接收通知消息从 Oracle 数据库并执行后续的选择和更新操作。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleDB 单向接收端口，从而从 Oracle 数据库运行时接收通知消息。  
  
-   正在从 Oracle 数据库中接收消息，两个文件发送端口。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 启动 BizTalk 业务流程后，下面的一组操作发生：  
  
-   因为**NotifyOnListenerStart**绑定属性设置为**True**，收到以下消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     请注意，中的值`<Info>`标记为"ListnerStarted"。 因此，在 C:\TestLocation\OtherNotification 文件夹中收到此消息。  
  
-   ACCOUNTACTIVITY 表中插入一条记录。 你将收到类似于以下通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     请注意，中的值`<Info>`标记为"插入"。 因此，在 C:\TestLocation\UpsertNotification 文件夹中收到此消息。  
  
-   更新 ACCOUNTACTIVITY 表中的记录。 你将收到类似于以下通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     请注意，中的值`<Info>`标记为"更新"。 因此，在 C:\TestLocation\UpsertNotification 文件夹中收到此消息。  
  
-   从 ACCOUNTACTIVITY 表中删除一条记录。 你将收到类似于以下通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>16</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Delete</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     请注意，中的值`<Info>`标记为"Delete"。 因此，在 C:\TestLocation\OtherNotification 文件夹中收到此消息。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>接收通知消息之后执行复杂的操作  
 为简单和更好地了解，本主题中的业务流程将消息复制到不同的文件夹，基于通知类型。 但是，在实际方案中你可能想要执行更复杂的操作。 对其执行操作要生成此主题中所述，你可以执行类似的过程。 例如，你可以更改业务流程如果 ACCOUNTACTIVITY 表上的插入操作获取一条通知消息，另一个表中插入记录。 在这种情况下，你可以确定形状中的相应更改。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 的接收 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)