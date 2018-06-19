---
title: 调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures with REF CURSORS, invoking by using BizTalk Server
- functions and procedures with RECORD types, invoking by using BizTalk Server
- REF CURSORS
- RECORD types
ms.assetid: 5e84b8d3-6352-4911-93f9-5d455ff579d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9072f3df5c85ed09c5efbdc5e690a8eccc97b2f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967475"
---
# <a name="invoke-functions-and-procedures-with-ref-cursors-in-oracle-database-using-biztalk-server"></a>调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR
REF CURSOR 是表示指向服务器端结果集通过执行查询生成的指针的 PL/SQL 数据类型。 REF CURSOR 类型使输入和输出流的数据非常适合传输大量数据传入和传出的 PL/SQL 代码。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供支持强类型和弱类型 (SYS_REFCURSOR) REF Cursor，可在缩小，传递给 PL/SQL 过程和函数中或在 OUT 参数。 有关详细信息，如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持 REF Cursor，请参阅[函数和过程与 REF CURSOR 参数上的操作](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)。 REF CURSOR 的 XML 结构的信息，请参阅[REF CURSOR 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>如何在 Oracle 数据库中调用函数？  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要调用作为 in 参数接受 REF CURSOR 并作为输出参数提供 REF CURSOR 的 Oracle 数据库中的函数，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成你想要在 Oracle 数据库中调用的函数的架构。  
  
2.  在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程来调用该函数的 Oracle 数据库中。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，Func_RefCursor，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在此主题中，以演示如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持调用带 REF CURSOR 参数函数，我们将调用 GET_ACTIVITY 过程。 此过程使用弱类型在 REF CURSOR 和强类型 IN 出 REF CURSOR 作为参数。 该函数返回的状态，弱类型出 REF CURSOR 和强类型 IN 出 REF CURSOR。 GET_ACTIVITY 过程可通过运行这些示例提供的 SQL 脚本创建 ACCOUNT_PKG 的一部分。 若要了解有关这些示例和 SQL 脚本的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 因此，若要调用 GET_ACTIVITY 过程，我们生成架构 SCOTT\Package\ACCOUNT_PKG 架构在相同的过程。 请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您生成第一步中的邮件从 BizTalk 项目的业务流程视图窗口的架构。  
  
 对于本主题中，你必须创建两条消息，另一个用于将请求发送到 Oracle 数据库，另一个用于接收响应。  
  
 执行以下步骤以创建消息并将它们链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Func_RefCursor.OracleDBBindingSchema.GET_ACTIVITY*，其中*Func_RefCursor*是你的 BizTalk 的名称项目。 *OracleDBBindingSchema*是为 GET_ACTIVITY 过程生成的架构。|  
  
5.  重复上述步骤以创建新的消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|*Func_RefCursor.OracleDBBindingSchema.GET_ACTIVITYResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用带 REF CURSOR 参数的过程。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息，并通过 ODP 将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 调用函数和过程与 REF Cursor 典型业务流程会包含：  
  
-   发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
-   单向接收端口接收请求消息发送到 Oracle 数据库。  
  
-   双向发送端口发送请求消息到 Oracle 数据库和接收响应。  
  
-   单向发送端口将响应从 Oracle 数据库发送到的文件夹。  
  
 示例业务流程如下所示：  
  
 ![在 Oracle 中使用 Ref Cursor 的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/41ed9647-a49d-4122-b9fc-c5ce4dca3533.gif "41ed9647-a49d-4122-b9fc-c5ce4dca3533")  
  
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
 下表指定属性应设置为指定操作形状的消息并将它们链接到端口及其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*FileIn.REFCURSOR.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.REFCURSOR.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.REFCURSOR.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse.REFCURSOR.Request*|  
  
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
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置使用端口绑定到 Oracle 数据库的文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动的 BizTalk 应用程序调用一个 Oracle 数据库表中的过程。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须符合你先前生成的过程的架构。 请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)为调用的请求消息架构有关的详细信息函数使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 若要调用 GET_ACTIVITY 过程，必须指定弱类型在 REF CURSOR 和强类型 IN 出 REF CURSOR 作为参数。 因此，要调用此过程的请求消息是：  
  
```  
<GET_ACTIVITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <INRECS>BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;</INRECS>  
  <INOUTRECS_IN>BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;</INOUTRECS_IN>  
</GET_ACTIVITY>  
```  
  
 业务流程使用请求消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。  
  
 以上的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GET_ACTIVITYResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <STATUS>5</STATUS>   
  <INOUTRECS>  
    <INOUTRECSRECORD xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY">  
      <TID>1</TID>   
      <ACCOUNT>100001</ACCOUNT>   
      <AMOUNT>500</AMOUNT>   
      <DESCRIPTION />   
      <TRANSDATE>2007-10-16T16:58:44</TRANSDATE>   
      <PROCESSED>n</PROCESSED>   
    </INOUTRECSRECORD>  
    <INOUTRECSRECORD xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY">  
      .....   
      .....   
    </INOUTRECSRECORD>  
    ....  
    ....  
  </INOUTRECS>  
  <OUTRECS>  
    <GenRecordRow xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>TID</ColumnName>   
          <ColumnValue>1</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          ....   
        </GenRecordColumn>  
        .....  
        .....  
      </GenRecordColumn>  
    </GenRecordRow>  
    <GenRecordRow xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      .....  
      .....  
    </GenRecordRow>  
    .....  
    .....  
  </OUTRECS>  
</GET_ACTIVITYResponse>  
```  
  
 请注意，响应包含状态、 弱类型出 REF CURSOR 和强类型 IN 出 REF CUROSR。  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到时调用函数和过程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
 [开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)