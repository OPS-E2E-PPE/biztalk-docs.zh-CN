---
title: 使用 SQL 适配器的大型数据类型包含运行操作表和视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cec15b01-7a57-4917-8c21-44a1cfaadc59
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c1bc305e45747c4471894cc362ebeeec2ee36a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013102"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter"></a>使用 SQL 适配器的大型数据类型包含运行操作表和视图
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端读取和更新的大型数据类型列中的数据，它是、 varchar （max）、 nvarchar （max） 或 varbinary （max）。 若要从这样的列读取数据，适配器客户端可以使用选择的操作。 若要插入或更新到此类列的数据，该适配器公开设置 < column_name > 操作中，其中 < column_name > 是类型 varchar （max）、 nvarchar （max） 或 varbinary （max） 列的名称。  
  
 此外，在 SQL Server 2008 中，您可以存储非结构化的数据，例如文本文档和图像的 varbinay(max) 列。 此类非结构化的数据称为 FILESTREAM 数据。 FILESTREAM 数据可以存储为文件系统上的文件。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许客户端输入到类型 varbinary （max） 列的 FILESTREAM 数据。 有关 FILESTREAM 存储的详细信息，请参阅[FILESTREAM 概述](https://msdn.microsoft.com/library/bb933993(SQL.100).aspx)。  
  
 本主题提供有关特定任务的信息必须执行的计算机上运行 SQL Server 和运行适配器客户端将无法插入或更新 FILESTREAM 数据的计算机。 本主题还说明了执行集合 < column_name > 操作插入 FILESTREAM 数据。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="prerequisites"></a>必要條件  
 运行 SQL Server 的计算机和运行适配器客户端计算机上，必须执行以下任务。  

  
- **运行 SQL Server 的计算机上**  
  
  -   您必须对 SQL Server 实例启用 FILESTREAM。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=122486 ](http://go.microsoft.com/fwlink/?LinkId=122486)。  
  
  -   必须创建启用了 FILESTREAM 的数据库。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=122487 ](http://go.microsoft.com/fwlink/?LinkId=122487)。  
  
  -   您必须有一个表以存储 FILESTREAM 数据。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=122488 ](http://go.microsoft.com/fwlink/?LinkId=122488)。  
  
  -   承载 SQL Server 数据库的计算机上，必须配置 MSDTC。 有关如何配置 MSDTC 的说明，请参阅[SQL Server 和适配器客户端上配置 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
- **运行适配器客户端的计算机上**  
  
  -   您必须安装的 SQL 客户端连接 SDK。 可以通过运行 SQL Server 2008 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，随 SQL 客户端连接 SDK，用于执行 FILESTREAM 操作。  
  
  -   运行适配器客户端的计算机上，必须配置 MSDTC。 有关如何配置 MSDTC 的说明，请参阅[SQL Server 和适配器客户端上配置 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
  完成这些任务后，您将所有设置为插入或更新 SQL Server 2008 数据库表中的 FILESTREAM 数据。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>本主题演示对大型数据类型的操作的方式  
 若要演示如何设置 < column_name > 对表执行操作包含大型数据类型，使一个表，记录，其中包含列 Id 和文档。 为 uniqueidentifier 类型的 Id 列，并采用一个 GUID。 Varbinary （max） 类型的文档列。 假定 Id 列已有一个 GUID`438B7B4C-5491-409F-BCC1-78817C399EC3`。 若要更新的文档列，该适配器公开 SetDocument 操作。  
  
> [!NOTE]
>  对于 SQL Server 2008 中，以演示 FILESTREAM 操作，假定文档列可以存储 FILESTREAM 数据。  
  
## <a name="how-to-perform-operations-on-a-sql-server-database"></a>如何在 SQL Server 数据库上执行操作  
 使用执行 SQL Server 数据库上的操作的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要执行对表具有较大的数据类型的操作，这些任务包括：  
  
1. 创建 BizTalk 项目，并针对组 < column_name > 操作生成架构。 对于本主题中，生成的架构**SetDocument**操作**记录**表。  
  
2. 在发送和接收消息，从 SQL Server 数据库的 BizTalk 项目中创建的消息。  
  
3. 创建一个业务流程调用记录表上的 SetDocument 操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用提供的示例中，FILESTREAMOperation，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 若要演示如何更新中的较大的数据类型的列的值，生成对于 SetDocument 记录表的架构。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SetOperation.TableOperation_dbo_Records.SetDocument*，其中 SetOperation 是 BizTalk 项目的名称。 TableOperation_dbo_Records 是为 SetDocument 操作记录表上生成的架构。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SetOperation.TableOperation_dbo_Records.SetDocumentResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的 SQL Server 上执行操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 您必须包括发送和接收形状将消息发送到 SQL Server 并将它们分别收到答复。 SetDocument 操作的示例业务流程如下所示：  
  
 ![用于执行 FILESTREAM 操作的业务流程](../../adapters-and-accelerators/adapter-sql/media/b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b.gif "b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b")  
  
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
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.FileStream.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.FileStream.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.FileStream.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.FileStream.Request*|  
  
 指定这些属性后，连接的消息形状和端口，并在业务流程已完成。  
  
 现在，必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
    > [!IMPORTANT]
    >  要输入 FILESTREAM 数据的操作必须在事务内执行。 因此，请确保**UseAmbientTransaction**绑定属性设置为**True**上的 WCF 自定义或 WCF-SQL 发送端口。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
    > 
    > [!IMPORTANT]
    >  执行操作以插入 FILESTREAM 数据，必须始终使用 Windows 身份验证连接到 WCF 自定义上的 SQL Server 或 WCF-SQL 发送端口。 因此，在**凭据**在端口属性对话框中，选择的选项卡**不使用单一登录**选项，并将用户名和密码保留为空。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序用于执行**SetDocument**上的操作**记录**表。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合先前生成 SetDocument 操作的架构。 例如，要更新的文档列的请求消息是：  
  
```  
<SetDocument xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records">  
  <Filter>WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'</Filter>  
  <Data>UwBlAHQAdgBfAHYAYQByAGIAaQBuAGEAcgB5AE0AQQBYAA==</Data>  
</SetDocument>  
```  
  
> [!IMPORTANT]
>  `Filter`元素必须包含 WHERE 子句基于适配器在其上更新的记录。 `Data`元素必须包含一个 base64 编码值，你想要插入到文档列。  
  
 此请求消息使用指定的值更新的文档列。 业务流程使用该消息并将其发送到 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SetDocumentResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records" />  
```  
  
 适配器发送一个空响应**设置 < column_name >** 操作。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)