---
title: "PartyResolution （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- orchestrations, examples
- parties, examples
- parties, orchestrations
- examples, routing
- orchestrations, parties
- examples, orchestrations
- examples, messages
- routing, messages
- messages, routing
ms.assetid: 220e6bc5-6f04-4f37-b0d0-f11c2cc14422
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abf8944c3f55422189c0866608a3fd412dafe21d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="partyresolution-biztalk-server-sample"></a>PartyResolution （BizTalk Server 示例）
PartyResolution 示例演示了如何配合使用 BizTalk 业务流程与参与方解析以将消息路由到两个可能的收件人中的某一个。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例运行用于演示以下各个不同角色的多个业务流程：  
  
-   买方业务流程：用于启动采购订单 (PO) 消息处理。  
  
-   供应商业务流程：用于演示入站和出站参与方解析。  
  
-   ShipmentAgency1 和 ShipmentAgency2 业务流程：用于根据采购订单上的发货目的地响应供应商业务流程。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 参与方解析是指确定发送消息的参与方的过程。 例如，你可能希望只让已知参与方发送消息。 出站参与方解析是指确定应将消息发送给哪些参与方的过程。  
  
 除参与方解析以外，本示例还将演示如何实现和使用角色。 例如，若要进行发货，你需要创建一个向其发送文档的发送端口，此文档指示发运方发送产品。 如果有多个发运方可供选择，则可以在业务流程中创建发运方角色，而不是创建只有发运方 URL 不同的多个发送端口。 然后，你可以将与产品发货有关的消息发送给该发运方角色。 你需要创建各个参与方，并为每个参与方和参与方证书都关联一个发送端口。 最后，在发运方角色中登记每个参与方以启用该参与方。 然后，你可在业务流程中动态指定将消息发送到哪个发运方。  
  
 本示例还演示了如何使用相关将传入消息与适当的业务流程实例匹配。  
  
-   买方、供应商和发货机构的业务流程如下所示：  
  
-   买方业务流程：  
  
    1.  以 .xml 文件的形式从内部部门接收采购订单消息。  
  
    2.  将采购订单消息发送给供应商。  
  
-   供应商业务流程：  
  
    1.  根据签名证书解析参与方（入站参与方解析）以更新源参与方。  
  
    2.  从买方接收激活消息（采购订单）。  
  
    3.  向买方发送采购订单确认消息。  
  
    4.  验证要送达的国家/地区。  
  
    5.  解析出站参与方以找到要使用的发货机构。 如果国家/地区是美国，则发货机构为 ShipmentAgency2。 如果国家/地区是加拿大，则发货机构为 ShipmentAgency1。  
  
    6.  向相应的发货机构发送发货订单请求消息。  
  
    7.  从相应的发货机构接收发货订单确认消息。  
  
    8.  向相应的发货机构发送发货通知消息。  
  
    9. 从相应的发货机构接收发货通知确认消息。  
  
    10. 将最终的采购订单送达回执消息发送给买方。  
  
-   发货机构业务流程（两个发货机构的业务流程相同）：  
  
    1.  从供应商接收发货订单请求消息。  
  
    2.  生成并发送发货订单请求消息的确认消息。  
  
    3.  从供应商接收发货通知消息。  
  
    4.  生成并发送发货通知消息的确认消息。  
  
 以下说明解释了此示例是如何设计的：  
  
-   BuyerProcess.odx 业务流程接收消息，然后使用自定义管道 MimePartyResSendPipeline 对该消息进行编码，再将其发送给供应商。 这是通过使用管道设计器构建和部署自定义发送管道实现的。 在将消息发送给供应商之前，系统使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的 BizTalk 组属性中指定的买方私钥对消息进行数字签名。  
  
-   然后，SupplierProcess.odx 业务流程使用自定义管道 MimePartyResReceivePipeline（其中包含 MIME/SMIME 解码器组件）对该消息进行解码，然后使用买方公钥执行入站参与方解析，以解析和验证买方标识。 这是通过构建和部署自定义接收管道实现的。  
  
-   供应商业务流程随后启动 POCorrelationSets，后者被定义为基于升级属性 PONo。 PONo 用于在后面的阶段中将入站和出站消息与此业务流程实例匹配，因为整个业务流程中包括多个发送和接收操作。  
  
-   供应商业务流程实现角色链接，以便处理入站和出站参与方解析。 供应商业务流程使用两种角色链接类型：  
  
    -   Buyer_Supplier 角色链接类型  
  
    -   Supplier_Shipment 角色链接类型  
  
-   在 Buyer_Supplier**角色链接**形状，供应商正在将提供程序角色，因为供应商购买者从接收第一条消息，买方在使用者角色中。 当供应商业务流程向买方角色发送确认消息时，有一个发送端口与买方相关联，该消息通过此指定发送端口发送给买方。 若要查找发送端口，右键单击**BuyerAgency**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**属性**。 发送端口将显示在**发送端口**。  
  
-   然后，此业务流程使用以下表达式返回合作伙伴信息，并通过调用名为 CheckPartyName 的外部程序集将一个 XML 文件写入一个文件夹。  
  
    ```  
    Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
    ```  
  
-   在 Supplier_Shipment**角色链接**形状，装运角色包含具有用于将消息从供应商发送到对相应传送一家旅行社具体取决于目标方的两个操作发送端口。 供应商角色包含一个具有两个操作的接收端口，这两个操作用于从发货机构接收响应。 在发送和接收这些消息时将使用相关，该相关基于 PONo。  
  
    > [!NOTE]
    >  在绑定供应商业务流程时，你将发现只有一个发送端口和两个接收端口需要绑定。 这是因为到目标参与方的发送端口已与目标参与方绑定。 此外，业务流程中的接收端口之一包含两个接收操作，因此即使你看到三个**接收**形状，其中只有两个需要绑定。  
  
-   供应商业务流程使用以下代码中的第一行，通过调用名为 QueryShipmentCatalogComponent 的外部程序集来获取发货机构。 然后，此业务流程使用第二行为发货角色设置目标参与方。  
  
    ```  
    strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
    Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
    ```  
  
-   生成 Shipper1Process.odx 和 Shipper2Process.odx 以从 SupplierProcess.odx 接收发货订单和发货通知，并将响应发送回 SupplierProcess.odx。 在这两个发运方业务流程中都将使用相关，且相关类型基于已升级的属性 PONo。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\Orchestrations\PartyResolution\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|BuyerBinding.xml、ShippingAgency1Binding.xml、ShippingAgency2Binding.xml 和 SupplierBinding.xml|用于如端口绑定之类的自动化设置。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|PartyResolution.sln|包含各种子文件夹中的所有项目的解决方案文件。|  
|PurchaseOrder.xml|示例输入采购订单。|  
|Setup.bat|用于生成和初始化本示例的各个部分。|  
|在 \Buyer 文件夹中：<br /><br /> Buyer.btproj、BuyerProcess.odx|用于实现本示例中的买方的 BizTalk 项目和业务流程。|  
|在 \Catalog 文件夹中：<br /><br /> Catalog.xml|用于根据采购订单中指定的发货目的地确定发货机构。|  
|在 \CheckPartyName 文件夹中：<br /><br /> AssemblyInfo.cs、CheckPartyName.csproj 和 Class1.cs|用于访问源参与方属性的 CheckPartyName 应用程序的 Microsoft Visual C# 项目和源文件。|  
|在 \FilePolling 文件夹中：<br /><br /> App.ico、AssemblyInfo.cs、FilePolling.cs、FilePolling.csproj、FilePolling.resx 和 FilePolling.sln|FilePolling 应用程序的 Visual C# 解决方案、项目、源文件以及相关文件。<br /><br /> 使用此应用程序可了解此自动化方案的进展情况。|  
|在 \Pipeline\projectschema 文件夹中：<br /><br /> MimePartyResReceivePipeline.btp、MimePartyResSendPipeline.btp|本示例中的各个不同角色使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道文件。|  
|在 \QueryShipmentCatalogComponent 文件夹中：<br /><br /> AssemblyInfo.cs、QueryShipmentCatalog.cs 和 QueryShipmentCatalogComponent.csproj|QueryShipmentCatalog 组件的 Visual C# 项目和源文件，该组件用于访问在 Catalog.xml 文件中定义的发货目录。<br /><br /> QueryShipmentCatalog 组件确定供应商要使用的发货机构。 它使用 Catalog.xml 中的数据，根据地理位置确定最佳发运方。|  
|在 \Schemas 文件夹中：<br /><br /> PODeliveryReceipt.xsd、POPropertySchema.xsd、PurchaseOrder.xsd、PurchaseOrderAcknowledgement.xsd、Schemas.btproj、ShipmentAdvice.xsd、ShipmentAdviceAcknowledgement.xsd、ShipmentOrderAcknowledgement.xsd 和 ShipmentOrderRequest.xsd|本示例中的各种角色使用的架构。|  
|在 \ShipmentAgency1 文件夹中：<br /><br /> ShipmentAdviceAck.btm、ShipmentAgency1.btproj、ShipmentOrderAck.btm 和 Shipper1Process.odx|用于实现本示例中的 ShipmentAgency1 的 BizTalk 项目、业务流程和映射。|  
|在 \ShipmentAgency2 文件夹中：<br /><br /> ShipmentAdviceAck.btm、ShipmentAgency2.btproj、ShipmentOrderAck.btm 和 Shipper2Process.odx|用于实现本示例中的 ShipmentAgency2 的 BizTalk 项目、业务流程和映射。|  
|在 \Supplier 文件夹中：<br /><br /> PO_POAck.btm、PO_ShipmentOrderRequest.btm、ShipmentAdviceAck_PODeliveryReceipt.btm、ShipmentOrder_ShipmentAdvice.btm、Supplier.btproj 和 SupplierProcess.odx|用于实现本示例中的供应商的 BizTalk 项目、业务流程和映射。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
> [!NOTE]
>  在生成并初始化本示例之前，需要确保将默认 BizTalk 进程内主机配置为“受信任验证”。 有关详细信息，请参阅[BizTalk Server 运行时安全建议](../core/biztalk-server-runtime-security-recommendations.md)。  
  
 64 位主机实例不支持 MIME 管道组件。 与文件适配器的发送和接收处理程序相关联的主机必须配置为仅 32 位主机。 有关详细信息此，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。 如果你已具有 32 位唯一的一个主机配置在系统上，并想要使用它，请参阅[配置文件适配器](../core/configure-the-file-adapter.md)配置与文件适配器相关联的主机的说明发送和接收处理程序。  
  
 本部分中提及的证书必须添加到为默认 BizTalk 进程内主机实例（将对消息进行签名）配置的登录帐户的“个人”存储中。  
  
 默认情况下，下面提到的 setup.bat 文件会将参与方解析示例添安装到默认 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中。 你可以修改 setup.bat 文件以将该示例部署到新的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中，方法是打开 setup.bat 文件，并将本部分前面的语句 `@ECHO Deploy Assemblies...` 替换为以下内容：  
  
```  
@ECHO Deploy Assemblies...  
  
btstask AddApp -ApplicationName:PartyResolutionSample -Description:"Party Resolution Orchestration sample from the SDK"  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Schemas\bin\Release\Schemas.dll -Options:GacOnAdd  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Pipeline\projectschema\bin\Release\ProjectSchema.dll -Options:GacOnAdd   
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Buyer\bin\Release\Buyer.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%BuyerBindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency1\bin\Release\ShipmentAgency1.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency1BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency2\bin\Release\ShipmentAgency2.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency2BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Supplier\bin\Release\Supplier.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%SupplierBindingFileName%  
```  
  
#### <a name="to-build-and-initialize-the-partyresolution-sample"></a>生成并初始化 PartyResolution 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \Orchestrations\PartyResolution  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。  
  
         在设置过程中，你可能会接收到以下警告或类似警告。 你可以放心地忽略它们。  
  
        ```  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
        (CompileODX target) ->  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
  
        ```  
  
3.  启动**Visual Studio 命令提示**。  
  
4.  键入下述命令将这些程序集安装到全局程序集缓存中：  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll  
  
    -   gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll  
  
5.  从证书颁发机构 (CA) 获得安全的电子邮件证书。 CA 可以是第三方颁发机构，也可以是你所在组织的颁发机构。 获得证书后，导出公钥和私钥。  
  
6.  若要将私钥导入主机实例登录帐户的“个人”存储区中，并将公钥导入本地计算机的“其他人”存储区中，请执行以下操作：  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开 BizTalk 组，然后展开**平台设置**。  
  
    2.  单击**主机实例**并查找显示默认进程内主机实例的登录帐户。 在默认安装中，默认的进程内主机的名称应为 BizTalkServerApplication。  
  
    3.  单击 **“启动”**，再单击 **“运行”**。 在**运行**框中，键入**mmc.exe**，然后单击**确定**。 为主机实例登录帐户输入正确的密码以打开该帐户下的 Microsoft 管理控制台 (MMC)。  
  
    4.  在“文件”  菜单上，单击“添加/删除管理单元” 。  
  
    5.  在**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。  
  
    6.  在**证书管理单元**对话框中，选择**我的用户帐户**，然后单击**完成**。  
  
    7.  在**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。  
  
    8.  在**证书管理单元**对话框中，选择**计算机帐户**，然后单击**下一步**。  
  
    9. 在**选择计算机**对话框中，选择**本地计算机**，然后单击**完成**。  
  
    10. 在**添加或删除管理单元**对话框中，单击**确定**。  
  
    11. 展开**证书-当前用户**节点，然后展开**个人**。 右键单击**证书**，单击**所有任务**，然后单击**导入**。  
  
    12. 导入私钥，并在向导中提供密码。  
  
    13. 展开**证书 （本地计算机）**节点，然后展开**其他人**。 右键单击**证书**，单击**所有任务**，然后单击**导入**。  
  
    14. 导入公钥。  
  
7.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，然后单击**属性**。 在**BizTalk 组-组属性**对话框中，选择**证书**。  
  
8.  在**证书**对话框中，单击**浏览**和选择你刚导入的私钥。 此处指定的证书用于对出站消息进行签名。 单击 **“确定”**。  
  
9. 若要更新本示例中的 BuyerAgency 参与方，请执行以下操作：  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，选择**方**。  
  
    2.  右键单击**BuyerAgency** ，然后单击**属性**。 在**BuyerAgency 的参与方属性**对话框中，选择**常规**。  
  
    3.  下**别名**部分的对话框中，添加具有名称和限定符设置为新的别名**WindowsUser**。 将值设置为用户名称的格式\<域 \ 用户名 > (例如 SOMEDOMAIN\someuser)。  
  
    4.  选择**证书**，然后单击**浏览**，然后选择你刚导入的公钥。 此处指定的证书将用于验证入站消息的发送方标识。 单击 **“确定”**。  
  
10. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机**。  
  
11. 右键单击**BizTalkServerApplication** ，然后单击**属性**。 在**BizTalkServerApplication-主机属性**对话框中，选择**证书**。  
  
12. 单击**浏览**和选择你刚导入的私钥。 此处指定的证书用于对入站消息进行解密。 单击 **“确定”**。  
  
13. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机实例**。  
  
14. 右键单击**BizTalkServerApplication** ，然后单击**重新启动**。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-partyresolution-sample"></a>运行 PartyResolution 示例  
  
1.  从以下文件夹中运行 FilePolling.exe：  
  
     *\<示例路径 >*\Orchestrations\PartyResolution\FilePolling\bin\Debug  
  
2.  单击**开始轮询**。  
  
3.  将所提供的采购订单实例文件 PurchaseOrder.xml 的副本复制到以下文件夹中：  
  
     *\<示例路径 >*\Orchestrations\PartyResolution\FileDrop\PurchaseOrder  
  
4.  观察以消息框形式提供的通知你本示例进度的消息序列：  
  
    1.  供应商从买方接收采购订单的时间。  
  
    2.  从发货机构 1 或 2 接收到发货订单请求的时间。  
  
    3.  发货机构 1 或 2 接收到发货通知的时间。  
  
    4.  供应商向买方发送采购订单送达回执的时间。  
  
5.  单击**退出**关闭文件轮询程序。  
  
> [!NOTE]
>  你可以编辑的国家/地区标记为"美国"的 PurchaseOrder.xml 中，然后重复步骤 2 和步骤 3。 观察装运顺序现在发送到装运机构 2。  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-partyresolution-sample"></a>卸载 PartyResolution 示例  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 到\<*示例路径*> \Orchestrations\ PartyResolution\\。  
  
2.  运行 Cleanup.bat。  
  
## <a name="see-also"></a>另请参阅  
 [参与方解析管道组件](../core/party-resolution-pipeline-component.md)   
 [如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [业务流程 （BizTalk Server 示例文件夹中）](../core/orchestrations-biztalk-server-samples-folder.md)