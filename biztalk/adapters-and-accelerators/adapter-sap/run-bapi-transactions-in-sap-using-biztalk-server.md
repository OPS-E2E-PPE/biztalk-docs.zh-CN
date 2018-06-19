---
title: SAP 使用 BizTalk Server 中运行 BAPI 事务 |Microsoft 文档
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
ms.openlocfilehash: 79cfa3f1b799c4a96cdad7f4c9b89b4b594dc4d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967947"
---
# <a name="run-bapi-transactions-in-sap-using-biztalk-server"></a>SAP 使用 BizTalk Server 中运行 BAPI 事务
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端可以使用某个 SAP 系统执行事务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 在创建之前事务业务流程，你必须首先了解将在其中执行事务的基本方案。 在典型事务方案中，与多个操作 （例如调用 BAPI） 请求消息发送到 SAP 系统。 这将称为"操作消息"。 业务流程必须从请求消息中提取每个操作消息并将各个操作消息发送到 SAP 系统。 业务流程将它们发送一次是在另一个使用相同的连接。 业务流程使用通过 BizTalk 映射的 XML 转换中提取的"操作消息"从各条消息。  
  
 执行的操作后，业务流程必须提交或中止事务通过分别 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK，发送消息。 这些将被称为"事务处理消息。"  
  
## <a name="how-does-the-adapter-enable-transactions-through-biztalk-server"></a>适配器如何启用事务通过 BizTalk 服务器？  
 若要启用 SAP 系统使用的事务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   提供消息上下文属性打开、 关闭、 重用和中止。  
  
-   使用 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 来提交或中止操作。 这些公开的 SAP 系统。  
  
 下表列出了关于 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 中使用属性的某些准则：  
  
|消息|OPEN|重复使用|CLOSE|中止|  
|-------------|----------|-----------|-----------|-----------|  
|第一条消息 （操作消息）|是|“否”|“否”|是|  
|后续消息 （操作消息）|是|是|“否”|是|  
|BAPI_TRANSACTION_COMMIT （事务消息）|是|是|是|是|  
|BAPI_TRANSACTION_ROLLBACK （事务消息）|是|是|是|是|  
  
 在表中，"是"表示要用于消息的消息上下文属性。 同样，"否"表示不要与消息使用的消息上下文属性。  
  
 下面汇总表：  
  
-   第一条消息必须始终为操作消息，并且必须仅使用打开的属性。  
  
-   后续操作消息必须使用重用属性。  
  
-   对应于 BAPI_TRANSACTION_COMMIT 为提交事务的事务消息必须使用关闭属性。  
  
-   对应于 BAPI_TRANSACTION_ROLLBACK 的事务消息中止事务可以使用关闭或中止属性。 如果使用中止，理想情况下消息必须在业务流程异常块。  
  
## <a name="key-considerations-related-to-transactions-using-biztalk-server"></a>与使用 BizTalk Server 的事务相关的关键注意事项  
  
-   如果正在多个发送端口业务流程，适配器自动分隔从每个端口接收的消息的事务。 也就是说，事务不能跨越端口。  
  
-   在 SAP 事务中的消息不支持消息重试尝试。 因此，用户应设置为零的消息重试尝试。  
  
-   该适配器可能生成意外的结果为标记为"否"前面的表中的组合。 你应使用标记为"是"的组合。  
  
-   没有消息上下文属性的消息发送到适配器将不绑定到当前的事务上下文的情况下正常执行。  
  
-   理想情况下，BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 应为业务流程中的当前事务上下文中最后一条消息。  
  
 下列各节提供有关如何执行事务中使用 SAP 说明[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="how-to-perform-a-transaction-on-an-sap-system"></a>如何在某个 SAP 系统上执行事务？  
 执行对 SAP 系统使用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要执行的事务上的 SAP 系统，这些任务包括：  
  
1.  创建 BizTalk 项目，并为你想要执行该事务的 RFC 生成架构。 此外，你必须为 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK Rfc 生成架构。  
  
2.  在发送和接收消息从 SAP 系统的 BizTalk 项目中创建消息。  
  
3.  创建业务流程，从请求消息中提取单个"操作消息"，并将其发送到 SAP 系统。 根据请求消息，业务流程还决定是提交还是回滚事务。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SAPTransaction，基于本主题提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 若要演示如何在某个 SAP 系统上执行事务，你需要以下架构：  
  
-   "操作的消息"在 SAP 系统上执行操作。 请求消息发送到适配器必须符合此架构。 这可以是包含任意数量的操作节点任何特定于用户的架构。 在本主题中，使用架构 MultipleOrders.xsd。 按事务示例的一部分附带还提供架构[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 有关详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
-   用于执行上的 SAP 系统，例如调用 RFC 的操作。 要执行操作的请求消息必须符合此架构。 必须通过使用生成此架构[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 在本主题中，调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC。 有关为 RFC 生成架构的信息，请参阅[浏览，搜索和获取元数据在 SAP 中的 RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。  
  
-   用于中止或提交事务。 提交或中止事务的请求必须符合此架构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI_TRANSACTION_COMMIT 分别使用和 BAPI_TRANSACTION_ROLLBACK RFC 为提交和回滚操作。 您必须为使用这些 Rfc 生成架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
> [!NOTE]
>  你必须确保所有必需的架构将添加到 BizTalk 项目。  
  
> [!IMPORTANT]
>  你必须添加到 BizTalk 属性的架构的引用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到你的 BizTalk 项目。 架构文件中， *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装过程中，通常情况下\<安装驱动器\>: files\microsoft BizTalk 适配器包\bin。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您生成第一步中的邮件从 BizTalk 项目的业务流程视图窗口的架构。  
  
 之前创建消息，您必须确定 （MultipleOrders.xsd 类型） 的请求消息具有的"操作"节点数。 对于此示例，假定请求消息具有两个操作消息来调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC。 因此，你必须创建一个映射到为此 RFC 生成的架构的请求-响应消息集。  
  
 在 BizTalk 项目，必须创建以下消息。  
  
-   一条消息，SendtoAdapter，它将发送到业务流程的请求消息。 此消息必须映射到输入消息，MultipleOrders.xsd 的架构。  
  
-   操作的消息，BAPIMessage，第一个发送到 SAP 系统。 你还必须创建第一个操作的响应的响应消息 BAPIResponse。 请求和响应消息必须映射到为 BAPI_SALESORDER_CREATEFROMDAT2 RFC 生成的架构。  
  
-   操作的消息，BAPICommitMessage，提交。 你还必须创建相应的响应消息的响应消息 BAPICommitResponse。 请求和响应消息必须映射到 BAPI_TRANSACTION_COMMIT RFC 的架构。  
  
-   操作的消息，BAPIRollbackMessage，回滚。 你还必须创建相应的响应消息的响应消息 BAPIRollbackResponse。 请求和响应消息必须映射到 BAPI_TRANSACTION_ROLLBACK RFC 的架构。  
  
 执行以下步骤以创建消息并将它们链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  如果它不是已打开，请打开业务流程视图 BizTalk 项目。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**SendToAdapter**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SAPTransaction.MultipleOrders*，其中*SAPTransaction*是 BizTalk 项目的名称。 *MultipleOrders*是请求消息的架构。|  
  
5.  重复上述步骤以创建六个详细消息。 在**属性**窗格中是否有新消息，执行以下操作。  
  
    |设置为标识符|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |BAPIMessage|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2*|  
    |BAPIResponse|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |BAPICommitMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMIT*|  
    |BAPICommitResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMITResponse*|  
    |BAPIRollbackMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACK*|  
    |BAPIRollbackResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACKResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]来 SAP 系统中执行事务。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。 从 SAP 系统的响应保存到另一个位置。  
  
 可以在创建业务流程时使用的另一个注意事项是：  
  
-   请求消息架构映射到的 BAPI_SALESORDER_CREATEFROMDAT2 RFC。  
  
-   请求消息架构映射到 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK RFC。  
  
 你可以通过使用通过 BizTalk 映射的 XML 转换映射架构。 若要实现此目的，包括业务流程中转换形状。  
  
 最后，根据请求消息是否有的信息来提交或中止事务，业务流程必须确定适当的消息发送到 SAP 系统。 若要实现此目的，包括业务流程中确定形状。  
  
 有关不同的形状包含在业务流程的详细信息，请参阅**Orchestration 设计器 UI** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
 SAP 事务示例业务流程如下所示。  
  
 ![若要在 SAP 中执行事务的业务流程](../../adapters-and-accelerators/adapter-sap/media/727f82e9-51a9-4a94-9d0a-d05c17904bde.gif "727f82e9-51a9-4a94-9d0a-d05c17904bde")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 前面的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveInputXML|Receive|-将设置**名称**到*ReceiveInputXML*<br /><br /> -将设置**激活**到*True*|  
|SendToLOB|Send|-将设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br /><br /> -将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
 由于请求消息具有两个插入消息，你必须创建另一组发送和接收形状将消息发送到 SAP，并接收响应。 但是，因为可能会提交或回滚插入消息，必须在决策块内创建形状的第二个集。 必须创建一组用于提交的形状和另一组用于回滚的形状。  
  
> [!NOTE]
>  您可以通过拖放判定形状从 BizTalk 业务流程在工具箱中添加一个决策模块。  
  
#### <a name="message-shapes-for-commit"></a>有关消息形状提交  
 下表列出的业务流程的"提交路径"的形状。 在这里，你不需要创建的请求消息的接收消息。 请求消息将在从以前的消息形状的传递。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|SendBAPICommit|Send|-将设置**名称**到*SendBAPICommit*|  
|ReceiveCommitResponse|Receive|-将设置**名称**到*ReceiveCommitResponse*<br /><br /> -将设置**激活**到*False*|  
|SendResponse2|Send|-将设置**名称**到*SendResponse2*|  
  
#### <a name="message-shapes-for-abort"></a>有关消息形状中止  
 下表列出为"回滚路径"业务流程的形状。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|SendBAPIRollback|Send|-将设置**名称**到*SendBAPIRollback*|  
|ReceiveRollbackResponse|Receive|-将设置**名称**到*ReceiveRollbackResponse*<br /><br /> -将设置**激活**到*False*|  
|SendResponse3|Send|-将设置**名称**到*SendResponse3*|  
  
### <a name="setting-the-rule-expression"></a>设置规则表达式  
 包含用于提交消息形状，并通过添加判定形状中止决策块内的操作。 若要指定在其业务流程将做出决策的条件，必须指定在规则形状的表达式中基于在其上事务将提交或回滚。 例如，你必须指定规则形状的以下表达式：  
  
```  
SendToAdapter.isCommit == true  
```  
  
 其中，SendToAdapter 是你创建的请求消息的架构的消息。 因此，在请求消息中，如果`isCommit`标记设置为**True**，业务流程采用"提交"路由。 否则，业务流程将"回滚"路由。  
  
 为你能够指定此条件表达式编辑器中，你必须具有提升`isCommit`请求消息发送到适配器的消息架构中的属性。 本主题中，对于要使用的输入的架构是 MultipleOrders.xsd。 你必须升级`isCommit`此架构中的属性。 有关将升级属性的详细信息，请参阅[提升属性](../../core/promoting-properties.md)。
  
### <a name="adding-construct-message-shapes"></a>添加构造消息形状  
 如前面所述，请求消息发送到适配器将包含两个插入消息，然后提交或中止消息。 必须添加构造消息形状，并在其中一个转换调整提取单个操作消息发送到 SAP 系统。 你还必须添加某个消息分配形状将设置为启用事务的上下文属性的消息。  
  
#### <a name="the-first-construct-message-shape"></a>第一个构造消息形状  
 假设称为"ReceiveXML。"的第一个构造消息形状。 为此形状中，指定为"BAPIMessage"的构造消息属性。 双击要打开的转换形状**转换配置**对话框。 在对话框中：  
  
-   选择创建新的映射。  
  
-   从左窗格中，选择**源**和从**变量名称**下拉列表中选择*SendToAdapter*。  
  
-   从左窗格中，选择**目标**和从**变量名称**下拉列表中选择*BAPIMessage*。  
  
-   单击**确定**启动映射器。 请求消息架构映射到 BAPI_SALESORDER_CREATEFROMDAT2 的架构。 你可以使用**索引**functoid 来创建源和目标架构之间的映射。 **索引**functoid 使您能够选择在一系列记录的特定记录的信息。  
  
     下图显示了使用映射的架构**索引**functoid。  
  
     ![使用索引 functoid 映射架构](../../adapters-and-accelerators/adapter-sap/media/d0ade577-ea74-4be3-a724-4ba19397d8d3.gif "d0ade577-ea74-4be3-a724-4ba19397d8d3")  
  
     有关使用**转换配置**对话框中，请参阅**转换配置对话框** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
     有关使用索引 functoid 的详细信息，请参阅[索引 Functoid](../../core/index-functoid.md)。
       
     映射架构后，你可以测试使用映射文件的属性页上的映射。 有关详细信息，请参阅**<Map File>属性页对话框中，测试映射**选项卡[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
 在消息分配形状中，指定要启动事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPIMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "OPEN";  
```  
  
#### <a name="the-commit-construct-message-shape"></a>提交构造消息形状  
 假设提交操作的构造消息形状称为"CommitMessage。" 为此形状中，指定为"BAPICommitMessage"的构造消息属性。 双击要打开的转换形状**转换配置**对话框。 在对话框中：  
  
-   选择创建新的映射。  
  
-   从左窗格中，选择**源**和从**变量名称**下拉列表中选择*SendToAdapter*。  
  
-   从左窗格中，选择**目标**和从**变量名称**下拉列表中选择*BAPICommitMessage*。  
  
-   单击确定以启动映射器。 请求消息架构映射到 BAPI_TRANSACTION_COMMIT 的架构。 因为 BAPI_TRANSACTION_COMMIT 节点不包含记录层次结构，不需要包括此映射索引 functoid。  
  
 在消息分配形状中，指定要提交该事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPICommitMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "CLOSE";  
```  
  
#### <a name="the-rollback-construct-message-shape"></a>回滚构造消息形状  
 假设回滚操作构造消息形状称为"RollbackMessage。" 为此形状中，指定为"BAPIRollbackMessage"的构造消息属性。 双击要打开的转换形状**转换配置**对话框。 在对话框中：  
  
-   选择创建新的映射。  
  
-   从左窗格中，选择**源**和从**变量名称**下拉列表中选择*SendToAdapter*。  
  
-   从左窗格中，选择**目标**和从**变量名称**下拉列表中选择*BAPIRollbackMessage*。  
  
-   单击确定以启动映射器。 请求消息架构映射到 BAPI_TRANSACTION_ROLLBACK 的架构。 因为 BAPI_TRANSACTION_ROLLBACK 节点不包含记录层次结构，不需要包括此映射索引 functoid。  
  
 在消息分配形状中，指定回滚事务的消息上下文属性。 例如，可能是第一条消息的消息上下文属性：  
  
```  
BAPIRollbackMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "ABORT";  
```  
  
> [!IMPORTANT]
>  在典型方案中，必须在异常块中使用对应于 BAPI_TRANSACTION_ROLLBACK 与中止上下文属性的消息。  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 中列出的名称*端口*列是业务流程中显示的端口的名称。  
  
 对于此业务流程，将创建三个端口。 第一个端口选取从指定的文件夹的请求消息。 第二个端口将消息发送到 SAP 系统，并接收响应。 第三个端口将保存到另一个文件夹的响应。 因此：  
  
-   第一个端口只接收单个架构，即，即 MultipleOrders.xsd 的消息。  
  
-   第二个端口发送和接收 BAPI_SALESORDER_CREATEFROMDAT2 RFC 架构的消息。 此外，将使用相同端口来提交或回滚事务。 因此，此端口还会收到消息的架构 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK Rfc。 若要启用此功能，三个不同的操作创建在此端口，每个对应于特定消息架构。  
  
-   类似于第二个端口，此端口将同时收到具有三个不同的架构的消息。 因此，它是创建此端口三个不同的操作所需的。  
  
|端口|属性|  
|----------|----------------|  
|文件|-将设置**标识符**到*文件*<br /><br /> -将设置**类型**到*FileInType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br /><br /> -将设置**类型**到*LOBPortType*<br /><br /> -将设置**通信模式**到*请求-响应*<br /><br /> -将设置**通信方向**到*发送接收*<br /><br /> -创建一个操作*BAPIMessage*。<br /><br /> -创建一个操作*CommitMessage*。 此操作将用于发送提交消息。<br /><br /> -创建一个操作*RollbackMessage*。 此操作将用于发送回滚消息。|  
|SaveResponse|-将设置**标识符**到*SaveResponse*<br /><br /> -将设置**类型**到*SaveResponseType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*。<br /><br /> -创建一个操作*BAPIMessage*。<br /><br /> -创建一个操作*CommitMessage*。 此操作将用于保存提交消息的响应。<br /><br /> -创建一个操作*RollbackMessage*。 此操作将用于保存回滚消息的响应。|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveInputXML|-将设置**消息**到*SendToAdapter*<br /><br /> -将设置**操作**到*FileIn.Transaction.Request*|  
|SendToLOB|-将设置**消息**到*BAPIMessage*<br /><br /> -将设置**操作**到*LOBPort.BAPIMessage.Request*|  
|ReceiveResponse|-将设置**消息**到*BAPIResponse*<br /><br /> -将设置**操作**到*LOBPort.BAPIMessage.Response*|  
|SendResponse|-将设置**消息**到*BAPIResponse*<br /><br /> -将设置**操作**到*SaveResponse.BAPIMessage.Request*|  
|SendBAPICommit|-将设置**消息**到*BAPICommitMessage*<br /><br /> -将设置**操作**到*LOBPort.CommitMessage.Request*|  
|ReceiveCommitResponse|-将设置**消息**到*BAPICommitResponse*<br /><br /> -将设置**操作**到*LOBPort.CommitMessage.Response*|  
|SendResponse2|-将设置**消息**到*BAPICommitResponse*<br /><br /> -将设置**操作**到*SaveResponse.CommitMessage.Request*|  
|SendBAPIRollback|-将设置**消息**到*BAPIRollbackMessage*<br /><br /> -将设置**操作**到*LOBPort.RollbackMessage.Request*|  
|ReceiveRollbackResponse|-将设置**消息**到*BAPIRollbackResponse*<br /><br /> -将设置**操作**到*LOBPort.RollbackMessage.Response*|  
|SendResponse3|-将设置**消息**到*BAPIRollbackResponse*<br /><br /> -将设置**操作**到*SaveResponse.RollbackMessage.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
## <a name="handling-exceptions"></a>处理异常  
 在所示来执行 BAPI 事务的复杂业务流程，很重要，跟踪的业务流程的状态，报表错误，因为它们发生，以便在发生，可以解决问题。 BizTalk 业务流程提供工具来处理错误，来保持业务流程的状态和修复问题，在发生这些通过事务、 补偿和异常处理。  
  
 业务流程设计器提供一个框架，用于事务和异常处理，作为**作用域**形状。 作用域可以具有事务类型、补偿和任意数目的异常处理程序。 一个作用域包含一个或多个块。 它具有一个主体，并可根据需要任意数量的异常处理块追加到它。 对于 BAPI 事务整个业务流程 （请参见前面的图） 可以包含作用域中。  
  
 若要捕获异常，你必须添加**捕获异常**业务流程的块。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 必须在 BAPI 事务的情况下添加到"中止"例程**捕获异常**块中，也就是说，你必须将以下代码添加到"中止"例程：  
  
-   构造消息形状组成一个 （可从输入消息中提取请求消息） 的转换和消息分配形状 （若要设置的上下文属性）  
  
-   发送和接收形状。  
  
 用于的 SAP 事务示例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](SAPTransaction) 附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]演示异常处理、 过。 有关该示例的详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
 有关如何处理异常的详细信息，通常情况下，使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用事务和处理异常](../../core/using-transactions-and-handling-exceptions.md)。
  
## <a name="add-the-biztalk-property-schema-to-biztalk"></a>将 BizTalk 属性架构添加到 BizTalk  
 在 BizTalk 项目中，添加的 BizTalk 属性架构的程序集引用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 必须将相同的程序集添加为 BizTalk 应用程序，即，应用程序将在其中部署 BizTalk 项目中的资源。 架构文件中， *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常低于设置\<安装驱动器\>: files\microsoft BizTalk AdapterPack\bin。 如果没有此资源，你将不能将项目部署。  
  
#### <a name="to-add-an-assembly-as-a-resource-in-biztalk"></a>若要将程序集添加为 BizTalk 中的资源  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，展开**应用程序**，然后你想要添加 BizTalk 程序集与应用程序。  
  
3.  右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。  
  
4.  在**添加资源**对话框中，单击**添加**，导航到包含 BizTalk 程序集文件的文件夹，选择 BizTalk 程序集文件，，然后单击**打开**。  
  
5.  在**选项**，指定安装到 GAC 中，BizTalk 程序集的选项，然后单击**确定**。  
  
 你必须立即生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。 由于发送端口发送和接收消息符合多个架构，并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[配置 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)。 请确保在创建 WCF 自定义时遵守以下的关键注意事项或 WCF SAP 发送端口执行事务。  
  
        |设置以下各项|为此值|  
        |-----------------------|-------------------|  
        |操作|发送端口发送和接收多个操作的消息。 因此，发送端口上的操作必须设置为每个操作。<br /><br /> `<BtsActionMapping>   <Operation Name="BAPIMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_SALESORDER_CREATEFROMDAT2" />   <Operation Name="CommitMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT" />   <Operation Name="RollbackMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK" /> </BtsActionMapping>`|  
        |EnableBizTalkCompatibilityMode|将此绑定属性设置为**True**。|  
        |EnableConnectionPooling|将此绑定属性设置为**False**之前执行任何事务。 在而意外终止的适配器和 BizTalk 之间设置通道的情况下，相应的连接添加到连接池。 时将打开另一个通道，并且新通道选取相同的连接对象，如果这些事务是提交通过新通道，也将很旧的连接对象上未提交的事务的提交情况。 要避免此问题，连接池必须禁用执行事务时。|  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
        > [!IMPORTANT]
        >  你可以在 WCF 自定义配置备份传输或 WCF SAP 发送端口，可用于将消息发送到另一个 SAP 系统，如果的主要传输无法正常工作。 但是，对于基于 WCF 的 SAP 系统上执行事务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持指定指向另一个 SAP 服务器的备份传输。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序执行事务的 SAP 系统。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)，[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须在预定义位置删除业务流程的请求消息。 请求消息必须符合特定的架构，例如，MultipleOrders.xsd 架构。 例如，在某个 SAP 系统中创建销售订单请求消息，然后提交该操作被：  
  
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
  
 业务流程使用该消息，并将其发送到 SAP 系统。 从 SAP 系统的响应保存在定义为业务流程的一部分的其他文件位置中。 对于以上的请求消息中，你可以获取两条响应消息 — 一个用于调用 BAPI_SALESORDER_CREATEFROMDAT2 RFC 和另一个用于使用 BAPI_TRANSACTION_COMMIT 提交操作。  
  
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
>  如果请求消息调用 BAPI_TRANSACTION_ROLLBACK RFC，第二个响应将 BAPI_TRANSACTION_ROLLBACK。  
  
## <a name="possible-exceptions"></a>可能的异常  
 使用 BizTalk Server SAP 系统上执行事务时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口和接收端口，相同的业务流程。 有关绑定文件的详细信息，请参阅[重用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)