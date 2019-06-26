---
title: 在 SAP 中使用 BizTalk Server 运行 BAPI 事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ff5cf7-5e98-4d74-a13f-4de65c215d41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21e0a04d9e35b900dab5d32d21abfba6bf3a8c03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373012"
---
# <a name="run-bapi-transactions-in-sap-using-biztalk-server"></a>在 SAP 中使用 BizTalk Server 运行 BAPI 事务
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端能够使用在 SAP 系统上执行事务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 创建一个事务的业务流程之前, 必须先了解可在其中执行事务的基本方案。 在典型的事务方案中，多个操作 （如调用 BAPI） 的请求消息发送到 SAP 系统。 这会将称为"操作消息"。 业务流程必须从请求消息中提取每个操作消息，并将各个操作消息发送到 SAP 系统。 业务流程向他们发送一次是在另一个使用相同的连接。 业务流程使用通过 BizTalk 映射的 XML 转换中提取各个消息从"操作消息"。  
  
 执行完操作后，业务流程必须提交或中止事务通过分别为 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK，发送消息。 这些将被称为"事务消息。"  
  
## <a name="how-does-the-adapter-enable-transactions-through-biztalk-server"></a>适配器如何启用事务通过 BizTalk Server？  
 若要启用 SAP 系统使用的事务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- 提供消息上下文属性打开、 关闭、 重用和中止。  
  
- 使用 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 来提交或中止操作。 这些字段公开由 SAP 系统。  
  
  下表列出了一些指导原则上 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 中使用属性：  
  
|消息|OPEN|重复使用|CLOSE|ABORT|  
|-------------|----------|-----------|-----------|-----------|  
|第一条消息 （操作消息）|是|否|否|否|  
|随后的消息 （操作消息）|否|是|否|否|  
|BAPI_TRANSACTION_COMMIT （事务消息）|否|否|是|否|  
|BAPI_TRANSACTION_ROLLBACK （事务消息）|否|否|是|是|  
  
 在表中，"是"表示要用于消息的消息上下文属性。 同样，"否"表示的消息上下文属性不与消息一起使用。  
  
 若要汇总表：  
  
-   第一条消息必须始终为操作消息，并且必须仅使用打开属性。  
  
-   后续操作消息必须使用重复使用属性。  
  
-   对应于 BAPI_TRANSACTION_COMMIT 的提交事务的事务消息必须使用关闭属性。  
  
-   对应于 BAPI_TRANSACTION_ROLLBACK 中止事务的事务消息可以使用关闭或中止的属性。 如果使用的中止，理想情况下消息必须在业务流程异常块中。  
  
## <a name="key-considerations-related-to-transactions-using-biztalk-server"></a>使用 BizTalk Server 的事务相关的关键注意事项  
  
- 如果在业务流程中有多个发送端口，适配器会自动将从每个端口接收的消息的事务。 也就是说，事务不能跨越跨端口。  
  
- 在 SAP 事务中的消息不支持消息重试尝试次数。 因此，用户应设置为零的消息重试尝试。  
  
- 该适配器可能会产生不良结果标记为"否"上, 表中的组合。 您应使用标记为"Yes"的组合。  
  
- 没有消息上下文属性的消息发送到适配器将不绑定到当前事务上下文的情况下通常情况下执行。  
  
- BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 理想情况下应在业务流程中的当前事务上下文中的最后一个消息。  
  
  以下各节提供有关如何执行事务中使用 SAP 说明[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="how-to-perform-a-transaction-on-an-sap-system"></a>如何将 SAP 系统上执行事务？  
 对 SAP 系统使用执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要在 SAP 系统上执行事务，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要执行该事务的 RFC 生成架构。 此外，您必须为 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK Rfc 来生成架构。  
  
2. 用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。  
  
3. 创建从请求消息中提取单个"操作消息"，并将其发送到 SAP 系统的业务流程。 根据请求消息，业务流程还决定是提交还是回滚事务。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，SAPTransaction，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 若要演示如何将 SAP 系统上执行事务，需要以下架构：  
  
- 对于"操作消息"若要在 SAP 系统上执行操作。 向适配器发送的请求消息必须符合此架构。 这可以是任何特定于用户的架构包含任意数量的操作节点。 在本主题中，使用架构 MultipleOrders.xsd。 架构还提供了与产品附带的事务示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 有关详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
- 执行上的 SAP 系统，如调用 RFC 的操作。 要执行的操作的请求消息必须符合此架构。 必须使用生成此架构[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 在本主题中，调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC。 有关为 RFC 生成架构的信息，请参阅[浏览、 搜索和获取元数据中 SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。  
  
- 正在中止或提交事务。 提交或中止事务的请求必须符合此架构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK RFC 为提交和回滚操作分别使用。 您必须为使用这些 Rfc 生成架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
> [!NOTE]
>  您必须确保所有必需的架构将添加到 BizTalk 项目。  
> 
> [!IMPORTANT]
>  必须添加对 BizTalk 属性架构的引用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]向 BizTalk 项目。 架构文件*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装过程中，通常在\<安装驱动器\>: \Program Files\Microsoft BizTalk 适配器包\bin。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图窗口。  
  
 创建消息之前, 您必须确定请求消息 （的 MultipleOrders.xsd 类型） 具有"操作"节点的数。 此示例中，假设该请求消息具有两个操作消息来调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC。 因此，必须创建一个映射到为此 RFC 生成的架构的请求-响应消息集。  
  
 在 BizTalk 项目中，必须创建以下消息。  
  
- 消息，SendtoAdapter，它将发送到业务流程的请求消息。 此消息必须映射到输入消息，MultipleOrders.xsd 的架构。  
  
- 操作的消息，BAPIMessage，第一个发送到 SAP 系统。 此外必须创建第一个操作的响应的响应消息 BAPIResponse。 请求和响应消息必须映射到生成 BAPI_SALESORDER_CREATEFROMDAT2 RFC 的架构。  
  
- 消息，BAPICommitMessage，提交操作。 此外必须创建相应的响应消息的响应消息 BAPICommitResponse。 请求和响应消息必须映射到 BAPI_TRANSACTION_COMMIT RFC 的架构。  
  
- 操作的消息，BAPIRollbackMessage，回滚。 此外必须创建相应的响应消息的响应消息 BAPIRollbackResponse。 请求和响应消息必须映射到 BAPI_TRANSACTION_ROLLBACK RFC 的架构。  
  
  执行以下步骤来创建消息并将其链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  如果不是已打开，请打开 BizTalk 项目中，在业务流程视图。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，并选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**SendToAdapter**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SAPTransaction.MultipleOrders*，其中*SAPTransaction*是 BizTalk 项目的名称。 *MultipleOrders*是请求消息的架构。|  
  
5.  重复上述步骤创建六个更多的消息。 在中**属性**窗格中的新消息，执行以下操作。  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |BAPIMessage|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2*|  
    |BAPIResponse|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |BAPICommitMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMIT*|  
    |BAPICommitResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMITResponse*|  
    |BAPIRollbackMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACK*|  
    |BAPIRollbackResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACKResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]来执行 SAP 系统中的事务。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。 从 SAP 系统的响应保存到另一个位置。  
  
 可以在创建业务流程时使用的另一个注意事项是：  
  
- 将请求消息的架构映射到的 BAPI_SALESORDER_CREATEFROMDAT2 RFC。  
  
- 将请求消息的架构映射到的 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK RFC。  
  
  可以使用通过 BizTalk 映射的 XML 转换映射架构。 若要实现此目的，包括在业务流程转换形状。  
  
  最后，根据请求消息是否有的信息来提交或中止事务，该业务流程必须决定要发送到 SAP 系统的相应消息。 若要实现此目的，请在业务流程中包括判定形状。  
  
  有关不同的形状在业务流程中包含的详细信息，请参阅**业务流程设计器用户界面** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
  SAP 事务的示例业务流程如下所示。  
  
  ![若要在 SAP 中执行事务的业务流程](../../adapters-and-accelerators/adapter-sap/media/727f82e9-51a9-4a94-9d0a-d05c17904bde.gif "727f82e9-51a9-4a94-9d0a-d05c17904bde")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 上述业务流程中所示，形状列中列出的名称是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveInputXML|Receive|-设置**名称**到*ReceiveInputXML*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SendToLOB|Send|-设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br /><br /> -设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
 由于请求消息具有两个插入消息，必须创建另一组发送和接收形状将消息发送到 SAP 并接收响应。 但是，因为 insert 消息可能会提交或回滚后，必须在判定块内创建形状的第二个集。 必须创建一组用于提交的形状和另一组用于回滚的形状。  
  
> [!NOTE]
>  可以通过拖放判定形状从 BizTalk 业务流程工具箱中添加判定块。  
  
#### <a name="message-shapes-for-commit"></a>消息形状的提交  
 下表列出了业务流程的"提交路径"的形状。 在这里，您不需要创建请求消息的接收消息。 请求消息将传递中，从上一个消息形状中。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|SendBAPICommit|Send|-设置**名称**到*SendBAPICommit*|  
|ReceiveCommitResponse|Receive|-设置**名称**到*ReceiveCommitResponse*<br /><br /> -设置**激活**到*False*|  
|SendResponse2|Send|-设置**名称**到*SendResponse2*|  
  
#### <a name="message-shapes-for-abort"></a>消息形状的中止  
 下表列出了业务流程的"rollback 路径"的形状。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|SendBAPIRollback|Send|-设置**名称**到*SendBAPIRollback*|  
|ReceiveRollbackResponse|Receive|-设置**名称**到*ReceiveRollbackResponse*<br /><br /> -设置**激活**到*False*|  
|SendResponse3|Send|-设置**名称**到*SendResponse3*|  
  
### <a name="setting-the-rule-expression"></a>设置规则表达式  
 包含消息形状用于提交和中止通过添加判定形状的判定块内的操作。 若要指定该业务流程将在其做出决策的条件，必须指定在规则形状的表达式中基于在其上将是进行提交或回滚事务。 例如，您必须指定对于由规则形状，以下表达式：  
  
```  
SendToAdapter.isCommit == true  
```  
  
 其中，SendToAdapter 是为请求消息的架构创建的消息。 因此，在请求消息中，如果`isCommit`标记设置为**True**，业务流程获取的"提交"路由。 否则，业务流程获取"回滚"路由。  
  
 你可以将无法在表达式编辑器中指定此条件，您必须已提升`isCommit`请求消息发送到适配器的消息架构中的属性。 本主题中，对于要使用的输入的架构是 MultipleOrders.xsd。 必须升级`isCommit`此架构中的属性。 有关升级属性的详细信息，请参阅[升级属性](../../core/promoting-properties.md)。
  
### <a name="adding-construct-message-shapes"></a>添加构造消息形状  
 如前面所述，请求消息发送到适配器中包含两个插入消息，然后提交或中止消息。 必须添加构造消息形状，并在其中一个转换，转换形状来提取单个操作将消息发送到 SAP 系统。 您还必须添加用于设置属性启用事务的上下文属性的消息的消息赋值形状。  
  
#### <a name="the-first-construct-message-shape"></a>第一个构造消息形状  
 假设第一个构造消息形状称为"ReceiveXML。" 为此形状中，指定为"BAPIMessage"的构造的消息属性。 双击转换形状以打开**转换配置**对话框。 在对话框中：  
  
- 选择创建新的映射。  
  
- 从左窗格中，选择**源**来回**变量的名称**下拉列表中选择*SendToAdapter*。  
  
- 从左窗格中，选择**目标**来回**变量的名称**下拉列表中选择*BAPIMessage*。  
  
- 单击**确定**启动映射器。 将请求消息的架构映射到 BAPI_SALESORDER_CREATEFROMDAT2 的架构。 可以使用**索引**functoid 来创建源和目标架构之间的映射。 **索引**functoid，您可以在一系列记录中选择特定记录的信息。  
  
   下图显示了使用映射的架构**索引**functoid。  
  
   ![使用索引 functoid 映射的架构](../../adapters-and-accelerators/adapter-sap/media/d0ade577-ea74-4be3-a724-4ba19397d8d3.gif "d0ade577-ea74-4be3-a724-4ba19397d8d3")  
  
   有关使用详细信息**转换配置**对话框中，请参阅**转换 Configuration Dialog Box** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
   有关使用索引 functoid 的详细信息，请参阅[索引 Functoid](../../core/index-functoid.md)。
       
   映射架构后，可以测试映射使用映射文件的属性页。 有关详细信息，请参阅 **<Map File>属性页对话框中，测试映射**选项卡[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
  在消息赋值形状中，指定要启动事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPIMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "OPEN";  
```  
  
#### <a name="the-commit-construct-message-shape"></a>提交构造消息形状  
 假设提交操作在构造消息形状称为"CommitMessage。" 为此形状中，指定为"BAPICommitMessage"的构造的消息属性。 双击转换形状以打开**转换配置**对话框。 在对话框中：  
  
- 选择创建新的映射。  
  
- 从左窗格中，选择**源**来回**变量的名称**下拉列表中选择*SendToAdapter*。  
  
- 从左窗格中，选择**目标**来回**变量的名称**下拉列表中选择*BAPICommitMessage*。  
  
- 单击确定以启动映射器。 将请求消息的架构映射到 BAPI_TRANSACTION_COMMIT 的架构。 因为 BAPI_TRANSACTION_COMMIT 节点不包含记录层次结构，不需要包括此映射索引 functoid。  
  
  在消息赋值形状中，指定要提交事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPICommitMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "CLOSE";  
```  
  
#### <a name="the-rollback-construct-message-shape"></a>回滚构造消息形状  
 假设回滚操作在构造消息形状称为"RollbackMessage。" 为此形状中，指定为"BAPIRollbackMessage"的构造的消息属性。 双击转换形状以打开**转换配置**对话框。 在对话框中：  
  
- 选择创建新的映射。  
  
- 从左窗格中，选择**源**来回**变量的名称**下拉列表中选择*SendToAdapter*。  
  
- 从左窗格中，选择**目标**来回**变量的名称**下拉列表中选择*BAPIRollbackMessage*。  
  
- 单击确定以启动映射器。 将请求消息的架构映射到 BAPI_TRANSACTION_ROLLBACK 的架构。 因为 BAPI_TRANSACTION_ROLLBACK 节点不包含记录层次结构，不需要包括此映射索引 functoid。  
  
  在消息赋值形状中，指定回滚事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPIRollbackMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "ABORT";  
```  
  
> [!IMPORTANT]
>  在典型方案中，必须在异常块中使用相对应的 BAPI_TRANSACTION_ROLLBACK 中止上下文属性的消息。  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
 对于此业务流程，创建三个端口。 第一个端口从指定的文件夹中提取请求消息。 第二个端口将消息发送到 SAP 系统，并接收响应。 第三个端口将保存到另一个文件夹的响应。 因此：  
  
-   第一个端口仅接收消息的单个架构，即 MultipleOrders.xsd。  
  
-   第二个端口发送和接收消息的架构 BAPI_SALESORDER_CREATEFROMDAT2 RFC。 此外，相同的端口将用于提交或回滚事务。 因此，此端口还接收消息的架构，BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK Rfc。 若要启用此功能，三个不同的操作将创建此端口，每个对应于特定的消息架构。  
  
-   类似于第二个端口，此端口将还在接收消息具有三个不同的架构。 因此，有必要创建此端口上的三个不同操作。  
  
|Port|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br /><br /> -设置**类型**到*FileInType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br /><br /> -设置**类型**到*LOBPortType*<br /><br /> -设置**通信模式**到*请求-响应*<br /><br /> -设置**通信方向**到*发送接收*<br /><br /> -创建一个操作*BAPIMessage*。<br /><br /> -创建一个操作*CommitMessage*。 此操作将用于发送提交消息。<br /><br /> -创建一个操作*RollbackMessage*。 此操作将用于发送回滚消息。|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br /><br /> -设置**类型**到*SaveResponseType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*。<br /><br /> -创建一个操作*BAPIMessage*。<br /><br /> -创建一个操作*CommitMessage*。 此操作将用于保存提交消息的响应。<br /><br /> -创建一个操作*RollbackMessage*。 此操作将用于保存对回滚消息的响应。|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveInputXML|-设置**消息**到*SendToAdapter*<br /><br /> -设置**操作**到*FileIn.Transaction.Request*|  
|SendToLOB|-设置**消息**到*BAPIMessage*<br /><br /> -设置**操作**到*LOBPort.BAPIMessage.Request*|  
|ReceiveResponse|-设置**消息**到*BAPIResponse*<br /><br /> -设置**操作**到*LOBPort.BAPIMessage.Response*|  
|SendResponse|-设置**消息**到*BAPIResponse*<br /><br /> -设置**操作**到*SaveResponse.BAPIMessage.Request*|  
|SendBAPICommit|-设置**消息**到*BAPICommitMessage*<br /><br /> -设置**操作**到*LOBPort.CommitMessage.Request*|  
|ReceiveCommitResponse|-设置**消息**到*BAPICommitResponse*<br /><br /> -设置**操作**到*LOBPort.CommitMessage.Response*|  
|SendResponse2|-设置**消息**到*BAPICommitResponse*<br /><br /> -设置**操作**到*SaveResponse.CommitMessage.Request*|  
|SendBAPIRollback|-设置**消息**到*BAPIRollbackMessage*<br /><br /> -设置**操作**到*LOBPort.RollbackMessage.Request*|  
|ReceiveRollbackResponse|-设置**消息**到*BAPIRollbackResponse*<br /><br /> -设置**操作**到*LOBPort.RollbackMessage.Response*|  
|SendResponse3|-设置**消息**到*BAPIRollbackResponse*<br /><br /> -设置**操作**到*SaveResponse.RollbackMessage.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
## <a name="handling-exceptions"></a>处理异常  
 在复杂的业务流程来执行 BAPI 事务类似，非常重要，跟踪的业务流程的状态，报告的错误发生时，以便在发生，可以解决这些问题。 BizTalk 业务流程提供了工具来处理错误，维护业务流程的状态并解决问题，在发生通过事务、 补偿和异常处理。  
  
 作为用于事务和异常处理框架，业务流程设计器提供了**作用域**形状。 作用域可以具有事务类型、 补偿和任意数量的异常处理程序。 一个作用域包含一个或多个块。 它具有一个主体，并可根据需要任意数量的异常处理块追加到它。 在 BAPI 事务的情况下整个业务流程 （请参阅前面的图） 可以包含的作用域中。  
  
 若要捕获的异常，必须添加**捕获异常**向业务流程的块。 **捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。 必须在 BAPI 事务的情况下将添加到"中止"例程**捕获异常**块中，也就是说，必须将以下添加到"中止"例程：  
  
- 构造消息形状组成一个 （可从输入消息中提取请求消息） 的转换和消息赋值形状 （若要设置上下文属性）  
  
- 发送和接收形状。  
  
  用于 SAP 事务示例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](SAPTransaction) 附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]演示异常处理、 过。 有关该示例的详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
  有关如何处理异常的详细信息，一般情况下，使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用事务和处理异常](../../core/using-transactions-and-handling-exceptions.md)。
  
## <a name="add-the-biztalk-property-schema-to-biztalk"></a>将 BizTalk 属性架构添加到 BizTalk  
 在 BizTalk 项目中，添加的 BizTalk 属性架构的程序集引用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 必须将同一程序集添加为 BizTalk 应用程序，即，将在其中部署 BizTalk 项目的应用程序中的资源。 架构文件*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常在安装程序\<安装驱动器\>: \Program Files\Microsoft BizTalk 适配器Pack\bin。 如果没有此资源，你将无法再部署你的项目。  
  
#### <a name="to-add-an-assembly-as-a-resource-in-biztalk"></a>若要将程序集添加为 BizTalk 中的资源  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，展开**应用程序**，，然后你想要添加 BizTalk 程序集的应用程序。  
  
3. 右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
4. 在中**添加资源**对话框中，单击**添加**，导航到包含 BizTalk 程序集文件的文件夹中，选择 BizTalk 程序集文件，然后单击**打开**。  
  
5. 在中**选项**，为 BizTalk 程序集安装到 GAC 中，指定选项，然后单击**确定**。  
  
   你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。 由于发送端口发送和接收符合多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[配置用于 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)。 请确保创建 WCF 自定义时遵守以下重要注意事项或 WCF SAP 发送端口以执行事务。  
  
    |设置以下各项|为此值|  
    |-----------------------|-------------------|  
    |操作|发送端口发送和接收消息的多个操作。 因此，必须为每个操作设置发送端口上的操作。<br /><br /> `<BtsActionMapping>   <Operation Name="BAPIMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_SALESORDER_CREATEFROMDAT2" />   <Operation Name="CommitMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT" />   <Operation Name="RollbackMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK" /> </BtsActionMapping>`|  
    |EnableBizTalkCompatibilityMode|将此绑定属性设置为 **，则返回 True**。|  
    |EnableConnectionPooling|将此绑定属性设置为**False**之前执行任何事务。 在其中设置了适配器和 BizTalk 之间的通道意外终止时的情况下，相应的连接添加到连接池。 会打开另一个通道，而新通道选择相同的连接对象，旧的连接对象上未提交的事务也将提交事务时已提交，通过新的通道。 若要避免此问题，连接池时必须禁用执行事务。|  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
    > 
    > [!IMPORTANT]
    >  可以在 WCF 自定义配置备份传输或 WCF SAP 发送端口，可用于将消息发送到另一个 SAP 系统，如果主传输无法正常工作。 但是，对于基于 WCF 的 SAP 系统上执行事务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持指定指向另一台 SAP 服务器的备份传输。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序执行事务的 SAP 系统。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须在预定义的位置删除该业务流程的请求消息。 请求消息必须符合特定架构，例如，MultipleOrders.xsd 架构。 例如，在 SAP 系统中创建销售订单请求消息，然后提交该操作：  
  
```  
<ns0:Orders xmlns:ns0="http://BAPISend.MultipleOrders">  
  <Order>  
      <ORDER_HEADER_IN>  
        <DOC_TYPE>TA</DOC_TYPE>  
        <SALES_ORG>1000</SALES_ORG>  
        <DISTR_CHAN>10</DISTR_CHAN>  
        <DIVISION>00</DIVISION>  
        <SALES_OFF>1000</SALES_OFF>  
        <REQ_DATE_H>20060901</REQ_DATE_H>  
        <PURCH_DATE>20060901</PURCH_DATE>  
        <PURCH_NO_C>Cust A</PURCH_NO_C>  
        <CURRENCY>EUR</CURRENCY>  
      </ORDER_HEADER_IN>  
      <ORDER_ITEMS_IN>  
          <MATERIAL>P-109</MATERIAL>  
          <PLANT>1000</PLANT>  
          <TARGET_QU>ST</TARGET_QU>  
      </ORDER_ITEMS_IN>  
      <ORDER_PARTNERS>  
          <PARTN_ROLE>AG</PARTN_ROLE>  
          <PARTN_NUMB>0000000257</PARTN_NUMB>  
      </ORDER_PARTNERS>  
    <RETURN></RETURN>  
  </Order>  
  <isCommit>true</isCommit>  
  <BAPI_TRANSACTION_COMMIT>  
  </BAPI_TRANSACTION_COMMIT>  
</ns0:Orders>  
```  
  
 业务流程使用该消息并将其发送到 SAP 系统。 来自 SAP 系统的响应被保存在定义为业务流程的一部分的其他文件位置。 对于更高版本的请求消息，您会得到两条响应消息 — 一个用于调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC，另一个用于使用 BAPI_TRANSACTION_COMMIT 提交操作。  
  
 BAPI_SALESORDER_CREATEFROMDAT2 的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <SALESDOCUMENT />   
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <ITM_NUMBER>0</ITM_NUMBER>   
      <HG_LV_ITEM>0</HG_LV_ITEM>   
      <PO_ITM_NO />   
      ......  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>   
      <PARTN_NUMB>0000000257</PARTN_NUMB>   
      <ITM_NUMBER>0</ITM_NUMBER>   
      ......   
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
</BAPI_SALESORDER_CREATEFROMDAT2Response>  
```  
  
 BAPI_TRANSACTION_COMMIT 的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_TRANSACTION_COMMITResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <RETURN>  
    <TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ID xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <NUMBER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</NUMBER>   
    <MESSAGE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_MSG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</LOG_MSG_NO>   
    <MESSAGE_V1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V3 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V4 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <PARAMETER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ROW xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</ROW>   
    <FIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <SYSTEM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
  </RETURN>  
</BAPI_TRANSACTION_COMMITResponse>  
```  
  
> [!NOTE]
>  如果请求消息调用 BAPI_TRANSACTION_ROLLBACK RFC，第二个响应将是针对 BAPI_TRANSACTION_ROLLBACK。  
  
## <a name="possible-exceptions"></a>可能的异常  
 通过使用 BizTalk Server 上的 SAP 系统中执行事务时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口和接收端口、 同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)