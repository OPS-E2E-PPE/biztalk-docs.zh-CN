---
title: "从 SAP 使用 BizTalk Server 接收到的 Idoc |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDOCs, sample (receiving)
- IDOCs, business scenarios for receiving
- IDOCs, receiving from SAP using BizTalk Server
ms.assetid: b904bf07-1108-4ed3-8564-d83eaafff247
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb03368a9d046eacf31f8b7bbed5c0a7f090c3d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="receive-idocs-from-sap-using-biztalk-server"></a>从 SAP 使用 BizTalk Server 接收到的 Idoc
接收 IDOC 涉及[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当了 RFC 服务器以接收来自 SAP 的特殊 RFC 呼叫。 SAP 适配器可以接收到的 Idoc 充当 RFC 服务器或 tRFC 服务器。 有关与 tRFC 服务器正常运行的适配器接收 IDOC 的详细信息，请参阅[接收从通过使用 BizTalk Server 事务上下文中的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现两个不同的操作，以接收到的 Idoc:  
  
-   **接收**操作允许适配器接收到的 Idoc 具有强类型的架构。  
  
-   **ReceiveIdoc**操作允许适配器接收到的 Idoc 具有弱类型的架构。 此操作作为字符串下一条 XML 消息中接收到的 Idoc \<idocData\>标记。  
  
 在适配器端中，你可以为指定值**ReceiveIDocFormat**绑定属性指定的适配器将会收到的 IDOC 的格式。  
  
-   **类型化**指定适配器将接收到的 Idoc 具有强类型的架构。 这会生成 XML IDOC。  
  
-   **字符串**指定适配器将接收到的 Idoc 与弱类型的架构。 这将生成的 XML 消息\<idocData\>标记。  
  
-   **Rfc**指定适配器将接收到的 Idoc 的任何格式。  
  
 用于接收到的 Idoc，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还支持在业务流程中的一组适配器客户端可以使用的消息上下文属性。 属性的列表，请参阅[接收到的 Idoc 的消息上下文属性](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)。  
  
 有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持接收到的 Idoc 从 SAP 系统，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 对于用于接收 IDOC 消息的 SOAP 结构的详细信息，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
## <a name="biztalk-scenarios-for-receiving-idocs-from-an-sap-system"></a>用于从 SAP 系统接收到的 Idoc 的 BizTalk 方案  
 下表提供了用于从 SAP 系统接收到的 Idoc 的密钥 BizTalk 方案：  
  
|从 SAP 输入到适配器|BizTalk 处理|“输出”|  
|-------------------------------|------------------------|------------|  
|（通过 tRFC 接口） 的 IDOC|**元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到**True**。<br />2.生成的架构**接收**操作特定的 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**类型化**。<br /><br /> **业务流程设计时**<br /><br /> 1.接收 XML IDOC。<br />2.使用平面文件汇编器将 XML IDOC 转换为平面文件。|平面文件 IDOC|  
|（通过 tRFC 接口） 的 IDOC|**元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到**True**。<br />2.生成的架构**接收**操作特定的 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**类型化**。<br /><br /> **业务流程的设计时**<br /><br /> 接收 XML IDOC。|XML IDOC|  
|（通过 tRFC 接口） 的 IDOC|**元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到**True**。<br />2.生成的架构**接收**操作特定的 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**字符串**。<br /><br /> **业务流程设计时**<br /><br /> 1.接收平面文件中的 IDOC 具有的 XML 消息\<idocData\>标记。<br />2.使用中的接收端口配置 WCF 适配器的 XPath 支持从 XML 消息中提取平面文件 IDoc。 例如：<br />     `/*[local-name()='ReceiveIdoc']/*[local-name()='idocData']`<br />3.平面文件反汇编程序用于将平面文件 IDOC 转换为 XML IDOC。<br /><br /> **重要**这种方法可以用于接收到的 Idoc 使用新的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并直接将其应用在现有 BizTalk 项目中编写从现有的 BizTalk SAP 适配器接收到的 Idoc。 这也是版本号小于发行版号 (SYSREL) 接收到的 Idoc 的建议的方法。|XML IDOC|  
|（通过 tRFC 接口） 的 IDOC|**元数据设计时**<br /><br /> 1.生成的架构**ReceiveIdoc**操作从 IDOC 节点使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />2.设置绑定属性 ReceiveIdocFormat 到**字符串**。<br /><br /> **业务流程设计时**<br /><br /> -收到的 IDOC 表示中的字符串为 XML 消息\<idocData\>标记。|XML 消息中的平面文件 IDOC|  
  
## <a name="how-to-receive-an-idoc-from-an-sap-system"></a>如何从某个 SAP 系统接收 IDOC？  
 执行对 SAP 系统使用的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要从某个 SAP 系统接收 IDOC，这些任务包括：  
  
1.  创建 BizTalk 项目，并为你想要在 SAP 系统调用 IDOC 生成架构。 生成架构时确保您设置所需的绑定属性中上, 表中列出。 有关如何设置绑定属性的说明，请参阅[配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
2.  在发送和接收消息从 SAP 系统的 BizTalk 项目中创建消息。  
  
3.  创建业务流程的 SAP 系统从接收 IDOC。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="samples-based-on-this-topic"></a>基于本主题的示例  
 示例、 ReceiveIDOC 和 ReceiveIDOC_SYSREL，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成架构*接收*操作*ORDERS03。V3.620*下的 IDOC */IDOC/ORDERS/ORDERS03*节点。 请参阅[浏览，搜索和获取元数据中 SAP IDOC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)有关如何为特定的 IDOC 生成架构的说明。 生成时的架构，你可能想要设置以下属性：  
  
-   *GenerateFlatFileCompatibleIDoc* – 生成\<appinfo\>标记，以便可以在 BizTalk 方案中使用 BizTalk 平面文件分析器来支持平面文件 Idoc。  
  
-   *FlatFileSegmentIndicator* – 指示如果 IDOC 架构\<appinfo\>标记应包含段定义名称或段类型名称。 这是使用希望发送/接收平面文件 IDOC 向/从 SAP 时适用。 如果*GenerateFlatFileCompatibleIDoc*设置为 false，则*FlatFileSegmentIndicator*绑定属性将被忽略。  
  
> [!IMPORTANT]
>  因为您正在生成的入站 IDOC 调用的架构，请确保选择**服务 （入站操作）**从**选择协定类型**下拉列表中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您从生成的架构中的第一步的邮件 BizTalk 项目的业务流程视图。  
  
 对于本主题中，你必须创建两条消息 — 一个用于从 SAP 系统，另一个用于发送响应接收 IDOC。  
  
 执行以下步骤以创建消息并将它们链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  向 BizTalk 项目中添加新的业务流程。  
  
2.  打开业务流程视图 BizTalk 项目中，如果不是已打开。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建消息，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ReceiveIDOC.SAPBindingSchema2*，其中*ReceiveIDOC*是 BizTalk 项目的名称。 *SAPBindingSchema2*是为接收操作生成的架构。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ReceiveIDOC.SAPBindingSchema3*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 SAP 系统接收到的 Idoc。 在典型方案中， [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 系统中收到的 IDOC 调用、 处理请求，并将传递到 SAP 系统的响应。 若要实现此业务流程的一部分，必须包含业务流程：  
  
-   双向接收端口从 SAP 系统接收到的 Idoc 和发送响应。  
  
-   发送和接收形状。  
  
-   构造消息形状，并在其中某个消息分配形状，生成响应发送到 SAP 系统。  
  
    > [!NOTE]
    >  如果业务流程中包含的双向接收端口 （请求-响应），以便从 SAP 系统接收到的 Idoc，业务流程必须将响应发送回 SAP 系统。 如果没有，SAP 系统不会发送下一步 IDOC。 但是，如果单向接收端口，业务流程没有要发送到 SAP 系统的响应。  
  
-   要发送到 SAP 系统从接收到的文件夹的 Idoc 单向发送端口。  
  
 从 SAP 系统接收 IDOC 示例业务流程如下所示：  
  
 ![业务流程能够接收到的 Idoc](../../adapters-and-accelerators/adapter-sap/media/20d4f251-2474-4fd5-becd-2915f9efa81b.gif "20d4f251-2474-4fd5-becd-2915f9efa81b")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-将设置**名称**到*ListenToSAP*<br /><br /> -将设置**激活**到*True*|  
|SaveIDOC|Send|-将设置**名称**到*SaveIDOC*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 在业务流程，必须生成响应，并将其发送到 SAP 系统。 若要执行此操作，你必须添加构造消息形状和消息分配到您的业务流程在其中的形状。 消息赋值形状调用生成一条响应消息发送到 SAP 系统的代码。 消息赋值形状还将设置到 SAP 系统发送的响应的操作。  
  
> [!IMPORTANT]
>  如果业务流程中包含的双向接收端口 （请求-响应），以便从 SAP 系统接收到的 Idoc，业务流程必须将响应发送回 SAP 系统。 如果没有，SAP 系统不会发送下一步 IDOC。 但是，如果单向接收端口，业务流程没有要发送到 SAP 系统的响应。  
  
 构造消息形状，请设置**构造消息**属性**响应**。  
  
 用于生成响应的代码可能与 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 示例代码，用于生成响应消息如下所示。  
  
```  
namespace IdocReceiveResponseMessageCreator  
{  
    public class IdocReceiveResponseMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\test\\in";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 IdocReceiveResponseMessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。  
  
 添加以下表达式来调用此代码从消息赋值形状并设置发送到 SAP 系统的响应操作。 若要添加一个表达式，双击要打开表达式编辑器中的消息分配形状。  
  
```  
Response = IdocReceiveResponseMessageCreator.IdocReceiveResponseMessageCreator.XMLMessageCreator();  
Response(WCF.Action)= "http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response";  
```  
  
> [!IMPORTANT]
>  在响应消息上，必须显式设置操作。 如果未设置操作，WCF 自定义适配器在通过附加到请求的操作的"响应"到达操作消息。 因此，响应消息的操作会成为`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/ReceiveResponse`。 但是，sapBinding 需要响应操作按追加"/ 响应"到所请求操作，例如`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response`。  
  
### <a name="adding-ports"></a>添加端口  
 请确保指定的逻辑端口的以下属性。 中列出的名称*端口*列是端口的名称的业务流程中所示。  
  
|端口|属性|  
|----------|----------------|  
|ReceiveIDOCPort|-将设置**标识符**到*ReceiveIDOCPort*<br /><br /> -将设置**类型**到*ReceiveIDOCPortType*<br /><br /> -将设置**通信模式**到*请求-响应*<br /><br /> -将设置**通信方向**到*接收发送*|  
|GetIDOCPort|-将设置**标识符**到*GetIDOCPort*<br /><br /> -将设置**类型**到*GetIDOCPortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*|  
  
> [!IMPORTANT]
>  如果业务流程中包含的双向接收端口 （请求-响应），以便从 SAP 系统接收到的 Idoc，业务流程必须将响应发送回 SAP 系统。 如果没有，SAP 系统不会发送下一步 IDOC。  
  
### <a name="adding-a-flat-file-assembler"></a>添加平面文件汇编器  
 你必须添加汇编程序将传入的 IDOC 消息转换为平面文件。  
  
##### <a name="to-add-a-flat-file-assembler"></a>若要添加平面文件汇编器  
  
1.  右键单击 BizTalk 项目，指向**添加**，然后选择**新项**。  
  
2.  从对话框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |类别|管道文件|  
    |Visual Studio 已安装的模板|发送管道|  
    |Name|SendIDOC|  
  
3.  这将打开管道设计器。 从**BizTalk 管道组件**工具箱中，拖动**平面文件汇编器**管道组件复制到**装配**发送管道的阶段。  
  
4.  从**管道组件属性**视图中，为指定值**文档架构**属性。 从下拉列表中，确保选择的架构对应 IDOC 接收操作。  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ListenToSAP|-将设置**消息**到*请求*<br /><br /> -将设置**操作**到*ReceiveIDOCPort.ReceiveIDOC.Request*|  
|SaveIDOC|-将设置**消息**到*请求*<br /><br /> -将设置**操作**到*GetIDOCPort.ReceiveIDOC.Request*|  
|SendResponse|-将设置**消息**到*响应*<br /><br /> -将设置**操作**到*ReceiveIDOCPort.ReceiveIDOC.Response*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   定义发送位置和物理发送端口。 此位置将包含来自 SAP 系统 Idoc。  
  
        > [!IMPORTANT]
        >  对于 XMLTransmit 管道，请确保你选择***SendIDOC***。 创建此管道作为 BizTalk 项目的一部分。  
  
    -   定义 WCF 自定义或 WCF SAP 接收端口。 此端口将收到来自 SAP 系统的入站的 IDOC 并将其传递到业务流程。 此端口也发送到 SAP 系统的响应。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。
  
        > [!IMPORTANT]
        >  请确保绑定属性**ReceiveIDocFormat**设置为**类型化**。  
  
        > [!IMPORTANT]
        >  如果绑定属性**EnableBizTalkCompatibilityMode**已设置为 true，请确保添加 BizTalk 属性架构 DLL 为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为你的 BizTalk 应用程序，即用的应用程序中的资源你部署项目。 有关将资源添加说明请参阅[与 SAP 适配器故障排除操作问题](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
 你还必须向 BizTalk 应用程序添加 IdocReceiveResponseMessageCreator 项目的程序集。 创建此项目以生成发送到 SAP 系统的响应。 为此：  
  
1.  在 BizTalk Server 管理控制台中，你可以导入的绑定，该 BizTalk 应用程序下的左侧的控制台树中右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。  
  
2.  在**添加资源**对话框中，单击**添加**并导航到包含 IdocReceiveResponseMessageCreator.dll 的文件夹。 选择该文件，然后单击**打开**。  
  
3.  在**添加资源**对话框中，单击**确定**。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动用于从 SAP 系统接收 IDOC BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)，或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   若要将传入的 IDOC 保存到文件位置的文件发送端口正在运行  
  
-   WCF 自定义或 WCF SAP 接收端口，以便接收到的 Idoc 从 SAP 系统正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，你必须转 SAP 系统，然后将 IDOC 发送到适配器。 适配器接收 IDOC 并将其保存到文件位置指定为业务流程的一部分。  
  
## <a name="possible-exceptions"></a>可能的异常  
 从 SAP 系统使用 BizTalk Server 接收 IDOC 时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)