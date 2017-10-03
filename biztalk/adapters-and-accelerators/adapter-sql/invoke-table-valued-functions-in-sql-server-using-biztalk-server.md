---
title: "调用 SQL Server 使用 BizTalk Server 中的表值函数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d360c15-699e-4859-8143-798c1de821db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24713b4df4064c788651b0b34397a58c110b0d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-table-valued-functions-in-sql-server-using-biztalk-server"></a>调用 SQL Server 使用 BizTalk Server 中的表值函数
你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用 SQL Server 中的表值函数。 适配器将表值函数公开为可以直接在 SQL Server 调用的操作。 有关如何适配器支持表值函数的详细信息，请参阅[Executing Table-Valued 函数中使用的 SQL 适配器的 SQL Server](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)。 为了调用表值函数的 SOAP 消息结构的信息，请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   创建[强名称密钥文件中，并了解工具](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
-   [配置 MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)运行的计算机上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server。
  
## <a name="invoke-table-valued-functions-on-a-sql-server-database"></a>调用 SQL Server 数据库上的表值函数  
 通过使用执行 SQL Server 数据库上的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要调用 SQL Server 中的表值函数，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成你想要在 SQL Server 中调用表值的函数的架构。  
  
2.  在发送和接收消息从 SQL Server 的 BizTalk 项目中创建消息。  
  
3.  创建业务流程以调用 SQL Server 上的操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generate-schema"></a>生成架构  
 本主题演示如何调用表值函数中使用 SQL Server[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 为了演示此操作，本主题中执行 TVF_EMPLOYEE 函数。 此函数采用员工的代码作为参数并返回具有该标志，为的表类型的所有员工记录。 通过运行这些示例提供的脚本会创建员工表和函数。 有关的脚本的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
 为了演示如何调用表值函数，架构生成 TVF_EMPLOYEE 表值函数的方法。 您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="define-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在，创建业务流程的消息，并将它们链接到你在上一步中生成的架构。  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*TableFunctions.TableValuedFunction_dbo。TVF_EMPLOYEE*，其中 TableFunctions 是 BizTalk 项目的名称。 TableValuedFunction_dbo 是为 TVF_EMPLOYEE 函数生成的架构。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*TableFunctions.TableValuedFunction_dbo。TVF_EMPLOYEEResponse*。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 创建 BizTalk 业务流程中，若要使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 SQL Server 上执行操作。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 你必须包括发送和接收形状将消息发送到 SQL Server，并接收响应，分别。 调用表值函数示例业务流程如下所示：  
  
 ![业务流程调用表 &#45; 值函数](../../adapters-and-accelerators/adapter-sql/media/28ca3930-7ce8-423a-9edd-cb2888eebaac.gif "28ca3930-7ce8-423a-9edd-cb2888eebaac")  
  
### <a name="add-message-shapes"></a>添加消息形状  
 为每个消息形状中输入以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="add-ports"></a>添加端口  
 为每个逻辑端口输入以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-them-to-ports"></a>对于操作形状，输入消息和将其连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.TVF.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.TVF.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.TVF.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.TVF.Request*|  
  
 指定这些属性后，消息形状和端口将连接，并且您的业务流程已完成。  
  
 现在，生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configure-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。 
 
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到的 SQL Server 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="start-the-application"></a>启动应用程序  
 启动 SQL Server 数据库中的 BizTalk 应用程序调用表值函数。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   正在运行的 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="execute-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须与你先前生成的 TVF_EMPLOYEE 表值的函数的架构一致。 例如，要调用 TVF_EMPLOYEE 函数的请求消息是：  
  
```  
<TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/dbo">  
  <emp_desig>Tester</emp_desig>  
</TVF_EMPLOYEE>  
```  
  
 此请求消息时，将调用 TVF_EMPLOYEE 函数以检索具有指定为"测试人员"的员工记录。 请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)有关为了调用表值函数中使用 SQL Server 的请求消息架构的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
> [!NOTE]
>  如果不指定参数的值适配器内部执行中使用 DEFAULT 关键字，这意味着如果可用，适配器，执行通过传递参数，默认值的函数的函数作为函数定义的一部分。  
  
 业务流程使用该消息，并将其发送到的 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置中。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<TVF_EMPLOYEEResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/dbo">  
  <TVF_EMPLOYEEResult>  
    <TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/TableFunctionReturnTables/dbo">  
      <Employee_ID>10499</Employee_ID>   
      <Name>John</Name>   
      <Designation>Tester</Designation>   
      <Salary>999999.00</Salary>   
      <Last_Modified>AAAAAAAAJBM=</Last_Modified>   
    </TVF_EMPLOYEE>  
    <TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/TableFunctionReturnTables/dbo">  
      ......  
      ......  
    </TVF_EMPLOYEE>  
    ......  
    ......  
  </TVF_EMPLOYEEResult>  
</TVF_EMPLOYEEResponse>  
```  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
[开发使用 SQL 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)