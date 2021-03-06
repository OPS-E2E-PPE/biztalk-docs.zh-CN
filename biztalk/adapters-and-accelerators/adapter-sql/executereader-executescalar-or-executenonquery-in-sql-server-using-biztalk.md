---
title: ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8def133-cbe1-4648-ae41-6b8ce6640cb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2eb2ee60bd327cc00eb1cadaa56b22f4d29499a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369472"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-biztalk-server"></a>ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]如公开泛型 SQL Server 操作**ExecuteNonQuery**， **ExecuteReader**，并且**ExecuteScalar**。 这些操作可用于 SQL Server 数据库上执行任何 SQL 语句。 这些操作因的响应获取的 SQL 语句的类型。 有关适配器如何支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
 本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 可以按照同一套过程来执行本主题中所述**ExecuteNonQuery**并**ExecuteScalar**操作。  
  
## <a name="prerequisites"></a>先决条件  
  
- 创建[强名称密钥文件，并了解相关工具](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
- [配置 MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)运行的计算机上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server。
  
## <a name="invoke-the-executereader-operation-on-a-sql-server-database"></a>调用 ExecuteReader 操作的 SQL Server 数据库上  
 使用执行 SQL Server 数据库上的操作的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要调用**ExecuteReader** SQL Server 中的操作，这些任务是：  
  
1. 创建 BizTalk 项目，并生成的架构**ExecuteReader**操作。  
  
2. 用于发送和接收来自 SQL Server 的消息在 BizTalk 项目中创建消息。  
  
3. 创建一个业务流程调用 SQL Server 上的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generate-schema"></a>生成架构  
 本主题演示如何调用**ExecuteReader**操作中使用 SQL Server[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 **ExecuteReader**操作采用任何 SQL 语句作为参数并返回的数据集作为一个数组的操作的结果集。 本主题说明如何以 ADD_EMP_DETAILS 存储过程使用执行**ExecuteReader**操作。 此存储的过程将一条记录添加到 Employee 表，并返回新添加的员工的 ID。 通过运行这些示例提供的脚本创建的表和主题中使用的存储的过程。 有关脚本的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
 若要演示如何调用**ExecuteReader**操作，用于生成架构**ExecuteReader**操作。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="define-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在，为业务流程创建消息并将其链接到上一步中生成的架构。  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Execute_Reader.GenericOperation.ExecuteReader*，其中 Execute_Reader 是 BizTalk 项目的名称。 *GenericOperation*是为生成的架构**ExecuteReader**操作。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Execute_Reader.GenericOperation.ExecuteReaderResponse*。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 SQL Server 上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 您必须包括发送和接收形状将消息发送到 SQL Server 并将它们分别收到答复。 用于调用示例业务流程**ExecuteReader**操作如下所示：  
  
 ![调用 ExecuteReader 操作的业务流程](../../adapters-and-accelerators/adapter-sql/media/2ac8dc12-918a-4077-a95c-f66b1c0ef4f0.gif "2ac8dc12-918a-4077-a95c-f66b1c0ef4f0")  
  
### <a name="add-message-shapes"></a>添加消息形状  
 为每个消息形状中输入以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="add-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-them-to-ports"></a>消息输入到操作形状，并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.ExecuteReader.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.ExecuteReader.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.ExecuteReader.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.ExecuteReader.Request*|  
  
 指定这些属性后，连接的消息形状和端口，并在业务流程已完成。  
  
 现在，必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configure-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="start-the-application"></a>启动应用程序  
 启动 BizTalk 应用程序用于调用**ExecuteReader** SQL Server 数据库中的操作。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="execute-the-operation"></a>执行此操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构的架构必须符合**ExecuteReader**先前生成的操作。 例如，请求消息来调用使用 ADD_EMP_DETAILS **ExecuteReader**操作：  
  
```  
<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">  
  <Query>EXEC ADD_EMP_DETAILS Tom,Manager,100000</Query>  
</ExecuteReader>  
```  
  
 请参阅[ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息架构](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)有关调用的请求消息架构的详细信息**ExecuteReader**操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
> [!NOTE]
>  在`<Query>`标记，可以指定以分号分隔的多个 SQL 语句。  
  
 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 为响应**ExecuteReader**操作包含一个结果集作为数据集数组。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">  
  <ExecuteReaderResult>  
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
            <Employee_ID>10767</Employee_ID>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </DataSet>  
  </ExecuteReaderResult>  
</ExecuteReaderResponse>  
```  
  
 在响应中，10767 是员工的新创建的 ID。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)