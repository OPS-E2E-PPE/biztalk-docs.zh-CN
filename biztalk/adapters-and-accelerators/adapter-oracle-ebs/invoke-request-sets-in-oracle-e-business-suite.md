---
title: 调用请求集 Oracle E-business Suite 中的 |Microsoft Docs
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
ms.openlocfilehash: da52668f0e94da23afdd8246f0acb0ca89d1c36a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014118"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite"></a>调用 Oracle E-business Suite 中的请求集
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 可以在 Oracle E-business Suite 中执行请求集。 请求集划分为一个或多个阶段，并且每个阶段包含了一组报表和并发程序。 有关如何在适配器支持请求集的详细信息，请参阅[对请求设置操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。 对于用于调用请求集消息的 SOAP 结构有关的信息，请参阅[请求设置的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)。  

## <a name="prerequisites"></a>必要條件  
 你必须完成中的步骤[创建 Oracle E-business Suite 的应用程序的先决条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)。  

## <a name="how-to-invoke-request-sets-in-oracle-e-business-suite"></a>在 Oracle E-business Suite 中如何调用请求集  
 对 Oracle E-business Suite 使用执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要调用请求集，这些任务：  

- 创建 BizTalk 项目，并为你想要调用的请求集生成架构。  

- 用于 Oracle E-business Suite 中发送和接收消息的 BizTalk 项目中创建消息。  

- 创建一个业务流程调用请求集。  

- 生成并部署 BizTalk 项目。  

- 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

- 启动 BizTalk 应用程序。  

  本主题介绍如何执行这些任务。  

## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用请求集通过调用**函数的安全报告**（友好名称） 请求设置从**应用程序对象库**应用程序。 请求集的实际名称是**FNDRSSUB43**。 此请求集是可用于默认 Oracle E-business Suite 应用程序。 此请求集将返回请求 id。  

 因此，在本主题中，我们生成的架构**FNDRSSUB43**请求组。 请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到你在上一步中生成的架构。  

 在此业务流程中，你必须创建两条消息，其中一个将消息发送到调用请求集，另一个用于接收响应的请求集。  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  

2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  

4.  右键单击新创建的消息，然后依次**属性窗口**。  

5.  在中**属性**窗格**Message_1**，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RequestSet.OracleEBSBindingRequestSets_FND。FNDRSSUB43*，其中 RequestSet 是 BizTalk 项目的名称。 OracleEBSBindingRequestSets 是用于调用生成的架构**FNDRSSUB43**请求组。|  

6.  重复步骤 3 以创建一条消息。 在中**属性**窗格中的新消息，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |响应|*RequestSet.OracleEBSBindingRequestSets_FND。FNDRSSUB43Response*|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于调用 Oracle E-business Suite 中的请求集。 在此业务流程中删除时的请求消息定义接收位置。 业务流程使用此消息，并将其传递到 Oracle E-business Suite 来调用**FNDRSSUB43**请求组。 请求集的响应从 Oracle 接收，然后保存在另一个位置。 一个典型的业务流程调用请求集将包含：  

- 发送和接收形状来将消息发送到 Oracle E-business Suite 和接收响应。  

- 一个单向接收端口接收请求消息将发送到 Oracle E-business Suite。  

- 一个双向发送端口以将请求消息发送到 Oracle E-business Suite 和接收响应。  

- 一个单向发送端口用于从 Oracle E-business Suite 将响应发送到的文件夹。  

  示例业务流程调用请求集如下所示：  

  ![调用请求集的业务流程](../../adapters-and-accelerators/adapter-oracle-ebs/media/ea161292-8613-4c0b-ac24-2f26c54bf3a3.gif "ea161292-8613-4c0b-ac24-2f26c54bf3a3")  

### <a name="adding-message-shapes"></a>添加消息形状  
 为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-设置**名称**到*ReceiveMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendMessage|Send|-设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  

### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  

|端口|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，以前的业务流程中所示。  

|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-设置**消息**到*请求*<br />-设置**操作**到*MessageIn.RequestSet.Request*|  
|SendMessage|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.RequestSet.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.RequestSet.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*ResponseOut.RequestSet.Request*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  

  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Oracle E-business Suite。  

  - 硬盘和相应的 BizTalk 业务流程放置包含来自 Oracle E-business Suite 的响应的响应消息的位置的文件端口上定义的位置。  

  - 定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite。 您必须在发送端口中指定的操作。 有关如何创建发送端口的信息，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  

     若要调用请求集使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须设置正确的应用程序上下文中调用操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供某些绑定的属性以指定任何操作的应用程序上下文。 必须在用于调用请求集的 WCF 自定义或 WCF OracleEBS 端口上设置这些绑定属性。  

    - 如果**ClientCredentialType**绑定属性设置为**数据库**，则必须指定要设置应用程序上下文的以下绑定属性。  


      |        绑定属性         |                                                                                                                                                                                                                                                                                     ReplTest1                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | 指定 Oracle E-business Suite 用户的名称。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的用例**OracleUserName**属性绑定到 Oracle E-business Suite 连接时。 用户名称传递给 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的用户名的大小写或你想要输入用户名称包含特殊字符，必须指定在双引号内的值。 |
      |       **OraclePassword**        |   Oracle E-business Suite 用户的密码。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会保留你输入的值的用例**OraclePassword**属性绑定到 Oracle E-business Suite 连接时。 密码传递到 Oracle E-business Suite 使用 SQL 的标准规则\*加上。 但是，如果你想要保留的密码的情况下，或者你想要输入包含特殊字符的密码，你必须指定在双引号内的值。    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     与 Oracle E-business Suite 用户相关联的职责。                                                                                                                                                                                                                                                      |


    - 如果**ClientCredentialType**绑定属性设置为**EBusiness**，你必须已指定 Oracle 电子商务凭据建立连接时。 这种情况下才必须指定值**OracleEBSResponsibilityName**属性绑定。  

      有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 适配器如何支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

    > [!NOTE]
    >  您可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[配置适用于 Oracle E-business Suite 的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文中使用消息上下文属性的说明，请参阅[Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动调用请求集的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   文件接收端口接收请求消息的业务流程正在运行。  

-   运行文件发送端口以接收来自业务流程的响应消息。  

-   WCF 自定义或 WCF OracleEBS 发送端口以调用**FNDRSSUB43**请求组正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须删除与用于调用架构一致的请求消息**FNDRSSUB43**请求组。 例如，请求消息调用**FNDRSSUB43**请求集是：  

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
>  调用请求集的请求消息需要某些可选参数，例如 SetRelClassOptions、 SetPrintOptions、 SetRepeatOptions 和 SetNlsOptions。 此处提供的请求消息不包含这些可选参数。 有关完整的请求消息，包括可选参数，请参阅[请求集的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)。  

 业务流程将使用消息、 将其传递到 Oracle E-business Suite，并接收响应。 响应消息保存在指定的业务流程一部分的其他文件位置。 为响应**FNDRSSUB43**请求集如下所示：  

```  
<?xml version="1.0" encoding="utf-8"?>  
<FNDRSSUB43Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <FNDRSSUB43Result>2543208</FNDRSSUB43Result>  
</FNDRSSUB43Response>  
```  

 来自 Oracle E-business Suite 的响应包含请求 id。 请求 ID"0"表示最后一个提交操作上设置失败的请求。 在这种情况下，可以指定其他可选参数在请求消息中，如 ContinueOnFail，可以找出失败的原因并进行进一步调试。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  

## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器 ](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)