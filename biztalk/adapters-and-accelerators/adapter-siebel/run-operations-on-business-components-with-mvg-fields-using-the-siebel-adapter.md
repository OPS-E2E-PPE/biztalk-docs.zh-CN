---
title: 使用 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作 |Microsoft 文档
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
ms.openlocfilehash: 4f2e1f867ba4f7759afa67a271bc6523b93e9a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226957"
---
# <a name="run-operations-on-business-components-with-mvg-fields-using-biztalk-server-and-the-siebel-adapter"></a>使用 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作
此部分提供有关执行在业务组件包含多值字段上的操作的说明。 为了演示这种业务组件上的端到端操作，你需要执行：  
  
-   在父业务组件上插入操作  
  
-   在子业务组件上插入操作  
  
-   父级和子级在业务组件之间的多值链接执行关联的操作  
  
-   上一条记录的父业务组件 Query_ [MVG_Child_Business_Comp] 操作  
  
 有关详细信息，如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持操作上的业务组件，请参阅[业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。 有关执行这些操作的消息的 SOAP 结构的详细信息，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="how-to-perform-operations-on-a-business-component-with-multi-value-fields"></a>如何在具有多值字段的业务组件上执行操作？  
 Siebel 系统使用上执行操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Siebel 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。 若要执行的业务组件上的操作，这些任务包括：  
  
1.  创建 BizTalk 项目，并为你想要在业务组件上调用的所有操作生成架构。 如前面所述，在具有多值字段的业务组件上执行操作的父级和子级的业务组件上的插入操作生成架构，因此必须关联父级和子级之间的多值链接上的操作业务组件，并在父业务组件上的查询操作。  
  
2.  在发送和接收消息从 Siebel 系统的 BizTalk 项目中创建消息。  
  
3.  创建要在 Siebel 系统调用不同的操作的业务流程。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，MVLDemo，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在此主题中，来演示如何将父业务组件，相关联**帐户**到子业务组件时，**联系人**，我们将生成以下架构：  
  
-   上的插入操作**帐户**在业务组件。 请参阅[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
-   上的插入操作**联系人**在业务组件。  
  
-   上的关联操作**帐户**在业务组件。  
  
-   QUERY_CONTACT 操作**帐户**在业务组件。  
  
 请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您从生成的架构中的第一步的邮件 BizTalk 项目的业务流程视图。  
  
 对于本主题中，你必须创建四个集的请求和响应消息，另一个用于将调用 Siebel 系统每个操作。 每个设置必须具有请求消息和响应消息。 例如，以下过程提供了创建关联操作的请求和响应消息的说明。 你必须执行类似的步骤来创建其他操作的消息。  
  
 执行以下步骤以创建消息并将它们链接到该架构：  
  
### <a name="create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果不是已打开。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**AccountAssociate_Request**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*MVLDemo.SiebelBindingSchema.Associate*，其中*MVLDemo*是 BizTalk 项目的名称。 *SiebelBindingSchema*是为调用生成的架构*关联*操作*帐户*在业务组件。|  
  
5.  重复上述步骤以创建新的消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**AccountAssociate_Response**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*MVLDemo.SiebelBindingSchema.AssociateResponse*。|  
  
## <a name="set-up-the-orchestrations"></a>设置业务流程  
 你必须现在将设置业务流程为使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在客户和联系人的业务组件上执行操作。  
  
-   设置上执行插入操作的业务流程**帐户**在业务组件。 请参阅[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
-   设置上执行插入操作的业务流程**联系人**在业务组件。 它类似于上的插入操作**帐户**在业务组件。  
  
-   设置业务流程，以对执行关联操作**帐户**在业务组件。  
  
-   设置业务流程，以对执行 QUERY_CONTACT 操作**帐户**在业务组件。  
  
 本主题将演示如何设置关联操作业务流程**帐户**在业务组件。 你必须执行类似的任务以设置剩余业务流程。  
  
 帐户在业务组件上的关联操作的业务流程如下所示：  
  
 ![使用在 Siebel MVL 业务流程](../../adapters-and-accelerators/adapter-siebel/media/6c7d548d-dc80-490f-89fe-12aff10fa3cf.gif "6c7d548d-dc80-490f-89fe-12aff10fa3cf")  
  
 以下部分提供有关如何设置此业务流程通过将消息形状，端口，链接消息到架构，等的信息。你必须执行类似的任务以设置的其他业务流程以及。  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|AccountAssociateXML|Receive|-将设置**名称**到*AccountAssociateXML*<br />-将设置**激活**到*True*|  
|SendToLOB|Send|-将设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 中列出的名称*端口*列是业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|FileIn_AccountAssociate|-将设置**标识符**到*FileIn_AccountAssociate*<br />-将设置**类型**到*FileInAccountAssociateType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort_AccountAssociate|-将设置**标识符**到*LOBPort_AccountAssociate*<br />-将设置**类型**到*LOBPortAccountAssociateType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|SaveResponse_AccountAssociate|-将设置**标识符**到*SaveResponse_AccountAssociate*<br />-将设置**类型**到*SaveResponseAccountAssociateType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|AccountAssociateXML|-将设置**消息**到*AccountAssociate_Request*<br />-将设置**操作**到*FileIn_AccountAssociate.Associate.Request*|  
|SendToLOB|-将设置**消息**到*AccountAssociate_Request*<br />-将设置**操作**到*LOBPort_AccountAssociate.Associate.Request*|  
|ReceiveResponse|-将设置**消息**到*AccountAssociate_Response*<br />-将设置**操作**到*LOBPort_AccountAssociate.Associate.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*SaveResponse_AccountAssociate.Associate.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[如何构建业务流程](../../core/how-to-build-orchestrations.md)和[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。 你可以为所有四个的业务流程的同一端口。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的相应文件端口上定义的位置。 你可以为所有四个的业务流程的同一端口。  
  
    -   定义物理 WCF 自定义或 WCF Siebel 发送端口将消息发送到 Siebel 系统。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。 你必须具有不同的端口，所有四个的业务流程。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动的 BizTalk 应用程序将关联到子业务组件父在业务组件。 有关启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   正在运行的四个 WCF 自定义或 WCF Siebel 发送端口，每个用于将消息发送到 Siebel 系统  
  
-   运行不同的操作的四个 BizTalk 业务流程  
  
## <a name="executing-the-operation"></a>执行该操作  
 你必须删除请求的文件的消息接收端口。 请求消息的架构必须符合本主题前面的生成的架构。 请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关不同的操作的请求消息的架构的详细信息。 您必须按以下顺序来删除请求消息：  
  
-   删除要插入到记录的请求消息**帐户**在业务组件。 请求消息将类似于在主题中的帐户业务组件中插入一条记录中删除的一个[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。 业务流程使用该消息，并将其发送到 Siebel 系统。 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。  
  
-   删除要插入到记录的请求消息**联系人**在业务组件。 请求消息将类似于在主题中的帐户业务组件中插入一条记录中删除的一个[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。 业务流程使用该消息，并将其发送到 Siebel 系统。 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。  
  
-   删除要对执行关联操作的请求消息**帐户**在业务组件。 这会将关联父级和子级业务组件根据搜索表达式和输入 XML 中指定多值字段的名称。 注意：  
  
    -   关联操作中的父搜索表达式必须与父表中的唯一记录匹配。  
  
    -   关联操作中的子搜索表达式必须匹配子表中的唯一记录。  
  
     例如，要执行关联操作帐户在业务组件上的请求消息是：  
  
    ```  
    <Associate xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <ViewMode>3</ViewMode>  
      <ParentSearchExpr>[Name] LIKE "SampleName1"</ns0:ParentSearchExpr>   
      <ParentMVGField>Bill To First Name</ns0:ParentMVGField>   
      <ChildSearchExpr>[First Name] LIKE "SampleName2"</ns0:ChildSearchExpr>   
    </Associate>  
    ```  
  
     业务流程使用该消息，并将其发送到 Siebel 系统。 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。 例如，上面的请求消息的响应是：  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <AssociateResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <AssociateResult>  
        <ChildID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8AO09</ChildID>  
        <ParentID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8ANZ5</ParentID>  
      </AssociateResult>  
    </AssociateResponse>  
    ```  
  
-   删除请求消息上执行 QUERY_CONTACT 操作**帐户**在业务组件。 例如，QUERY_CONTACT 操作的请求消息是：  
  
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
  
     业务流程使用该消息，并将其发送到 Siebel 系统。 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。  
  
 请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关请求消息的架构的详细信息。  
  
## <a name="possible-exceptions"></a>可能的异常  
 有关异常的信息可能会遇到与使用多值字段执行在业务组件上的操作时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)