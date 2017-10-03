---
title: "使用 BizTalk Server 的 Oracle 数据库中运行 SQLEXECUTE 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operation, performing by using BizTalk Server
- SQLEXECUTE operation
ms.assetid: 7fdd1ead-0bf0-46cf-86fc-db513f76f6b3
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa982b938fc4fcb9096ca30209938b3b635d9fb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-biztalk-server"></a>使用 BizTalk Server 的 Oracle 数据库中运行 SQLEXECUTE 操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使客户端能够在 Oracle 数据库上运行参数化的 SQL 语句。 若要支持此类操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现 SQLEXECUTE 操作。 SQLEXECUTE 操作支持组成使你可以执行一次为每个集的相同 SQL 语句的参数集的输入的参数块。 SQLEXECUTE 操作返回泛型记录集内的 SQL 语句的结果。 有关操作的详细信息，请参阅[Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。 有关 SQLEXECUTE 操作的 SOAP 消息结构的信息，请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。  
  
## <a name="how-to-perform-a-sqlexecute-operation-on-an-oracle-database"></a>如何执行对 Oracle 数据库的 SQLEXECUTE 操作？  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要执行 SQLEXECUTE 操作，这些任务包括：  
  
1.  创建 BizTalk 项目和 SQLEXECUTE 操作生成架构。 在根节点 （/） 下显示 SQLEXECUTE 操作**选择类别**窗格中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
2.  在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程以调用在 Oracle 数据库表或视图上的操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SqlExec，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，来演示如何运行参数化的 SQL 查询中，我们将生成 SQLEXECUTE 操作可在根节点 （/） 中的架构**选择类别**窗格中的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您生成第一步中的邮件从 BizTalk 项目的业务流程视图窗口的架构。  
  
 对于本主题中，你必须创建两条消息，另一个用于将请求发送到 Oracle 数据库，另一个用于接收响应。  
  
 执行以下步骤以创建消息并将它们链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SqlExec.OracleDBBindingSchema.SQLEXECUTE*，其中*SqlExec*是 BizTalk 项目的名称。 *OracleDBBindingSchema*是为 SQLEXECUTE 操作生成的架构。|  
  
5.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SqlExec.OracleDBBindingSchema.SQLEXECUTEResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于运行参数化的 SQL 查询使用 SQLEXECUTE 操作。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息，并通过 ODP 将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 将包含 SQLEXECUTE 上执行操作 Oracle 数据库典型业务流程：  
  
-   发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
-   单向接收端口接收请求消息发送到 Oracle 数据库。  
  
-   双向发送端口发送请求消息到 Oracle 数据库和接收响应。  
  
-   单向发送端口将响应从 Oracle 数据库发送到的文件夹。  
  
 SQLEXECUTE 操作示例业务流程如下所示：  
  
 ![业务流程，以调用 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/media/bdb47660-6013-46f7-aa4b-fe5eb83f3a1e.gif "bdb47660-6013-46f7-aa4b-fe5eb83f3a1e")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|文件|-将设置**标识符**到*文件*<br />-将设置**类型**到*FileInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|SaveResponse|-将设置**标识符**到*SaveResponse*<br />-将设置**类型**到*SaveResponseType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>对于操作形状，指定消息并将其连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*FileIn.SQLEXECUTE.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.SQLEXECUTE.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.SQLEXECUTE.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse.SQLEXECUTE.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库。 你必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 WCF OracleDB 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序执行 SQLEXECUTE 操作。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须符合你先前生成 SQLEXECUTE 操作的架构。 业务流程使用该消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。 请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)有关调用 SQLEXECUTE 操作的请求消息架构的详细信息。  
  
 因为 SQLEXECUTE 操作不显示在任何 Oracle 数据库项目下，你可以使用相同的架构在视图上执行参数化的 SQL 查询或者某些其他表执行操作的过程。  
  
 例如，下面的请求消息使用 SQLEXECUTE 操作帐户表上执行参数化的 SELECT 语句。 帐户表 SCOTT 架构下创建通过运行这些示例提供的 SQL 脚本。 若要了解有关这些示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
```  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLSTATEMENT>select * from ACCOUNT where ACCTID=:num</SQLSTATEMENT>  
  <PARAMETERSCHEMA>num number</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <PARAMETER>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">100000</string>  
      </PARAMETER>  
    </PARAMETERDATA>  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 来自 Oracle 数据库以实现更高版本的请求消息的响应是：  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<SQLEXECUTEResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLEXECUTEResult>  
    <GenRecordRow xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>ACCTID</ColumnName>   
          <ColumnValue>100000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>NAME</ColumnName>   
          <ColumnValue>Kim Ralls</ColumnValue>   
          <ColumnType>System.String</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>BALANCE</ColumnName>   
          <ColumnValue>10000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
      </GenRecordColumn>  
    </GenRecordRow>  
  </SQLEXECUTEResult>  
</SQLEXECUTEResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到时执行 DML 操作使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)