---
title: 调用在 Oracle E-business Suite 的并发程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85c55a35-bee4-4b50-8b00-e4198ad4c2af
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0991ab2714ddb7acc22161ffcd29179ff7339c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964611"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite"></a>调用在 Oracle E-business Suite 的并发程序
Oracle E-business Suite 公开可以执行以执行对 Oracle 应用程序的特定操作的并发程序。 每个 Oracle 应用程序具有一套标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。 有关如何的适配器支持并发程序的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。 对于调用并发程序消息的 SOAP 结构的信息，请参阅[并发程序的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)。  
  
> [!NOTE]
>  对于不公开其元数据的并发程序，Oracle E-business 适配器为每个这些并发程序公开 100 的可选参数。 若要成功调用这些并发程序，用户必须咨询 Oracle E-business Suite 文档以找出需要一个值，并发程序的参数，然后指定它们。 这样的并发程序的一个示例是**日志导入**(实际名称： **GLLEZL**) 中**常规分类帐**应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成中的步骤[创建 Oracle E-business Suite 应用程序的先决条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)。
  
## <a name="how-to-invoke-concurrent-programs-in-oracle-applications"></a>如何以调用 Oracle 应用程序中的并发程序  
 执行对 Oracle E-business Suite 使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要调用的并发程序，这些任务包括：  
  
-   创建 BizTalk 项目，并为你想要调用的并发程序生成架构。  
  
-   创建在 BizTalk 项目中为从 Oracle E-business Suite 发送和接收消息的消息。  
  
-   创建业务流程来调用并发程序。  
  
-   生成和部署 BizTalk 项目。  
  
-   配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
-   启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用**客户接口**从并发程序**应收帐款**应用程序。 此应用程序时使用默认 Oracle E-business Suite 应用程序。 此并发程序返回请求 id。 若要检查的并发程序的状态，我们执行**Get_Status**通过将传入的请求 ID 的并发程序收到的响应中**客户接口**并发程序。  
  
 我们可以在本主题中，来生成两个架构**客户接口**和**Get_Status**并发程序。 有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，为其类型由相应的架构定义。 你现在必须创建消息业务流程，并将它们链接到你在上一步中生成的架构。  
  
 在此业务流程中，你必须创建四条消息 — 一个接收响应设置才能调用**客户接口**并发程序和其他接收的响应设置才能调用**Get_Status**并发程序。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ConcurrentProgram.OracleEBSBindingSchema.RACUST*，其中 ConcurrentProgram 是 BizTalk 项目的名称。 OracleEBSBindingSchema 是为调用生成的架构**客户接口**并发程序。 **注意：** RACUST 是实际名称**客户接口**并发程序。 虽然[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示友好名称 (**客户接口**)，架构包含并发程序的实际名称。|  
  
6.  重复步骤 3 以创建三个新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |设置为标识符|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |响应|*ConcurrentProgram.OracleEBSBindingSchema.RACUSTResponse*|  
    |Get_StatusRequest|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgram*|  
    |Get_StatusResponse|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgramResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用 Oracle E-business Suite 中的并发程序。 此业务流程，在删除时的请求消息的定义接收位置。 业务流程使用此消息，并将其传递到 Oracle E-business Suite 来调用**客户接口**并发程序。 并发程序的响应接收到来自 Oracle 和保存在另一个位置。 响应消息包含一个请求 id。 业务流程包括**构造消息**形状，可从响应中提取的请求 ID，并构造一条消息，与的架构一致**Get_Status**并发程序。 要调用的消息**Get_Status**并发程序发送到 Oracle E-business Suite 与作为参数的请求 ID。 你必须包括发送和接收形状、 消息构造形状和端口，以将消息发送到 Oracle 和接收响应。  
  
 通常情况下，**客户接口**并发程序将需要一些时间来执行，因此你需要在执行前等待**Get_Status**并发。 您可以通过添加来自动化这**延迟**形状。  
  
 示例业务流程如下所示：  
  
 ![业务流程来调用并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a02e9d8-8ea8-4898-8d05-c060761f4feb.gif "2a02e9d8-8ea8-4898-8d05-c060761f4feb")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 为每个消息形状中指定以下属性。 中列出的名称**形状**列对应于消息形状前面业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
|SendGetStatus|Send|-将设置**名称**到*SendGetStatus*|  
|ReceiveStatusResponse|Receive|-将设置**名称**到*ReceiveStatusResponse*<br />-将设置**激活**到*False*|  
|SaveStatusResponse|Send|-将设置**名称**到*SaveStatusResponse*|  
  
### <a name="adding-a-delay-shape"></a>添加延迟形状  
 如果你想业务流程调用之间的等待**客户接口**和**Get_Status**并发程序，你必须添加**延迟**形状上的与业务流程。 你必须添加**延迟**调整后业务流程将复制的响应**客户接口**到文件的并发程序发送端口。 因此，必须添加**延迟**后调整**SendResponse**形状。  
  
 在**延迟**形状，可以指定等待的时间间隔为其业务流程必须在继续之前通过将以下代码添加到的表达式编辑器**延迟**形状：  
  
```  
new System.TimeSpan(0,2,0)  
```  
  
 通过将此代码添加，业务流程将等待两分钟，然后再继续。 有关如何配置详细信息**延迟**形状，请参阅[如何配置延迟形状](../../core/how-to-configure-the-delay-shape.md)。  
  
### <a name="adding-the-construct-message-shape"></a>添加构造消息形状  
 为 Oracle E-business Suite 回应**客户接口**并发程序包含一个请求 id。 若要获取的并发程序状态，必须传递的相同的请求 ID 作为参数传递给**Get_Status**并发程序。 为此，请在业务流程中，必须包括**构造消息**形状，并在其中**消息分配**形状。 用途**构造消息**形状：  
  
-   若要从收到的响应中提取的请求 ID**客户接口**并发程序。  
  
-   若要构造一条消息的消息架构符合**Get_Status**并发程序。  
  
 有关**构造消息**形状，设置**构造消息**属性**Get_StatusRequest**。  
  
 有关**消息分配**形状，添加下面。 在之前将代码添加，您必须：  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<GetStatusForConcurrentProgram xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR'><RequestId /></GetStatusForConcurrentProgram>");  
Get_StatusRequest = XmlDoc;  
Get_StatusRequest.RequestId = xpath(Response,"string(/*[local-name()='RACUSTResponse']/*[local-name()='RACUSTResult']/text())");  
```  
  
### <a name="adding-ports"></a>添加端口  
 若要配置的端口，你可以指定下表中列出的每个逻辑端口的属性。 中列出的名称*端口*列对应于业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*<br />-创建一个操作*Cust_Interface*。 此操作用于**客户接口**并发程序。<br />-创建一个操作*Get_Status*。 此操作用于**Get_Status**并发程序。|  
|LOBPort_GetStatus|-将设置**标识符**到*LOBPort_GetStatus*<br />-将设置**类型**到*LOBPort_GetStatusType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性值用于指定消息的操作形状并将它们链接到的端口。 中列出的名称**形状**列的名称相对应的消息形状中业务流程关系图所示。  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 你必须立即生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.Cust_Interface.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBport.Cust_Interface.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBport.Cust_Interface.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.Cust_Interface.Request*|  
|SendGetStatus|-将设置**消息**到*Get_StatusRequest*<br />-将设置**操作**到*LOBPort_GetStatus.Get_Status.Request*|  
|ReceiveStatusResponse|-将设置**消息**到*Get_StatusResponse*<br />-将设置**操作**到*LOBPort_GetStatus.Get_Status.Response*|  
|SaveStatusResponse|-将设置**消息**到*Get_StatusResponse*<br />-将设置**操作**到*ResponseOut.Get_Status.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 你必须立即生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Oracle E-business Suite。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 Oracle E-business Suite 的响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义两个物理 WCF 自定义或 WCF OracleEBS 发送端口-一个用于将消息发送到 Oracle E-business Suite 执行**客户接口**并发程序，另一个用于执行**Get_Status**并发程序。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  
  
         若要调用并发程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须设置在其中调用该操作的适当的应用程序上下文。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供某些绑定属性以指定用于任何操作的应用程序上下文。 你必须在用于调用并发程序的 WCF 自定义或 WCF OracleEBS 端口上设置这些绑定属性。  
  
        -   如果**ClientCredentialType**绑定属性设置为**数据库**，则必须指定以下的绑定属性，以设置应用程序上下文。  
  
            |绑定属性|值|  
            |----------------------|-----------|  
            |**OracleUserName**|指定 Oracle E-business Suite 用户的名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的大小写**OracleUserName**连接到 Oracle E-business Suite 时绑定属性。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的用户名称的大小写或你想要输入用户名称包含特殊字符，你必须指定在双引号内的值。|  
            |**OraclePassword**|Oracle E-business Suite 用户的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的大小写**OraclePassword**连接到 Oracle E-business Suite 时绑定属性。 密码传递到 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。|  
            |**OracleEBSResponsibilityName**|负责与 Oracle E-business Suite 用户关联。|  
  
        -   如果**ClientCredentialType**绑定属性设置为**EBusiness**，你必须已将指定 Oracle E-business 凭据建立连接时。 在这种情况下才必须指定值**OracleEBSResponsibilityName**绑定属性。  
  
         有关不同的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何的适配器支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
        > [!NOTE]
        >  你可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[配置的 Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文使用消息上下文属性的说明，请参阅[在 Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序，然后调用的并发程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口来调用**客户接口**并发程序正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口来调用**Get_Status**并发程序正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，你必须删除与调用的架构一致的请求消息**客户接口**并发程序。 例如，请求消息来调用**客户接口**并发程序：  
  
```  
<RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <Description>Customer Interface Program</Description>  
  <StartTime></StartTime>  
  <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
  <ORG_ID>203</ORG_ID>  
</RACUST>  
```  
  
> [!NOTE]
>  调用并发程序的请求消息需要如 SetOptions、 SetPrintOptions 和 SetRepeatOptions 某些可选参数。 此处提供的请求消息不包含这些可选参数。 有关完整的请求消息，包括可选参数，请参阅[并发程序的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)。  
  
 业务流程使用该消息，将其传递到 Oracle E-business Suite，并收到响应。 响应消息保存在其他文件位置指定为业务流程的一部分。 客户接口并发程序的响应如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<RACUSTResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <RACUSTResult>2794708</RACUSTResult>  
</RACUSTResponse>  
```  
  
 来自 Oracle E-business Suite 的响应包含一个请求 id。 业务流程从响应消息中提取的请求 ID，构造一条消息，调用**Get_Status**并发程序，并将其传递到 Oracle E-business Suite 执行**Get_Status**并发程序。 有关 th 收到的响应之后**Get_Status**并发程序复制到与第一个响应相同的文件位置。 有关响应**Get_Status**并发程序如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GetStatusForConcurrentProgramResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <GetStatusForConcurrentProgramResult>true</GetStatusForConcurrentProgramResult>   
  <Phase>Pending</Phase>   
  <Status>Standby</Status>   
  <DevPhase>PENDING</DevPhase>   
  <DevStatus>STANDBY</DevStatus>   
  <Message>null</Message>   
</GetStatusForConcurrentProgramResponse>  
```  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，可以从文件导入的配置设置，以便不需要创建项如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)