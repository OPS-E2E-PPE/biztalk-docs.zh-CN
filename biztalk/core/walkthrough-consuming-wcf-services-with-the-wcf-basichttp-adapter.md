---
title: 演练：使用 Wcf-basichttp 适配器使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d280198-ba55-4937-91c9-19d6d0ed3194
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd4997c26328721e5ff10218a8ebe07ea52987f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250239"
---
# <a name="walkthrough-consuming-wcf-services-with-the-wcf-basichttp-adapter"></a>演练：使用 Wcf-basichttp 适配器使用 WCF 服务
  
> [!NOTE]
>  有关适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
## <a name="introduction"></a>简介
  
 在本演练中，将使用[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]服务托管在 Internet 信息服务 (IIS) 使用 BizTalk 消息传送和 Wcf-basichttp 发送适配器。 此适配器使用**BasicHttpBinding**绑定来提供与 Web 服务作为 Microsoft 之间的桥梁的早期版本兼容的传输/协议堆栈实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能。 可以将业务流程绑定到使用的发送端口[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器来调用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务并利用其逻辑业务处理中的功能。  
  
 Wcf-basichttp 适配器由发送适配器和接收适配器组成。 在此示例中您将使用此适配器的发送端以便通过 HTTP 协议向 WCF 服务请求[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  对于要求-响应发送端口，将发送到的发送适配器[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务并接收结果响应。  也可反过来[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]接收适配器允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程能够被发布并从外部调用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端应用程序。 请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)有关其他信息。  
  
 完成此演练后，你将了解如何执行以下任务：  
  
- 从[!INCLUDE[btsCoName](../includes/btsconame-md.md)]Visual Studio 中，使用**部署**命令来部署包含的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案并[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务到本地实例中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这将创建 BizTalk 应用程序中已填充的程序集。  
  
- 从 Visual Studio 中，使用**BizTalk WCF 服务使用向导**生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构和类型使用所需[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 可以使用并绑定到逻辑端口，还生成空业务流程。 此业务流程是编译并部署与架构和类型。 但业务流程工作流处理为空此处并不在此示例，因为它只是纯[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息传送的方案。  
  
- 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，配置基于内容的路由通过使用 Wcf-basichttp 发送端口。 将配置**SOAPAction**标头的目标[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务将要接收。  
  
- 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，配置筛选器表达式进行路由任何 SOAP 错误消息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务可以发送到输出文件夹。  
  
- 从 Internet 信息服务 (IIS) 管理器中配置 Web 应用程序宿主[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务以公开其元数据。 启用后， **BizTalk WCF 服务使用向导**可以获得此元数据来生成架构和类型来访问[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此示例中的步骤，请确保您的环境安装以下先决条件：  
  
- 运行本示例的计算机和生成程序集和运行部署过程的计算机需要 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，与 Microsoft BizTalk Server。  
  
- 用于生成程序集和运行部署过程的计算机需要 Microsoft Visual Studio。  
  
- 运行示例的计算机需要[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]管理工具。 这些是用于安装 Microsoft BizTalk Server 安装过程的选项。  
  
- 在计算机上用于执行管理任务，您必须运行的成员的用户帐户作为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组以配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内的应用程序设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 此用户帐户还必须是管理主机实例和其他任务所需的应用程序部署的本地管理员组的成员。  
  
- 需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在示例[ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510)。  
  
- 运行示例并将一个绑定或到某一.msi 文件导入的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保主机不受信任的主机或导入将失败。  
  
- 你必须下载演练代码并将其解压缩到您的计算机。  本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 您可以下载文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心，[http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)。  
  
## <a name="deploy-the-sample-wcf-service"></a>部署示例 WCF 服务  
  
1. 运行自解压**WCFBasicHttpSendAdapter.exe**文件，并将文件提取到**C:\WCFBasicHttpSendAdapter**文件夹。  
  
2. 打开**C:\WCFBasicHttpSendAdapter\WCFBasicHttpSendAdapter.sln** Visual Studio 中。  
  
3. 在解决方案资源管理器，展开**BasicHttpWCFServiceConsuming**项目。 此项目是[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]将由发送端口调用的服务。 它将托管在使用 Internet Information Services (IIS) 的托管的主机环境。 在 IIS 中承载使用基于消息的激活来激活和服务的生命周期管理。 展开**App_Code**，然后打开**OrderProcess.cs**查看。 这[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务接收订单请求消息通过**OrderRequest**方法。 在 OrderProcess.cs 文件包含接口定义和实现[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 它仅返回该订单响应消息通过**OrderResponse**方法。  
  
4. 查看 OrderProcess.svc 文件。 它仅包含一条用于告诉 IIS 以激活客户端应用程序的服务。 <strong>@ServiceHost</strong>属性用来承载该服务是中的扩展点[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]编程模型。 使用工厂模式**ServiceHostFactory**若要创建的实例**ServiceHost**的实例与[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务来处理传入的请求。 基于此实例的实例化**ServiceBehaviorAttribute.ConcurrencyMode**属性，确定服务是否支持一个线程、 多个线程或可重入调用。 实例化也由**ServiceBehavior.InstanceMode**属性，确定如果只有一个实例将提供所有调用方 （单一实例），如果一个实例将创建每个调用 （无状态），或者如果一个实例将为每个会话 （有状态） 创建。  
  
   ```  
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.OrderProcessServiceType" %>  
   ```  
  
5. 在 Visual Studio 中，在解决方案资源管理器中打开**Web.config**查看。 当在 IIS 中承载时[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务配置控制台应用程序中托管时，使用 Web.config 文件而不作为一个 app.config 文件。  
  
   -   请确保**httpGetEnabled**的属性\< **serviceMetaData** \>元素设置为`true`以便**BizTalk WCF 服务使用向导**可以使用该服务的元数据。  
  
   -   请确保**模式下**的属性\<**安全**\>元素设置为**无**。 由于本演练使用**None**安全模式下，Web 应用程序承载该服务必须配置为允许匿名访问。  
  
6. 因为**Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming**程序集必须安装在 GAC 中，它将需要一个强名称密钥文件，以完成部署过程。 右键单击**BasicHttpWcfServiceConsuming**项目，并单击**属性**。 上**属性**页上，单击**签名**，然后选择**程序集签名**。 单击中的向下箭头**选择强名称密钥文件**下拉列表中，单击**\<新建\>**，然后输入`keyfile.snk`中**密钥文件名称**文本框中。  取消选中**保护密钥文件使用密码**，然后单击**确定**。  
  
7. 在解决方案资源管理器中右键单击**BasicHttpWcfServiceConsuming**，然后单击**重新生成**。  
  
8. 使用 Windows 资源管理器中，将复制的内容**C:\WCFBasicHttpSendAdapter\BasicHttpWCFServiceConsuming**到**C:\InetPub\wwwroot**文件夹。  
  
9. 配置 Web 应用程序以承载[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，如下所示：  
  
   1. 单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
   2. 创建此服务将在其中运行应用程序池。 右键单击**应用程序池**，单击**添加应用程序池...**，输入应用程序池的名称，然后单击**确定**。  
  
   3. 展开**应用程序池**，右键单击您刚的应用程序池创建，并选择**高级设置**。 下**过程模型**部分中，输入的帐户有权[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库下**标识**字段。  
  
   4. 展开**站点**，展开**Default Web Site**，右键单击**BasicHttpWCFServiceConsuming**，然后单击**转换为应用程序**若要为此创建 Web 应用程序[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
   5. 在中**转换为应用程序**对话框中，单击**选择**若要选择之前创建的应用程序池，然后单击**确定**。  
  
   6. 在功能视图中，单击**身份验证**图标，并确保**匿名身份验证**选项**启用**。 这支持[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务与**None**安全模式。  
  
10. 测试已发布[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，如下所示：  
  
    1. 在 IIS 管理器中，展开**网站**，然后展开**BasicHttpWCFServiceConsuming**。  
  
    2. 在 IIS 管理器中，在右窗格中，右键单击**OrderProcess.svc**，然后单击**浏览**。 这将打开 Internet Explorer 以显示**OrderProcessServiceType 服务**页，指示你已成功创建一个正在运行[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 此页还包含完整的 WSDL 地址，可以复制和使用服务元数据工具 (svcutil.exe) 来创建代理代码和可用于开发该服务的客户端应用程序的配置文件。  
  
    3. 将完整的 WSDL 地址复制到系统剪贴板中。 不复制 **"svcutil.exe"** 一部分： **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc?wsdl**  
  
## <a name="add-the-schemas-and-types-for-the-wcf-basichttp-adapter-to-the-sample-biztalk-application"></a>将架构和 Wcf-basichttp 适配器的类型添加到 BizTalk 应用程序示例  
  
1. 由于此适配器将调用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务需要架构和类型中有关如何进行此调用使用元数据对该服务的信息。 **BizTalkApp**提供了要使用的项目[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 在 Visual Studio 中，在解决方案资源管理器中右键单击**BizTalkApp**，单击**添加**，然后单击**添加生成的项**。  
  
2. 在中**添加生成的项**对话框中**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。  
  
3. 上**欢迎使用 BizTalk WCF 服务使用向导**页上，单击**下一步**。 此向导将读取元数据，并创建架构和类型。  
  
4. 上**元数据来源**页上，选择**元数据交换 (MEX) 终结点**选项以使用元数据从 URL 复制到剪贴板中的上一个过程，然后单击**下一步**。  
  
5. 上**元数据终结点**页上，将粘贴到在上一步骤中复制的完整 WSDL 地址**元数据地址**下拉列表，再单击**获取**获取该示例的元数据文档[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 获取元数据使**下一步**按钮。 单击 **“下一步”** 继续。  
  
6. 上**导入 WCF 服务元数据摘要**页上，查看你的设置。 此对话框显示命名空间、 XSD 和 WSDL 导入的元数据的摘要。 它还显示业务流程 (.odx)、 绑定 (.xml) 和架构 (.xsd) 文件的写入位置导入过程。 单击**导入**创建 BizTalk 项目和使用该示例使用类型[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
7. 上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。  
  
8. 在 Visual Studio 中，在解决方案资源管理器**BizTalk WCF 服务使用向导**生成以下文件：  
  
   - 业务流程文件**OrderProcessServiceType.odx**。 此业务流程中有任何工作流阶段。 但是，您可以向其添加，并将其绑定到逻辑端口以使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 它包含重要的 BizTalk 类型，例如端口类型和多部分消息类型，此示例中使用。 若要查看此信息，请双击**OrderProcessServiceType.odx**业务流程。 单击**视图**，单击**其他 Windows**，然后单击**业务流程视图**。 展开**类型**，展开**端口类型**，然后展开**IOrderProcess**。 你将看到**提交**方法。 展开该方法，您将看到**OrderRequest**并**OrderResponse**端口类型。 单击每个端口类型并查看其**说明**字段中的属性浏览器和查看不同的 WSDL 输入和输出消息。 单击**多部分消息类型**并查看**OrderRequest**并**OrderResponse**多部分消息类型。 单击他们**说明**字段和视图 WDSL 消息名称对于每个消息类型。  
  
   - 将生成两个架构文件。 第一个架构文件 (**OrderProcessServiceType_biztalk_WCF_basichttpsendadapter_basichttpWCFserviceconsuming.xsd**) 定义的消息类型示例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务使用。 它使用**OrderID**字段中同时**OrderRequest**并**OrderResponse**调用。  
  
   - 第二个架构文件 (**OrderProcessServiceType_schemas_microsoft_com_2003_10_Serialization.xsd**) 由导出[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)的类型、 元素和属性命名空间， http://schemas.microsoft.com/2003/10/Serialization/。  
  
   - 生成两个绑定文件，这将在稍后创建 BizTalk 应用程序：**OrderProcessServiceType.BindingInfo.xml**并**OrderProcessServiceType_Custom.BindingInfo.xml**。 一般情况下通常会使用非自定义绑定文件。 但在某些极少数的情况下，必须使用自定义绑定文件的自定义绑定元素。 自定义绑定元素创建的应用程序的发送端口。 双击**OrderProcessServiceType.BindingInfo.xml**文件并搜索**发送端口**定义行，并查看文件导入此绑定时，将创建的发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
     ```  
     <SendPort Name="WCFSendPort_OrderProcessServiceType_ServiceEndpoint" …  >  
     ```  
  
   - 这些文件将用于发送端口使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器使用示例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务元数据中所述。  
  
## <a name="deploy-the-sample-biztalk-solution-biztalkapp"></a>部署示例 BizTalk 解决方案 BizTalkApp  
  
1. 部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，如下所示：  
  
   1. 在 Visual Studio 中，在解决方案资源管理器中右键单击**BizTalkApp**，然后单击**属性**。  
  
   2. 在中**项目设计器**窗口中，单击**部署**选项卡，然后将更改**Server**属性，如果使用不同的数据库的服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。 请确保应用程序名称**WCFBasicHttpSendAdapter**。  
  
   3. 在 Visual Studio 中，在解决方案资源管理器中右键单击**BizTalkApp**，然后单击**重新生成**。  
  
   4. 在 Visual Studio 中，在解决方案资源管理器中右键单击**BizTalkApp**，然后单击**部署**。  这将 Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp 程序集部署到 GAC，并为项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]名为应用程序**WCFBasicHttpSendAdapter**。  
  
2. 按如下所示的 BizTalk 应用程序中配置 Wcf-basichttp 发送端口：  
  
   1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
   2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，右键单击**WCFBasicHttpSendAdapter**，指向**导入**，然后单击**绑定**。  
  
   3. 在中**导入绑定**对话框中，转到**C:\WCFBasicHttpSendAdapter\BizTalkApp**文件夹，选择**OrderProcessServiceType.BindingInfo.xml**，然后单击**打开**。 这是由创建的绑定文件之一**BizTalk WCF 服务使用向导**以前。 这将创建**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**发送端口。  
  
   4. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，然后单击**发送端口**。  
  
   5. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在右窗格中，双击**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**，来创建通过导入绑定文件OrderProcessServiceType.BindingInfo.xml。 这将显示**发送端口属性**对话框。  
  
   6. 在中**发送端口属性**对话框中，单击**配置**。  
  
   7. 上**常规**选项卡上查看**地址 （uri)** 字段**<http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc>**。 这是地址[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]Wcf-basichttp 适配器将调用的 IIS 中承载的服务。  
  
   8. 查看的内容**SOAP 操作标头/操作**文本框中：  
  
      ```  
      <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
        <Operation Name="Submit" Action="http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming/IOrderProcess/Submit" />  
      </BtsActionMapping>  
      ```  
  
       此字段指示传出 SOAP HTTP 请求消息的意图。 此处它是从 Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming 命名空间调用 IOrderProcess 接口上的提交操作。  
  
      > [!NOTE]
      >  绑定文件**BizTalk WCF 服务使用向导**生成操作映射格式用于**StaticAction**属性。 在使用基于内容的路由用于 WCF 发送适配器将消息发送到 WCF 服务时，需要设置**BTS。操作**在管道组件中针对操作映射格式用于基于内容的路由此字段的属性。 或者，您可以使用单一操作格式用于基于内容的路由。 在本演练中，您将使用单一操作格式。 有关单一操作格式和操作映射格式的详细信息，请参阅**Wcf-basichttp 传输属性对话框，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
   9. 单击**确定**两次以返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3. 创建一个单向静态接收端口和 FILE 接收位置。 接收端口是一个或多个接收位置的逻辑容器。 这是一个示例将存放[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]条消息，将文件适配器拾取，然后发送到[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
   2. 在中**接收端口属性**对话框中**名称**文本框中，键入`WCFBasicSendAdapter.ReceivePurchaseOrder`，然后单击**确定**。  
  
   3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFBasicHttpSendAdapter.ReceivePurchaseOrder**，依次指向**新建**，然后单击**接收位置**.  
  
   4. 在中**接收位置属性**对话框中**名称**文本框中，键入`WCFBasicSendAdapter.ReceivePurchaseOrder.FILE`。  
  
   5. 在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**文件**从下拉列表中，然后单击**配置**。  
  
   6. 在**FILE 传输属性**对话框中，在**常规**选项卡上，在**接收文件夹**文本框中，键入`C:\WCFBasicHttpSendAdapter\OrderRequestIn`，然后单击**确定**.  
  
   7. 在中**接收位置属性**对话框中，单击**确定**。  
  
4. 创建一个筛选器，将消息路由到 Wcf-basichttp 发送端口从该文件接收在上一步中创建的位置。 与端口关联的筛选器的作用类似的 SQL"where"子句中，如果其计算结果为 true，该消息将发送至该端口。  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，单击**发送端口**，然后双击**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**。  
  
   2. 在中**发送端口属性**对话框中，在**筛选器**选项卡上，选择**BTS。ReceivePortName**中**属性**字段中，键入`WCFBasicSendAdapter.ReceivePurchaseOrder`中**值**字段，，然后单击**确定**。 此筛选器表达式将路由传入消息从 WCFBasicSendAdapter.ReceivePurchaseOrder 接收到此 Wcf-basichttp 发送端口的端口。  
  
5. 创建两个文件发送端口的示例应用程序。 第一个发送端口发送消息到该文件从端口的输出响应[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 第二个发送端口用于处理错误消息从发送[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]发往客户端的服务。  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
   2. 在中**发送端口属性**对话框中**名称**文本框中，键入`WCFBasicSendAdapter.SendPurchaseOrder.FILE`。  
  
   3. 在中**发送端口属性**对话框中**传输**类型旁，选择部分**文件**从下拉列表中，然后单击**配置**.  
  
   4. 在中**FILE 传输属性**对话框中，在**常规**选项卡上，在**目标文件夹**文本框中，键入`C:\WCFBasicHttpSendAdapter\OrderResponseOut`，然后单击**确定**.  
  
   5. 在中**发送端口属性**对话框中，在**筛选器**选项卡上，选择**BTS。MessageType**中**属性**字段中，键入`http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse`中**值**字段来指定响应消息类型的示例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，并然后单击**确定**。 此筛选器表达式将响应消息中的示例路由[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务对此文件发送端口。 发送端口订阅 OrderResponse 类型的消息通过筛选器属性中指定该类型。 这是从响应消息的消息类型[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
   6. 在中**发送端口属性**对话框中，单击**确定**。  
  
   7. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
   8. 在中**发送端口属性**对话框中**名称**文本框中，键入`WCFAdapterErrorSend.FILE`。  
  
   9. 在**发送端口属性**对话框中**传输**部分旁边**类型**，选择**文件**从下拉列表中，然后单击**配置**。  
  
   10. 在中**FILE 传输属性**对话框中，在**常规**选项卡上，在**目标文件夹**文本框中，键入`C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut\`，然后单击**确定**.  
  
   11. 在中**发送端口属性**对话框中，在**筛选器**选项卡上，选择**WCF。IsFault**中**属性**字段中，键入`True`中**值**字段，，然后单击**确定**。 可以通过检查应用程序中检测异常或错误**WCF。IsFault**发送回调用方的消息的属性。 此属性将设置为 **，则返回 True**如果发送的消息的 SOAP 错误消息。 此筛选器表达式将从该示例的错误消息路由[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务对此文件发送端口。  
  
6. 指定的主机名和示例应用程序的绑定，如下所示：  
  
    在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，展开**业务流程**，右键单击**Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp.OrderProcessServiceTypeClient**业务流程中，单击**属性**，单击**绑定**，设置**主机**到**BizTalkServerApplication**，然后单击**确定**保存配置。  
  
## <a name="test-the-sample-solution-with-the-wcf-basichttp-send-adapter"></a>测试示例解决方案使用 Wcf-basichttp 发送适配器  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFBasicHttpSendAdapter**，然后单击**启动**。  
  
2. 在中**启动**对话框中，单击**启动**。  
  
3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**或另一个相应的主机实例，然后依次**重新启动**。  
  
4. 打开命令提示符，键入**iisreset**回收 IIS 及其依存的服务，然后按 ENTER。  
  
5. 在命令提示符下，复制**C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Sample.xml**到**C:\WCFBasicHttpSendAdapter\OrderRequestIn**文件夹。 此消息路由到双向**WcfSendPort_OrderProcessServiceType_ServiceEndpoint**静态要求响应发送端口。  此双向发送方发送端口调用**提交**方法[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在 IIS 中承载的服务。 结果返回到的响应端口**WcfSendPort_OrderProcessServiceType_ServiceEndpoint**发送端口。  **WCFBasicSendAdapter.SendPurchaseOrder.FILE**发送端口订阅该消息的类型时，将触发**<http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse>**。它将获取已成功处理的消息并将其写出到**C:\WCFBasicHttpSendAdapter\OrderResponseOut**文件夹。  
  
6. 检查**C:\WCFBasicHttpSendAdapter\OrderResponseOut**文件夹中的响应消息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
7. 在命令提示符**C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Invalid.xml**到**C:\WCFBasicHttpSendAdapter\OrderRequestIn**文件夹。 此消息包含无效的命名空间，以便[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务将返回错误消息。  
  
8. 检查**C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut**包含从错误消息的 XML 文件的文件夹[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 看看\< **faultstring** \>字段显示错误消息是一个无效的消息正文，其中的原因。  
  
## <a name="see-also"></a>请参阅  
 [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)   
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)