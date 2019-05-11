---
title: 调用业务服务方法使用 BizTalk Server 和 Siebel 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke business service methods
- business service methods, invoking
ms.assetid: cf437c4f-fa65-4f89-a197-c83869930b2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b9a7f701fe5aafe1a9692f45fd826ea99d5c5a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371489"
---
# <a name="invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter"></a>调用业务服务方法使用 BizTalk Server 和 Siebel 适配器
Siebel 业务服务是一系列可以在 Siebel 中直接调用的业务方法。 详细了解如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持调用业务服务在 Siebel 系统中，请参阅[在 Siebel 业务服务上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)。 对于执行业务服务操作的消息的 SOAP 结构有关的详细信息，请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)。  
  
## <a name="how-to-invoke-business-services"></a>如何调用业务服务？  
 执行对 Siebel 系统使用的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。 若要调用的业务服务，这些任务包括：  
  
1. 创建 BizTalk 项目，并为你想要调用的业务服务方法生成架构。  
  
2. 用于发送和接收来自 Siebel 系统的消息在 BizTalk 项目中创建消息。  
  
3. 创建业务流程调用业务服务方法在 Siebel 系统中。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，BusinessService，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 在本主题中，用于演示如何调用业务服务方法，我们将生成的架构**Execute**方法公开**时间戳**业务服务。 请参阅[检索 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，您必须创建两条消息，另一个用于将请求发送到 Siebel 系统，另一个用于接收响应。  
  
 执行以下步骤以创建消息并将其链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建消息，然后选择**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BusinessService.SiebelBindingSchema.Execute*，其中*BusinessService*是 BizTalk 项目的名称。 *SiebelBindingSchema*是用于调用生成的架构*Execute*业务服务方法。|  
  
5.  重复上述步骤以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BusinessService.SiebelBindingSchema.ExecuteResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用业务服务。 在将请求消息放在此业务流程，定义接收位置。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用此消息并将其传递到 Siebel 系统。 来自 Siebel 系统的响应保存到另一个位置。 典型的业务流程调用业务服务方法将包含：  
  
- 发送和接收形状来将消息发送到 Siebel 和接收响应。  
  
- 一个单向接收端口接收请求消息将发送到 Siebel。  
  
- 一个双向发送端口以将请求消息发送到 Siebel 和接收响应。  
  
- 一个单向发送端口以从 Siebel 将响应发送到的文件夹。  
  
  调用示例业务流程*Execute*方法*时间戳*业务服务，如下所示：  
  
  ![调用业务服务的业务流程](../../adapters-and-accelerators/adapter-siebel/media/5a776e5d-855f-4d1b-8d26-7de747b1865d.gif "5a776e5d-855f-4d1b-8d26-7de747b1865d")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-设置**名称**到*ReceiveXML*<br />-设置**激活**到 *，则返回 True*|  
|SendToLOB|Send|-设置**名称**到*SendToLOB*|  
|ReceiveResponse|Receive|-设置**名称**到*ReceiveResponse*<br />-设置**激活**到*False*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|FileIn|-设置**标识符**到*FileIn*<br />-设置**类型**到*FileInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*|  
|SaveResponse|-设置**标识符**到*SaveResponse*<br />-设置**类型**到*SaveResponseType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveXML|-设置**消息**到*请求*<br />-设置**操作**到*FileIn.ServiceInvoke.Request*|  
|SendToLOB|-设置**消息**到*请求*<br />-设置**操作**到*LOBPort.ServiceInvoke.Request*|  
|ReceiveResponse|-设置**消息**到*响应*<br />-设置**操作**到*LOBPort.ServiceInvoke.Response*|  
|SendResponse|-设置**消息**到*响应*<br />-设置**操作**到*SaveResponse.ServiceInvoke.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[如何生成业务流程](../../core/how-to-build-orchestrations.md)并[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序用于执行*Execute*方法*时间戳*在 Siebel 业务服务。 在启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 必须将请求消息放置到的文件接收位置。 本主题中前面生成的架构必须确认请求消息的架构。 请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)有关调用业务服务的架构的详细信息。 例如，请求消息调用*Execute*方法*时间戳*业务服务是：  
  
```  
<Execute xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation" />  
```  
  
 业务流程将使用请求消息并将其传递到 Siebel 系统。 来自 Siebel 系统的响应保存在文件发送位置。 上面的请求消息的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ExecuteResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation">  
  <ExecuteResult>  
    <Time xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp">2007-11-25T20:42:11.0000000</Time>  
  </ExecuteResult>  
</ExecuteResponse>  
```  
  
## <a name="possible-exceptions"></a>可能的异常  
 使用业务服务上执行操作时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理与 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。
  
## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)