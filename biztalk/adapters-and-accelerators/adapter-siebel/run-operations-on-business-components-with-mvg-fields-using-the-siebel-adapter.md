---
title: 在包含 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c5db211-76a2-4c27-97f4-382302c722da
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35ec36bd9dd0949289a8799be8844721cd5bb8ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979990"
---
# <a name="run-operations-on-business-components-with-mvg-fields-using-biztalk-server-and-the-siebel-adapter"></a>在包含 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作
本部分说明了执行包含多值字段在业务组件上的操作。 若要演示此类业务组件上的端到端操作，需要执行：  
  
- 父业务组件上插入操作  
  
- 子业务组件上插入操作  
  
- 对父和子业务组件之间的多值链接的关联操作  
  
- 父业务组件上一条记录 Query_ [MVG_Child_Business_Comp] 操作  
  
  详细了解如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持业务组件上的操作，请参阅[业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。 对于执行这些操作的消息的 SOAP 结构有关的详细信息，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="how-to-perform-operations-on-a-business-component-with-multi-value-fields"></a>如何在具有多值字段的业务组件上执行操作？  
 执行对 Siebel 系统使用的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。 若要执行的业务组件上的操作，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要调用的业务组件上的所有操作生成架构。 如前文所述，在具有多值字段的业务组件上执行操作必须为父和子业务组件上的插入操作生成架构，将父级和子级之间的多值链接的操作相关联业务组件和父业务组件上的查询操作。  
  
2. 用于发送和接收来自 Siebel 系统的消息在 BizTalk 项目中创建消息。  
  
3. 创建调用 Siebel 系统中的不同操作的业务流程。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，MVLDemo，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何将父业务组件中，相关联**帐户**向子业务组件**联系人**，我们将生成以下架构：  
  
- 在插入操作**帐户**业务组件。 请参阅[运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
- 在插入操作**联系人**业务组件。  
  
- 在关联操作**帐户**业务组件。  
  
- QUERY_CONTACT 操作**帐户**业务组件。  
  
  请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，必须创建四个请求和响应消息，一个用于将调用 Siebel 系统每个操作集。 每个集必须具有请求消息和响应消息。 例如，以下过程介绍如何创建关联操作的请求和响应消息。 必须执行类似的步骤来创建其他操作的消息。  
  
 执行以下步骤以创建消息并将其链接到该架构：  
  
### <a name="create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**AccountAssociate_Request**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*MVLDemo.SiebelBindingSchema.Associate*，其中*MVLDemo*是 BizTalk 项目的名称。 *SiebelBindingSchema*是用于调用生成的架构*相关联*上的操作*帐户*业务组件。|  
  
5.  重复上述步骤以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**AccountAssociate_Response**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*MVLDemo.SiebelBindingSchema.AssociateResponse*。|  
  
## <a name="set-up-the-orchestrations"></a>设置业务流程  
 你必须现在设置业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行帐户和联系人业务组件上的操作。  
  
- 设置在执行插入操作的业务流程**帐户**业务组件。 请参阅[运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
- 设置在执行插入操作的业务流程**联系人**业务组件。 它类似于上的插入操作**帐户**业务组件。  
  
- 设置要对其执行关联操作业务流程**帐户**业务组件。  
  
- 设置要对其执行 QUERY_CONTACT 操作的业务流程**帐户**业务组件。  
  
  本主题将演示如何设置关联操作业务流程上**帐户**业务组件。 必须执行类似任务以设置剩余业务流程。  
  
  为帐户业务组件上的关联操作业务流程如下所示：  
  
  ![使用 Siebel 中的 MVL 的业务流程](../../adapters-and-accelerators/adapter-siebel/media/6c7d548d-dc80-490f-89fe-12aff10fa3cf.gif "6c7d548d-dc80-490f-89fe-12aff10fa3cf")  
  
  以下部分提供有关如何设置此业务流程通过删除消息形状，端口，链接消息架构等信息。必须执行类似任务以设置其他流程。  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|AccountAssociateXML|Receive|-设置**名称**到*AccountAssociateXML*<br />-设置**激活**到 *，则返回 True*|  
|SendToLOB|Send|-设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|FileIn_AccountAssociate|-设置**标识符**到*FileIn_AccountAssociate*<br />-设置**类型**到*FileInAccountAssociateType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort_AccountAssociate|-设置**标识符**到*LOBPort_AccountAssociate*<br />-设置**类型**到*LOBPortAccountAssociateType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse_AccountAssociate|-设置**标识符**到*SaveResponse_AccountAssociate*<br />-设置**类型**到*SaveResponseAccountAssociateType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|AccountAssociateXML|-设置**消息**到*AccountAssociate_Request*<br />-设置**操作**到*FileIn_AccountAssociate.Associate.Request*|  
|SendToLOB|-设置**消息**到*AccountAssociate_Request*<br />-设置**操作**到*LOBPort_AccountAssociate.Associate.Request*|  
|ReceiveResponse|-设置**消息**到*AccountAssociate_Response*<br />-设置**操作**到*LOBPort_AccountAssociate.Associate.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse_AccountAssociate.Associate.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[如何生成业务流程](../../core/how-to-build-orchestrations.md)并[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。 您可以为所有四个业务流程的同一端口。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口上定义的位置。 您可以为所有四个业务流程的同一端口。  
  
  - 定义物理 WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。 您必须具有不同的所有四个业务流程的端口。  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 首先必须将关联到子业务组件的父业务组件的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   正在运行的四个 WCF 自定义或 Wcf-siebel 发送端口，分别用于将消息发送到 Siebel 系统  
  
-   适用于不同操作的四个 BizTalk 业务流程正在运行  
  
## <a name="executing-the-operation"></a>执行该操作  
 必须删除请求消息的文件接收端口。 在本主题前面生成的架构必须符合请求消息的架构。 请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)详细了解不同操作的请求消息的架构。 必须按以下顺序删除请求消息：  
  
- 若要插入到的记录将请求消息放**帐户**业务组件。 请求消息将类似于删除的主题中的帐户业务组件中插入记录的一个[运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。 业务流程使用该消息并将其发送到 Siebel 系统。 来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。  
  
- 若要插入到的记录将请求消息放**联系人**业务组件。 请求消息将类似于删除的主题中的帐户业务组件中插入记录的一个[运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。 业务流程使用该消息并将其发送到 Siebel 系统。 来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。  
  
- 若要对其执行关联操作将请求消息放**帐户**业务组件。 这会将父和子业务组件根据搜索表达式和多值字段中，输入 XML 中指定的名称相关联。 注意：  
  
  - 在关联操作中的父搜索表达式必须与父表中的唯一记录匹配。  
  
  - 关联操作中的子搜索表达式必须与匹配的子表中的唯一记录。  
  
    例如，要执行帐户业务组件上的关联操作的请求消息是：  
  
  ```  
  <Associate xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
    <ViewMode>3</ViewMode>  
    <ParentSearchExpr>[Name] LIKE "SampleName1"</ns0:ParentSearchExpr>   
    <ParentMVGField>Bill To First Name</ns0:ParentMVGField>   
    <ChildSearchExpr>[First Name] LIKE "SampleName2"</ns0:ChildSearchExpr>   
  </Associate>  
  ```  
  
   业务流程使用该消息并将其发送到 Siebel 系统。 来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。 例如，上面的请求消息的响应是：  
  
  ```  
  <?xml version="1.0" encoding="utf-8"?>  
  <AssociateResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
    <AssociateResult>  
      <ChildID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8AO09</ChildID>  
      <ParentID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8ANZ5</ParentID>  
    </AssociateResult>  
  </AssociateResponse>  
  ```  
  
- 若要对其执行 QUERY_CONTACT 操作将请求消息放**帐户**业务组件。 例如，QUERY_CONTACT 操作的请求消息是：  
  
  ```  
  <Query_Contact xmlns ="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
    <ViewMode>3</ViewMode>   
    <ParentSearchExpr>[Name] LIKE "SampleName1"</ParentSearchExpr>   
    <ParentMVGField>Bill To First Name</ParentMVGField>   
    <ContactQueryInputRecord>  
      <SearchExpr xmlns:ns1="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">[Id] LIKE '*'</SearchExpr>   
    </ContactQueryInputRecord>  
  </Query_Contact>  
  ```  
  
   业务流程使用该消息并将其发送到 Siebel 系统。 来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。  
  
  请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关请求消息的架构的详细信息。  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到与使用多值字段执行业务组件上的操作时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)