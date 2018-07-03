---
title: 处理通知消息，以完成 Oracle E-business Suite 中的特定任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bddeb5a-3819-40cc-aae0-c49963f0beb1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d671ee0b4ab351bce8109cdd20635d6f838da9ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995950"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-e-business-suite"></a>处理通知消息来完成 Oracle E-business Suite 中的特定任务
可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收到 Oracle 数据库表的更改通知。 但是，适配器仅向你发送某些记录已插入、 更新或删除数据库表中的通知。 这些记录的任何后续处理必须由客户端应用程序本身进行处理。 本主题显示如何处理从 Oracle 数据库接收的通知类型基于在表中的记录上的基于方案的说明。  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>收到通知后执行后续操作的方案  
 以下是几种方案，适配器客户端必须执行某些通知后任务。  
  
-   **方案 1。** 假设适配器客户端必须在其中执行某些任务基于从 Oracle 数据库接收的通知的类型。 例如，如果在表"B"中插入记录客户端应用程序必须更新表"A"中的记录。 同样，客户端应用程序必须从表"B"中删除记录如果从表"A"中删除记录。  
  
     从通知消息接收到，在此方案中，适配器客户端必须提取要决定是否通知已为插入操作或删除操作的通知类型。 一旦确定通知类型，适配器客户端必须执行后续操作来插入或更新相关表。  
  
-   **方案 2。** 假设接收对表的更改的通知消息的接收位置出现故障。 关闭接收位置时，某些记录添加到表。 但是，这些记录的适配器客户端不接收任何通知。 当接收位置重新启动时，适配器通过发送特定消息，通知客户端，然后客户端应用程序必须查找的接收位置时向下插入数据库表中的所有记录。  
  
     从通知消息接收到，在此方案中，适配器客户端必须提取有关该通知是对数据库表的更改或接收位置开始的信息。 通知所针对的接收位置开始，如果适配器客户端必须实现逻辑以处理可能具有已插入、 更新或接收位置已关闭时删除的记录。  
  
> [!NOTE]
>  这些是为更好地了解如何使用通知功能中的列出的只是一些示例方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 但是，一组基本的通知接收到的类型中提取所需的任务将适用于所有方案类似。 本主题将说明了如何从通知消息中提取的通知类型。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>如何本主题演示如何接收通知消息  
 在本主题中，用于演示如何处理通知消息，以执行后续任务中，我们考虑其中适配器客户端使用的 BizTalk 应用程序接收到 ACCOUNTACTIVITY 表更改的通知消息的基本方案。 收到通知后，客户端筛选收到的通知的类型，并执行后续操作。 若要演示最基本方案，让我们设想适配器客户端将通知消息复制到不同的文件夹，根据收到的通知的类型。 因此：  
  
- 如果通知消息是针对 Insert 或 Update 操作，适配器客户端会将消息复制到 C:\TestLocation\UpsertNotification 文件夹中。  
  
- 如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。  
  
  为此 BizTalk 应用程序的一部分，该业务流程必须包含以下信息：  
  
- 一个单向接收端口以接收通知消息。  
  
- 表达式形状包含 xpath 查询来提取有关收到通知消息的类型信息。  
  
- 判定形状在业务流程中包括判定块。 在此决策块中，应用程序确定要执行的后续操作根据收到的通知消息。  
  
- 两个单向发送端口的最后接收的通知消息。  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>使用 Oracle E-business 适配器的绑定属性中配置通知  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置 Oracle E-business Suite 中接收通知的属性。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  您可以选择生成的架构时指定这些绑定属性**通知**操作，即使并不总是这样。 如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。 稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF OracleEBS 属性已设置对绑定接收端口。 有关创建使用绑定文件的 WCF 自定义或 WCF OracleEBS 端口的详细信息，请参阅[配置物理端口绑定使用端口绑定文件到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationPort**|指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。|  
|**NotificationStatement**|指定用于对查询通知注册的 SELECT 语句。 仅当指定的 SELECT 语句更改的结果集时，适配器将获取一条通知消息。|  
|**NotifyOnListenerStart**|指定适配器是否启动侦听器时在向适配器客户端发送了通知。|  
  
 有关这些属性的更完整说明，请参阅 [[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 中接收通知，请阅读更多。  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a>如何从 Oracle E-business Suite 中接收通知消息  
 对 Oracle E-business Suite 使用执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置要接收通知消息的适配器，这些任务包括：  
  
1. 创建 BizTalk 项目，然后生成的架构**通知**的入站操作。 或者，您可以指定的值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**绑定属性。  
  
2. 用于 Oracle E-business Suite 中接收通知的 BizTalk 项目中创建一条消息。  
  
3. 在上一部分中所述创建一个业务流程。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
   > [!NOTE]
   >  对于入站操作，如接收通知消息，则必须仅配置一个单向 WCF 自定义或 Wcf-oracleebs 接收端口。 双向接收端口不支持的入站操作。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**通知**的入站操作。 有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。 生成架构时，请执行以下任务。 如果不想指定绑定属性在设计时，跳过的第一步。  
  
 生成架构时，请执行以下任务。 如果不想指定绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何指定绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  
2.  选择作为协定类型**服务 （入站操作）**。  
  
3.  生成架构**通知**操作。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你在上一节中生成此架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 生成架构后，必须直接将其链接到的消息，业务流程视图中的 BizTalk 项目。  
  
 对于本主题中，必须创建一条消息从 Oracle 数据库接收通知。  
  
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
    |消息类型|从下拉列表中，展开**架构**，然后选择*Process_Notification.OracleEBSBinding.Notification*，其中*Process_Notification*的名称在BizTalk 项目。 *OracleEBSBinding*是为生成的架构**通知**操作。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]有关从 Oracle 数据库接收通知消息，然后执行任务根据收到的通知的类型。 在此业务流程，适配器将接收通知消息根据 SELECT 语句为指定**NotificationStatement**属性绑定。 表达式形状中指定的 xpath 查询中提取到变量中，通知的类型说**NotificationType**。 判定形状使用此变量中的值来确定接收通知的类型和使用的相应"路径"以执行后续操作。 如前面部分中所述，业务流程将执行以下操作，根据收到的通知消息类型。  
  
- 如果通知消息是针对 Insert 或 Update 操作，适配器客户端会将消息复制到 C:\TestLocation\UpsertNotification 文件夹中。  
  
- 如果通知消息是针对任何其他操作，例如删除，适配器客户端将该邮件复制到 C:\TestLocation\OtherNotificaiton 文件夹。  
  
  因此，您的业务流程必须包含以下信息：  
  
- 一个单向接收端口以接收通知消息。  
  
- 表达式形状包含 xpath 查询来提取通知接收到的类型。  
  
- 判定形状在业务流程中包括判定块。 在此决策块中，应用程序确定要执行的后续操作根据收到的通知消息。  
  
- 两个单向发送端口的最后接收的通知消息。  
  
- 接收形状。  
  
  示例业务流程如下所示：  
  
  ![业务流程，以执行 post&#45;通知任务](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称**形状**列是在业务流程关系图中显示消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-设置**名称**到*ReceiveNotification*<br /><br /> -设置**激活**到 *，则返回 True*|  
  
### <a name="adding-an-expression-shape"></a>添加表达式形状  
 在业务流程中包括的表达式形状的用途是收到通知消息的类型中提取的 xpath 查询。 然后再创建 xpath 查询，让我们看一下通知消息的格式。 典型的通知消息如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
 正如您看到的通知类型有关的信息中有可用`<info>`标记，在父级内的`<Notification>`标记。 因此，在此表达式形状，你必须：  
  
-   创建包含中的值的变量`<Info>`标记并将其类型设置为 System.String。 有关创建变量的详细信息，请参阅[业务流程中使用变量](../../core/using-variables-in-orchestrations.md)。  
  
     有关本主题中，将变量命名为**NotificationType**。  
  
-   创建 xpath 查询中的值中提取\<信息\>标记。 Xpath 查询将如下所示：  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     在此 xpath 查询中， **NotifyReceive**是创建用于接收通知消息的消息。 中的摘录`string`函数指明查询必须在值中提取`<Info>`标记，它又是内`<Notification>`标记。 最后，在查询中提取的值分配给**NotificaitonType**变量。  
  
### <a name="adding-a-decide-shape"></a>添加判定形状  
 添加判定形状的目的是要包含在业务流程，以决定要执行的后续操作根据收到的通知消息类型中的判定块。 基于的值做出的决定**NotificationType**变量。 在本主题中，业务流程可以根据收到的通知消息类型的决策。 因此，规则形状中的条件，如下所示指定：  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 这种情况表明，如果的值**NotificaitonType**变量是插入或更新，该业务流程将执行的一组任务。 如果的值**NotificationType**变量是任何其他操作，业务流程将执行另一组任务。  
  
 如前面部分中所述，来演示一种简单方法，该业务流程会将消息复制到不同的文件夹的通知消息类型。 因此，规则中，Else 块，必须添加发送形状将消息发送到不同的端口。 本主题中，命名为规则块中的发送形状**SendUpsertNotification**和 Else 块作为中的发送形状**SendOtherNotification**。  
  
### <a name="adding-ports"></a>添加端口  
 您现在必须将以下逻辑端口添加到业务流程：  
  
- 单向接收端口以从 Oracle 数据库接收通知消息。  
  
- 单向发送端口以将 Insert 和 Update 操作的通知消息发送到特定文件夹。  
  
- 若要将任何其他操作的通知消息发送到特定文件夹的单向发送端口。  
  
  请确保为每个逻辑端口中指定以下属性。 中列出的名称**端口**列是本主题前面所述的业务流程关系图中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|OracleNotifyPort|-设置**标识符**到*OracleNotifyPort*<br /><br /> -设置**类型**到*OracleNotifyPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|NotificationUpsertPort|-设置**标识符**到*NotificationUpsertPort*<br /><br /> -设置**类型**到*NotificationUpsertPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  
|OtherNotificationPort|-设置**标识符**到*OtherNotificationPort*<br /><br /> -设置**类型**到*OtherNotificationPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 中列出的名称**形状**列是消息形状的名称，如本主题前面所述的业务流程关系图中显示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*OracleNotifyPort.Notify.Request*|  
|SendUpsertNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-设置**消息**到*选择*<br /><br /> -设置**操作**到*OtherNotificationPort.Other.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。 此端口侦听来自 Oracle E-business Suite 的通知。 有关如何创建接收端口，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果指定在设计时的绑定属性。 在这种情况下，您可以创建 WCF 自定义或 WCF OracleEBS 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|将此设置为**通知**。|  
    |**NotificationPort**|指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。 将此设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。<br /><br /> **重要**如果将其设置为默认值-1，必须完全禁用 Windows 防火墙，以接收通知消息。|  
    |**NotificationStatement**|将此设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **请注意**必须指定表名称以及架构名称。 例如， `SCOTT.ACCOUNTACTIVITY`。|  
    |**NotifyOnListenerStart**|将此设置为 **，则返回 True**。|  
  
     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
    > [!IMPORTANT]
    >  如果要配置通知的接口表，则必须通过指定必要的绑定属性来设置应用程序上下文。 有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
    > 
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 您为此，可添加服务行为配置 WCF 自定义时或 WCF OracleEBS 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  
  
  - 硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Insert 和 Update 操作的 Oracle 数据库的相应文件端口上定义的位置。 配置此端口，放到文件夹 C:\TestLocation\UpsertNotification 通知消息。  
  
  - 硬盘和 BizTalk 业务流程将放置的位置的通知消息从 Oracle 数据库的所有其他操作的相应文件端口上定义的位置。 配置此端口，放到文件夹 C:\TestLocation\OtherNotification 通知消息。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序从 Oracle 数据库接收通知消息并执行后续的 Select 和 Update 操作。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleEBS 单向接收端口，从而从 Oracle 数据库运行时接收通知消息。  
  
-   正在从 Oracle 数据库接收消息，两个文件发送端口。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 启动 BizTalk 业务流程后，以下组操作发生：  
  
-   因为**NotifyOnListenerStart**绑定属性设置为**True**，收到以下消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     请注意，中的值`<Info>`标记为"ListnerStarted"。 因此，C:\TestLocation\OtherNotification 文件夹中收到此消息。  
  
-   ACCOUNTACTIVITY 表中插入一条记录。 你将收到类似于以下的通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     请注意，中的值`<Info>`标记为"Insert"。 因此，C:\TestLocation\UpsertNotification 文件夹中收到此消息。  
  
-   更新 ACCOUNTACTIVITY 表中的记录。 你将收到类似于以下的通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     请注意，中的值`<Info>`标记为"Update"。 因此，C:\TestLocation\UpsertNotification 文件夹中收到此消息。  
  
-   从 ACCOUNTACTIVITY 表中删除一条记录。 你将收到类似于以下的通知消息：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     请注意，中的值`<Info>`标记为"Delete"。 因此，C:\TestLocation\OtherNotification 文件夹中收到此消息。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>接收通知消息后执行复杂的操作  
 对于简单起见，更好地了解本主题中的业务流程将消息复制到不同的文件夹的通知类型。 但是，在实际方案中你可能想要执行更复杂的操作。 在此主题，并对其执行操作需要的生成中提供，可以执行类似的过程。 例如，可以更改业务流程，以在另一个表中插入记录，如果 ACCOUNTACTIVITY 表上的插入操作获取通知消息。 在这种情况下，您可以判定形状中的相应更改。  
  
## <a name="see-also"></a>请参阅  
 [接收 Oracle E-business Suite 数据库更改通知使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)