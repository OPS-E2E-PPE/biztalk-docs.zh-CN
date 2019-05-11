---
title: PartyResolution （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d0b60bb871ed25b344ef525bc85c90afaae04f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395016"
---
# <a name="partyresolution-biztalk-server-sample"></a>PartyResolution （BizTalk Server 示例）
PartyResolution 示例演示如何使用 BizTalk 业务流程具有将消息路由到两个可能的收件人的一个参与方解析。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例运行演示以下各个不同角色的多个业务流程：  

-   买方业务流程，用于启动采购订单 (PO) 消息处理。  

-   供应商业务流程，该示例演示了这两个入站和出站参与方解析。  

-   ShipmentAgency1 和 ShipmentAgency2 业务流程，响应根据采购订单的发货目的地供应商业务流程。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 参与方解析是指确定谁的过程 （即，参与方） 发送一条消息。 例如，你可能想要启用仅已知参与方发送一条消息。 出站参与方解析是指确定哪一方应发送一条消息的过程。  

 除了参与方解析，此示例演示如何实现和使用角色。 例如，若要处理你的产品发货，则创建发送端口向其发送的文档指示发运方交付产品。 如果有多个运货商可供选择，您可以在业务流程中创建发运方角色，而不是创建多个发送端口，其唯一的区别是送货商的 URL。 然后可以发送与产品发货再转为发运方角色相关的消息。 创建参与方，并将每个参与方和参与方证书的发送端口相关联。 最后，您登记每个参与方在发运方角色，若要启用它。 在业务流程，然后可以动态地指定哪个发运方发送到的消息。  

 此示例还演示如何使用相关来匹配传入消息与正确的业务流程实例。  

- 买方、 供应商和发货机构业务流程如下所示：  

- 买方业务流程：  

  1.  为.xml 文件从内部部门接收采购订单消息。  

  2.  将采购订单消息发送到供应商。  

- 供应商业务流程：  

  1.  解析参与方 （入站参与方解析） 以更新源参与方签名证书。  

  2.  从买方接收激活消息 (PO)。  

  3.  向买方发送采购订单确认消息。  

  4.  验证传递国家/地区。  

  5.  解析出站参与方查找要使用哪个发货机构。 如果国家/地区是美国，则发货机构为 ShipmentAgency2。 如果国家/地区是加拿大，则发货机构为 ShipmentAgency1。  

  6.  向相应的发货机构发送发货订单请求消息。  

  7.  从相应的发货机构接收发货订单确认消息。  

  8.  向相应的发货机构发送发货通知消息。  

  9. 从相应的发货机构接收发货通知确认消息。  

  10. 将最终的采购订单送达回执消息发送给买方。  

- 发货机构业务流程 （两个发货机构相同）：  

  1.  从供应商接收发货订单请求消息。  

  2.  生成并发送发货订单请求消息的确认消息。  

  3.  从供应商接收发货通知消息。  

  4.  生成并发送发货通知消息的确认消息。  

  以下说明解释了如何设计此示例：  

- BuyerProcess.odx 业务流程接收消息，并使用自定义管道 MimePartyResSendPipeline 对消息进行编码并将其发送给供应商。 这是通过使用管道设计器来生成和部署自定义发送管道。 将消息发送给供应商之前, 该消息进行数字签名买方私钥，后者在 BizTalk 组属性中指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

- SupplierProcess.odx 业务流程使用自定义管道 MimePartyResReceivePipeline，其中包括 MIME/SMIME 解码器组件，若要解码的消息和执行使用买方公钥进行解析和验证入站参与方解析购买者的标识。 这是通过构建和部署自定义接收管道。  

- 供应商业务流程随后启动 POCorrelationSets，后者定义要基础基于升级属性 PONo。 PONo 用于在后面的阶段中，匹配到此业务流程实例的入站和出站消息，因为有多个发送和接收整个业务流程的操作。  

- 供应商业务流程实现角色链接，以便处理入站和出站参与方解析。 供应商业务流程使用两种角色链接类型：  

  -   Buyer_Supplier 角色链接类型  

  -   Supplier_Shipment 角色链接类型  

- 在 Buyer_Supplier**角色链接**形状中将提供程序角色是供应商和买方属于使用者角色，因为供应商从买方接收第一条消息。 当供应商业务流程向买方角色发送确认，则发送端口与买方相关联，将消息发送给买方通过指定发送端口。 若要查找该发送端口，右键单击**BuyerAgency**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**属性**。 发送端口将显示在下**发送端口**。  

- 然后，业务流程使用以下表达式返回合作伙伴信息，并将 XML 文件写入到通过调用名为 CheckPartyName 的外部程序集的文件夹。  

  ```  
  Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
  ```  

- 在 Supplier_Shipment**角色链接**形状，发货角色包含具有用于将消息从供应商发送到目标参与方根据相应的发货机构的两个操作的发送端口。 供应商角色包含一个具有两个用于从发货机构接收响应的操作的接收端口。 发送和接收这些消息时，将使用相关和基于 PONo。  

  > [!NOTE]
  >  在绑定供应商业务流程时，您会发现只有一个发送端口和两个接收端口需要绑定。 这是因为与参与方已绑定到目标参与方的发送端口。 此外，一个业务流程中的接收端口包含两个接收操作，因此，即使你看到了三个**接收**形状，其中只有两个需要绑定。  

- 供应商业务流程使用的第一行中的以下代码通过调用名为 QueryShipmentCatalogComponent 的外部程序集获取发货机构。 然后使用第二行来设置发货角色的目标参与方。  

  ```  
  strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
  Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
  ```  

- 生成 Shipper1Process.odx 和 Shipper2Process.odx 是构建从 SupplierProcess.odx 接收发货订单和发货通知并将响应发送回 SupplierProcess.odx。 在这两个发运方业务流程，将使用相关，和相关类型基于升级属性 PONo。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \Orchestrations\PartyResolution\  

 下表显示了本示例中的文件及其用途说明：  


|                                                                                                                                 文件                                                                                                                                 |                                                                                                                                                              Description                                                                                                                                                              |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                      BuyerBinding.xml，ShippingAgency1Binding.xml，ShippingAgency2Binding.xml SupplierBinding.xml                                                                                      |                                                                                                                                            用于如端口绑定之类的自动化设置。                                                                                                                                             |
|                                                                                                                               Cleanup.bat                                                                                                                               |                                                                   用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。                                                                    |
|                                                                                                                           PartyResolution.sln                                                                                                                           |                                                                                                                              包含所有各个子文件夹中的项目的解决方案文件。                                                                                                                               |
|                                                                                                                            PurchaseOrder.xml                                                                                                                            |                                                                                                                                                           示例输入采购订单。                                                                                                                                                            |
|                                                                                                                                Setup.bat                                                                                                                                |                                                                                                                                         用于生成并初始化本示例的部分。                                                                                                                                         |
|                                                                                                    在 \Buyer 文件夹中：<br /><br /> Buyer.btproj、 BuyerProcess.odx                                                                                                     |                                                                                                                             BizTalk 项目和业务流程用于实现本示例中的买方。                                                                                                                             |
|                                                                                                             在 \Catalog 文件夹中：<br /><br /> Catalog.xml                                                                                                             |                                                                                                                         用于确定基于采购订单中指定的发货目的地的发货机构。                                                                                                                          |
|                                                                                      在 \CheckPartyName 文件夹中：<br /><br /> AssemblyInfo.cs、 checkpartyname.csproj 和 Class1.cs                                                                                       |                                                                                                  Microsoft Visual C# 项目文件和源文件的用于访问源参与方的属性的 CheckPartyName 应用程序。                                                                                                   |
|                                                                在 \FilePolling 文件夹中：<br /><br /> App.ico、 AssemblyInfo.cs、 FilePolling.cs、 FilePolling.csproj、 FilePolling.resx、 和 filepolling.sln                                                                 |                                                                 Visual C# 解决方案、 项目、 源和 FilePolling 应用程序关联的文件。<br /><br /> 使用此应用程序可了解此自动化方案的进展。                                                                  |
|                                                                            在 \Pipeline\projectschema 文件夹中：<br /><br /> MimePartyResReceivePipeline.btp, MimePartyResSendPipeline.btp                                                                             |                                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在此示例中的不同角色使用的管道文件。                                                                                             |
|                                                                在 \QueryShipmentCatalogComponent 文件夹中：<br /><br /> AssemblyInfo.cs、 QueryShipmentCatalog.cs 和 QueryShipmentCatalogComponent.csproj                                                                 | Visual C# 项目文件和源文件 QueryShipmentCatalog 组件用于访问在 Catalog.xml 文件中定义的发货目录。<br /><br /> QueryShipmentCatalog 组件确定供应商将使用的发货机构。 它使用 Catalog.xml 中的数据来确定最佳发运方根据地理位置。 |
| 在 \Schemas 文件夹中：<br /><br /> PODeliveryReceipt.xsd、 POPropertySchema.xsd、 PurchaseOrder.xsd、 PurchaseOrderAcknowledgement.xsd、 Schemas.btproj、 ShipmentAdvice.xsd、 ShipmentAdviceAcknowledgement.xsd、 ShipmentOrderAcknowledgement.xsd、 ShipmentOrderRequest.xsd |                                                                                                                                           此示例中的各种角色所使用的架构。                                                                                                                                           |
|                                                                  在 \ShipmentAgency1 文件夹中：<br /><br /> ShipmentAdviceAck.btm，ShipmentAgency1.btproj，和 Shipper1Process.odx                                                                   |                                                                                                                      BizTalk 项目、 业务流程和用于实现本示例中的 ShipmentAgency1 的映射。                                                                                                                       |
|                                                                  在 \ShipmentAgency2 文件夹中：<br /><br /> ShipmentAdviceAck.btm，ShipmentAgency2.btproj，和 Shipper2Process.odx                                                                   |                                                                                                                      BizTalk 项目、 业务流程和用于实现本示例中的 ShipmentAgency2 的映射。                                                                                                                       |
|                                     在 \Supplier 文件夹中：<br /><br /> PO_POAck.btm、 PO_ShipmentOrderRequest.btm、 ShipmentAdviceAck_PODeliveryReceipt.btm、 ShipmentOrder_ShipmentAdvice.btm、 supplier.btproj 和、 SupplierProcess.odx                                     |                                                                                                                        BizTalk 项目、 业务流程和用于实现本示例中的供应商的映射。                                                                                                                        |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

> [!NOTE]
>  生成并初始化本示例之前，您需要确保默认 BizTalk 进程内主机配置为受信任的身份验证。 有关详细信息，请参阅[BizTalk Server 运行时安全建议](../core/biztalk-server-runtime-security-recommendations.md)。  

 在 64 位主机实例中不支持 MIME 管道组件。 在主机与发送和接收处理程序文件适配器必须配置为仅 32 位的主机。 为此，请参阅的详细信息[如何修改主机属性](../core/how-to-modify-host-properties.md)。 如果已配置的系统上，32 位仅主机并想要使用它，请参阅[配置文件适配器](../core/configure-the-file-adapter.md)发送和接收处理程序配置与文件适配器的相关联的主机上的说明。  

 在本部分中所述的证书必须添加到配置为将对消息进行签名的默认 BizTalk 进程内主机实例的登录帐户的个人存储。  

 下面所述的文件将在默认的参与方解析示例安装默认情况下，setup.bat[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 您可以修改 setup.bat 文件部署到新的示例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序通过打开 setup.bat 文件，并替换为部分中前面的语句`@ECHO Deploy Assemblies...`以下：  

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

#### <a name="to-build-and-initialize-the-partyresolution-sample"></a>若要生成并初始化 PartyResolution 示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*示例路径*> \Orchestrations\PartyResolution  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口。  

      在安装过程中，可能会收到以下或类似警告。 您可以放心地忽略它们。  

     ```  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
     (CompileODX target) ->  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  

     ```  

3. 启动**Visual Studio 命令提示符**。  

4. 键入以下命令以将程序集安装到全局程序集缓存：  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll  

5. 从证书颁发机构 (CA) 获取安全的电子邮件证书。 CA 可以是第三方颁发机构或组织中的颁发机构。 获取证书后，导出公钥和私钥。  

6. 专用密钥导入到的主机实例登录帐户和到本地计算机其他人存储公钥的个人存储中，执行以下操作：  

   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开 BizTalk 组，然后展开**平台设置**。  

   2. 单击**主机实例**和查找显示为默认进程内主机实例的登录帐户。 在默认安装中默认进程内主机应为 BizTalkServerApplication。  

   3. 单击 **“启动”**，再单击 **“运行”**。 在中**运行**框中，键入**mmc.exe**，然后单击**确定**。 输入要打开该帐户下的 Microsoft 管理控制台 (MMC) 的主机实例登录帐户的正确密码。  

   4. 在“文件”  菜单上，单击“添加/删除管理单元” 。  

   5. 在中**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。  

   6. 在中**管理单元中的证书**对话框中，选择**我的用户帐户**，然后单击**完成**。  

   7. 在中**添加或删除管理单元**对话框中，选择**证书**，然后单击**添加**。  

   8. 在中**管理单元中的证书**对话框中，选择**计算机帐户**，然后单击**下一步**。  

   9. 在中**选择计算机**对话框中，选择**本地计算机**，然后单击**完成**。  

   10. 在中**添加或删除管理单元**对话框中，单击**确定**。  

   11. 展开**证书-当前用户**节点，然后展开**个人**。 右键单击**证书**，单击**的所有任务**，然后单击**导入**。  

   12. 导入的私钥并提供在向导中的密码。  

   13. 展开**证书 （本地计算机）** 节点，然后展开**其他人**。 右键单击**证书**，单击**的所有任务**，然后单击**导入**。  

   14. 导入的公钥。  

7. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，然后单击**属性**。 在中**BizTalk 组-组属性**对话框中，选择**证书**。  

8. 在中**证书**对话框中，单击**浏览**并选择刚导入的私钥。 此处指定的证书用于对出站消息进行签名。 单击“确定” 。  

9. 若要更新 BuyerAgency 参与方在此示例中执行以下步骤：  

   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，选择**方**。  

   2. 右键单击**BuyerAgency** ，然后单击**属性**。 在中**BuyerAgency-参与方属性**对话框中，选择**常规**。  

   3. 下**别名**部分中的对话框中，添加具有名称和限定符设置为新的别名**WindowsUser**。 将值设置为用户名称格式为\<域 \ 用户名 > (例如 SOMEDOMAIN\someuser)。  

   4. 选择**证书**，然后单击**浏览**并选择刚导入的公共密钥。 此处指定的证书用于验证入站消息的发件人标识。 单击“确定” 。  

10. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机**。  

11. 右键单击**BizTalkServerApplication** ，然后单击**属性**。 在中**BizTalkServerApplication-主机属性**对话框中，选择**证书**。  

12. 单击**浏览**并选择刚导入的私钥。 此处指定的证书用于入站的消息进行解密。 单击“确定” 。  

13. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，然后选择**主机实例**。  

14. 右键单击**BizTalkServerApplication** ，然后单击**重新启动**。  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-partyresolution-sample"></a>若要运行 PartyResolution 示例  

1.  从以下文件夹中运行 FilePolling.exe:  

     *\<Samples Path>* \Orchestrations\PartyResolution\FilePolling\bin\Debug  

2.  单击**启动轮询**。  

3.  提供采购订单实例文件 PurchaseOrder.xml 的副本粘贴以下文件夹中：  

     *\<Samples Path>* \Orchestrations\PartyResolution\FileDrop\PurchaseOrder  

4.  观察中向您通知的示例进度的消息框形式提供的消息序列：  

    1.  当供应商从买方接收采购订单。  

    2.  当从发货机构 1 或 2 收到发货订单请求。  

    3.  当由发货机构 1 或 2 接收发货通知。  

    4.  当供应商向买方发送采购订单送达回执。  

5.  单击**退出**关闭文件轮询程序。  

> [!NOTE]
>  您可以编辑为"美国"PurchaseOrder.xml 中的国家/地区标记，然后重复步骤 2 和步骤 3。 观察到发货订单现在发送给发货机构 2。  

## <a name="uninstalling-this-sample"></a>卸载本示例  

#### <a name="to-uninstall-the-partyresolution-sample"></a>卸载 PartyResolution 示例  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 对\<*示例路径*> \Orchestrations\ PartyResolution\\。  

2. 运行 Cleanup.bat。  

## <a name="see-also"></a>请参阅  
 [参与方解析管道组件](../core/party-resolution-pipeline-component.md)   
 [如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)