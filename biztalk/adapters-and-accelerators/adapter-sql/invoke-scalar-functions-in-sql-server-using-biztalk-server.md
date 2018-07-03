---
title: 调用标量函数中使用 BizTalk Server 的 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70bb7be9-ae31-4505-9406-f9d4744b65e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7ad0d193f3445fd751c7893277588348342802
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979046"
---
# <a name="invoke-scalar-functions-in-sql-server-using-biztalk-server"></a>调用 SQL Server 使用 BizTalk Server 中的标量函数
可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]来调用 SQL Server 中的标量函数。 该适配器将标量函数公开为可直接在 SQL Server 调用的操作。 有关如何在适配器支持标量函数的详细信息，请参阅[执行 SQL Server 使用 SQL 适配器中的标量函数](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)。 用于调用标量函数的 SOAP 消息的结构有关的信息，请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)。  
  
## <a name="prerequisites"></a>必要條件  
  
- 创建[强名称密钥文件，并了解相关工具](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
- [配置 MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)运行的计算机上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server。
  
## <a name="invoke-scalar-functions-on-sql-server-database"></a>调用 SQL Server 数据库上的标量函数  
 使用执行 SQL Server 数据库上的操作的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要调用 SQL Server 中的标量函数，这些任务包括：  
  
1. 创建 BizTalk 项目，并生成了你想要在 SQL Server 中调用标量函数的架构。  
  
2. 用于发送和接收来自 SQL Server 的消息在 BizTalk 项目中创建消息。  
  
3. 创建一个业务流程调用 SQL Server 上的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generate-schema"></a>生成架构  
 本主题演示如何使用 SQL Server 中的标量函数中调用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 为了演示此操作，本主题中执行 GET_EMP_ID 函数。 此函数接受雇员的名称作为参数并返回该员工从 EMPLOYEE 表的 ID。 通过运行这些示例提供的脚本创建表和函数。 有关脚本的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
 若要演示如何调用标量函数，为 GET_EMP_ID 标量函数生成架构。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于在 Visual Studio 中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="define-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在，为业务流程中，创建消息并将其链接到上一步中生成的架构。    
 
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ScalarFunction.ScalarFunction_dbo。GET_EMP_ID*，其中 ScalarFunction 是 BizTalk 项目的名称。 ScalarFunction_dbo 是为 GET_EMP_ID 函数生成的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ScalarFunction.ScalarFunction_dbo。GET_EMP_IDResponse*。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 SQL Server 上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 您必须包括发送和接收形状将消息发送到 SQL Server 并将它们分别收到答复。 用于调用标量函数的示例业务流程如下所示：  
  
 ![用于调用标量函数的业务流程](../../adapters-and-accelerators/adapter-sql/media/9f69c9b9-2466-46d5-8423-1ccdc37a93fb.gif "9f69c9b9-2466-46d5-8423-1ccdc37a93fb")  
  
### <a name="add-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="add-ports"></a>添加端口  
 为每个逻辑端口输入以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.ScalarFunction.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.ScalarFunction.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.ScalarFunction.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.ScalarFunction.Request*|  
  
 输入这些属性后，连接的消息形状和端口，并在业务流程已完成。  
  
 现在，生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configure-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
   
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="start-the-application"></a>启动应用程序  
 启动 BizTalk 应用程序用于调用 SQL Server 数据库中的标量函数。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="execute-the-operation"></a>执行此操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合 GET_EMP_ID 函数前面生成的架构。 例如，要调用 GET_EMP_ID 函数的请求消息是：  
  
```  
<GET_EMP_ID xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <emp_desig>Manager</emp_desig>  
</GET_EMP_ID>  
```  
  
 此请求消息调用 GET_EMP_ID 函数以检索标识"Manager"员工 ID。 请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)详细了解用于调用标量函数中使用 SQL Server 的请求消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_EMP_IDResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <GET_EMP_IDResult>10072</GET_EMP_IDResult>  
</GET_EMP_IDResponse>  
```  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)