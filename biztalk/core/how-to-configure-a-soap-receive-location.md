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
ms.openlocfilehash: 4de95a4d414cddde0812f590c84c237866772741
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999262"
---
# <a name="how-to-configure-a-soap-receive-location"></a><span data-ttu-id="0d49c-102">如何配置 SOAP 接收位置</span><span class="sxs-lookup"><span data-stu-id="0d49c-102">How to Configure a SOAP Receive Location</span></span>
<span data-ttu-id="0d49c-103">可以通过编程方式或使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来配置 SOAP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="0d49c-103">You can configure a SOAP receive location either programmatically or by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

 <span data-ttu-id="0d49c-104">**如何配置 SOAP 接收位置以编程方式**</span><span class="sxs-lookup"><span data-stu-id="0d49c-104">**How to Configure a SOAP Receive Location Programmatically**</span></span>  

 <span data-ttu-id="0d49c-105">BizTalk 浏览器对象模型使您可以创建和配置接收位置以编程方式。</span><span class="sxs-lookup"><span data-stu-id="0d49c-105">The BizTalk Explorer object model enables you to create and configure receive locations programmatically.</span></span> <span data-ttu-id="0d49c-106">BizTalk 浏览器对象模型公开**IReceiveLocation**接收位置配置接口具有**TransportTypeData**读/写属性。</span><span class="sxs-lookup"><span data-stu-id="0d49c-106">The BizTalk Explorer object model exposes the**IReceiveLocation** receive location configuration interface that has a **TransportTypeData** read/write property.</span></span> <span data-ttu-id="0d49c-107">此属性以 XML 字符串的名称-值对形式接受 SOAP 接收位置配置属性包。</span><span class="sxs-lookup"><span data-stu-id="0d49c-107">This property accepts a SOAP receive location configuration property bag in the form of a name-value pair of XML strings.</span></span> <span data-ttu-id="0d49c-108">若要在 BizTalk 浏览器对象模型中设置此属性，必须设置**InboundTransportLocation**的属性**IReceiveLocation**接口。</span><span class="sxs-lookup"><span data-stu-id="0d49c-108">To set this property in the BizTalk Explorer object model, you must set the **InboundTransportLocation** property of the **IReceiveLocation** interface.</span></span>  

 <span data-ttu-id="0d49c-109">**TransportTypeData**的属性**IReceiveLocation**接口无需设置。</span><span class="sxs-lookup"><span data-stu-id="0d49c-109">The **TransportTypeData** property of the **IReceiveLocation** interface does not have to be set.</span></span> <span data-ttu-id="0d49c-110">如果未设置该属性，则 SOAP 适配器将使用 SOAP 接收位置配置的默认值，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="0d49c-110">If it is not set, the SOAP adapter uses the default values for the SOAP receive location configuration as indicated in the following table.</span></span>  

 <span data-ttu-id="0d49c-111">下表列出了可在 SOAP 接收位置中为 BizTalk 浏览器对象模型设置的配置属性：</span><span class="sxs-lookup"><span data-stu-id="0d49c-111">The following table lists the configuration properties that you can set in the BizTalk Explorer object model for the SOAP receive location.</span></span>  

|<span data-ttu-id="0d49c-112">属性名称</span><span class="sxs-lookup"><span data-stu-id="0d49c-112">Property name</span></span>|<span data-ttu-id="0d49c-113">类型</span><span class="sxs-lookup"><span data-stu-id="0d49c-113">Type</span></span>|<span data-ttu-id="0d49c-114">Description</span><span class="sxs-lookup"><span data-stu-id="0d49c-114">Description</span></span>|  
|-------------------|----------|-----------------|  
|<span data-ttu-id="0d49c-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="0d49c-115">**URI**</span></span>|<span data-ttu-id="0d49c-116">String</span><span class="sxs-lookup"><span data-stu-id="0d49c-116">String</span></span>|<span data-ttu-id="0d49c-117">在部署服务器上包含 Web Services 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="0d49c-117">Virtual directory containing the Web service on the deployment server.</span></span>|  
|<span data-ttu-id="0d49c-118">**AddressableURI**</span><span class="sxs-lookup"><span data-stu-id="0d49c-118">**AddressableURI**</span></span>|<span data-ttu-id="0d49c-119">String</span><span class="sxs-lookup"><span data-stu-id="0d49c-119">String</span></span>|<span data-ttu-id="0d49c-120">包含整个可调用 URL 的公用地址字段。</span><span class="sxs-lookup"><span data-stu-id="0d49c-120">Public address field containing the entire, callable URL.</span></span><br /><br /> <span data-ttu-id="0d49c-121">默认值： 空</span><span class="sxs-lookup"><span data-stu-id="0d49c-121">Default value: Blank</span></span>|  
|<span data-ttu-id="0d49c-122">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="0d49c-122">**UseSSO**</span></span>|<span data-ttu-id="0d49c-123">Boolean</span><span class="sxs-lookup"><span data-stu-id="0d49c-123">Boolean</span></span>|<span data-ttu-id="0d49c-124">指定 SOAP 适配器是否会向此接收位置收到的消息颁发单一登录票证。</span><span class="sxs-lookup"><span data-stu-id="0d49c-124">Specifies whether the SOAP adapter issues the Single Sign-On ticket to the messages that arrive on this receive location.</span></span><br /><br /> <span data-ttu-id="0d49c-125">默认值：False</span><span class="sxs-lookup"><span data-stu-id="0d49c-125">Default value: False</span></span>|  

 <span data-ttu-id="0d49c-126">请使用以下格式设置属性：</span><span class="sxs-lookup"><span data-stu-id="0d49c-126">Use the following format to set the properties:</span></span>  

```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  

 <span data-ttu-id="0d49c-127">**URI**并**AddressableURI**属性设置为使用**地址**并**PublicAddress**的接收位置属性对象。</span><span class="sxs-lookup"><span data-stu-id="0d49c-127">The **URI** and **AddressableURI** properties are set using the **Address** and **PublicAddress** properties of the receive location object.</span></span>  

 <span data-ttu-id="0d49c-128">以下代码段显示了如何创建 SOAP 接收位置：</span><span class="sxs-lookup"><span data-stu-id="0d49c-128">The following code fragment illustrates creating a SOAP receive location:</span></span>  

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

 <span data-ttu-id="0d49c-129">**如何配置 SOAP 接收位置使用 BizTalk Server 管理控制台**</span><span class="sxs-lookup"><span data-stu-id="0d49c-129">**How to Configure a SOAP Receive Location with the BizTalk Server Administration Console**</span></span>  

 <span data-ttu-id="0d49c-130">您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置 SOAP 接收位置适配器变量。</span><span class="sxs-lookup"><span data-stu-id="0d49c-130">You can set SOAP receive location adapter variables in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0d49c-131">如果未设置接收位置的属性，则使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置的默认接收处理程序值。</span><span class="sxs-lookup"><span data-stu-id="0d49c-131">If properties are not set in the receive location, the default receive handler values set in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console are used.</span></span>  

> [!NOTE]
>  <span data-ttu-id="0d49c-132">完成以下过程之前，必须已添加接收端口。</span><span class="sxs-lookup"><span data-stu-id="0d49c-132">Before completing the following procedures you must have already added a receive port.</span></span> <span data-ttu-id="0d49c-133">有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="0d49c-133">For more information, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  

### <a name="to-configure-variables-for-a-soap-receive-location"></a><span data-ttu-id="0d49c-134">配置 SOAP 接收位置的变量</span><span class="sxs-lookup"><span data-stu-id="0d49c-134">To configure variables for a SOAP receive location</span></span>  

1. <span data-ttu-id="0d49c-135">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要在其中创建接收位置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d49c-135">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application you want to create a receive location in.</span></span>  

2. <span data-ttu-id="0d49c-136">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在左窗格中，单击**接收端口**节点。</span><span class="sxs-lookup"><span data-stu-id="0d49c-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, in the left pane, click the **Receive Port** node.</span></span> <span data-ttu-id="0d49c-137">随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="0d49c-137">Then in the right pane, right-click the receive port that is associated with an existing receive location or that you want to associate with a new receive location, and then click **Properties**.</span></span>  

3. <span data-ttu-id="0d49c-138">在中**接收端口属性**对话框中，在左窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**以创建新的接收位置。</span><span class="sxs-lookup"><span data-stu-id="0d49c-138">In the **Receive Port Properties** dialog box, in the left pane, select **Receive Locations**, and then in the right pane, double-click an existing receive location or click **New**to create a new receive location.</span></span>  

4. <span data-ttu-id="0d49c-139">在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**SOAP**从下拉列表中，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-139">In the **Receive Location Properties** dialog box, in the **Transport** section next to **Type**, select **SOAP** from the drop-down list, and then click **Configure**.</span></span>  

5. <span data-ttu-id="0d49c-140">在中**SOAP 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0d49c-140">In the **SOAP Transport Properties** dialog box, do the following:</span></span>  


   |                     <span data-ttu-id="0d49c-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0d49c-141">Use this</span></span>                      |                                                                                                                                                                                                                                                                                                              <span data-ttu-id="0d49c-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0d49c-142">To do this</span></span>                                                                                                                                                                                                                                                                                                               |
   |---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="0d49c-143">**虚拟目录和 Web 服务.asmx 文件**</span><span class="sxs-lookup"><span data-stu-id="0d49c-143">**Virtual directory plus Web Service .asmx file**</span></span> |                                                                                                                 <span data-ttu-id="0d49c-144">指示由 BizTalk Web Services 发布向导创建的 .asmx 文件。</span><span class="sxs-lookup"><span data-stu-id="0d49c-144">Indicate the .asmx file created by the BizTalk Web Services Publishing Wizard.</span></span><br /><br /> <span data-ttu-id="0d49c-145">此消息的格式类似于以下格式：</span><span class="sxs-lookup"><span data-stu-id="0d49c-145">The format of this message is similar to the following:</span></span><br /><br /> <span data-ttu-id="0d49c-146">/PurchaseOrder/POOrchestration.asmx</span><span class="sxs-lookup"><span data-stu-id="0d49c-146">/PurchaseOrder/POOrchestration.asmx</span></span><br /><br /> <span data-ttu-id="0d49c-147">其中，.asmx 文件的完整位置是 http://localhost/PurchaseOrder/POOrchestration.asmx 。</span><span class="sxs-lookup"><span data-stu-id="0d49c-147">Where the full location of the .asmx file is http://localhost/PurchaseOrder/POOrchestration.asmx.</span></span> <span data-ttu-id="0d49c-148">**注意：** 的 URI 发送端口或接收位置不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="0d49c-148">**Note:**  The URI for a send port or receive location cannot exceed 256 characters.</span></span>                                                                                                                 |
   |                <span data-ttu-id="0d49c-149">**公用地址**</span><span class="sxs-lookup"><span data-stu-id="0d49c-149">**Public address**</span></span>                 | <span data-ttu-id="0d49c-150">指定此接收位置的完全限定 URI。</span><span class="sxs-lookup"><span data-stu-id="0d49c-150">Specify the fully qualified URI for this receive location.</span></span> <span data-ttu-id="0d49c-151">此属性的值是服务器名和虚拟目录的组合。</span><span class="sxs-lookup"><span data-stu-id="0d49c-151">The value for this property is a combination of the server name and the virtual directory.</span></span> <span data-ttu-id="0d49c-152">指定的 URI 应指定在向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送消息时贸易合作伙伴要连接到的公共网站 URL。</span><span class="sxs-lookup"><span data-stu-id="0d49c-152">The specified URI should designate the public Web site URL for trading partners to connect to when sending messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="0d49c-153">此信息是可选的，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 并不使用。</span><span class="sxs-lookup"><span data-stu-id="0d49c-153">This information is optional and is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0d49c-154">管理员可使用此参数记录与接收位置相关联的公共 URL。</span><span class="sxs-lookup"><span data-stu-id="0d49c-154">This parameter is available to allow administrators to document the public URL that the receive location is tied to.</span></span> |
   |              <span data-ttu-id="0d49c-155">**使用单一登录**</span><span class="sxs-lookup"><span data-stu-id="0d49c-155">**Use Single Sign-On**</span></span>               |                                                                                                                                                                                                 <span data-ttu-id="0d49c-156">指示 SOAP 适配器使用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="0d49c-156">Indicate that the SOAP adapter uses Enterprise Single Sign-On.</span></span> <span data-ttu-id="0d49c-157">**注意：** BizTalk Web Services 发布向导允许您使用 SharePoint Portal Server 单一登录; 此属性只能启用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="0d49c-157">**Note:**  The BizTalk Web Services Publishing Wizard allows you to use SharePoint Portal Server Single Sign-On; this property only enables Enterprise Single Sign-On.</span></span>                                                                                                                                                                                                 |


6. <span data-ttu-id="0d49c-158">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0d49c-158">Click **OK**.</span></span>  

7. <span data-ttu-id="0d49c-159">在中**接收位置属性**对话框框中，输入适当的值以完成配置该接收位置，然后单击**确定**以保存设置。</span><span class="sxs-lookup"><span data-stu-id="0d49c-159">In the **Receive Location Properties** dialog box, enter the appropriate values to complete the configuration of the receive location, and then click **OK** to save settings.</span></span> <span data-ttu-id="0d49c-160">璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="0d49c-160">For information about the **Receive Locations Properties** dialog box, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

   <span data-ttu-id="0d49c-161">SOAP 接收位置使用的安全设置是在 IIS 中设置的。</span><span class="sxs-lookup"><span data-stu-id="0d49c-161">The security settings used by the SOAP receive location are set in IIS.</span></span> <span data-ttu-id="0d49c-162">默认情况下，SOAP 接收位置不设置为使用匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="0d49c-162">By default, the SOAP receive location is not set to use anonymous authentication.</span></span>  

   <span data-ttu-id="0d49c-163">当 SOAP 客户端调用 Web Services 时，SOAP 适配器将使用匿名、基本、摘要或 Windows 集成身份验证来对 SOAP 客户端进行验证。</span><span class="sxs-lookup"><span data-stu-id="0d49c-163">While the SOAP client calls the Web service, the SOAP adapter authenticates the SOAP client by using either Anonymous, Basic, Digest, or Windows Integrated authentication.</span></span> <span data-ttu-id="0d49c-164">如果用户通过验证，则将用户上下文传递到接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d49c-164">If the user is verified, the user context is passed to the receive handler.</span></span>  

> [!NOTE]
>  <span data-ttu-id="0d49c-165">任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。</span><span class="sxs-lookup"><span data-stu-id="0d49c-165">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="0d49c-166">对于每个进程，只能有一个独立的接收器。</span><span class="sxs-lookup"><span data-stu-id="0d49c-166">You can have only one isolated receiver per process.</span></span>  

### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a><span data-ttu-id="0d49c-167">若要更新虚拟目录以使用 ASP.NET 4.0</span><span class="sxs-lookup"><span data-stu-id="0d49c-167">To update a virtual directory to use ASP.NET 4.0</span></span>  

1.  <span data-ttu-id="0d49c-168">启动 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="0d49c-168">Launch the Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="0d49c-169">单击**启动**，单击**所有程序**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-169">Click **Start**, click **All Programs**, and click **Internet Information Services (IIS) Manager**.</span></span>  

2.  <span data-ttu-id="0d49c-170">如果需要连接到远程 IIS 服务器，请右键单击**Internet 信息服务**节点，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-170">If you need to connect to a remote IIS server, right click the **Internet Information Services** node and then click **Connect**.</span></span>  

3.  <span data-ttu-id="0d49c-171">如果需要，请键入远程 IIS 服务器的计算机名称和凭据。</span><span class="sxs-lookup"><span data-stu-id="0d49c-171">Type the computer name for the remote IIS server and credentials if necessary.</span></span>  

4.  <span data-ttu-id="0d49c-172">展开其中包含要更新的网站或虚拟目录的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="0d49c-172">Expand the server name that houses the Web site or virtual directory to be updated.</span></span>  

5.  <span data-ttu-id="0d49c-173">展开**站点**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-173">Expand **Sites**.</span></span>  

6.  <span data-ttu-id="0d49c-174">展开**默认网站**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-174">Expand **Default Web Site**.</span></span>  

7.  <span data-ttu-id="0d49c-175">展开要查看 Web 站点下的虚拟目录的默认 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="0d49c-175">Expand the Default Web site to view the virtual directories under the Web site.</span></span>  

8.  <span data-ttu-id="0d49c-176">右键单击你想要更新，以使用 ASP.NET 4.0 中，单击虚拟目录**管理应用程序**，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-176">Right-click the virtual directory that you want to update to use ASP.NET 4.0, click **Manage Application**, and then click **Advanced Settings**.</span></span> <span data-ttu-id="0d49c-177">**应用程序池**字段显示为所选的虚拟目录设置的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="0d49c-177">The **Application Pool** field displays the application pool set for the selected virtual directory.</span></span> <span data-ttu-id="0d49c-178">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0d49c-178">Click **OK**.</span></span>  

9. <span data-ttu-id="0d49c-179">在 Internet 信息服务 (IIS) 管理器窗口中，单击**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-179">In the Internet Information Services (IIS) Manager window, click **Application Pools**.</span></span> <span data-ttu-id="0d49c-180">详细信息窗格中显示服务器上的应用程序池的列表。</span><span class="sxs-lookup"><span data-stu-id="0d49c-180">The details pane displays a list of application pools on the server.</span></span>  

10. <span data-ttu-id="0d49c-181">右键单击在步骤 8 中的应用程序池集，然后单击**基本设置**。</span><span class="sxs-lookup"><span data-stu-id="0d49c-181">Right-click the application pool set in step 8, and then click **Basic Settings**.</span></span>  

11. <span data-ttu-id="0d49c-182">在中**编辑应用程序池**对话框框中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="0d49c-182">In the **Edit Application Pool** dialog box, change the following:</span></span>  

    -   <span data-ttu-id="0d49c-183">**.NET framework 版本**到**4.0**</span><span class="sxs-lookup"><span data-stu-id="0d49c-183">**.NET Framework version** to **4.0**</span></span>  

    -   <span data-ttu-id="0d49c-184">**托管的管道模式**到**经典**</span><span class="sxs-lookup"><span data-stu-id="0d49c-184">**Managed pipeline mode** to **Classic**</span></span>  

12. <span data-ttu-id="0d49c-185">单击**确定**以应用更改。</span><span class="sxs-lookup"><span data-stu-id="0d49c-185">Click **OK** to apply the changes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0d49c-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d49c-186">See Also</span></span>  
 [<span data-ttu-id="0d49c-187">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0d49c-187">Consuming Web Services</span></span>](../core/consuming-web-services.md)