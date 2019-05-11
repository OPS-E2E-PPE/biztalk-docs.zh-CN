---
title: 使用 Oracle 数据库中的大型对象数据类型运行对表的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing on tables
- operations, performing on LOB data
ms.assetid: 74276b85-daf1-4d0f-92f9-46d5c27a95a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407c161590753a1d6d31b03f1b97eb86ddb58723
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376340"
---
# <a name="run-operations-on-tables-with-large-object-data-types-in-oracle-database"></a>使用 Oracle 数据库中的大型对象数据类型运行对表的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]对 Oracle 大型对象 (LOB) 数据类型提供支持：  

- 二进制大型对象 (BLOB)  

- 字符大型对象 (CLOB)  

- 国家/地区字符大型对象 (NCLOB)  

- 二进制文件 (BFILE)。 有关详细信息，请参阅[对包含 BFILE 数据类型，请使用 BizTalk Server 的 Oracle 数据库中的表执行操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)。  

  [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为包含 LOB 列的表的 ReadLOB 和 UpdateLOB 操作为此目的。 有关这些操作的详细信息请参阅[对表和视图，包含 LOB 数据在 Oracle 数据库中操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)。 有关调用这些操作的 SOAP 消息的结构的详细信息，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)。  

> [!NOTE]
>  使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，ReadLOB 操作不支持从 Oracle 数据库的流式处理 LOB 类型数据。 将数据从 Oracle 数据库使用的流式传输 LOB[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应改为使用选择的操作。 有关流式处理的详细信息，请参阅[Oracle 数据库中的 LOB 数据类型的流式处理支持](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)。 此外，从 Oracle 数据库 ReadLOB 操作响应将失败 WSDL 的验证。 了解如何解决失败，请参阅[故障排除操作问题](https://msdn.microsoft.com/library/dd787883.aspx)。  

## <a name="how-to-perform-operations-on-lob-data"></a>如何对 LOB 数据执行操作？  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[构建基块来开发 BizTalk 应用程序与 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要调用 ReadLOB 和 UpdateLOB Oracle 数据库中的表操作，这些任务包括：  

1. 创建 BizTalk 项目，并为 ReadLOB 和 UpdateLOB 操作生成架构。  

2. 在 BizTalk 项目中为发送和接收消息从 Oracle 数据库创建消息。 必须创建用于发送请求和接收针对这两个操作的响应消息。  

3. 创建一个业务流程调用 ReadLOB 和 UpdateLOB 操作。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，Operate_LOB，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  

## <a name="generating-schema"></a>生成架构  
 在本主题中，若要演示如何执行 ReadLOB 和 UpdateLOB 操作，我们将生成的 Oracle 数据库中的 SCOTT 架构下的客户表显示这些操作的元数据。 通过运行这些示例提供的 SQL 脚本在 SCOTT 架构下创建此表。 若要了解有关这些示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图窗口。  

 对于本主题中，您必须创建两个请求-响应消息集 — ReadLOB 操作和第二个请求的响应为 UpdateLOB 操作设置的一个请求-响应设置。  

 执行以下步骤来创建消息并将其链接到该架构。  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1. 如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

2. 在业务流程视图中，右键单击**消息**，然后单击**新消息**。  

3. 右键单击新创建的消息，然后依次**属性窗口**。  

4. 在中**属性**窗格**Message_1**，执行以下操作：  


   |   使用此选项   |                                                                                                                                       执行的操作                                                                                                                                       |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  Identifier  |                                                                                                                                   类型**请求**。                                                                                                                                    |
   | 消息类型 | 从下拉列表中，展开**架构**，然后选择*Operate_LOB。OracleDBBindingSchema.ReadLOB*<em>，</em>其中*Operate_LOB*是 BizTalk 项目的名称。 *OracleDBBindingSchema*是对 CUSTOMER 表的 ReadLOB 和 UpdateLOB 操作生成的架构。 |


5. 重复上述步骤创建三个更多的消息。 在中**属性**窗格中的新消息，执行以下操作：  

   |将标识符设置为|将消息类型设置为|  
   |-----------------------|-------------------------|  
   |响应|*Operate_LOB.OracleDBBindingSchema.ReadLOBResponse*|  
   |请求 2|*Operate_LOB.OracleDBBindingSchema.UpdateLOB*|  
   |Response2|*Operate_LOB.OracleDBBindingSchema.UpdateLOBResponse*|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用 ReadLOB 和 UpdateLOB 对表的操作。 在此业务流程，则删除两个请求消息，一个用于 ReadLOB 操作，另一个用于 UpdateLOB 操作。 这些消息的接收位置将被删除。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息并通过 ODP 将它们传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。  

 因为业务流程提取两个请求的同时，您需要在业务流程中包括并行操作形状。 对于每个并行操作，必须包括发送和接收形状来将消息发送到 Oracle 数据库和接收响应。 但是，您可以使用相同的端口来发送和接收这两种操作的消息。 将包含一个典型的业务流程的同时执行的 ReadLOB 和 UpdateLOB 操作：  

- 发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  

- 一个单向接收端口接收请求消息将发送到 Oracle 数据库。  

- 一个双向发送端口以发送请求消息到 Oracle 数据库和接收响应。  

- 一个单向发送端口用于从 Oracle 数据库将响应发送到的文件夹。  

  示例业务流程如下所示：  

  ![用于读取和更新 LOB 数据的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/6523b5e4-3689-433a-8287-eebc36f10442.gif "6523b5e4-3689-433a-8287-eebc36f10442")  

### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。 下表列出了必须包括一个并行操作形状。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  

 下表列出了你必须将包含其他并行操作形状。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-设置**名称**到*ReceiveMessage2*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage2|Send|-设置**名称**到*SendMessage2*|  
|ReceiveResponse2|Receive|-设置**名称**到*ReceiveResponse2*<br />-设置**激活**到*False*|  
|SendResponse2|Send|-设置**名称**到*SendResponse2*|  

### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  

|Port|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br />-设置**类型**到*SaveResponseType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  

 因为您将处理这两个请求和响应消息使用这些端口，则必须创建每个端口，其中每个操作对应于一种消息类型的两个操作。 要创建一个操作，端口形状中，右键单击，然后选择**新的操作**。 命名为每个端口的第一个操作**ReadLOB**并为每个端口的第二个操作**UpdateLOB**。  

### <a name="using-correlation"></a>使用相关  
 相关是将传入消息与业务流程的相应实例相匹配的过程。 将删除您在业务流程中两个请求消息，一个用于每个重载。 要使用相关，与正确的业务流程关联的请求消息。 有关相关的详细信息，请参阅[业务流程中使用相关性](../../core/using-correlations-in-orchestrations.md)。  

##### <a name="to-use-correlations"></a>若要使用的相关性  

1.  从每个操作生成的架构升级属性。 例如，从 ReadLOB 操作架构; 升级 LOB_COLUMN 属性将筛选器属性提升从 UpdateLOB 操作架构。 若要将属性升级，右键单击架构视图中的属性，指向**Promote**，然后选择**快速升级**。 这将 PropertySchema.xsd 文件添加到您的 BizTalk 项目。  

     有关提升的属性的信息，请参阅[升级属性](../../core/promoting-properties.md)。  

2.  从业务流程视图中，右键单击**相关类型**，然后选择**新相关类型**。  

3.  **相关性属性**对话框会列出升级在步骤 1 中的属性。 选择一个属性，然后依次**添加**。  

4.  单击“确定” 。  

5.  若要创建其他升级属性的相关类型，请重复这些步骤。  

6.  重命名基于与之关联的操作的相关类型。 你可以重命名为相关类型*CorrelationType_ReadLOB* （适用于 ReadLOB 操作） 和*CorrelationType_UpdateLOB* （适用于 UpdateLOB 操作）。  

7.  从业务流程视图中，右键单击**相关集**，然后选择**新建相关集**。  

8.  右键单击新添加的相关集，然后依次**属性**。 在中**属性**窗格中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*Operate_LOB.CorrelationType_ReadLOB*|  
    |Identifier|*Correlation_ReadLOB*|  

9. 添加另一个相关集，并指定属性窗格的以下属性。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*Operate_LOB.CorrelationType_UpdateLOB*|  
    |Identifier|*Correlation_UpdateLOB*|  

## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定的属性和它们应设置为指定操作形状的消息并将其链接到的端口的值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  

|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**初始化相关集**到*Correlation_ReadLOB*<br />-设置**消息**到*请求*<br />-设置**操作**到*FileIn.ReadLOB.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.ReadLOB.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.ReadLOB.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.ReadLOB.Request*|  
|ReceiveMessage2|-设置**初始化相关集**到*Correlation_UpdateLOB*<br />-设置**消息**到*请求 2*<br />-设置**操作**到*FileIn.UpdateLOB.Request*|  
|SendMessage2|-设置**消息**到*请求 2*<br />-设置**操作**到*LOBPort.UpdateLOB.Request*|  
|ReceiveResponse2|-设置**消息**到*Response2*<br />-设置**操作**到*LOBPort.UpdateLOB.Response*|  
|SendResponse2|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.UpdateLOB.Request*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  

  - 硬盘和相应的文件端口请求消息，分别对应于 ReadLOB 和 UpdateLOB 操作放置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  

  - 硬盘和相应的 BizTalk 业务流程放置响应消息，一个用于每个操作，其中包含从 Oracle 数据库的响应的位置的文件端口上定义的位置。  

  - 定义一个物理 WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库。 您必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 Wcf-oracledb 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 由于 WCF 自定义或 Wcf-oracledb 发送端口发送和接收符合多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。 对于此业务流程，应将操作设置，如下所示：  

    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="ReadLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB" />  
      <Operation Name="UpdateLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB" />  
    </BtsActionMapping>  
    ```  

    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动 Oracle 数据库上执行操作的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   文件接收端口接收请求消息的业务流程正在运行。  

-   运行文件发送端口以接收来自业务流程的响应消息。  

-   WCF 自定义发送端口或 Wcf-oracledb 将消息发送到 Oracle 数据库正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须删除的文件的消息的接收位置的请求。 请求消息的架构必须符合前面生成的操作的架构。 请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)详细了解针对 LOB 数据类型使用调用操作的请求消息架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  

 业务流程使用的请求消息并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置。  

 对于此业务流程，我们先删除 UpdateLOB 操作来更新客户表的照片列 （的 BLOB 数据类型） 的请求消息。 请求消息以调用特定客户的 PHOTO 列更新为：  

```  
<UpdateLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>Name='Mindy Martin'</FILTER>  
  <Stream>YWJjZA==</Stream>  
</UpdateLOB>  
```  

> [!NOTE]
>  筛选器字符串必须始终提取一个匹配行否则 XmlReaderParsingException Oracle 数据库适配器引发。 值为\<Stream\>元素必须为 base64Binary 类型。  

 UpdateLOB 操作的响应是：  

```  
<?xml version="1.0" encoding="utf-8"?>  
<UpdateLOBResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER"></UpdateLOBResponse>  
```  

 我们现在删除 ReadLOB 操作读取 UpdateLOB 操作已更新的数据的请求消息。 要调用特定客户的 PHOTO 列 ReadLOB 操作的请求消息是：  

```  
<ReadLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>NAME='Mindy Martin'</FILTER>  
</ReadLOB>  
```  

> [!NOTE]
>  筛选器字符串始终必须获取一个匹配行。 如果多个匹配行，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]只返回第一个 （匹配） 行的 LOB 列。  

 ReadLOB 操作的响应是：  

```  
<?xml version="1.0" encoding="utf-8"?>  
<ReadLOBResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <ReadLOBResult>YWJjZA==</ReadLOBResult>  
</ReadLOBResponse>  
```  

> [!NOTE]
>  ReadLOB 操作的响应可能会失败，以对 WSDL 进行验证。 必须执行某些任务来验证对 WSDL ReadLOB。 有关详细信息请参阅[故障排除操作问题](https://msdn.microsoft.com/library/dd787883.aspx)。  

## <a name="possible-exceptions"></a>可能的异常  
 对包含 LOB 数据使用表执行操作时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  

## <a name="see-also"></a>请参阅  
[向开发 BizTalk 应用程序与 Oracle 数据库的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)