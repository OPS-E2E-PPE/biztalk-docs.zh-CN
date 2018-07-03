---
title: 使用存储的过程轮询 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e89dfe-f33a-436b-94c6-be78e84d5efd
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0301a571fba8e768052fa9caaf1465abd8aa162
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990910"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures"></a>轮询 Oracle E-business Suite 使用存储过程
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过使用存储的过程，若要连续轮询 Oracle 数据库接收定期的数据更改消息。 您可以指定存储的过程作为适配器执行定期轮询 Oracle 数据库的轮询语句。  

 若要启用轮询，必须指定 WCF 自定义或 WCF OracleEBS 的特定绑定属性接收端口。  有关如何在适配器支持轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。 轮询操作的 SOAP 消息结构的信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a>使用 Oracle E-business 适配器的绑定属性中配置轮询操作  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 必须指定配置 WCF 自定义或 WCF OracleEBS 时这些绑定属性接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  


|         绑定属性         |                                                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                                                       |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                                   指定是否想要执行**轮询**或**通知**的入站操作。 默认值是**轮询**。                                                                                                                                                                                                                    |
| **PolledDataAvailableStatement** |                                                                                                                                                       指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 仅当一条记录不可用，存储的过程为指定**PollingInput**将执行属性绑定。                                                                                                                                                       |
|       **PollingInterval**        |                                           指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将休眠的剩余时间间隔中。                                            |
|         **PollingInput**         | 指定的轮询语句。 若要轮询使用存储的过程，必须指定此绑定属性的整个请求消息。 请求消息必须向适配器发送用于调用存储的过程以出站操作的方式相同。 默认值为 null。<br /><br /> 必须指定的值**PollingInput**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。 |
|        **PollingAction**         |                                                                                                                                               指定轮询操作的操作。 您可以确定操作使用生成的元数据中的特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。                                                                                                                                               |
|      **PostPollStatement**       |                                                                                                                                                                                                            指定在指定的语句之后执行的语句块**PollingInput**执行绑定属性。                                                                                                                                                                                                             |
|      **PollWhileDataFound**      |                                                                               指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略的轮询间隔，连续执行轮询语句中，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。                                                                               |

 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]来轮询 Oracle 数据库，请阅读以下部分。  

## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何将[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持接收数据更改消息使用存储的过程，创建 BizTalk 项目并生成你想要使用来轮询 Oracle 数据库的存储过程的架构。 在本主题中，我们使用 GET_ACTIVITYS 存储过程轮询 ACCOUNTACTIVITY 表。 此存储的过程是与 ACCOUNT_PKG 包可用。 可以运行这些示例以在数据库中创建这些对象提供的 SQL 脚本。  

> [!NOTE]
>  此主题轮询 ACCOUNTACTIVITY 表，其中基本的数据库表创建示例运行提供的脚本中的业务流程。 若要轮询任何其他表，其中包括接口表本主题中所述，必须执行类似的过程。  

 为了演示轮询操作，我们执行以下操作：  

-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性，以确定其中表正在轮询一次 (ACCOUNTACTIVITY) 有任何数据。 在此示例中，可以设置为此绑定属性：  

    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  

     这可确保只有 ACCOUNTACTIVITY 表有某些记录时，适配器都将执行轮询语句。  

-   作为的一部分提供的请求消息来执行存储的过程，GET_ACTIVITYS， **PollingInput**属性绑定。 此存储的过程将检索 ACCOUNTACTIVITY 表中的所有行，并将从适配器获取响应消息。  

-   作为的一部分执行一个 PL/SQL 块**PostPollStatement**属性绑定。 此语句将所有数据从 ACCOUNTACTIVITY 表到另一个数据库表中。 一旦发生这种情况下, 一次**PollingInput**将执行，它将不提取任何数据，因此 GET_ACTIVITYS 存储过程将返回一个空响应消息。  

-   更多的数据添加到 ACCOUNTACTIVITY 表，直到你将继续获取空的响应消息。 因此，您必须重新填充的新记录所在 ACCOUNTACTIVITY 的表。 可以通过运行这些示例提供的 more_activity_data.sql 脚本执行操作。 在运行此脚本后下, 一个轮询操作将提取新记录插入到表。  

## <a name="how-to-receive-data-change-messages-from-oracle"></a>如何从 Oracle 接收数据更改消息  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及以下过程任务中所述[若要创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置的适配器轮询 Oracle 数据库使用的存储的过程，这些任务包括：  

1. 创建 BizTalk 项目，并生成要使用的轮询的存储过程的架构。  

2. 用于从 Oracle 数据库接收消息的 BizTalk 项目中创建一条消息。  

3. 创建业务流程从 Oracle 数据库接收消息并将其保存到的文件夹。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

   > [!IMPORTANT]
   >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用 BizTalk Adapter Pack 还提供的示例中，PollingUsingStoredProc，根据本主题。 有关详细信息，请参阅[示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。  

## <a name="generating-schema"></a>生成架构  
 必须生成 GET_ACTIVITYS 操作的架构。 执行以下任务，同时生成架构使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

- 选择作为协定类型**服务 （入站操作）**。  

- 生成架构**GET_ACTIVITYS**过程。  

  有关如何生成架构的详细信息，请参阅[浏览、 搜索和获取 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  

 对于本主题中，必须创建一条消息用于从 Oracle 接收消息。  

 执行以下步骤创建消息并将其链接到架构。  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1. 向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  

2. 如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

3. 在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  

4. 右键单击新创建的消息，然后依次**属性窗口**。  

5. 在中**属性**窗格**Message_1**，执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |Identifier|类型**接收**。|  
   |消息类型|从下拉列表中，展开**架构**，然后选择*Polling.OracleEBSBindingSchema*，其中*轮询*是 BizTalk 项目的名称。 *OracleEBSBindingSchema*是为生成的响应架构**GET_ACTIVITYS**存储过程。<br /><br /> **重要说明：** 由于轮询是一种方法的操作，适配器生成的架构不包含响应节点中，因此，没有只有一个根节点在架构中。 如果消息类型使用此类架构，则必须通过生成的架构的文件名标识架构。<br /><br /> 例如，如果创建双向操作的架构，架构中的节点文件的名称`OracleEBSBindingSchema`可能看起来像"请求"和"响应"。 如果你想要在业务流程映射到请求架构中创建一条消息，可以通过查找来确定在列表中的架构`OracleEBSBindingSchema.Request`。 但是，在执行轮询操作时，唯一的节点是"轮询"，因为它并不容易标识你想要映射到，因为单个节点包含以下架构： 不会作为列出的架构\<schemafilename\>。\<rootnodename\>。 相反，仅文件名，列出了此类架构。 在这种情况下，标识架构的唯一方法是按架构文件名，例如，OracleEBSBindingSchema。|  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为入站和出站操作 GET_ACTIVITYS 存储过程生成架构。 入站操作，必须使用该架构：  

   - 业务流程的一部分创建消息映射。  

   - 若要检索必须为指定的操作**PollingAction**属性绑定在运行时。  

     必须使用出站操作的架构来获取请求消息必须指定作为的一部分**PollingInput**属性绑定。  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]以便从 Oracle 接收基于轮询的数据更改消息。 在此业务流程，该适配器接收的响应通过执行您指定的请求消息的一部分的存储的过程**PollingInput**属性绑定。 存储过程的响应消息将保存到文件位置。 用于轮询 Oracle 数据库的典型业务流程将包含：  

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

|端口|属性|  
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
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  

  - 硬盘和相应的 BizTalk 业务流程将放置的位置将消息从 Oracle FILE 端口上定义的位置。 这些消息将以响应接收端口中指定的轮询语句。  

  - 定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。 此端口将轮询 Oracle 数据库。 有关如何创建接收端口，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 请确保指定的接收端口的以下绑定属性。  


    |         绑定属性         |                                                                                                                                                                                                                                                                                                                                                  ReplTest1                                                                                                                                                                                                                                                                                                                                                   |
    |----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     **InboundOperationType**     |                                                                                                                                                                                                                                                                                                                                         将此设置为**轮询**。                                                                                                                                                                                                                                                                                                                                         |
    | **PolledDataAvailableStatement** |                                                                                                                                                                                                                                    对于此示例中，此绑定属性设置为：<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> 这可确保只有 ACCOUNTACTIVITY 表有某些记录时，适配器都将执行轮询语句。                                                                                                                                                                                                                                    |
    |        **PollingAction**         |                                                                                                                                                                                                                                           轮询操作检索用于 GET_ACTIVITYS 过程的入站消息生成的架构。 对于此示例中，此绑定属性设置为**PollingPackageApis/应用/ACCOUNT_PKG/GET_ACTIVITYS**。                                                                                                                                                                                                                                           |
    |         **PollingInput**         | 对于此绑定属性，指定要调用 GET_ACTIVITYS 的请求消息存储过程。 您可以从架构获取请求消息生成的出站操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 您必须为此绑定属性作为输入提供整个 XML 消息。 对于此示例中，此绑定属性设置为：<br /><br /> `<GET_ACTIVITYS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG">   <INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS> </GET_ACTIVITYS>`<br /><br /> GET_ACTIVITYS 存储过程采用输入的 REF CURSOR 作为参数。 |
    |      **PostPollStatement**       |                                                                                                                                                                                                                                                  指定要将所有数据从 ACCOUNTACTIVITY 表都移到另一个表的轮询后语句。 对于此示例中，此绑定属性设置为：<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`                                                                                                                                                                                                                                                  |

     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  

    > [!IMPORTANT]
    >  如果轮询接口表，则必须通过指定必要的绑定属性来设置应用程序上下文。 有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
    > 
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 您为此，可添加服务行为配置 WCF 自定义时或 WCF OracleEBS 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动轮询 Oracle 数据库的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。

 在此阶段，请确保：  

-   WCF 自定义或 WCF OracleEBS 单向接收端口，轮询 Oracle 使用为指定的存储的过程**PollingInput**绑定属性，正在运行。  

-   FILE 发送端口，从 Oracle 数据库接收消息，正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，以下组操作需要置于相同的序列：  

-   适配器将执行**PolledDataAvailableStatement**这会返回正值，指示要执行的语句为指定的适配器**PollingInput**属性绑定。  

-   适配器将执行为指定的 GET_ACTIVITYS 存储过程**PollingInput** ACCOUNTACTIVITY 表中的绑定属性，并返回所有行。 从 Oracle 数据库的响应类似于以下内容：  

    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <GET_ACTIVITYS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG">  
      <OUTRECS>  
        <OUTRECSRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ReferencedRecordTypes/APPS/ACCOUNT_PKG/GET_ACTIVITYS/APPS/GET_ACTIVITYS">  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </OUTRECSRecord>  
        <OUTRECSRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ReferencedRecordTypes/APPS/ACCOUNT_PKG/GET_ACTIVITYS/APPS/GET_ACTIVITYS">  
          ......  
          ......   
        </OUTRECSRecord>  
        ......  
        ......  
      </OUTRECS>  
    </GET_ACTIVITYS>  
    ```  

-   适配器执行轮询后语句，后者将所有数据从 ACCOUNTACTIVITY 表都移动到另一个表。  

-   轮询间隔后，适配器再次执行**PolledDataAvailableStatement**。 因为 ACCOUNTACTIVITY 表现在，有没有记录**PolledDataAvailableStatement**不会返回正值，因此该适配器不会执行该语句为指定**PollingInput**绑定属性。 因此，适配器客户端不会获取任何轮询消息。  

-   适配器客户端不会获得更多轮询消息，直到显式向 ACCOUNTACTIVITY 表中插入一些记录。 要插入更多的记录，可以运行这些示例提供的 more_activity_data.sql 脚本。 在运行此脚本中下, 一次后**PolledDataAvailableStatement**是执行，它会返回正值。 因此，适配器将执行轮询语句和适配器客户端再次接收轮询消息。  

> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。  

## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)