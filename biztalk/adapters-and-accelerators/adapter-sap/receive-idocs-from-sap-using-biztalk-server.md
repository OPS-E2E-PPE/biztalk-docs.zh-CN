---
title: 接收来自使用 BizTalk Server 的 SAP 的 Idoc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, sample (receiving)
- IDOCs, business scenarios for receiving
- IDOCs, receiving from SAP using BizTalk Server
ms.assetid: b904bf07-1108-4ed3-8564-d83eaafff247
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3620ea444dd42863ea8242640fb94c873f63c001
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989766"
---
# <a name="receive-idocs-from-sap-using-biztalk-server"></a>接收来自使用 BizTalk Server 的 SAP 的 Idoc
接收 IDOC 涉及[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当一个 RFC 服务器用于从 SAP 接收特殊的 RFC 调用。 SAP 适配器可以接收 Idoc 作为 RFC 服务器或 tRFC 服务器。 有关使用 tRFC 服务器正常运行的适配器接收 IDOC 的详细信息，请参阅[接收来自事务性上下文中使用 BizTalk server 中的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)。  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]两个不同的操作，用于接收 Idoc 的图面：  

- **接收**操作启用适配器用于接收 Idoc 具有强类型化的架构。  

- **ReceiveIdoc**操作启用适配器用于接收 Idoc 具有弱类型的架构。 此操作在下一条 XML 消息中字符串形式接收 Idoc \<idocData\>标记。  

  在适配器端中，可以指定的值**ReceiveIDocFormat**绑定属性来指定适配器将接收的 IDOC 的格式。  

- **类型化**指定适配器将接收 Idoc，具有强类型化的架构。 这会生成 XML IDOC。  

- **字符串**指定适配器将接收 Idoc 与弱类型的架构。 这将生成的 XML 消息\<idocData\>标记。  

- **Rfc**指定适配器将接收 Idoc 中的任何格式。  

  用于接收 Idoc，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还支持业务流程中的一组适配器客户端可以使用的消息上下文属性。 有关属性的列表，请参阅[接收 idoc 的消息上下文属性](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)。  

  详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持接收 Idoc 来自 SAP 系统，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 对于用于接收 IDOC 消息的 SOAP 结构有关的详细信息，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  

## <a name="biztalk-scenarios-for-receiving-idocs-from-an-sap-system"></a>用于从 SAP 系统接收 Idoc BizTalk 方案  
 下表提供用于从 SAP 系统接收 Idoc BizTalk 的关键方案：  


| 从 SAP 输入到适配器 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        BizTalk 处理                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |            “输出”             |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| （通过 tRFC 接口） 的 IDOC |                                                                                                                                                                                                                                                                                                                                           **元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到 **，则返回 True**。<br />2.生成的架构**接收**操作的特定 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**类型化**。<br /><br /> **业务流程设计时**<br /><br /> 1.收到 XML IDOC。<br />2.使用平面文件组装器将 XML IDOC 转换为平面文件。                                                                                                                                                                                                                                                                                                                                           |        平面文件 IDOC         |
| （通过 tRFC 接口） 的 IDOC |                                                                                                                                                                                                                                                                                                                                                                             **元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到 **，则返回 True**。<br />2.生成的架构**接收**操作的特定 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**类型化**。<br /><br /> **业务流程设计时**<br /><br /> 接收 XML IDOC。                                                                                                                                                                                                                                                                                                                                                                              |           XML IDOC            |
| （通过 tRFC 接口） 的 IDOC | **元数据设计时**<br /><br /> 1.设置绑定属性 GenerateFlatFileCompatibleIdocSchema 到 **，则返回 True**。<br />2.生成的架构**接收**操作的特定 IDOC 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />3.设置绑定属性 ReceiveIdocFormat 到**字符串**。<br /><br /> **业务流程设计时**<br /><br /> 1.接收 XML 消息中的平面文件 IDOC \<idocData\>标记。<br />2.使用中的接收端口配置 WCF 适配器的 XPath 支持从 XML 消息中提取平面文件 IDoc。 例如：<br />     `/*[local-name()='ReceiveIdoc']/*[local-name()='idocData']`<br />3.使用平面文件拆装器将平面文件 IDOC 转换为 XML IDOC。<br /><br /> **重要**这种方法可用于接收 Idoc 使用新的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并直接将其应用在现有 BizTalk 项目中编写用于从现有的 BizTalk SAP 适配器接收 Idoc。 这也是推荐的方法，用于接收 Idoc 版本号小于发行版号 (SYSREL)。 |           XML IDOC            |
| （通过 tRFC 接口） 的 IDOC |                                                                                                                                                                                                                                                                                                                                                                                     **元数据设计时**<br /><br /> 1.生成的架构**ReceiveIdoc**操作从 IDOC 节点使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。<br />2.设置绑定属性 ReceiveIdocFormat 到**字符串**。<br /><br /> **业务流程设计时**<br /><br /> -收到的 IDOC 中以字符串形式表示的 XML 消息\<idocData\>标记。                                                                                                                                                                                                                                                                                                                                                                                     | XML 消息中的平面文件 IDOC |

## <a name="how-to-receive-an-idoc-from-an-sap-system"></a>如何从 SAP 系统接收 IDOC？  
 对 SAP 系统使用执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要从 SAP 系统接收 IDOC，这些任务包括：  

1. 创建 BizTalk 项目，并为你想要在 SAP 系统中调用的 IDOC 生成架构。 生成架构时请确保设置所需的绑定属性中上, 表中列出。 有关如何设置绑定属性的说明，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  

2. 用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。  

3. 创建用于从 SAP 系统接收 IDOC 的业务流程。  

4. 生成并部署 BizTalk 项目。  

5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  

6. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="samples-based-on-this-topic"></a>基于本主题的示例  
 示例、 ReceiveIDOC 和 ReceiveIDOC_SYSREL，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  

## <a name="generating-schema"></a>生成架构  
 必须生成的架构*接收*操作的*ORDERS03。V3.620*下的 IDOC */IDOC/ORDERS/ORDERS03*节点。 请参阅[浏览、 搜索和获取元数据中 SAP 的 IDOC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)有关如何为特定的 IDOC 生成架构的说明。 同时生成架构，你可能想要设置以下属性：  

-   *GenerateFlatFileCompatibleIDoc* – 生成\<appinfo\>标记，以便可以在 BizTalk 方案中使用 BizTalk 平面文件分析器以支持平面文件 Idoc。  

-   *FlatFileSegmentIndicator* – 指示如果 IDOC 架构\<appinfo\>标记应包含段定义名称或段的类型名称。 这是使用希望发送/接收平面文件 IDOC 向/从 SAP 时才适用。 如果*GenerateFlatFileCompatibleIDoc*设置为 false，则*FlatFileSegmentIndicator*绑定属性将被忽略。  

> [!IMPORTANT]
>  因为您正在生成的入站 IDOC 调用的架构，请确保选择**服务 （入站操作）** 从**选择协定类型**下拉列表中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  

## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。  

 对于本主题中，您必须创建两条消息，一个用于接收 IDOC SAP 系统，另一个将响应发送。  

 执行以下步骤以创建消息并将其链接到该架构：  

#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  

1.  将新的业务流程添加到 BizTalk 项目。  

2.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  

3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  

4.  右键单击新创建消息，然后选择**属性窗口**。  

5.  在中**属性**窗格**Message_1**，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ReceiveIDOC.SAPBindingSchema2*，其中*ReceiveIDOC*是 BizTalk 项目的名称。 *SAPBindingSchema2*是为接收操作生成的架构。|  

6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*ReceiveIDOC.SAPBindingSchema3*。|  

## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 SAP 系统接收 Idoc。 在典型方案中，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]从 SAP 系统接收 IDOC 调用、 处理此请求，并将传递到 SAP 系统的响应。 若要实现此业务流程的一部分，必须包含该业务流程：  

- 一个双向接收端口以接收来自 SAP 系统的 Idoc 并发送响应。  

- 发送和接收形状。  

- 构造消息形状，并在其中消息赋值形状，以生成要发送到 SAP 系统的响应。  

  > [!NOTE]
  >  如果业务流程包含一个双向接收端口 （请求-响应） 用于从 SAP 系统接收 Idoc，业务流程必须发送到 SAP 系统的响应。 否则，SAP 系统不会发送下一步的 IDOC。 但是，如果一个单向接收端口，业务流程没有要发送到 SAP 系统的响应。  

- 一个单向发送端口以发送接收到的文件夹从 SAP 系统的 Idoc。  

  用于从 SAP 系统接收 IDOC 的示例业务流程如下所示：  

  ![用于接收 Idoc 的业务流程](../../adapters-and-accelerators/adapter-sap/media/20d4f251-2474-4fd5-becd-2915f9efa81b.gif "20d4f251-2474-4fd5-becd-2915f9efa81b")  

### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  

|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-设置**名称**到*ListenToSAP*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveIDOC|Send|-设置**名称**到*SaveIDOC*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  

### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 在业务流程内必须生成响应，并将其发送到 SAP 系统。 若要执行此操作，必须添加构造消息形状和消息赋值形状向业务流程中的。 消息赋值形状调用生成响应消息发送到 SAP 系统的代码。 消息赋值形状也设置为要发送到 SAP 系统的响应的操作。  

> [!IMPORTANT]
>  如果业务流程包含一个双向接收端口 （请求-响应） 用于从 SAP 系统接收 Idoc，业务流程必须发送到 SAP 系统的响应。 否则，SAP 系统不会发送下一步的 IDOC。 但是，如果一个单向接收端口，业务流程没有要发送到 SAP 系统的响应。  

 对于构造消息形状，请设置**构造的消息**属性设置为**响应**。  

 若要生成响应的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 用于生成响应消息的示例代码如下所示。  

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

 添加以下表达式调用来调用此代码从消息赋值形状以及设置发送到 SAP 系统的响应的操作。 若要添加一个表达式，请双击消息赋值形状以打开表达式编辑器。  

```  
Response = IdocReceiveResponseMessageCreator.IdocReceiveResponseMessageCreator.XMLMessageCreator();  
Response(WCF.Action)= "http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response";  
```  

> [!IMPORTANT]
>  在响应消息，必须显式设置该操作。 如果未设置操作，WCF 自定义适配器到达的操作消息，通过追加到请求的操作的"响应"。 因此，响应消息的操作变得`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/ReceiveResponse`。 但是，sapBinding 要求响应操作通过追加"/ 响应"到请求的操作，例如`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response`。  

### <a name="adding-ports"></a>添加端口  
 请确保指定的逻辑端口的以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  

|端口|属性|  
|----------|----------------|  
|ReceiveIDOCPort|-设置**标识符**到*ReceiveIDOCPort*<br /><br /> -设置**类型**到*ReceiveIDOCPortType*<br /><br /> -设置**通信模式**到*请求-响应*<br /><br /> -设置**通信方向**到*接收发送*|  
|GetIDOCPort|-设置**标识符**到*GetIDOCPort*<br /><br /> -设置**类型**到*GetIDOCPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*|  

> [!IMPORTANT]
>  如果业务流程包含一个双向接收端口 （请求-响应） 用于从 SAP 系统接收 Idoc，业务流程必须发送到 SAP 系统的响应。 否则，SAP 系统不会发送下一步的 IDOC。  

### <a name="adding-a-flat-file-assembler"></a>添加平面文件组装器  
 您必须添加要将传入的 IDOC 消息转换为平面文件组装器。  

##### <a name="to-add-a-flat-file-assembler"></a>若要添加平面文件组装器  

1.  右键单击 BizTalk 项目，指向**外**，然后选择**新项**。  

2.  从对话框中，执行以下步骤：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |类别|管道文件|  
    |Visual Studio 已安装的模板|发送管道|  
    |“属性”|SendIDOC|  

3.  这将打开管道设计器。 从**BizTalk 管道组件**工具箱中拖动**平面文件组装器**管道组件复制到**组装**发送管道阶段。  

4.  从**管道组件属性**视图中，为指定值**文档架构**属性。 从下拉列表中，确保选择的架构与 IDOC 对应接收操作。  

## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。  

|形状|属性|  
|-----------|----------------|  
|ListenToSAP|-设置**消息**到*请求*<br /><br /> -设置**操作**到*ReceiveIDOCPort.ReceiveIDOC.Request*|  
|SaveIDOC|-设置**消息**到*请求*<br /><br /> -设置**操作**到*GetIDOCPort.ReceiveIDOC.Request*|  
|SendResponse|-设置**消息**到*响应*<br /><br /> -设置**操作**到*ReceiveIDOCPort.ReceiveIDOC.Response*|  

 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  

 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。

 配置应用程序包括：  

- 选择应用程序的主机。  

- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  

  - 定义的发送位置和物理发送端口。 此位置将包含来自 SAP 系统的 Idoc。  

    > [!IMPORTANT]
    >  XMLTransmit 管道，请确保选择***SendIDOC***。 创建此管道的 BizTalk 项目的一部分。  

  - 定义 WCF 自定义或 WCF SAP 接收端口。 此端口将接收来自 SAP 系统的入站的 IDOC 并将其传递到业务流程。 此端口还会发送到 SAP 系统的响应。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。

    > [!IMPORTANT]
    >  请确保绑定属性**ReceiveIDocFormat**设置为**类型化**。  
    > 
    > [!IMPORTANT]
    >  如果绑定属性**EnableBizTalkCompatibilityMode**设置为 true，则请确保添加 BizTalk 属性架构 DLL 为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 BizTalk 应用程序，即，在其中应用程序中的资源在部署项目。 有关将资源添加的说明请参阅[SAP 适配器的故障排除操作问题](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。

  您还必须将 IdocReceiveResponseMessageCreator 项目的程序集添加到 BizTalk 应用程序。 创建此项目以生成要发送到 SAP 系统的响应。 为此：  

1.  在下导入绑定，其中的 BizTalk 应用程序的 BizTalk Server 管理控制台左侧的控制台树中右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  

2.  在中**添加资源**对话框中，单击**添加**并导航到包含 IdocReceiveResponseMessageCreator.dll 的文件夹。 选择该文件，然后单击**打开**。  

3.  在中**添加资源**对话框中，单击**确定**。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动用于从 SAP 系统接收 IDOC BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。

 在此阶段，请确保：  

-   运行文件发送端口以将传入的 IDOC 保存到文件位置  

-   WCF 自定义或 WCF SAP 接收端口用于接收 Idoc 从 SAP 系统正在运行。  

-   该操作的 BizTalk 业务流程正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须转 SAP 系统，并将 IDOC 发送到适配器。 适配器接收 IDOC，并将其保存到文件位置指定为业务流程的一部分。  

## <a name="possible-exceptions"></a>可能的异常  
 从 SAP 系统使用 BizTalk Server 接收 IDOC 时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。

## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)