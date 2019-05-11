---
title: 在包含 BFILE 数据类型在 Oracle 数据库中使用 BizTalk Server 运行对表的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations on tables with BFILE data types, performing by using BizTalk Server
- BFILE data types
ms.assetid: 2e4af5a9-acde-419b-a99c-3eaa0c72daa8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f22e4fc3ad65c0aadd2015723241c6b909775e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376551"
---
# <a name="run-operations-on-tables-with-bfile-data-types-in-oracle-database-using-biztalk-server"></a>在包含 BFILE 数据类型在 Oracle 数据库中使用 BizTalk Server 运行对表的操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表和存储的过程中支持 BFILE 数据类型。 本部分提供有关如何对包含 BFILE 数据类型的列的表执行操作的信息。 详细了解如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持 BFILE，请参阅[对表使用 BFILE 数据类型在 Oracle 数据库中的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-with-bfile-data-types-in-oracle-database.md)。  
  
## <a name="setting-up-your-oracle-database-server-for-operations-on-bfile"></a>设置对 BFILE 操作 Oracle 数据库服务器  
 本部分演示如何调用 SCOTT 中插入一条记录的过程。CUSTOMERDOC 表。 此表包含 BFILE 数据类型的列，由正在运行的 SQL 脚本附带创建[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 若要了解有关这些示例和 SQL 脚本的详细信息，请参阅[适用于 Oracle 数据库适配器示例](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)。  
  
 运行该脚本以创建 CUSTOMERDOC 表后，您必须运行 Oracle 数据库，以启用对 BFILE 数据类型的操作的计算机上执行某些操作。 必须在 Oracle 数据库执行的任务包括：  
  
1.  运行 Oracle 数据库的计算机上创建一个目录 C:\MYDIR。  
  
2.  在 Oracle 数据库中创建逻辑目录。 这通常需要具有 SYSDBA 权限的用户。 例如：  
  
    ```  
    CREATE OR REPLACE DIRECTORY MYDIR AS 'C:\MYDIR';  
    ```  
  
3.  将权限添加到用户访问 Oracle 中的逻辑目录。 例如：  
  
    ```  
    GRANT READ, WRITE ON DIRECTORY MYDIR to SCOTT;  
    ```  
  
4.  将复制到物理目录位置，运行与在 Oracle 中的逻辑目录关联的 Oracle 数据库的计算机上访问文件。 步骤 1 中创建此目录。  
  
     根据上面的示例中，将复制的文件到目录 C:\MYDIR customer_profile.txt。 此文件现已可供 BFILE 操作。 有关执行操作的详细信息，请参阅[对具有 Oracle 数据库中使用 BizTalk server 的大型对象类型数据的表执行操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)。  
  
    > [!IMPORTANT]
    >  在包含 BFILE 数据类型的表上支持 ReadLOB 操作。 不支持 UpdateLOB 操作。 但是，用户可以或者使用更新操作。  
  
## <a name="how-to-perform-operations-using-bfile-data-types"></a>如何使用 BFILE 数据类型执行操作  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[构建基块来开发 BizTalk 应用程序与 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。 若要调用 SCOTT 中插入一条记录的过程。CUSTOMERDOC 表，这些任务包括：  
  
1. 创建 BizTalk 项目并生成为 CREATE_CUSTOMERDOC 存储过程的架构。  
  
2. 在 BizTalk 项目中为发送和接收消息从 Oracle 数据库创建消息。  
  
3. 创建一个业务流程调用上的 Oracle 数据库表或视图的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，Operate_BFILE，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适用于 Oracle 数据库适配器示例](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，若要演示如何对包含 BFILE 列的表执行操作我们将调用 CREATE_CUSTOMERDOC 过程。 通过运行这些示例提供的 SQL 脚本在 SCOTT\Package\ACCOUNT_PKG 架构下创建此过程。 此过程将 BFILE 记录类型，CUSTOMERDOC 表中添加一条记录。 SQL 脚本的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。  
  
 请参阅[检索用于 Oracle 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
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
    |消息类型|从下拉列表中，展开**架构**，然后选择*BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOC*，其中*BFILE_Operations*的名称您的 BizTalk 项目。 *OracleDBBindingSchema*是为 CREATE_CUSTOMERDOC 过程生成的架构。|  
  
5.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOCResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行过程。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息并通过 ODP 将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 在 Oracle 数据库表中执行 BFILE 列上的操作的一个典型的业务流程将包含：  
  
- 发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  
  
- 一个单向接收端口接收请求消息将发送到 Oracle 数据库。  
  
- 一个双向发送端口以发送请求消息到 Oracle 数据库和接收响应。  
  
- 一个单向发送端口用于从 Oracle 数据库将响应发送到的文件夹。  
  
  示例业务流程如下所示：  
  
  ![用于使用 BFILE 执行操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/5902cf48-0555-4d9a-b902-5208949b6c87.gif "5902cf48-0555-4d9a-b902-5208949b6c87")  
  
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
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br />-设置**类型**到*SaveResponseType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>为操作形状指定消息并将它们连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*FileIn.Create_BFILE。请求*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.Create_BFILE。请求*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.Create_BFILE。响应*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.Create_BFILE。请求*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库。 您必须在发送端口中指定的操作。 有关如何创建 WCF 自定义或 Wcf-oracledb 端口的信息，请参阅[手动配置物理端口绑定到 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序用于调用 CUSTOMERDOC 表中创建一条记录的过程。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 Wcf-oracledb 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合前面生成的过程的架构。 请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)详细了解用于调用过程使用的请求消息架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 例如，要调用 CREATE_CUSTOMERDOC 过程的请求消息是：  
  
```  
<CREATE_CUSTOMERDOC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CNAME>John Smith</CNAME>  
  <CDOC>MYDIR/John_Smith_profile.txt</CDOC>  
</CREATE_CUSTOMERDOC>  
```  
  
> [!NOTE]
>  文本文件，John_Smith_profile.txt 必须位于与 Oracle 中的逻辑目录关联的物理目录位置。 对于此示例，该文本文件必须位于 C:\MYDIR  
  
 业务流程使用该消息并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置。 例如，从 Oracle 数据库以实现更高版本的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CREATE_CUSTOMERDOCResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"></CREATE_CUSTOMERDOCResponse>  
```  
  
> [!NOTE]
>  您可以创建一个类似的业务流程，从具有 BFILE 类型字段的表中读取数据。 附带的 SQL 脚本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]创建包含 GET_CUSTOMERDOC 过程 ACCOUNT_PKG。 可以使用此过程从 SCOTT 检索 BFILE 数据。CUSTOMERDOC 表。  
> 
>  示例，Operate_BFILE，也是附带的示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此示例演示如何将记录插入到 SCOTT。使用 CREATE_CUSTOMERDOC CUSTOMERDOC 表存储过程 （如本主题中所述）。此示例还演示如何从 SCOTT 读取 BFILE 数据。使用 GET_CUSTOMERDOC CUSTOMERDOC 表的存储过程。  
  
## <a name="possible-exceptions"></a>可能的异常  
 执行 DML 操作使用时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)