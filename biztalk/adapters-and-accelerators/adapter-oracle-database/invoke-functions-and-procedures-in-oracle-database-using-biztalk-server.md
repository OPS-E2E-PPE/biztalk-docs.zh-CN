---
title: 调用函数和 Oracle 数据库使用 BizTalk Server 中的过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, invoking by using BizTalk Server
ms.assetid: 35f2c40e-1151-4941-9030-16464fc1caf8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02770e1fec3cb11846e855ed0b9bca9d72c38fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-biztalk-server"></a>调用函数和 Oracle 数据库使用 BizTalk Server 中的过程
适配器客户端可以通过调用函数和 Oracle 数据库中的过程[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现过程、 函数和包作为操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]此外允许适配器客户端调用：  
  
-   重载的函数和存储的过程。 请参阅[调用重载函数和 Oracle 数据库使用 BizTalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。  
  
-   函数和过程外，无 IN、 和 IN 出 REF CURSOR 参数。 请参阅[调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)。  
  
-   功能和过程有 IN、 OUT，以及在出记录的类型参数。 请参阅[调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的记录类型](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)。  
  
 有关函数和存储的过程使用处理的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[对函数和 Oracle 数据库中的存储过程的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)。 调用函数和过程的 SOAP 消息的结构有关的信息，请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>如何在 Oracle 数据库中调用函数？  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要调用的 Oracle 数据库中的函数，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成你想要在 Oracle 数据库中调用的函数的架构。  
  
2.  在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程来调用该函数的 Oracle 数据库中。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，InvokeFunction，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，来演示如何调用函数，我们将调用下 SCOTT\Package\ACCOUNT_PKG 架构 CREATE_ACCOUNT 函数。 通过运行这些示例提供的 SQL 脚本在 SCOTT 架构下创建此包。 CREATE_ACCOUNT 函数使用帐户和地址作为输入的信息并在帐户和客户表中创建记录。 如果已存在该记录，函数将返回 0。否则，该函数返回帐户 id。 若要了解有关这些示例和 SQL 脚本的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 若要调用 CREATE_ACCOUNT 函数，我们必须生成 SCOTT\Package\ACCOUNT_PKG 架构在同一函数的架构。 请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
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
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeFunction.OracleDBBindingSchema.CREATE_ACCOUNT*，其中*InvokeFunction*是的名称你BizTalk 项目。 *OracleDBBindingSchema*是为 CREATE_ACCOUNT 函数生成的架构。|  
  
5.  重复上述步骤以创建新的消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InvokeFunction.OracleDBBindingSchema.CREATE_ACCOUNTResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用上的 Oracle 数据库的功能。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息，并通过 ODP 将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 将包含典型业务流程调用函数和 Oracle 数据库中的过程：  
  
-   发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
-   单向接收端口接收请求消息发送到 Oracle 数据库。  
  
-   双向发送端口发送请求消息到 Oracle 数据库和接收响应。  
  
-   单向发送端口将响应从 Oracle 数据库发送到的文件夹。  
  
 示例业务流程如下所示：  
  
 ![要调用 Oracle 中的函数的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/f102c81b-be2b-4e3c-89aa-25a4af5e6739.gif "f102c81b-be2b-4e3c-89aa-25a4af5e6739")  
  
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
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*FileIn.Function.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.Function.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.Function.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse.Function.Request*|  
  
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
 你必须启动的 BizTalk 应用程序调用一个 Oracle 数据库表中的函数。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须与你先前生成的函数的架构一致。 请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)为调用的请求消息架构有关的详细信息函数使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 例如，要调用 CREATE_ACCOUNT 函数的请求消息是：  
  
```  
<CREATE_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <ACCT>  
    <ACCTID xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT"></ACCTID>  
    <NAME xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">John Smith</NAME>  
    <BALANCE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">10000</BALANCE>  
  </ACCT>  
  <ADDR>  
    <STREET xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">BelRed Road</STREET>  
    <CITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">Redmond</CITY>  
    <STATE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">WA</STATE>  
  </ADDR>  
</CREATE_ACCOUNT>  
```  
  
 业务流程使用该消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。 例如，来自 Oracle 数据库以实现更高版本的请求消息的响应是：  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<CREATE_ACCOUNTResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
<CREATE_ACCOUNTResult>[ID]</CREATE_ACCOUNTResult>  
</CREATE_ACCOUNTResponse>  
```  
  
 其中，[ID] 是帐户的由该函数创建的 ID。  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到时调用函数和过程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>另请参阅  
[对开发 BizTalk 应用程序与 Oracle 数据库的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)