---
title: "调用重载函数和 Oracle 数据库使用 BizTalk Server 中的过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: overloaded functions and procedures, invoking by using BizTalk Server
ms.assetid: a3d76361-6b0c-415a-b4f9-31939abfdc36
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d036313a69025e7fcf0e37116fc729623ac782
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server"></a>调用重载函数和 Oracle 数据库使用 BizTalk Server 中的过程
存储的过程和函数可以进行重载 Oracle 数据库中。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持重载函数和过程的更改操作的目标命名空间。 例如，两个重载过程的消息结构如下所示：  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
 调用重载的函数时所需要的 SOAP 消息结构和 SOAP 操作或过程是类似于调用的函数和过程，在所述[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)。  
  
 调用重载的过程是类似于调用任何其他函数中所述[调用函数和 Oracle 数据库使用 BizTalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。 若要区分重载函数，但是[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将是唯一的字符串追加到的节点 ID 和它会显示为重载项目的命名空间。 此字符串为"overload1"的第一个重载，"overload2"下一步重载中，依次类推。  
  
## <a name="how-to-invoke-overloaded-functions-and-procedures"></a>如何调用重载的函数和过程？  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要调用的 Oracle 数据库中的函数，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成你想要在 Oracle 数据库中调用的重载函数的架构。  
  
2.  在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。 你必须创建每个重载的消息。  
  
3.  创建业务流程来调用重载的函数的 Oracle 数据库中。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，InvokeOverloadedProc，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，来演示如何调用的重载的函数或过程，我们将调用下 SCOTT\Package\ACCOUNT_PKG 架构 GET_ACCOUNT 过程。 通过运行这些示例提供的 SQL 脚本在 SCOTT 架构下创建此包。 这是重载的过程其中：  
  
-   一个重载采用作为 IN 参数的帐户 ID，并作为输出参数返回了帐户 %rowtype。  
  
-   第二个重载采用作为 IN 参数的帐户名称，并返回了帐户 %rowtype 作为输出参数。  
  
 若要了解有关这些示例和 SQL 脚本的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 若要调用重载的函数，我们生成这两个重载过程，GET_ACCOUNT.1 和 GET_ACCOUNT.2 架构。 请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您生成第一步中的邮件从 BizTalk 项目的业务流程视图窗口的架构。  
  
 对于本主题中，你必须创建两个请求-响应消息集-一个请求-响应设置为第一个重载过程和第二个请求-响应设置为第二个重载过程。  
  
 执行以下步骤以创建消息并将它们链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNT*，其中*InvokeOverloadedProc*是的名称你的 BizTalk 项目。 *OracleDBBindingSchema*是为 GET_ACCOUNT 过程生成的架构。|  
  
5.  重复上述步骤以创建三个详细消息。 在**属性**窗格中是否有新消息，执行以下操作：  
  
    |设置为标识符|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |响应|*InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNTResponse*|  
    |次数 2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNT*|  
    |Response2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNTResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用重载的过程 Oracle 数据库中。 此业务流程中放置两个请求消息，一个对应于每个重载过程，在定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用消息，并通过 ODP 将它们传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。  
  
 业务流程同时选取两个请求，因为你需要包括并行操作形状中业务流程。 对于每个并行操作，必须包括发送和接收形状来将消息发送到 Oracle 数据库和接收响应。 但是，你可以使用相同的端口用于发送和接收两个操作的消息。 将包含同时调用重载的过程典型业务流程：  
  
-   发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
-   单向接收端口接收请求消息发送到 Oracle 数据库。  
  
-   双向发送端口发送请求消息到 Oracle 数据库和接收响应。  
  
-   单向发送端口将响应从 Oracle 数据库发送到的文件夹。  
  
 要调用 GET_ACCOUNT 过程的第一个和第二个重载示例业务流程如下所示：  
  
 ![业务流程调用重载包](../../adapters-and-accelerators/adapter-oracle-database/media/f8e4ad6f-9140-43b1-b931-28c9ba11cc8e.gif "f8e4ad6f-9140-43b1-b931-28c9ba11cc8e")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。 下表列出了你必须将包含并行操作之一的形状。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
 下表列出了你必须将包含其他并行操作的形状。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-将设置**名称**到*ReceiveMessage2*<br />-将设置**激活**到*True*|  
|SendMessage2|Send|-将设置**名称**到*SendMessage2*|  
|ReceiveResponse2|Receive|-将设置**名称**到*ReceiveResponse2*<br />-将设置**激活**到*False*|  
|SendResponse2|Send|-将设置**名称**到*SendResponse2*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|文件|-将设置**标识符**到*文件*<br />-将设置**类型**到*FileInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|SaveResponse|-将设置**标识符**到*SaveResponse*<br />-将设置**类型**到*SaveResponseType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
 因为你将处理这两个请求和响应消息使用这些端口，你必须创建每个端口，其中每个操作对应于一种消息类型的两个操作。 若要创建一个操作，请右击端口形状，，然后选择**新操作**。 名称为每个端口的第一个操作**Overload1**和每个端口作为第二个操作**Overload2**。  
  
### <a name="using-correlation"></a>使用相关  
 相关是将传入消息与业务流程的相应实例相匹配的过程。 业务流程将删除你在两个请求消息，另一个用于每个重载。 要使用相关，与右业务流程关联的请求消息。 有关相关的详细信息，请参阅[在业务流程中使用相关性](../../core/using-correlations-in-orchestrations.md)。  
  
##### <a name="to-use-correlations"></a>若要使用的相关性  
  
1.  将属性提升从为每个重载函数生成的架构。 例如，将从第一个重载; 的架构提升辅助设备属性将从第二个重载的架构提升 ANAME 属性。 若要提升一个属性，右键单击该属性在架构视图中的，依次指向**Promote**，然后选择**快速升级**。 这将 PropertySchema.xsd 文件添加到你的 BizTalk 项目。  
  
     有关将升级属性的信息，请参阅[提升属性](../../core/promoting-properties.md)。  
  
2.  从 Orchestration 视图中，右键单击**相关性类型**，然后选择**新相关类型**。  
  
3.  **相关性属性**对话框将列出你在步骤 1 中提升的属性。 选择一个属性，然后单击**添加**。  
  
4.  单击 **“确定”**。  
  
5.  若要创建其他升级属性的相关类型，请重复这些步骤。  
  
6.  重命名基于到是对与其关联的属性的相关类型。 你可以重命名的相关类型*CorrelationType_AID* （对于帮助属性中） 和*CorrelationType_ANAME* （对于 ANAME 属性中）。  
  
7.  从 Orchestration 视图中，右键单击**关联集**，然后选择**新关联集**。  
  
8.  右键单击新添加的关联集，并依次**属性**。 在“属性”窗格中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*InvokeOverloadedProc.CorrelationType_AID*|  
    |Identifier|*Correlation_AID*|  
  
9. 添加另一个关联集，并指定属性窗格中的以下属性。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*InvokeOverloadedProc.CorrelationType_ANAME*|  
    |Identifier|*Correlation_ANAME*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>对于操作形状，指定消息并将其连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**初始化相关集**到*Correlation_AID*<br />-将设置**消息**到*请求*<br />-将设置**操作**到*FileIn.Overload1.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.Overload1.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.Overload1.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse.Overload1.Request*|  
|ReceiveMessage2|-将设置**初始化相关集**到*Correlation_ANAME*<br />-将设置**消息**到*次数 2*<br />-将设置**操作**到*FileIn.Overload2.Request*|  
|SendMessage2|-将设置**消息**到*次数 2*<br />-将设置**操作**到*LOBPort.Overload2.Request*|  
|ReceiveResponse2|-将设置**消息**到*Response2*<br />-将设置**操作**到*LOBPort.Overload2.Response*|  
|SendResponse2|-将设置**消息**到*Response2*<br />-将设置**操作**到*SaveResponse.Overload2.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和将的请求消息，另一个用于每个重载过程放置位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置响应消息，另一个用于每个重载的过程，其中包含从 Oracle 数据库响应的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库。 你必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 WCF OracleDB 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 由于 WCF 自定义或 WCF OracleDB 发送端口发送和接收符合到多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。 适用于此业务流程，应将操作设置，如下所示：  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Overload1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1" />  
          <Operation Name="Overload2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2" />  
        </BtsActionMapping>  
        ```  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动的 BizTalk 应用程序调用一个 Oracle 数据库表中的函数。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，你必须删除两个文件 （一个用于每个重载过程） 消息接收位置的请求。 请求消息的架构必须符合你先前生成的过程的架构。 请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)为调用的请求消息架构有关的详细信息函数使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 例如，要调用 GET_ACCOUNT 过程的第一个重载的请求消息是：  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
  <AID>100001</AID>  
</GET_ACCOUNT>  
```  
  
 同样，要调用 GET_ACCOUNT 过程的第二个重载的请求消息是：  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2">  
  <ANAME>Mindy Martin</ANAME>  
</GET_ACCOUNT>  
```  
  
 第一个请求消息时，将调用 GET_ACCOUNT 过程以检索帐户 id 等于 100020 的记录。 第二个请求消息时，将调用 GET_ACCOUNT 过程，若要检索具有帐户名称为"John Smith"的记录。  
  
 业务流程使用请求消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。 例如，调用第一个重载的过程的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
 <ACCT>  
  <ACCTID>100001</ACCTID>  
  <NAME>Ty Carlson</NAME>  
  <BALANCE>9000</BALANCE>  
 </ACCT>  
</GET_ACCOUNTResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到调用重载使用的包时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[对开发 BizTalk 应用程序与 Oracle 数据库的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)