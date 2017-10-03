---
title: "使用较大的数据类型使用的 SQL 适配器运行对表和视图的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cec15b01-7a57-4917-8c21-44a1cfaadc59
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85403ed8ed76246b93bd30c5246fb7a799284ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter"></a>在上运行操作表和视图与使用 SQL 适配器的较大的数据类型
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端读取和更新的大型数据类型列中的数据，它是、 varchar （max）、 nvarchar 或 varbinary （max）。 若要从这类列读取数据，适配器客户端可以使用选择的操作。 若要插入或更新到此类列的数据，该适配器公开 < column_name > 集运算中，其中 < column_name > 是的类型 varchar （max）、 nvarchar 或 varbinary （max） 列的名称。  
  
 此外，在 SQL Server 2008 中，你可以存储非结构化的数据，例如文本文档和图像的 varbinay(max) 列。 此类非结构化的数据称为 FILESTREAM 数据。 FILESTREAM 数据可以存储为文件系统上的文件。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端 FILESTREAM 数据输入到类型 varbinary （max） 列。 有关 FILESTREAM 存储空间的详细信息，请参阅[FILESTREAM 概述](https://msdn.microsoft.com/library/bb933993(SQL.100).aspx)。  
  
 本主题提供必须执行某些任务有关的信息的计算机上运行 SQL Server 和运行适配器客户端将无法插入或更新 FILESTREAM 数据的计算机。 本主题还提供有关执行插入 FILESTREAM 数据的组 < column_name > 操作的说明。  
  
> [!NOTE]
>  如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。  
  
## <a name="prerequisites"></a>先决条件  
 在运行 SQL Server 的计算机和运行适配器客户端的计算机上，必须执行以下任务。  

  
-   **运行 SQL Server 的计算机上**  
  
    -   你必须在 SQL Server 实例上启用 FILESTREAM。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=122486](http://go.microsoft.com/fwlink/?LinkId=122486)。  
  
    -   你必须创建启用 FILESTREAM 的数据库。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=122487](http://go.microsoft.com/fwlink/?LinkId=122487)。  
  
    -   你必须有一个表以存储 FILESTREAM 数据。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=122488](http://go.microsoft.com/fwlink/?LinkId=122488)。  
  
    -   你必须在承载 SQL Server 数据库的计算机上配置 MSDTC。 有关如何配置 MSDTC 的说明，请参阅[配置 SQL Server 和适配器客户端上的 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
-   **运行适配器客户端的计算机上**  
  
    -   你必须安装的 SQL 客户端连接 SDK。 你可以通过运行 SQL Server 2008 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。  
  
    -   你必须运行适配器客户端的计算机上配置 MSDTC。 有关如何配置 MSDTC 的说明，请参阅[配置 SQL Server 和适配器客户端上的 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
 完成这些任务后，你将插入或更新 SQL Server 2008 数据库表中的 FILESTREAM 数据。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>本主题演示对大型数据类型执行操作的方式  
 为了演示如何执行对表的较大的数据类型的组 < column_name > 操作，需要一个表，具有列 Id 和文档的记录。 Id 列是类型 uniqueidentifier，采用 GUID。 文档列是类型 varbinary （max）。 假定 Id 列已有一个 GUID`438B7B4C-5491-409F-BCC1-78817C399EC3`。 若要更新的文档列，该适配器显示 SetDocument 操作。  
  
> [!NOTE]
>  对于 SQL Server 2008 中，为了演示 FILESTREAM 操作，假定的文档列可以存储 FILESTREAM 数据。  
  
## <a name="how-to-perform-operations-on-a-sql-server-database"></a>如何在 SQL Server 数据库上执行操作  
 通过使用执行 SQL Server 数据库上的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。 若要执行对表较大的数据类型的操作，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成设置 < column_name > 操作的架构。 有关本主题中，生成架构**SetDocument**操作**记录**表。  
  
2.  在发送和接收消息从 SQL Server 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程来调用记录表上的 SetDocument 操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，FILESTREAMOperation，基于本主题提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 若要演示如何更新中的较大的数据类型的列的值，生成 SetDocument 操作的记录表的架构。 您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，为其类型由相应的架构定义。 现在，你必须创建业务流程的消息，并将它们链接到你在上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SetOperation.TableOperation_dbo_Records.SetDocument*，其中 SetOperation 是 BizTalk 项目的名称。 TableOperation_dbo_Records 是为 SetDocument 操作记录表上生成的架构。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*SetOperation.TableOperation_dbo_Records.SetDocumentResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 SQL Server 上执行操作。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。 从 SQL Server 的响应保存到另一个位置。 你必须包括发送和接收形状将消息发送到 SQL Server，并接收响应，分别。 SetDocument 操作示例业务流程如下所示：  
  
 ![业务流程执行 FILESTREAM 操作](../../adapters-and-accelerators/adapter-sql/media/b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b.gif "b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b")  
  
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
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>对于操作形状，指定消息并将其连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.FileStream.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.FileStream.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.FileStream.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.FileStream.Request*|  
  
 指定这些属性后，消息形状和端口将连接，并且您的业务流程已完成。  
  
 现在，你必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到的 SQL Server 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义物理 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
        > [!IMPORTANT]
        >  必须在事务中执行此操作输入 FILESTREAM 数据。 因此，请确保**UseAmbientTransaction**绑定属性设置为**True**上的 WCF 自定义或 WCF SQL 发送端口。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
        > [!IMPORTANT]
        >  正在执行的操作若要插入 FILESTREAM 数据你必须始终使用 Windows 身份验证连接到在 WCF 自定义的 SQL Server 或 WCF SQL 发送端口。 因此，在**凭据**端口属性对话框中的选项卡，选择**不使用单一登录**选项，然后将用户名和密码保留为空。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序用于执行**SetDocument**操作**记录**表。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   正在运行的 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须与你先前生成 SetDocument 操作的架构一致。 例如，要更新的文档列的请求消息是：  
  
```  
<SetDocument xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records">  
  <Filter>WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'</Filter>  
  <Data>UwBlAHQAdgBfAHYAYQByAGIAaQBuAGEAcgB5AE0AQQBYAA==</Data>  
</SetDocument>  
```  
  
> [!IMPORTANT]
>  `Filter`元素必须包含 WHERE 子句基于适配器在其上更新的记录。 `Data`元素必须包含一个 base64 编码值，你想要插入到文档列。  
  
 此请求消息具有指定值更新的文档列。 业务流程使用该消息，并将其发送到的 SQL Server 数据库。 从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置中。 例如，从前面的请求消息的 SQL Server 数据库响应是：  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<SetDocumentResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records" />  
```  
  
 适配器发送一个空响应**设置 < column_name >**操作。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
[开发使用 SQL 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)