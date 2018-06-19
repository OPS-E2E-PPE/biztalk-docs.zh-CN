---
title: 如何配置 SOAP 接收位置 |Microsoft 文档
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
ms.openlocfilehash: 5b33886296441082ea7d7e83b92659f81140d71f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250157"
---
# <a name="how-to-configure-a-soap-receive-location"></a>如何配置 SOAP 接收位置
可以通过编程方式或使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来配置 SOAP 接收位置。  
  
 **如何配置 SOAP 接收位置以编程方式**  
  
 对象模型使您可以创建和配置 BizTalk 资源管理器以编程方式接收位置。 BizTalk 资源管理器对象模型公开了**IReceiveLocation**接收具有的位置配置接口**TransportTypeData**读/写属性。 此属性以 XML 字符串的名称-值对形式接受 SOAP 接收位置配置属性包。 若要在 BizTalk 资源管理器对象模型中设置此属性，必须设置**InboundTransportLocation**属性**IReceiveLocation**接口。  
  
 **TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则 SOAP 适配器将使用 SOAP 接收位置配置的默认值，如下表所示。  
  
 下表列出了可在 SOAP 接收位置中为 BizTalk 浏览器对象模型设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**URI**|字符串|在部署服务器上包含 Web Services 的虚拟目录。|  
|**AddressableURI**|字符串|包含整个可调用 URL 的公用地址字段。<br /><br /> 默认值： 空白|  
|**UseSSO**|Boolean|指定 SOAP 适配器是否会向此接收位置收到的消息颁发单一登录票证。<br /><br /> 默认值：False|  
  
 请使用以下格式设置属性：  
  
```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  
  
 **URI**和**AddressableURI**属性都设置使用**地址**和**PublicAddress**接收位置的属性对象。  
  
 以下代码段显示了如何创建 SOAP 接收位置：  
  
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
  
 **如何配置 SOAP 接收与 BizTalk Server 管理控制台的位置**  
  
 您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置 SOAP 接收位置适配器变量。 如果未设置接收位置的属性，则使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在完成以下过程之前你必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
### <a name="to-configure-variables-for-a-soap-receive-location"></a>配置 SOAP 接收位置的变量  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要创建中的接收位置的应用程序。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**SOAP**从下拉列表中，然后单击**配置**。  
  
5.  在**SOAP 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**虚拟目录以及 Web 服务的.asmx 文件**|指示由 BizTalk Web Services 发布向导创建的 .asmx 文件。<br /><br /> 此消息的格式类似于以下格式：<br /><br /> /PurchaseOrder/POOrchestration.asmx<br /><br /> 其中，.asmx 文件的完整位置是 http://localhost/PurchaseOrder/POOrchestration.asmx。 **注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**公共地址**|指定此接收位置的完全限定 URI。 此属性的值是服务器名和虚拟目录的组合。 指定的 URI 应指定在向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送消息时贸易合作伙伴要连接到的公共网站 URL。<br /><br /> 此信息是可选的，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 并不使用。 管理员可使用此参数记录与接收位置相关联的公共 URL。|  
    |**使用单一登录**|指示 SOAP 适配器使用企业单一登录。 **注意：** BizTalk Web 服务发布向导允许您使用 SharePoint 门户服务器上单一登录; 此属性仅使企业单一登录。|  
  
6.  单击 **“确定”**。  
  
7.  在**接收位置属性**对话框框中，输入适当的值，以完成接收位置的配置，然后单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
 SOAP 接收位置使用的安全设置是在 IIS 中设置的。 默认情况下，SOAP 接收位置不设置为使用匿名身份验证。  
  
 当 SOAP 客户端调用 Web Services 时，SOAP 适配器将使用匿名、基本、摘要或 Windows 集成身份验证来对 SOAP 客户端进行验证。 如果用户通过验证，则将用户上下文传递到接收处理程序。  
  
> [!NOTE]
>  任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。 对于每个进程，只能有一个独立的接收器。  
  
### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a>若要更新虚拟目录以使用 ASP.NET 4.0  
  
1.  启动 Internet Information Services (IIS) 管理器。 单击**启动**，单击**所有程序**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  如果你需要连接到远程的 IIS 服务器，右键单击**Internet Information Services**节点，然后单击**连接**。  
  
3.  如果需要，请键入远程 IIS 服务器的计算机名称和凭据。  
  
4.  展开其中包含要更新的网站或虚拟目录的服务器名称。  
  
5.  展开**站点**。  
  
6.  展开**Default Web Site**。  
  
7.  展开要查看 Web 站点下的虚拟目录的默认 Web 站点。  
  
8.  右键单击你想要更新，以使用 ASP.NET 4.0，请单击该虚拟目录**管理应用程序**，然后单击**高级设置**。 **应用程序池**字段显示为选定的虚拟目录设置的应用程序池。 单击 **“确定”**。  
  
9. 在 Internet 信息服务 (IIS) 管理器窗口中，单击**应用程序池**。 详细信息窗格中显示服务器上的应用程序池的列表。  
  
10. 右键单击在步骤 8 中的应用程序池组，然后单击**基本设置**。  
  
11. 在**编辑应用程序池**对话框框中，进行以下更改：  
  
    -   **.NET framework 版本**到**4.0**  
  
    -   **托管的管道模式**到**经典**  
  
12. 单击**确定**以应用更改。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Web 服务](../core/consuming-web-services.md)