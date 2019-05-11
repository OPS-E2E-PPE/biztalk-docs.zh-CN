---
title: 从 SQL Server 使用 BizTalk Server 接收强类型基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6e6ba7e-9e13-4e28-b57d-d24569277bbc
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73916c93caec06870ffeca0ad33ffe837d38a14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368273"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>从 SQL Server 使用 BizTalk Server 接收强类型基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收强类型的轮询消息。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。  
  
 在方案中必须使用强类型轮询你想要将轮询消息中的元素映射到任何其他架构。 用于 SQL Server 上的另一操作可能是你想要将映射到的架构。 例如，你可以将轮询消息中的某些元素映射到另一个表插入操作的架构。 因此，轮询消息中的值用作参数的 Insert 操作。 在简单方案中，可以将强类型的轮询消息的架构映射到的架构文件，只需将存储的信息。  
  
> [!IMPORTANT]
>  如果想要在单个 BizTalk 应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。 使用唯一连接 URI，可以创建多个接收端口的同一个数据库或甚至同一个表在数据库中的轮询一次。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从使用 Biztalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。  
  
 有关如何在适配器支持强类型轮询的详细信息，请参阅[支持的轮询](https://msdn.microsoft.com/library/dd788416.aspx)。 有关强类型轮询的消息架构的详细信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。  
  
## <a name="how-this-topic-demonstrates-strongly-typed-polling"></a>本主题演示强类型轮询的方式  
 本主题演示如何使用强类型轮询来轮询消息映射到另一个架构。 本主题演示如何创建 BizTalk 项目，并生成的架构**TypedPolling**操作。 生成架构之前**TypedPolling**操作，必须执行以下操作：  
  
- 必须指定**InboundID**连接 URI 的一部分。  
  
- 必须指定的轮询语句**PollingStatement**属性绑定。  
  
  轮询语句的一部分，请执行以下操作：  
  
- 从 Employee 表选择所有行。  
  
- 执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。  
  
- 执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。 此过程将雇员姓名、 designation 和薪金作为参数。  
  
  若要执行这些操作，必须指定以下**PollingStatement**绑定属性：  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 由于生成的架构**TypedPolling**操作，该架构是强类型化，并包含将轮询消息中包含的所有元素。  
  
 作为同一个 BizTalk 项目的一部分，添加另一个架构文件，例如 EmployeeDetails.xsd。 EmployeeDetails.xsd 的架构如下所示：  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://Typed_Polling.EmployeeDetails" elementFormDefault="qualified" targetNamespace="http://Typed_Polling.EmployeeDetails" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="EmployeeDetails">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Employee_Info" type="xs:string" />   
        <xs:element name="Employee_Profile" type="xs:string" />   
        <xs:element name="Employee_Performance" type="xs:string" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 您还添加到项目，以将映射到 EmployeeDetails.xsd 架构中的元素的元素从 Employee 表 （收到轮询消息） 的 BizTalk 映射器。 作为该映射的一部分，您将轮询消息中的一个或多个元素组合，并将其映射到 EmployeeDetails 架构中的单个元素。 可以通过使用执行操作**字符串连接**functoid。  
  
 最后，BizTalk 项目的一部分作为符合 EmployeeDetails.xsd 架构将文件放到 FILE 发送端口。  
  
## <a name="configure-typed-polling-with-the-sql-adapter-binding-properties"></a>配置与 SQL 适配器的绑定属性的类型化的轮询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 以外**PollingStatement**绑定属性，在本部分中列出的所有其他绑定属性所需配置中的接收端口时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须指定**PollingStatement**属性绑定生成架构之前**TypedPolling**操作。  
  
> [!NOTE]
>  对于类型化的轮询，必须指定**PollingStatement**绑定生成架构时保留属性。 您可以选择指定其他绑定属性也生成架构时，即使它们不是必需的。 如果您指定的绑定属性，端口绑定文件中的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。 稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF SQL 属性已设置对绑定接收端口。 有关创建使用该绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
|         绑定属性         |                                                                                                                                                                                                                                                                                                   Description                                                                                                                                                                                                                                                                                                    |
|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                  指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。 默认值是**轮询**。 若要接收强类型的轮询消息，请将此设置为**TypedPolling**。                                                                                                                                                                                                   |
| **PolledDataAvailableStatement** |                                                                                                                                                 指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 SQL 语句必须返回的结果集由行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。                                                                                                                                                 |
|   **PollingIntervalInSeconds**   |                                                                                   指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。                                                                                    |
|       **PollingStatement**       | 指定要轮询 SQL Server 数据库表的 SQL 语句。 您可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 NULL。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。 可以指定任意数量的以分号分隔的 SQL 语句。<br /><br /> **重要提示：** 有关**TypedPolling**，生成元数据之前，必须指定此绑定属性。 |
|      **PollWhileDataFound**      |                                                                                      指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。                                                                                       |
  
 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读更多。  
  
## <a name="how-to-receive-strongly-typed-data-change-messages-from-the-sql-server-database"></a>如何接收来自 SQL Server 数据库的强类型化的数据更改消息  
 使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要配置要接收强类型化的数据更改消息的适配器，这些任务包括：  
  
1. 创建 BizTalk 项目，然后生成的架构**TypedPolling**操作。 必须指定**InboundID**连接属性和**PollingStatement**属性绑定在生成架构时。 例如，连接的 URI，使用指定的入站 ID 如下所示：  
  
   ```  
   mssql://mysqlserver//mysqldatabase?InboundID=mydatabaseId  
   ```  
  
2. 在从 SQL Server 数据库接收消息的 BizTalk 项目中创建一条消息。  
  
3. 创建业务流程从 SQL Server 数据库接收消息并将它们保存到一个文件夹。  
  
4. 在 BizTalk 项目中添加架构，例如，EmployeeDetails.xsd。  
  
5. 添加 BizTalk 映射器将映射到 EmployeeDetails.xsd 架构的轮询消息的架构。  
  
6. 生成并部署 BizTalk 项目。  
  
7. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
   > [!IMPORTANT]
   >  对于入站的轮询方案始终必须配置一个单向 WCF 自定义或 WCF SQL 接收端口。 双向 WCF 自定义或 WCF SQL 接收端口的入站操作不受支持。  
  
8. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，TypedPolling，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generate-schema"></a>生成架构  
 必须生成的架构**TypedPolling**操作。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。  
  
1.  指定**InboundID**连接属性，同时指定连接 URI。 对于本主题中，您可以指定**InboundID**作为**员工**。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
2.  为指定值**PollingStatement**属性绑定。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
     有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
3.  选择作为协定类型**服务 （入站操作）**。  
  
4.  生成架构**TypedPolling**操作。  
  
## <a name="define-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，必须创建一条消息从 SQL Server 数据库接收消息。  
  
 执行以下步骤创建消息并将其链接到架构。  
  
#### <a name="create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**PollingMessage**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Typed_Polling.TypedPolling_Employee.TypedPolling*，其中*Typed_Polling*是 BizTalk 的名称项目。 *TypedPolling_Employee*是为生成的架构**TypedPolling**操作。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于接收基于轮询的数据更改消息从 SQL Server 数据库。 在此业务流程，该适配器接收指定的轮询语句轮询消息。 然后，BizTalk 映射器将轮询消息架构映射到 EmployeeDetails.xsd 架构。 映射的消息然后保存到文件位置。 将包含一个典型的业务流程用于接收从 SQL Server 数据库的强类型的轮询消息：  
  
- 接收和发送形状从 SQL Server 接收消息并将发送给 FILE 端口，分别。  
  
- 一个单向接收端口以接收来自 SQL Server 的消息。  
  
  > [!IMPORTANT]
  >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  
  
- 单向发送端口将从 SQL Server 数据库轮询响应发送到的文件夹。  
  
- 若要将轮询消息的架构映射到任何其他架构的 BizTalk 映射器。  
  
  示例业务流程如下所示。  
  
  ![业务流程的强&#45;类型化轮询](../../adapters-and-accelerators/adapter-sql/media/1db03859-b7f8-470c-9158-2be4da0b45ae.gif "1db03859-b7f8-470c-9158-2be4da0b45ae")  
  
### <a name="add-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveMessage|Send|-设置**名称**到*SaveMessage*|  
  
### <a name="add-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|SQLReceivePort|-设置**标识符**到*SQLReceivePort*<br /><br /> -设置**类型**到*SQLReceivePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|SaveMessagePort|-设置**标识符**到*SaveMessagePort*<br /><br /> -设置**类型**到*SaveMessagePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-to-ports"></a>输入操作形状的消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|设置**消息**到*PollingMessage*<br /><br /> 设置**操作**到*SQLReceivePort.TypedPolling.Request*|  
|SaveMessage|设置**消息**到*PollingMessage*<br /><br /> 设置**操作**到*SaveMessagePort.TypedPolling.Request*|  
  
 指定这些属性后，连接的消息形状和端口。  
  
### <a name="add-a-biztalk-mapper"></a>添加 BizTalk 映射器  
 必须将 BizTalk 映射器添加到业务流程，以将轮询消息架构映射到 EmployeeDetails.xsd 架构。 在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您将使用此映射器将映射到 EmployeeDetails.xsd 架构的轮询消息的架构。  
  

1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
    在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，例如`MapSchema.btm`。 单击 **“添加”**。  
  
2. 在源架构窗格中，单击**打开源架构**。  
  
3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择轮询消息的架构。 对于本主题中，选择 Typed_Polling.TypedPolling_Employee。 单击“确定” 。  
  
4. 在中**源架构的根节点**对话框中，选择 TypedPolling 并单击**确定**。  
  
5. 从目标架构窗格中，单击**打开目标架构**。  
  
6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并为 EmployeeDetails 选择架构。 对于本主题中，选择 Typed_Polling.EmployeeDetails。 单击“确定” 。  
  
7. 在轮询消息的源架构中，展开 TypedPollingResultSet0 节点和后续节点来查看轮询消息中返回的元素。 在目标架构中，展开 EmployeeDetails 节点以查看架构中的不同元素。 对于本主题中，您必须映射这样一种方式中的架构的：  
  
   - **Employee_ID**并**名称**在源中架构必须映射到**Employee_Info**目标架构中。  
  
   - **指定内容**并**Job_Description**在源中架构必须映射到**Employee_Profile**目标架构中。  
  
   - **评级**并**薪金**在源中架构必须映射到**Employee_Performance**目标架构中。  
  
     若要合并多个源架构中的节点并将它们映射到目标架构中的单个节点，必须使用**String Concatenate functoid**。 详细信息[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
8. 若要使用字符串连接 functoid:  
  
   1.  从**工具箱**，拖动**字符串连接**functoid 并将其放在映射器网格。  
  
   2.  连接**Employee_ID**并**名称**至该 functoid 将源架构中的元素。  
  
   3.  连接到 functoid **Employee_Info**目标架构中的元素。  
  
   4.  你想要映射的所有元素重复这些步骤。 完成后的映射将如下所示：  
  
        ![将强类型的轮询架构映射](../../adapters-and-accelerators/adapter-sql/media/0a4a2608-3b84-4bac-9a16-512cf42c7525.gif "0a4a2608-3b84-4bac-9a16-512cf42c7525")  
  
   5.  保存该映射。  
  
   在创建映射器后，业务流程已完成。 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configure-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 单向接收端口。 此端口将轮询指定的端口的轮询语句与 SQL Server 数据库。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  请确保指定**InboundID**连接 URI 的一部分。 入站的 ID 必须是相同的生成架构时指定。  
    > 
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果指定在设计时的绑定属性。 在这种情况下，您可以创建 WCF 自定义或 WCF SQL 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|请确保将其设置为**TypedPolling**。|  
    |**PolledDataAvailableStatement**|请确保指定的架构，这是在生成时指定的同一 SQL 语句：<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|请确保提供的架构，这是在生成时指定的相同轮询语句：<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以执行以便通过将服务添加行为时配置 WCF 自定义或 WCF SQL 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和使用 SQL 事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。  
  
  - 定义 FILE 发送端口适配器放置消息的位置。 此发送端口还将使用轮询消息映射到符合 EmployeeDetails.xsd 架构的消息在业务流程中创建的映射。 执行以下步骤以配置 FILE 发送端口以使用映射。  
  
    1.  创建 FILE 发送端口。  
  
    2.  从发送端口属性对话框的左窗格中，单击**出站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**MapSchema**。 单击“确定” 。  
  
         ![FILE 发送端口上配置出站映射](../../adapters-and-accelerators/adapter-sql/media/831c9aee-fd97-466f-9270-3b04dbccd9fe.gif "831c9aee-fd97-466f-9270-3b04dbccd9fe")  
  
## <a name="start-the-application"></a>启动应用程序  
 必须启动 SQL Server 数据库中接收消息的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF-SQL 单向接收端口，轮询 SQL Server 数据库使用为指定的语句**PollingStatement**绑定属性，正在运行。  
  
-   FILE 发送端口，这将映射到 EmployeeDetails 架构的轮询消息，正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="execute-the-operation"></a>执行此操作  
 运行应用程序后，以下组操作需要置于相同的序列：  
  
- 适配器将执行**PolledDataAvailableStatement**对 Employee 上表，确定此表具有用于轮询的记录。  
  
- 适配器执行轮询语句。 轮询语句包含 SELECT 语句和存储的过程，因为该适配器将在它们执行所有语句一个。  
  
  - 适配器首先执行 SELECT 语句中的 Employee 表返回所有记录。  
  
  - 然后，适配器执行将所有数据从 Employee 表都移动到 EmployeeHistory 表 MOVE_EMP_DATA 存储过程。 此存储的过程不返回任何值。  
  
  - 然后，适配器执行将一条记录添加到 Employee 表的 ADD_EMP_DETAILS 存储过程。 此存储的过程返回插入的记录的员工 ID。  
  
    执行轮询语句和接收消息后，轮询消息获取到 FILE 发送端口发送。 此处，出站映射 (**MapSchema**) 配置上的发送端口映射到 EmployeeDetails 架构的轮询消息并且会将消息放到某个文件位置。 该消息类似于以下内容：  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <EmployeeDetails xmlns="http://Typed_Polling.EmployeeDetails">  
    <Employee_Info>10751John</Employee_Info>   
    <Employee_Profile>TesterManagesTesting</Employee_Profile>   
    <Employee_Performance>100000</EmployeePerformance>  
  </EmployeeDetails>  
  ```  
  
   在前面的响应中，可以注意到 Employee_Info 元素包含雇员 ID (10751) 和雇员姓名 (John) 的组合。 其他元素也包含在映射器中的业务流程一部分创建映射的组合。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
 [通过使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)