---
title: 如何配置 SOAP 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], virtual directories
- SOAP adapters, code samples
- configuring [SOAP adapters], receive locations
- virtual directories, SOAP adapters
- SOAP adapters, receive locations
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- SOAP adapters, virtual directories
- receive locations, SOAP adapters
ms.assetid: 7e348409-9181-47e4-b3c0-c73eb2acffa3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e30d505450103258ffea837f16de14319f38729
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342300"
---
# <a name="how-to-configure-a-soap-receive-location"></a>如何配置 SOAP 接收位置
你可以配置 SOAP 接收位置，以编程方式或使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

 **如何配置 SOAP 接收位置以编程方式**  

 BizTalk 浏览器对象模型使您可以创建和配置接收位置以编程方式。 BizTalk 浏览器对象模型公开**IReceiveLocation**接收位置配置接口具有**TransportTypeData**读/写属性。 此属性接受 SOAP 接收位置配置属性包形式的 XML 字符串的名称-值对。 若要在 BizTalk 浏览器对象模型中设置此属性，必须设置**InboundTransportLocation**的属性**IReceiveLocation**接口。  

 **TransportTypeData**的属性**IReceiveLocation**接口无需设置。 如果未设置，则 SOAP 适配器将使用默认值为 SOAP 接收位置配置下表中所示。  

 下表列出了可在 BizTalk 浏览器对象模型中为设置 SOAP 接收位置的配置属性。  

|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**URI**|String|虚拟目录，其中包含部署服务器上的 Web 服务。|  
|**AddressableURI**|String|包含整个可调用 URL 的公用地址字段。<br /><br /> 默认值：空白|  
|**UseSSO**|Boolean|指定单一登录票证到达此消息的 SOAP 适配器问题是否接收位置。<br /><br /> 默认值：False|  

 使用以下格式设置的属性：  

```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  

 **URI**并**AddressableURI**属性设置为使用**地址**并**PublicAddress**的接收位置属性对象。  

 下面的代码段说明了如何创建 SOAP 接收位置：  

```  
// Use BizTalk Explorer object model to create new SOAP receive location.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  

// Add a new Request-Response port  
ReceivePort receivePort = explorer.AddNewReceivePort(true);  
receivePort.Name = "SampleReceivePort";  
receivePort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  

// Add primary SOAP receive location  
ReceiveLocation receiveLocation = receivePort.AddNewReceiveLocation();  
receiveLocation.Name = "SampleReceiveLocation";  
receiveLocation.Address = "/PurchaseOrder/POOrchestration.asmx";  
receiveLocation.TransportType = explorer.ProtocolTypes["SOAP"];  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
receiveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
foreach (ReceiveHandler receiveHandler in explorer.ReceiveHandlers)  
{  
if (receiveHandler.TransportType.Name == receiveLocation.TransportType.Name)  
{  
receiveLocation.ReceiveHandler = receiveHandler;   
}  
}  

// Save  
explorer.SaveChanges();   
```  

 **如何配置 SOAP 接收位置使用 BizTalk Server 管理控制台**  

 您可以设置 SOAP 接收位置适配器变量中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 如果属性未设置接收位置中，在中设置的默认接收处理程序值[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用管理控制台。  

> [!NOTE]
>  完成以下过程之前，必须已添加接收端口。 有关详细信息，请参阅 [如何创建接收端口](../core/how-to-create-a-receive-port.md)。  

### <a name="to-configure-variables-for-a-soap-receive-location"></a>若要配置 soap 接收位置的变量  

1. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要在其中创建接收位置的应用程序。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  

3. 在中**接收端口属性**对话框中，在左窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**以创建新的接收位置。  

4. 在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**SOAP**从下拉列表中，然后单击**配置**。  

5. 在中**SOAP 传输属性**对话框框中，执行以下操作：  


   |                     使用此选项                      |                                                                                                                                                                                                                                                                                                              执行的操作                                                                                                                                                                                                                                                                                                               |
   |---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **虚拟目录和 Web 服务.asmx 文件** |                                                                                                                 指示由 BizTalk Web Services 发布向导创建的.asmx 文件。<br /><br /> 此消息的格式为类似于下面：<br /><br /> /PurchaseOrder/POOrchestration.asmx<br /><br /> 其中，.asmx 文件的完整位置是 http://localhost/PurchaseOrder/POOrchestration.asmx 。 **注意：** URI 发送端口或接收位置不能超过 256 个字符。                                                                                                                 |
   |                **公用地址**                 | 指定此接收位置的完全限定 URI。 此属性的值是服务器名称和虚拟目录的组合。 指定的 URI 应指定贸易合作伙伴时将消息发送到连接到的公共网站 URL [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> 此信息是可选的不使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此参数，可允许管理员文档的接收位置绑定到的公共 URL。 |
   |              **使用单一登录**               |                                                                                                                                                                                                 指示 SOAP 适配器使用企业单一登录。 **注意：** BizTalk Web Services 发布向导，可使用 SharePoint Portal Server 单一登录;此属性只能启用企业单一登录。                                                                                                                                                                                                 |


6. 单击“确定” 。  

7. 在中**接收位置属性**对话框框中，输入适当的值以完成配置该接收位置，然后单击**确定**以保存设置。 有关“接收位置属性”  对话框的信息，请参阅 [如何创建接收位置](../core/how-to-create-a-receive-location.md)。  

   使用 soap 的安全设置接收位置在 IIS 中设置。 默认情况下，SOAP 接收位置未设置为使用匿名身份验证。  

   当 SOAP 客户端调用 Web 服务时，则 SOAP 适配器进行 SOAP 客户端身份验证通过使用匿名、 基本、 摘要式、 或 Windows 集成身份验证。 如果用户通过验证，用户上下文传递到接收处理程序。  

> [!NOTE]
>  会导致 SOAP 与 HTTP 共享同一进程的任何 IIS 配置不是有效的。 您可以每个进程只有一个独立的接收器。  

### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a>若要更新虚拟目录以使用 ASP.NET 4.0  

1.  启动 Internet 信息服务 (IIS) 管理器。 单击**启动**，单击**所有程序**，然后单击**Internet Information Services (IIS) Manager**。  

2.  如果需要连接到远程 IIS 服务器，请右键单击**Internet 信息服务**节点，然后单击**Connect**。  

3.  如有必要，请键入远程 IIS 服务器和凭据的计算机名称。  

4.  展开服务器名称所在的网站或虚拟目录以进行更新。  

5.  展开**站点**。  

6.  展开**默认网站**。  

7.  展开要查看 Web 站点下的虚拟目录的默认 Web 站点。  

8.  右键单击你想要更新，以使用 ASP.NET 4.0 中，单击虚拟目录**管理应用程序**，然后单击**高级设置**。 **应用程序池**字段显示为所选的虚拟目录设置的应用程序池。 单击“确定” 。  

9. 在 Internet 信息服务 (IIS) 管理器窗口中，单击**应用程序池**。 详细信息窗格中显示服务器上的应用程序池的列表。  

10. 右键单击在步骤 8 中的应用程序池集，然后单击**基本设置**。  

11. 在中**编辑应用程序池**对话框框中，进行以下更改：  

    -   **.NET framework 版本**到**4.0**  

    -   **托管的管道模式**到**经典**  

12. 单击**确定**以应用更改。  

## <a name="see-also"></a>请参阅  
 [使用 Web 服务](../core/consuming-web-services.md)