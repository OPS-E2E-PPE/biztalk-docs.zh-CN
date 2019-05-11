---
title: 在 SQL Server 使用 BizTalk Server 中执行存储的过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4329a5c1-4df9-4bf7-8a9f-e3c19cb368fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d182d74d0fa8b694483917a3429e56e0bc375211
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369635"
---
# <a name="execute-stored-procedures-in-sql-server-using-biztalk-server"></a>在 SQL Server 使用 BizTalk Server 中执行存储的过程
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]显示 SQL Server 数据库中作为操作的过程。 适配器客户端可以通过使用调用过程[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关适配器如何支持这些操作的详细信息，请参阅[使用 SQL 适配器的 SQL Server 中执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-the-sql-adapter.md)。 有关这些操作的 SOAP 消息结构的信息，请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]还使适配器客户端能够调用：  
  
-   SQL Server 数据库中的标量函数。 请参阅[SQL Server 使用 BizTalk Server 中调用标量函数](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-using-biztalk-server.md)。  
  
-   SQL Server 数据库中的表值函数。 请参阅[Invoke Table-Valued 函数中使用 BizTalk Server 的 SQL Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="how-to-invoke-procedures-in-sql-server-database"></a>如何调用 SQL Server 数据库中的过程  
 使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要调用 SQL Server 数据库中的过程，这些任务包括：  
  
- 创建 BizTalk 项目，并生成为你想要在 SQL Server 数据库中调用的过程的架构。  
  
- 在从 SQL Server 数据库发送和接收消息的 BizTalk 项目中创建的消息。  
  
- 创建一个业务流程调用 SQL Server 数据库中的过程。  
  
- 生成并部署 BizTalk 项目。  
  
- 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
- 启动 BizTalk 应用程序。  
  
  本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，ExecuteStoredProcedure，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用过程，通过调用 ADD_EMP_DETAILS 过程。 此过程是通过运行这些示例提供的脚本创建的。 ADD_EMP_DETAILS 过程采用某些参数、 EMPLOYEE 表中插入一条记录并返回雇员 ID 插入记录。 有关示例和 SQL 脚本的信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 若要调用 ADD_EMP_DETAILS 过程，它是生成相同的过程的架构所必需。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到你在上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ExecProcedure.Procedure_dbo。ADD_EMP_DETAILS*，其中 ExecProcedure 是 BizTalk 项目的名称。 Procedure_dbo 是为调用 ADD_EMP_DETAILS 过程生成的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ExecProcedure.Procedure_dbo。ADD_EMP_DETAILSResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 SQL Server 上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 必须包括发送和接收形状将消息发送到 SQL Server 和接收响应，分别。 示例业务流程的调用的过程类似于以下内容：  
  
 ![用于调用过程的业务流程](../../adapters-and-accelerators/adapter-sql/media/698730c1-6aa9-49f3-97b3-adb5e6537300.gif "698730c1-6aa9-49f3-97b3-adb5e6537300")  
  
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
  
|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.Procedure.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.Procedure.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.Procedure.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.Procedure.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须在 SQL Server 数据库启动过程的调用的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合前面生成的过程的架构。 例如，要调用 GET_EMP_DETAILS 的请求消息是：  
  
```  
<ADD_EMP_DETAILS xmlns="mssql://Microsoft.LobServices.Sql/2008/01/Procedures/dbo">  
  <emp_name>John</emp_name>  
  <emp_desig>Developer</emp_desig>  
  <salary>100000</salary>  
</ADD_EMP_DETAILS>  
```  
  
 请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)详细了解 SQL Server 中的过程调用的请求消息架构数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<ADD_EMP_DETAILSResponse xmlns="mssql://Microsoft.LobServices.Sql/2008/01/Procedures/dbo">  
  <ADD_EMP_DETAILSResult>  
    <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:schema>  
      <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            <Employee_ID>10001</Employee_ID>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </DataSet>  
  </ADD_EMP_DETAILSResult>  
  <ReturnValue>0</ReturnValue>   
</ADD_EMP_DETAILSResponse>  
```  
  
 在上述响应中`<Employee_ID>`元素包含插入的记录的雇员 ID。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)