---
title: 向使用 BizTalk Server 的 SAP 发送 Idoc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, sample for sending
- IDOCs, sending to SAP using BizTalk Server
- IDOCs, business scenarios for sending
ms.assetid: 92042623-ffbf-472f-9515-e9a77eb320fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1030db388020104fcdf678cb08d09ec10fca0e58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372882"
---
# <a name="send-idocs-to-sap-using-biztalk-server"></a>向使用 BizTalk Server 的 SAP 发送 Idoc
所有对 SAP 的 IDOC 调用在内部被视为 tRFC 调用其中适配器可用作 tRFC 客户端，并在 SAP 发送 IDOC 中调用 RFC。 本部分介绍在使用向 SAP 发送 Idoc[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]两个不同的操作以发送 Idoc 的图面：  

- **发送**操作允许适配器客户端发送 Idoc 具有强类型化的架构。  

- **SendIdoc**操作允许适配器客户端发送 Idoc 具有弱类型的架构。 使用这种情况，适配器客户端可以将平面文件 Idoc 发送到 SAP 系统。 整个平面文件 IDOC 可能为 SendIdoc XML 消息中的节点值。  

  详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持将 Idoc 发送到 SAP 系统，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 对于以发送 IDOC 消息的 SOAP 结构有关的详细信息，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  

## <a name="biztalk-scenarios-for-sending-idocs-with-the-sap-adapter"></a>用于发送 Idoc 的 SAP 适配器与 BizTalk 方案  
 下表提供有关将 Idoc 发送到 SAP 系统的主要 BizTalk 方案：  


|       输入到 BizTalk        |                                                                                                                                                                                                                                                                                                                 BizTalk 处理                                                                                                                                                                                                                                                                                                                  | 输出到适配器 |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|        平面文件 IDOC         |                                                         **元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到 **，则返回 True**。<br />2.生成的架构**发送**操作的特定 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br /><br /> **业务流程设计时**<br /><br /> 1.接收平面文件 IDOC<br />2.使用平面文件拆装器将平面文件 IDOC 转换为使用刚生成的架构的 XML IDOC。<br />3.将操作设置为**发送**操作。                                                         |   发送消息    |
|        平面文件 IDOC         | **元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到 **，则返回 True**。<br />2.生成的架构**SendIdoc**操作从 IDOC 节点使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br /><br /> **业务流程设计时**<br /><br /> 1.接收平面文件 IDOC<br />2.使用平面文件拆装器将平面文件 IDOC 转换为 XML (在这种情况下，XML 消息包含\<idocData\>节点，其中包含整个平面文件 Idoc 消息) 使用刚生成的架构。<br />3.将操作设置为**SendIdoc**操作。 | SendIdoc 消息  |
|           XML IDOC            |                                                                                                                                                           **元数据设计时**<br /><br /> 生成的架构**发送**操作的特定 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br /><br /> **业务流程设计时**<br /><br /> 1.收到 XML IDOC。<br />2.将操作设置为**发送**操作。                                                                                                                                                           |   发送消息    |
| XML 消息中的平面文件 IDOC |                                                                                                                                                      **元数据设计时**<br /><br /> 生成的架构**SendIdoc**操作从 IDOC 节点使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br /><br /> **业务流程设计时**<br /><br /> 1.接收 XML 消息。<br />2.将操作设置为**SendIdoc**操作。                                                                                                                                                      | SendIdoc 消息  |

## <a name="how-to-send-an-idoc-to-an-sap-system"></a>如何将 IDOC 发送到 SAP 系统  
 对 SAP 系统使用执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要将 IDOC 发送到 SAP 系统，这些任务包括：  

1. 创建 BizTalk 项目，并为你想要在 SAP 系统中调用的 IDOC 生成架构。 生成架构时请确保设置所需的绑定属性中上, 表中列出。 有关如何设置绑定属性的说明，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  

2. 用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。  

3. 创建一个业务流程将 IDOC 发送到 SAP 系统。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，IDOCSend，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  

## <a name="generating-schema"></a>生成架构  
 本主题演示如何将 IDOC 发送到 SAP 系统，通过生成的架构*发送*\IDOC\ORDERS\ORDERS05\ORDERS05 下的操作。V3(620) IDOC。 请参阅[浏览、 搜索和获取 IDOC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)详细了解如何为特定的 IDOC 生成架构。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。  

 对于本主题中，您必须创建两条消息，另一个用于将 IDOC 发送到 SAP 系统，另一个用于接收响应。  

 执行以下步骤以创建消息并将其链接到该架构：  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

2.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  

3.  右键单击新创建消息，然后选择**属性窗口**。  

4.  在中**属性**窗格**Message_1**，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**IDOCSend**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*IDOCSend.SAPBindingSchema3*，其中*IDOCSend*是 BizTalk 项目的名称。 *SAPBindingSchema3*是发送操作生成的架构。|  

5.  重复上述步骤以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**IDOCResponse**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*IDOCSend.SAPBindingSchema4*。|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将 Idoc 发送到 SAP 系统。 在此业务流程中，删除平面文件 IDOC 在定义接收位置。 此文件将转换为 XML 请求消息使用平面文件拆装器。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用此消息并将其传递到 SAP 系统。 使用 GUID 响应从 SAP 收到并保存在另一个位置。 您必须包括发送和接收形状以将 Idoc 发送到 SAP 系统和接收响应。 此外必须包括平面文件拆装器将平面文件转换成一个 XML 文件。 将包含一个典型的业务流程将发送和 IDOC 到 SAP 系统：  

- 发送和接收形状来将消息发送到 SAP 系统和接收响应。  

- 一个单向接收端口以接收平面文件 Idoc 发送到 SAP 系统。  

- 平面文件拆装器将平面文件 IDOC 转换为 XML 文件。  

- 一个双向发送端口以将 IDOC 发送到 SAP 系统和接收响应。  

- 一个单向发送端口用于从 SAP 系统将响应发送到的文件夹。  

  示例业务流程将如下所示：  

  ![用于向 SAP 发送 Idoc 的业务流程](../../adapters-and-accelerators/adapter-sap/media/db1490c8-da52-4af3-8a4f-d93bd815025d.gif "db1490c8-da52-4af3-8a4f-d93bd815025d")  

### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveFile|Receive|-设置**名称**到*ReceiveFile*<br />-设置**激活**到 *，则返回 True*|  
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

### <a name="adding-a-flat-file-disassembler"></a>添加平面文件拆装器  
 必须将平面文件拆装器添加到您的业务流程将平面文件 IDOC 转换为 XML 格式。  

##### <a name="to-add-a-flat-file-disassembler"></a>若要添加平面文件拆装器  

1.  右键单击 BizTalk 项目，指向**外**，然后选择**新项**。  

2.  从对话框中，执行以下步骤：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Categories|管道文件|  
    |Visual Studio 已安装的模板|接收管道|  
    |“属性”|IDOCReceive|  

3.  这将打开管道设计器。 从**BizTalk 管道组件**工具箱中拖动**平面文件拆装器**管道组件复制到**拆装**接收管道阶段。  

4.  从**管道组件属性**视图中，为指定值**文档架构**属性。 从下拉列表中，确保选择与 IDOC 发送操作对应的架构。  

## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  

|形状|属性|  
|-----------|----------------|  
|ReceiveFile|-设置**消息**到*IDOCSend*<br />-设置**操作**到*FileIn.SendIDOC.Request*|  
|SendToLob|-设置**消息**到*IDOCSend*<br />-设置**操作**到*LOBPort.SendIDOC.Request*|  
|ReceiveResponse|-设置**消息**到*IDOCResponse*<br />-设置**操作**到*LOBPort.SendIDOC.Response*|  
|SendResponse|-设置**消息**到*IDOCResponse*<br />-设置**操作**到*SaveResponse.SendIDOC.Request*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  

  - 硬盘和相应 file 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  

    > [!IMPORTANT]
    >  XMLReceive 管道的此端口，请确保选择***IDOCReceive***。 创建此管道的 BizTalk 项目的一部分。  

  - 硬盘和相应的 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口上定义的位置。  

  - 定义一个物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。

    > [!NOTE]
    >  您还可以设置*AutoConfirmSentIdocs*绑定属性，可自动将 Idoc 提交到 SAP 系统。 如果您执行此操作，不需要显式调用 RfcConfirmTransID 操作提交 Idoc。 有关绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 有关 RfcConfirmTransID 操作的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。

## <a name="starting-the-application"></a>启动应用程序  
 必须启动将 IDOC 发送到 SAP 系统的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。

 在此阶段，请确保：  

-   文件接收端口接收请求消息的业务流程正在运行。  

-   运行文件发送端口以接收来自业务流程的响应消息。  

-   WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须删除该业务流程的请求消息。 对于此示例中，我们将在定义中删除平面文件 IDOC FILE 接收位置。 删除请求消息后，会发生下列操作：  

- 业务流程选取此平面文件 IDOC，并将其转换成的架构符合先前生成的架构的 XML 请求消息。  

- 如果你提供的请求消息包含一个 GUID，适配器将生成事务 ID (TID)，并将其发送到 SAP 系统。  

- 如果你提供的请求消息不包含一个 GUID，该适配器将生成一个 GUID，并使用该 GUID 来生成 TID。 TID 然后发送到 SAP 系统。  

  在这两种情况下，SAP 系统的响应消息包含的 GUID。 例如，对 ORDERS05 IDOC 上的发送操作的响应消息是：  

```  
<?xml version="1.0" encoding="utf-8"?>  
<SendResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send">  
  <guid>a5afe162-d5cc-47b0-bf6f-3b0bfe06a97e</guid>  
</SendResponse>  
```  

 在收到 GUID 之后必须调用**RfConfirmTransID**操作提交 TID。 有关详细信息**RfcConfirmTransID**操作，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 您可以创建新的业务流程可以调用此操作，或修改现有业务流程。 如果你想要创建新的业务流程，它将类似于在 SAP 系统上的任何其他业务流程。 如果你想要更新现有业务流程，请参阅[调用中使用 BizTalk Server 的 SAP Trfc](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)。 用于调用 tRFC，如本主题中所述的业务流程演示如何调用**RfcConfirmTransID**从同一业务流程的操作。  

> [!NOTE]
>  您不需要调用 RfcConfirmTransID 操作，如果您设置*AutoConfirmSentIdocs*属性绑定到**True**。  

## <a name="possible-exceptions"></a>可能的异常  
 将 IDOC 发送到 SAP 系统使用 BizTalk Server 时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。

## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)