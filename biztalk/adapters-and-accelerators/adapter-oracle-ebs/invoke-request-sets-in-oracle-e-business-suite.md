---
title: 调用在 Oracle E-business Suite 中的请求集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a79bff63-325d-4745-ab0e-839e00476ab1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b00fd382bb46df9de740b2308ad87c28720165a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967771"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite"></a>调用在 Oracle E-business Suite 中的请求集
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]使您能够在 Oracle E-business Suite 中执行请求集。 请求集划分为一个或多个阶段和每个阶段包含一组报表和并发程序。 有关如何的适配器支持请求集的详细信息，请参阅[对请求设置的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。 对于调用请求设置消息的 SOAP 结构的信息，请参阅[为请求设置的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成中的步骤[创建 Oracle E-business Suite 应用程序的先决条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)。  
  
## <a name="how-to-invoke-request-sets-in-oracle-e-business-suite"></a>如何调用请求在 Oracle E-business Suite 集  
 执行对 Oracle E-business Suite 使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要调用请求集，这些任务：  
  
-   创建 BizTalk 项目，并为你想要调用的请求集生成架构。  
  
-   创建在 BizTalk 项目中为从 Oracle E-business Suite 发送和接收消息的消息。  
  
-   创建业务流程来调用请求组。  
  
-   生成和部署 BizTalk 项目。  
  
-   配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
-   启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用请求一组中，通过调用**函数安全报告**（友好名称） 请求设置从**应用程序对象库**应用程序。 请求集的实际名称是**FNDRSSUB43**。 此请求集时使用默认 Oracle E-business Suite 应用程序。 此请求集将返回请求 id。  
  
 因此，在此主题中，我们生成架构**FNDRSSUB43**请求组。 请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，为其类型由相应的架构定义。 你现在必须创建消息业务流程，并将它们链接到你在上一步中生成的架构。  
  
 在此业务流程中，你必须创建两条消息，另一个用于发送邮件，以调用请求集，另一个用于接收请求集的响应。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RequestSet.OracleEBSBindingRequestSets_FND。FNDRSSUB43*，其中 RequestSet 是 BizTalk 项目的名称。 OracleEBSBindingRequestSets 是为调用生成的架构**FNDRSSUB43**请求组。|  
  
6.  重复步骤 3 以创建一条消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |响应|*RequestSet.OracleEBSBindingRequestSets_FND。FNDRSSUB43Response*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用在 Oracle E-business Suite 中的请求集。 此业务流程，在删除时的请求消息的定义接收位置。 业务流程使用此消息，并将其传递到 Oracle E-business Suite 来调用**FNDRSSUB43**请求组。 为请求设置响应接收到来自 Oracle 和保存在另一个位置。 典型的业务流程，以调用请求集将包含：  
  
-   发送和接收形状来将消息发送到 Oracle E-business Suite 和接收响应。  
  
-   单向接收端口接收请求消息发送到 Oracle E-business Suite。  
  
-   双向发送端口将请求消息发送到 Oracle E-business Suite 和接收响应。  
  
-   单向发送端口将响应从 Oracle E-business Suite 发送到的文件夹。  
  
 要调用请求集示例业务流程如下所示：  
  
 ![业务流程来调用请求集](../../adapters-and-accelerators/adapter-oracle-ebs/media/ea161292-8613-4c0b-ac24-2f26c54bf3a3.gif "ea161292-8613-4c0b-ac24-2f26c54bf3a3")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 为每个消息形状中指定以下属性。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 中列出的名称*端口*列是业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是以前的业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.RequestSet.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.RequestSet.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.RequestSet.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.RequestSet.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 你必须立即生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Oracle E-business Suite。  
  
    -   硬盘和 BizTalk 业务流程放置包含来自 Oracle E-business Suite 的响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite。 你必须在发送端口中指定的操作。 有关如何创建发送端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  
  
         若要调用请求集使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须设置在其中调用该操作的适当的应用程序上下文。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供某些绑定属性以指定用于任何操作的应用程序上下文。 你必须在用于调用请求集的 WCF 自定义或 WCF OracleEBS 端口上设置这些绑定属性。  
  
        -   如果**ClientCredentialType**绑定属性设置为**数据库**，则必须指定以下的绑定属性，以设置应用程序上下文。  
  
            |绑定属性|值|  
            |----------------------|-----------|  
            |**OracleUserName**|指定 Oracle E-business Suite 用户的名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的大小写**OracleUserName**连接到 Oracle E-business Suite 时绑定属性。 用户名称传递给 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的用户名称的大小写或你想要输入用户名称包含特殊字符，你必须指定在双引号内的值。|  
            |**OraclePassword**|Oracle E-business Suite 用户的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的大小写**OraclePassword**连接到 Oracle E-business Suite 时绑定属性。 密码传递到 Oracle E-business Suite 使用标准规则的 SQL * Plus。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。|  
            |**OracleEBSResponsibilityName**|负责与 Oracle E-business Suite 用户关联。|  
  
        -   如果**ClientCredentialType**绑定属性设置为**EBusiness**，你必须已将指定 Oracle E-business 凭据建立连接时。 在这种情况下才必须指定值**OracleEBSResponsibilityName**绑定属性。  
  
         有关不同的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何的适配器支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
        > [!NOTE]
        >  你可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[配置 Oracle E-business Suite 的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文使用消息上下文属性的说明，请参阅[在 Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动的 BizTalk 应用程序调用的请求集。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口来调用**FNDRSSUB43**请求组运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，你必须删除与调用的架构一致的请求消息**FNDRSSUB43**请求组。 例如，请求消息来调用**FNDRSSUB43**请求集是：  
  
```  
<FNDRSSUB43 xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <StartTime></ StartTime>  
  <All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
    <FNDMNNAV xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNNAV>  
    <ns2:FNDMNMNU xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNMNU>  
    <ns2:FNDMNFUN xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNFUN>  
  </ns0:All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
</ns0:FNDRSSUB43>  
```  
  
> [!NOTE]
>  调用请求集的请求消息需要如 SetRelClassOptions、 SetPrintOptions、 SetRepeatOptions 和 SetNlsOptions 某些可选参数。 此处提供的请求消息不包含这些可选参数。 有关完整的请求消息，包括可选参数，请参阅[请求集的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)。  
  
 业务流程使用该消息，将其传递到 Oracle E-business Suite，并收到响应。 响应消息保存在其他文件位置指定为业务流程的一部分。 有关响应**FNDRSSUB43**请求集如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<FNDRSSUB43Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <FNDRSSUB43Result>2543208</FNDRSSUB43Result>  
</FNDRSSUB43Response>  
```  
  
 来自 Oracle E-business Suite 的响应包含一个请求 id。 请求 ID"0"表示最后一个提交操作上设置失败的请求。 在这种情况下，你可以指定在请求消息中，如 ContinueOnFail，找出失败的原因和进一步调试其他可选参数。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)