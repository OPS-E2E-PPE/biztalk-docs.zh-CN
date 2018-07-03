---
title: 插入、 更新、 删除或选择对界面表和界面视图与 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85f42431-80fb-49be-86d1-bb21eee5e4f5
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9baefe803a7ab239a978c934a62dc5d0218ca4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982990"
---
# <a name="insert-update-delete-or-select-on-interface-tables-and-interface-views-with-oracle-e-business-suite"></a>插入、 更新、 删除或选择对界面表和界面视图与 Oracle E-business Suite
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]一组标准如 Insert 操作的图面，接口上的 Update、 Delete，选择表和视图。 本主题将说明了如何使用适配器执行这些操作。 有关适配器如何支持这些操作的详细信息，请参阅[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。 有关这些操作的 SOAP 消息结构的信息，请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。  

> [!NOTE]
>  适配器还公开了特定操作的表和包含较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 的视图。 有关此类操作的详细信息，请参阅[对界面表、 界面视图、 表和包含 LOB 数据的视图的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。 有关如何执行对表和列使用 BizTalk Server 的大型数据类型的操作的说明，请参阅[完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)。  

## <a name="how-to-perform-basic-operations-on-oracle-e-business-suite"></a>如何执行对 Oracle E-business Suite 的基本操作  
 通过执行对 Oracle E-business Suite 的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要执行 Oracle E-business Suite 中的插入、 更新、 删除或选择表和视图操作，这些任务包括：  

1. 创建 BizTalk 项目，并为你想要调用接口表或视图的操作生成架构。  

2. 在发送和接收消息从 Oracle E-business Suite 的 BizTalk 项目中创建的消息。  

3. 创建一个业务流程调用的接口表或视图上的操作。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="generating-schema"></a>生成架构  
 本主题演示如何执行基本的 Insert、 Update、 Delete 或 Select 操作的 Oracle E-business Suite 中 AR_ARCHIVE_PURGE_INTERIM 接口表中插入记录。 此接口表现已推出**应收帐款**Oracle E-business Suite 中应用程序。  

 若要演示如何插入记录，AR_ARCHIVE_PURGE_INTERIM 表的 Insert 操作生成架构。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在必须为该业务流程创建消息并将其链接到上一步中生成的架构。  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  

2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  

4.  右键单击新创建的消息，然后依次**属性窗口**。  

5.  在中**属性**窗格**Message_1**，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InsertInterfaceTable.OracleEBSBinding.Insert*，其中 InsertInterfaceTable 是 BizTalk 项目的名称。 OracleEBSBinding 是为 AR_ARCHIVE_PURGE_INTERIM 表上的插入操作生成的架构。|  

6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*InsertInterfaceTable.OracleEBSBinding.InsertResponse*。|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行对 Oracle E-business Suite 的操作。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用此消息并将其传递到 Oracle E-business Suite。 来自 Oracle E-business Suite 的响应保存到另一个位置。 执行对 Oracle 数据库的基本表操作的一个典型的业务流程将包含：  

- 发送和接收形状来将消息发送到 Oracle 数据库和接收响应。  

- 一个单向接收端口接收请求消息将发送到 Oracle 数据库。  

- 一个双向发送端口以发送请求消息到 Oracle 数据库和接收响应。  

- 一个单向发送端口用于从 Oracle 数据库将响应发送到的文件夹。  

  选择操作的示例业务流程如下所示：  

  ![将数据插入接口表的业务流程](../../adapters-and-accelerators/adapter-oracle-ebs/media/8a4508c5-9949-4043-9de5-d1226db8117b.gif "8a4508c5-9949-4043-9de5-d1226db8117b")  

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
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.Insert.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.Insert.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.Insert.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.Insert.Request*|  

 指定这些属性后，连接的消息形状和端口，并在业务流程已完成。  

 现在，必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  

  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Oracle E-business Suite。  

  - 硬盘和相应的 BizTalk 业务流程放置包含来自 Oracle E-business Suite 的响应的响应消息的位置的文件端口上定义的位置。  

  - 定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  

     若要执行的接口表或接口上的操作视图使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须设置正确的应用程序上下文中调用操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供某些绑定的属性以指定任何操作的应用程序上下文。 必须在用于对界面表执行操作的 WCF 自定义或 WCF OracleEBS 端口上设置这些绑定属性。  

    - 如果**ClientCredentialType**绑定属性设置为**数据库**，则必须指定要设置应用程序上下文的以下绑定属性。  


      |        绑定属性         |                                                                                                                                                                                                                                                                                     ReplTest1                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | 指定 Oracle E-business Suite 用户的名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的用例**OracleUserName**属性绑定到 Oracle E-business Suite 连接时。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的用户名的大小写或你想要输入用户名称包含特殊字符，必须指定在双引号内的值。 |
      |       **OraclePassword**        |   Oracle E-business Suite 用户的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的用例**OraclePassword**属性绑定到 Oracle E-business Suite 连接时。 密码传递到 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     与 Oracle E-business Suite 用户相关联的职责。                                                                                                                                                                                                                                                      |


    - 如果**ClientCredentialType**绑定属性设置为**EBusiness**，你必须已指定 Oracle 电子商务凭据建立连接时。 这种情况下才必须指定值**OracleEBSResponsibilityName**属性绑定。  

      有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 适配器如何支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

    > [!NOTE]
    >  您可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文中使用消息上下文属性的说明，请参阅[Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动将记录插入到 AR_ARCHIVE_PURGE_INTERIM 接口表的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   文件接收端口接收请求消息的业务流程正在运行。  

-   运行文件发送端口以接收来自业务流程的响应消息。  

-   WCF 自定义或 WCF OracleEBS 发送端口以发送消息到 Oracle E-business Suite 正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须放置到的文件的请求消息接收位置。 请求消息的架构必须符合前面生成的 Insert 操作的架构。 例如，要选择 AR_ARCHIVE_PURGE_INTERIM 接口表中的所有记录的请求消息是：  

```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID>001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  

 此请求消息将记录插入 AR_ARCHIVE_PURGE_INTERIM 接口表。 请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)详细了解执行对 Oracle E-business Suite 使用基本 DML 操作的请求消息架构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  

 对于简单的数据列，如在前面的请求消息中，您还可以使用**InlineValue**属性。 有关 InlineValue 属性的详细信息，请参阅中的插入操作的说明[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。  

 例如，使用内联值前面的请求消息将如下所示：  

```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID InlineValue="(Select TRX_ID FROM table_name)">001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  

 在此请求消息，另一个表中检索 TRX_ID 列的值。 因此，即使 TRX_ID"001"指定为一个值，SELECT 语句为 InlineValue 属性指定的值将插入到表。  

 业务流程使用该消息并将其发送到 Oracle E-business Suite。 来自 Oracle E-business Suite 的响应保存在定义为业务流程的一部分的其他文件位置。 例如，前面的请求消息从 Oracle E-business Suite 的响应是：  

```  
<?xml version="1.0" encoding="utf-8" ?>   
<InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <InsertResult>1</InsertResult>   
</InsertResponse>  
```  

 响应包含插入到表的行数。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 生成的绑定文件后，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  

## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)