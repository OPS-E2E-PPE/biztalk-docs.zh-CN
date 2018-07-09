---
title: 调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的记录类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdc150e-055a-47df-af3e-64931946455d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee3a55907fe2528e411ca11447e19fce9e79958
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998750"
---
# <a name="invoke-functions-and-procedures-with-record-types-in-oracle-database-using-biztalk-server"></a>调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的记录类型
Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。 详细了解如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持记录类型，请参阅[对函数和过程的 Oracle 数据库中的记录类型的操作。](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)。 记录类型的 XML 结构的信息，请参阅[记录类型的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>如何调用 Oracle 数据库中的函数？  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[构建基块来开发 BizTalk 应用程序与 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 要调用返回简单和嵌套的 Oracle 数据库中的函数记录类型，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要在 Oracle 数据库中调用该函数生成架构。  
  
2. 在 BizTalk 项目中为发送和接收消息从 Oracle 数据库创建消息。  
  
3. 创建一个业务流程调用的 Oracle 数据库中的函数。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，Func_RecordTypes，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何将[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持调用函数返回记录的类型的参数，我们将调用：  
  
- 返回一个简单的记录类型的 GET_ACCOUNTADDRESS 函数。  
  
- 返回嵌套的记录类型的 GET_ACCOUNTINFO 函数。  
  
  这些函数是可通过在运行这些示例提供的 SQL 脚本 ACCOUNT_PKG 的一部分。 若要了解有关这些示例和 SQL 脚本的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
  因此，我们必须生成这两个函数，GET_ACCOUNTADDRESS 和 GET_ACCOUNTINFO，SCOTT\Package\ACCOUNT_PKG 架构下提供的架构。 请参阅[检索用于 Oracle 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图窗口。  
  
 对于本主题中，您必须创建两个请求-响应消息集-一个请求-响应设置来调用 GET_ACCOUNTADDRESS 函数并接收响应;另一条请求-响应消息设置为调用 GET_ACCOUNTINFO 函数并接收响应。  
  
 执行以下步骤来创建消息并将其链接到该架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息，然后依次**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFO*，其中*Func_RecordTypes*的名称在BizTalk 项目。 *OracleDBBindingSchema*是为 GET_ACCOUNTADDRESS 函数生成的架构。|  
  
5.  重复上述步骤创建三个更多的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |响应|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFOResponse*|  
    |请求 2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESS*|  
    |Response2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对调用函数返回简单和复杂的记录类型。 在此业务流程，你删除两个请求消息：  
  
- 一个用于返回简单的记录类型的 GET_ACCOUNTADDRESS 函数。  
  
- 一个用于返回嵌套的记录类型的 GET_ACCOUNTINFO 函数。  
  
  这些消息的接收位置将被删除。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息并通过 ODP 将它们传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 因为业务流程提取两个请求的同时，您需要在业务流程中包括并行操作形状。 对于每个并行操作，必须包括发送和接收形状将消息发送到 Oracle 数据库和接收响应，分别。 但是，您可以使用相同的端口来发送和接收这两种操作的消息。 将包含一个典型的业务流程的同时执行这两项操作：  
  
- 发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
- 一个单向接收端口接收请求消息将发送到 Oracle 数据库。  
  
- 一个双向发送端口以发送请求消息到 Oracle 数据库和接收响应。  
  
- 一个单向发送端口用于从 Oracle 数据库将响应发送到的文件夹。  
  
  示例业务流程如下所示：  
  
  ![用于使用 Oracle 中的记录类型的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/6ee5e57b-48d5-435a-a16b-83bac878d0b7.gif "6ee5e57b-48d5-435a-a16b-83bac878d0b7")  
  
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
  
|端口|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br />-设置**类型**到*SaveResponseType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
 因为您将处理这两个请求和响应消息使用这些端口，则必须创建每个端口，其中每个操作对应于一种消息类型的两个操作。 若要创建一个操作，右键单击端口形状，然后选择**新的操作**。 命名为每个端口的第一个操作**NestedRecType**并为每个端口的第二个操作**SimpleRecType**。  
  
### <a name="using-correlations"></a>使用关联  
 相关是将传入消息与业务流程的相应实例相匹配的过程。 将删除您在业务流程中两个请求消息，一个用于每个重载。 要使用相关，与正确的业务流程关联的请求消息。 有关相关的详细信息，请参阅[业务流程中使用相关性](../../core/using-correlations-in-orchestrations.md)  
  
##### <a name="to-use-correlations"></a>若要使用的相关性  
  
1.  从每个函数生成的架构升级属性。 例如，从 GET_ACCOUNTADDRESS 函数; 架构升级 CUSTNAME 属性将从 GET_ACCOUNTINFO 函数的架构提升的辅助设备属性。 若要将属性升级，右键单击架构视图中的属性，指向**Promote**，然后选择**快速升级**。 这将 PropertySchema.xsd 文件添加到您的 BizTalk 项目。  
  
     有关提升的属性的信息，请参阅[升级属性](../../core/promoting-properties.md)。  
  
2.  从业务流程视图中，右键单击**相关类型**，然后选择**新相关类型**。  
  
3.  **相关性属性**对话框会列出升级在步骤 1 中的属性。 选择一个属性，然后依次**添加**。  
  
4.  单击“确定” 。  
  
5.  若要创建其他升级属性的相关类型，请重复这些步骤。  
  
6.  重命名基于到它们所关联的属性的相关类型。 你可以重命名为相关类型*CorrelationType_CUSTNAME* （适用于 CUSTNAME 属性） 和*CorrelationType_AID* （适用于帮助属性）。  
  
7.  从业务流程视图中，右键单击**相关集**，然后选择**新建相关集**。  
  
8.  右键单击新添加的相关集，然后依次**属性**。 在中**属性**窗格中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*Func_RecordTypes.CorrelationType_CUSTNAME*|  
    |Identifier|*Correlation_CUSTNAME*|  
  
9. 添加另一个相关集，并指定以下属性从**属性**窗格。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |相关类型|*Func_RecordTypes.CorrelationType_AID*|  
    |Identifier|*Correlation_AID*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定的属性和它们应设置为指定操作形状的消息并将其链接到的端口的值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**初始化相关集**到*Correlation_AID*<br />-设置**消息**到*请求*<br />-设置**操作**到*FileIn.NestedRecType.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.NestedRecType.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.NestedRecType.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.NestedRecType.Request*|  
|ReceiveMessage2|-设置**初始化相关集**到*Correlation_CUSTNAME*<br />-设置**消息**到*请求 2*<br />-设置**操作**到*FileIn.SimpleRecType.Request*|  
|SendMessage2|-设置**消息**到*请求 2*<br />-设置**操作**到*LOBPort.SimpleRecType.Request*|  
|ReceiveResponse2|-设置**消息**到*Response2*<br />-设置**操作**到*LOBPort.SimpleRecType.Response*|  
|SendResponse2|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.SimpleRecType.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
- 硬盘和相应的文件端口请求消息，一个用于每个重载过程将存放上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
- 硬盘和相应的 BizTalk 业务流程放置响应消息，一个用于每个函数，其中包含从 Oracle 数据库的响应的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库。 您必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 Wcf-oracledb 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 由于 WCF 自定义或 Wcf-oracledb 发送端口发送和接收符合多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。 对于此业务流程，应将操作设置，如下所示：  
  
    ```  
    <BtsActionMapping>  
      <Operation Name="NestedRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO" />  
      <Operation Name="SimpleRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS" />  
    </BtsActionMapping>  
    ```  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动调用的函数为 Oracle 数据库表中的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须删除两个请求的文件 （一个用于每个函数） 消息的接收位置。 请求消息的架构必须符合先前生成的函数的架构。 业务流程使用的请求消息并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置。  
  
 请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)的调用的请求消息架构有关的详细信息函数使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 例如，要调用 GET_ACCOUNINFO 函数的请求消息是：  
  
```  
<GET_ACCOUNTINFO xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <AID>100000</AID>  
</GET_ACCOUNTINFO>  
```  
  
 同样，要调用 GET_ACCOUNTADDRESS 函数的请求消息是：  
  
```  
<GET_ACCOUNTADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CUSTNAME>Mindy Martin</CUSTNAME>  
</GET_ACCOUNTADDRESS>  
```  
  
 第一个请求消息调用 GET_ACCOUNTINFO 函数返回嵌套的记录类型。 用于调用 GET_ACCOUNTINFO 函数响应消息为：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GET_ACCOUNTINFOResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTINFOResult>  
    <ACCT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <ACCTID>100000</ACCTID>   
      <NAME>Kim Ralls</NAME>   
      <BALANCE>10000</BALANCE>   
    </ACCT>  
    <ADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <STREET>1234 Main St.</STREET>   
      <CITY>Seattle</CITY>   
      <STATE>WA</STATE>   
    </ADDRESS>  
  </GET_ACCOUNTINFOResult>  
</GET_ACCOUNTINFOResponse>  
```  
  
 第二个请求消息调用 GET_ACCOUNTADDRESS 函数返回一个简单的记录类型。 用于调用 GET_ACCOUNTADDRESS 函数响应消息为：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTADDRESSResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTADDRESSResult>  
    <ID xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">100004</ID>  
    <NAME xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">Mindy Martin</NAME>  
    <STREET xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">6789 Cherry St.</STREET>  
    <CITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">New York</CITY>  
    <STATE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">NY</STATE>  
  </GET_ACCOUNTADDRESSResult>  
</GET_ACCOUNTADDRESSResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 调用函数或过程使用时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理与 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[向开发 BizTalk 应用程序与 Oracle 数据库的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)