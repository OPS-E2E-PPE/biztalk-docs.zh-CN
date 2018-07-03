---
title: 插入、 更新、 删除或选择 BizTalk Server 中使用 Oracle 数据库的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing basic operations using BizTalk Server
ms.assetid: debf450e-0936-42bb-b071-89d17e6e5da2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4aaaca2945fe3efc8ee26bfbcf976fc55f5e8c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988814"
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-oracle-database"></a>插入、 更新、 删除或选择 BizTalk Server 中使用 Oracle 数据库的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组标准 Oracle 数据库表和视图的操作。 这些称为数据操作语言 (DML) 操作操作使用它可以执行简单的 INSERT、 UPDATE、 SELECT 和 DELETE 语句由表和视图的 WHERE 子句限定。 有关适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择 Oracle 表和视图操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)。 DML 操作的 SOAP 消息结构的信息，请参阅[基本插入、 更新、 删除和选择表和视图操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
> [!NOTE]
>  若要执行更复杂的操作，例如运行参数化的 SQL SELECT 查询，可以使用 SQLEXECUTE 操作。 有关使用与 SQLEXECUTE 操作的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[通过使用 BizTalk Server 运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)。  
  
## <a name="how-to-perform-basic-operations-on-an-oracle-database"></a>如何针对 Oracle 数据库执行基本操作？  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发 BizTalk 应用程序](../../core/developing-biztalk-server-applications.md)。 若要在 Oracle 数据库中执行插入、 更新、 删除或选择表和视图操作，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要在 Oracle 数据库表或视图上调用该操作生成架构。  
  
2. 在 BizTalk 项目中为发送和接收消息从 Oracle 数据库创建消息。  
  
3. 创建一个业务流程调用上的 Oracle 数据库表或视图的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SelectAccTable，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，若要演示如何执行基本的 DML 操作，我们将记录从表中选择 ACCOUNTACTIVITY 下 SCOTT 架构的 Oracle 数据库中。 通过运行这些示例提供的 SQL 脚本在 SCOTT 架构下创建此表。 若要了解有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
 若要演示如何选择记录，我们生成 SCOTT 架构下 ACCOUNTACTIVITY 表选择操作的架构。 请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图窗口。  
  
 对于本主题中，您必须创建两条消息，另一个用于将请求发送到 Oracle 数据库，另一个用于接收响应。  
  
 执行以下步骤来创建消息并将其链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息，然后选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectAccTable.OracleDBBindingSchema.Select*，其中*SelectAccTable*是 BizTalk 的名称项目。 *OracleDBBindingSchema*是 ACCOUNTACTIVITY 表选择操作生成的架构。|  
  
5.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SelectAccTable.OracleDBBindingSchema.SelectResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 Oracle 数据库上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息并通过 ODP 将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 执行对 Oracle 数据库的基本表操作的一个典型的业务流程将包含：  
  
- 发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
- 一个单向接收端口接收请求消息将发送到 Oracle 数据库。  
  
- 一个双向发送端口以发送请求消息到 Oracle 数据库和接收响应。  
  
- 一个单向发送端口用于从 Oracle 数据库将响应发送到的文件夹。  
  
  选择操作的示例业务流程如下所示：  
  
  ![用于 Oracle 上的选择操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/444149d7-536d-40a8-8db4-e1410bb4689b.gif "444149d7-536d-40a8-8db4-e1410bb4689b")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInPort*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br />-设置**类型**到*SaveResponseType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*FileIn.Select.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.Select.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.Select.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.Select.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库。 您必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 Wcf-oracledb 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动从 Oracle 数据库表中选择记录的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 选择操作之前生成的架构必须符合请求消息的架构。 例如，要从 ACCOUNTACTIVITY 表中具有等于 100001 帐户字段中选择记录的请求消息是：  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>ACCOUNT=100001</FILTER>  
</Select>  
```  
  
 请参阅[基本插入、 更新、 删除和选择表和视图操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)详细了解请求消息架构执行对 Oracle 数据库的基本 DML 操作的表和视图使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 业务流程使用该消息并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置。 例如，从 Oracle 数据库以实现更高版本的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
  <SelectResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <SelectResult>  
      <ACCOUNTACTIVITYRECORDSELECT>  
        <TID>1</TID>   
        <ACCOUNT>100001</ACCOUNT>   
        <AMOUNT>500</AMOUNT>   
        <DESCRIPTION />   
        <TRANSDATE>2007-10-16T16:58:44</TRANSDATE>   
        <PROCESSED>n</PROCESSED>   
        </ACCOUNTACTIVITYRECORDSELECT>  
      <ACCOUNTACTIVITYRECORDSELECT>  
        ….   
        ….  
      <ACCOUNTACTIVITYRECORDSELECT>  
      ….  
      ….    
    </SelectResult>  
  </SelectResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 执行 DML 操作使用时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)