---
title: 调用 Oracle E-business Suite 中的并发程序 |Microsoft Docs
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
ms.openlocfilehash: 2f63efda0809a16335d8653e67b4bc1ec8987863
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375455"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite"></a>调用 Oracle E-business Suite 中的并发程序
Oracle E-business Suite 公开您可以执行对 Oracle 应用程序的特定操作的并发程序。 每个 Oracle 应用程序一的组标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。 适配器如何支持并发程序的详细信息，请参阅[操作对并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。 对于用于调用并发程序消息的 SOAP 结构有关的信息，请参阅[并发程序的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)。  

> [!NOTE]
>  对于那些不公开其元数据的并发程序，Oracle E-business 适配器公开这些并发程序的每个 100 的可选参数。 若要成功调用这些并发程序，用户必须请查阅 Oracle E-business Suite 文档以找出需要一个值，用于并发程序的参数，然后指定它们。 此类的并发程序的一个示例是**日记本的导入**(实际名称：**GLLEZL**) 中**总帐**应用程序。  

## <a name="prerequisites"></a>先决条件  
 你必须完成中的步骤[创建 Oracle E-business Suite 的应用程序的先决条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)。

## <a name="how-to-invoke-concurrent-programs-in-oracle-applications"></a>如何调用 Oracle 应用程序中的并发程序  
 对 Oracle E-business Suite 使用执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要调用并发程序，这些任务包括：  

- 创建 BizTalk 项目，并为你想要调用并发程序生成架构。  

- 用于 Oracle E-business Suite 中发送和接收消息的 BizTalk 项目中创建消息。  

- 创建用于调用并发程序的业务流程。  

- 生成并部署 BizTalk 项目。  

- 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

- 启动 BizTalk 应用程序。  

  本主题介绍如何执行这些任务。  

## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用**的客户界面**并发程序从此**应收帐款**应用程序。 此应用程序是可用于默认 Oracle E-business Suite 应用程序。 此并发程序返回请求 id。 若要检查并发程序的状态，我们执行**Get_Status**通过传递请求 ID 的并发程序的响应中收到**的客户界面**并发程序。  

 我们可以在此主题中，来生成两个架构**的客户界面**并**Get_Status**并发程序。 有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到你在上一步中生成的架构。  

 在此业务流程中，你必须创建四个消息 — 一个接收响应设置才能调用**的客户界面**并发程序和其他接收的响应设置才能调用**Get_Status**并发程序。  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1. 向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  

2. 如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

3. 在业务流程视图中，右键单击**消息**，然后单击**新消息**。  

4. 右键单击新创建的消息，然后依次**属性窗口**。  

5. 在中**属性**窗格**Message_1**，执行以下操作：  


   |   使用此选项   |                                                                                                                                                                                                                                                                                           执行的操作                                                                                                                                                                                                                                                                                           |
   |--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  Identifier  |                                                                                                                                                                                                                                                                                         类型 `Request`                                                                                                                                                                                                                                                                                         |
   | 消息类型 | 从下拉列表中，展开**架构**，然后选择*ConcurrentProgram.OracleEBSBindingSchema.RACUST*，其中 ConcurrentProgram 是 BizTalk 项目的名称。 OracleEBSBindingSchema 是用于调用生成的架构**的客户界面**并发程序。 **注意：** RACUST 是实际的名称**的客户界面**并发程序。 虽然[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示的友好名称 (**客户界面**)，该架构包含并发程序的实际名称。 |


6. 重复步骤 3 以创建三个新消息。 在中**属性**窗格中的新消息，执行以下操作：  

   |将标识符设置为|将消息类型设置为|  
   |-----------------------|-------------------------|  
   |响应|*ConcurrentProgram.OracleEBSBindingSchema.RACUSTResponse*|  
   |Get_StatusRequest|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgram*|  
   |Get_StatusResponse|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgramResponse*|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于调用 Oracle E-business Suite 中的并发程序。 在此业务流程中删除时的请求消息定义接收位置。 业务流程使用此消息，并将其传递到 Oracle E-business Suite 来调用**的客户界面**并发程序。 并发程序的响应从 Oracle 接收，然后保存在另一个位置。 响应消息包含请求 id。 业务流程包括**构造消息**形状，可从响应中提取的请求 ID，并构造一条消息，符合的架构**Get_Status**并发程序。 要调用的消息**Get_Status**并发程序发送到 Oracle E-business Suite 使用请求 ID 作为参数。 您必须包括发送和接收形状、 消息构造形状和端口来将消息发送到 Oracle 和接收响应。  

 通常情况下，**的客户界面**并发程序将需要一些时间才能执行，因此您需要执行之前要等待**Get_Status**并发。 可以通过添加自动化这**延迟**形状。  

 示例业务流程如下所示：  

 ![调用并发程序的业务流程](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a02e9d8-8ea8-4898-8d05-c060761f4feb.gif "2a02e9d8-8ea8-4898-8d05-c060761f4feb")  

### <a name="adding-message-shapes"></a>添加消息形状  
 为每个消息形状中指定以下属性。 中列出的名称**形状**列对应于消息形状上的业务流程中所示。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
|SendGetStatus|Send|-设置**名称**到*SendGetStatus*|  
|ReceiveStatusResponse|Receive|-设置**名称**到*ReceiveStatusResponse*<br />-设置**激活**到*False*|  
|SaveStatusResponse|Send|-设置**名称**到*SaveStatusResponse*|  

### <a name="adding-a-delay-shape"></a>添加延迟形状  
 如果你想要等待之间调用的业务流程**客户界面**并**Get_Status**并发程序，必须添加**延迟**向业务流程的形状。 必须添加**延迟**形状在业务流程将复制的响应后**的客户界面**并发程序的文件发送端口。 因此，必须添加**延迟**形状后面**SendResponse**形状。  

 内**延迟**形状，可以指定业务流程必须等待在继续之前通过将以下代码添加到的表达式编辑器的时间间隔**延迟**形状：  

```  
new System.TimeSpan(0,2,0)  
```  

 通过添加以下代码，该业务流程将等待两分钟后再继续下一步。 有关如何配置详细信息**延迟**形状中，请参阅[如何配置延迟形状](../../core/how-to-configure-the-delay-shape.md)。  

### <a name="adding-the-construct-message-shape"></a>添加构造消息形状  
 Oracle E-business Suite 的回应**的客户界面**并发程序包含请求 id。 若要获取并发程序的状态，必须在将作为参数传递相同的请求 ID **Get_Status**并发程序。 为此，请在业务流程中，必须包括**构造消息**形状，并在其中**消息赋值**形状。 目的**构造消息**形状是：  

- 若要从收到的响应中提取请求 ID**的客户界面**并发程序。  

- 若要构造一条消息，符合消息架构**Get_Status**并发程序。  

  有关**构造消息**形状中，设置**构造的消息**属性设置为**Get_StatusRequest**。  

  有关**消息赋值**形状中，添加如下。 在之前添加代码，您必须：  

```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<GetStatusForConcurrentProgram xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR'><RequestId /></GetStatusForConcurrentProgram>");  
Get_StatusRequest = XmlDoc;  
Get_StatusRequest.RequestId = xpath(Response,"string(/*[local-name()='RACUSTResponse']/*[local-name()='RACUSTResult']/text())");  
```  

### <a name="adding-ports"></a>添加端口  
 若要配置的端口，则指定下表中列出的每个逻辑端口的属性。 中列出的名称*端口*列对应于业务流程中显示的端口的名称。  

|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*<br />-创建一个操作*Cust_Interface*。 此操作用于**的客户界面**并发程序。<br />-创建一个操作*Get_Status*。 此操作用于**Get_Status**并发程序。|  
|LOBPort_GetStatus|-设置**标识符**到*LOBPort_GetStatus*<br />-设置**类型**到*LOBPort_GetStatusType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性值，以指定操作形状并将它们链接到的端口的消息。 中列出的名称**形状**列对应于消息形状的名称为业务流程关系图中显示。  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.Cust_Interface.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBport.Cust_Interface.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBport.Cust_Interface.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.Cust_Interface.Request*|  
|SendGetStatus|-设置**消息**到*Get_StatusRequest*<br />-设置**操作**到*LOBPort_GetStatus.Get_Status.Request*|  
|ReceiveStatusResponse|-设置**消息**到*Get_StatusResponse*<br />-设置**操作**到*LOBPort_GetStatus.Get_Status.Response*|  
|SaveStatusResponse|-设置**消息**到*Get_StatusResponse*<br />-设置**操作**到*ResponseOut.Get_Status.Request*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  

  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Oracle E-business Suite。  

  - 硬盘和相应的 BizTalk 业务流程放置包含来自 Oracle E-business Suite 的响应的响应消息的位置的文件端口上定义的位置。  

  - 定义两个物理 WCF 自定义或 WCF OracleEBS 发送端口，一个用于将消息发送到 Oracle E-business Suite 执行**客户界面**并发程序，另一个用于执行**Get_Status**并发程序。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  

     若要调用并发程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须设置正确的应用程序上下文中调用操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供某些绑定的属性以指定任何操作的应用程序上下文。 必须在用于调用并发程序的 WCF 自定义或 WCF OracleEBS 端口上设置这些绑定属性。  

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
 必须启动之前调用并发程序的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   文件接收端口接收请求消息的业务流程正在运行。  

-   运行文件发送端口以接收来自业务流程的响应消息。  

-   WCF 自定义或 WCF OracleEBS 发送端口以调用**的客户界面**并发程序正在运行。  

-   WCF 自定义或 WCF OracleEBS 发送端口以调用**Get_Status**并发程序正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须删除与用于调用架构一致的请求消息**的客户界面**并发程序。 例如，请求消息调用**的客户界面**并发程序是：  

```  
<RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <Description>Customer Interface Program</Description>  
  <StartTime></StartTime>  
  <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
  <ORG_ID>203</ORG_ID>  
</RACUST>  
```  

> [!NOTE]
>  用于调用并发程序的请求消息需要 SetOptions、 SetPrintOptions 和 SetRepeatOptions 等一些可选参数。 此处提供的请求消息不包含这些可选参数。 有关完整的请求消息，包括可选参数，请参阅[并发程序的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)。  

 业务流程将使用消息、 将其传递到 Oracle E-business Suite，并接收响应。 响应消息保存在指定的业务流程一部分的其他文件位置。 客户界面并发程序的响应类似于以下内容：  

```  
<?xml version="1.0" encoding="utf-8"?>  
<RACUSTResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <RACUSTResult>2794708</RACUSTResult>  
</RACUSTResponse>  
```  

 来自 Oracle E-business Suite 的响应包含请求 id。 业务流程从响应消息中提取的请求 ID，构造一条消息来调用**Get_Status**并发程序，并将其传递到 Oracle E-business Suite 执行**Get_Status**并发程序。 为收到的响应之后**Get_Status**并发程序复制到与第一个响应相同的文件位置。 为响应**Get_Status**并发程序如下所示：  

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
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以从文件导入的配置设置，以便不需要创建项如发送端口和接收同一业务流程的端口。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  

## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)