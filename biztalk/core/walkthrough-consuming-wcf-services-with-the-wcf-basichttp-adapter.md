---
title: 演练： 使用 WCF 服务与 WCF BasicHttp 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d280198-ba55-4937-91c9-19d6d0ed3194
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c85d550e7a1429e18035629517017c90b44c9e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="walkthrough-consuming-wcf-services-with-the-wcf-basichttp-adapter"></a>演练： 使用 WCF 服务与 WCF BasicHttp 适配器
  
> [!NOTE]
>  有关适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
## <a name="introduction"></a>简介
  
 在本演练中，将通过 BizTalk 消息传送和 WCF-BasicHttp 发送适配器使用 Internet 信息服务 (IIS) 中的 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 服务。 此适配器使用**BasicHttpBinding**绑定来提供与要用作 Microsoft 之间的桥梁的 Web 服务的早期版本兼容的传输/协议堆栈实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能。 业务流程可绑定至使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器来调用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的发送端口，并利用其逻辑业务处理中的功能。  
  
 WCF-BasicHttp 适配器由一个发送适配器和一个接收适配器组成。 在本示例中，将仅使用此适配器的发送功能通过 HTTP 协议进行对 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的 WCF 服务请求。  对于要求-响应发送端口，发送适配器将发送至 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务并接收结果响应。  相反，[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 接收适配器允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程由 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端应用程序从外部发布和调用。 请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)有关其他信息。  
  
 在完成本演练后，你将了解如何执行以下任务：  
  
-   在[!INCLUDE[btsCoName](../includes/btsconame-md.md)]Visual Studio 中，使用**部署**命令以部署包含的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务的本地实例来[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这将创建一个用这些程序集填充的 BizTalk 应用程序。  
  
-   在 Visual Studio 中使用**BizTalk WCF 服务使用向导**生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构和类型使用所需[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 将生成空业务流程，您可以使用并将其绑定至逻辑端口。 此业务流程与架构和类型一同进行编译和部署。 但是，业务流程工作流处理在此处为空，并不在此示例中使用，因为此示例仅是一个纯 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息传送方案。  
  
-   在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，通过使用 WCF-BasicHttp 发送端口来配置基于内容的路由。 你将配置**SOAPAction**标头的目标[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务期望接收。  
  
-   在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，将筛选器表达式配置为将 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务可以发送的任何 SOAP 错误消息路由到输出文件夹。  
  
-   在 Internet 信息服务 (IIS) 管理器中，将承载 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的 Web 应用程序配置为公开其元数据。 启用后， **BizTalk WCF 服务使用向导**可以获取此元数据来生成类型和架构访问[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本示例中的步骤，请确保你的环境中安装了以下必备软件：  
  
-   生成程序集并运行在部署过程的计算机和运行此示例中，计算机需要 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，和 Microsoft BizTalk Server。  
  
-   用于构建程序集和运行部署过程的计算机需要安装 Microsoft Visual Studio。  
  
-   运行示例的计算机需要 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理工具。 这些是用于安装 Microsoft BizTalk 服务器安装过程的选项。  
  
-   在用于执行管理任务的计算机上，你必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的用户帐户运行，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序设置。 此用户帐户还必须是本地管理员组的成员，才能部署应用程序，管理主机实例以及其他可能需要的任务。  
  
-   需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]示例在[ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510)。  
  
-   在运行示例并将绑定或 .msi 文件导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上，确保主机不是受信任主机，否则导入将失败。  
  
-   你必须下载演练代码并将其解压缩到你的计算机。  本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 你可以下载该文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心，[http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)。  
  
## <a name="deploy-the-sample-wcf-service"></a>部署示例 WCF 服务  
  
1.  运行自解压 **WCFBasicHttpSendAdapter.exe** 文件并将文件提取到 **C:\WCFBasicHttpSendAdapter** 文件夹。  
  
2.  打开**C:\WCFBasicHttpSendAdapter\WCFBasicHttpSendAdapter.sln** Visual Studio 中。  
  
3.  在解决方案资源管理器，展开 **BasicHttpWCFServiceConsuming** 项目。 此项目为将由发送端口调用的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 它将承载于使用 Internet 信息服务 (IIS) 的托管主机环境中。 在 IIS 中承载将使用基于消息的激活来管理服务的激活和生存期。 展开 **App_Code**, ，然后打开 **OrderProcess.cs** 查看。 这[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务接收订单请求消息通过**OrderRequest**方法。 OrderProcess.cs 文件包含 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的接口定义和实现。 只需返回响应消息通过顺序 **OrderResponse** 方法。  
  
4.  查看 OrderProcess.svc 文件。 它仅包含一行，该行用来告诉 IIS 为客户端应用程序激活服务。 **@ServiceHost**属性用于承载服务是中的扩展点[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]编程模型。 使用工厂模式**ServiceHostFactory**若要创建的实例**ServiceHost**与实例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务来处理传入请求。 基于此实例的实例化 **ServiceBehaviorAttribute.ConcurrencyMode** 属性，确定服务是否支持一个线程、 多个线程或可重入调用。 实例化也由 **ServiceBehavior.InstanceMode** 属性，确定如果只有一个实例将提供所有调用方 (转变成 singleton)，如果一个实例将创建每个调用 （无状态），或将为每个会话 （有状态） 创建一个实例。  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming.OrderProcessServiceType" %>  
    ```  
  
5.  在 Visual Studio 中，在解决方案资源管理器，打开**Web.config**查看。 承载于 IIS 中时，[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务使用 Web.config 文件进行配置，而不是像承载于控制台应用程序中时使用 app.config 文件。  
  
    -   请确保**httpGetEnabled**属性\< **serviceMetaData** \>元素设置为`true`以便**BizTalk WCF 服务使用向导**可以使用服务的元数据。  
  
    -   请确保**模式**属性\<**安全**\>元素设置为**无**。 由于本演练使用 **无** 安全模式下，Web 应用程序承载此服务必须配置为允许匿名访问。  
  
6.  因为 **Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming** 程序集必须安装到 GAC 中，它将需要一个强名称密钥文件，以完成部署过程。 右键单击 **BasicHttpWcfServiceConsuming** 项目，，然后单击 **属性**。 上 **属性** 页上，单击 **签名**, ，然后选择 **对程序集签名**。 单击中的向下箭头**选择强名称密钥文件**下拉列表中，单击**\<新建\>**，并输入`keyfile.snk`中**密钥文件名称**文本框。  取消选中 **保护我使用密码的密钥文件**, ，然后单击 **确定**。  
  
7.  在解决方案资源管理器，右键单击 **BasicHttpWcfServiceConsuming**, ，然后单击 **重新生成**。  
  
8.  使用 Windows 资源管理器，复制的内容 **C:\WCFBasicHttpSendAdapter\BasicHttpWCFServiceConsuming** 到 **C:\InetPub\wwwroot** 文件夹。  
  
9. 配置 Web 应用程序以承载[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，如下所示：  
  
    1.  单击 **启动**, ，指向 **管理员工具**, ，然后单击 **Internet Information Services (IIS) Manager**。  
  
    2.  创建此服务将运行在其中的应用程序池。 右键单击 **应用程序池**, ，单击 **添加应用程序池 …**, ，输入应用程序池的名称，然后单击 **确定**。  
  
    3.  展开 **应用程序池**, ，右键单击你刚的应用程序池创建，，然后选择 **高级设置**。 下**进程模型**部分中，输入可以访问的帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库下**标识**字段。  
  
    4.  展开**站点**，展开**Default Web Site**，右键单击**BasicHttpWCFServiceConsuming**，然后单击**转换为应用程序**此创建 Web 应用程序[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
    5.  在 **转换为应用程序** 对话框中，单击 **选择** 若要选择更早版本，创建的应用程序池，然后单击 **确定**。  
  
    6.  在功能视图中，单击 **身份验证** 图标，并确保 **匿名身份验证** 选项 **启用**。 此设置支持[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]使用服务**无**安全模式。  
  
10. 测试已发布的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务，如下所示：  
  
    1.  在 IIS 管理器中，展开 **网站**, ，然后展开 **BasicHttpWCFServiceConsuming**。  
  
    2.  在 IIS 管理器中，在右窗格中，右键单击 **OrderProcess.svc**, ，然后单击 **浏览**。 这将打开 Internet Explorer 显示**OrderProcessServiceType 服务**指示已成功创建正在运行的页[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 此页还包含一个完整的 WSDL 地址，您可以通过复制该地址并将其用于服务元数据工具 (svcutil.exe) 来创建可用于该服务客户端应用程序开发的代理代码和配置文件。  
  
    3.  将完整的 WSDL 地址复制到系统剪贴板中。 不复制 **"svcutil.exe"** 一部分︰ **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc?wsdl**  
  
## <a name="add-the-schemas-and-types-for-the-wcf-basichttp-adapter-to-the-sample-biztalk-application"></a>将架构和类型为 WCF BasicHttp 适配器添加到示例 BizTalk 应用程序  
  
1.  由于此适配器将调用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务，因此它需要架构和类型中有关如何使用元数据对该服务进行此调用的信息。 **BizTalkApp**提供的项目使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 在 Visual Studio 中，在解决方案资源管理器，右键单击**BizTalkApp**，单击**添加**，然后单击**添加生成的项**。  
  
2.  在 **添加生成的项** 对话框中，在 **模板** 部分中，选择 **使用 WCF 服务**, ，然后单击 **添加**。  
  
3.  上 **欢迎 BizTalk WCF 服务使用向导** 页上，单击 **下一步**。 此向导将读取元数据并创建架构和类型。  
  
4.  上 **元数据源** 页上，选择 **元数据交换 (MEX) 终结点** 选项以使用元数据从该 URL 复制到剪贴板中前面的过程中，然后单击 **下一步**。  
  
5.  上**元数据终结点**页上，粘贴你在上述步骤中复制的完整 WSDL 地址**元数据地址**下拉列表，然后单击**获取**来获取此示例的元数据文档[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 获取元数据使 **下一步** 按钮。 单击 **“下一步”** 继续。  
  
6.  上 **导入 WCF 服务元数据摘要** 页上，查看你的设置。 此对话框会显示要导入的元数据的命名空间、XSD 及 WSDL 摘要。 它还显示业务流程 (.odx)、 绑定 (.xml) 和架构 (.xsd) 文件将在其中写入在导入过程。 单击**导入**创建 BizTalk 项目和要使用此示例使用类型[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
7.  上 **完成 BizTalk WCF 服务使用向导** 页上，单击 **完成**。  
  
8.  在 Visual Studio 中，在解决方案资源管理器， **BizTalk WCF 服务使用向导**生成以下文件：  
  
    -   业务流程文件 **OrderProcessServiceType.odx**。 在此业务流程中没有工作流阶段。 但是，您可以向其中添加并将其绑定至逻辑端口以使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 它包含重要的 BizTalk 类型（例如端口类型和多部分消息类型），在此示例中将会使用这些类型。 若要查看此信息，请双击 **OrderProcessServiceType.odx** 业务流程。 单击 **视图**, ，单击 **其他窗口**, ，然后单击 **业务流程视图**。 展开 **类型**, ，展开 **端口类型**, ，然后展开 **IOrderProcess**。 你将看到 **提交** 方法。 展开该方法，你将看到 **OrderRequest** 和 **OrderResponse** 端口类型。 单击每个端口类型并查看其 **说明** 属性浏览器并查看不同的 WSDL 中的字段输入和输出消息。 单击 **多部分消息类型** 并查看 **OrderRequest** 和 **OrderResponse** 多个部分消息类型。 单击其 **说明** 字段和视图 WDSL 消息每种消息类型的名称。  
  
    -   将生成两个架构文件。 第一个架构文件 (**OrderProcessServiceType_biztalk_WCF_basichttpsendadapter_basichttpWCFserviceconsuming.xsd**) 定义消息类型示例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务使用。 它使用 **OrderID** 字段中都 **OrderRequest** 和 **OrderResponse** 调用。  
  
    -   第二个架构文件 (**OrderProcessServiceType_schemas_microsoft_com_2003_10_Serialization.xsd**) 由导出[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)有关类型、 元素和属性命名空间， http://schemas.microsoft.com/2003/10/Serialization/。  
  
    -   将生成两个绑定文件，这将在稍后用于创建 BizTalk 应用程序︰ **OrderProcessServiceType.BindingInfo.xml** 和 **OrderProcessServiceType_Custom.BindingInfo.xml**。 一般情况下，您通常使用非自定义绑定文件。 但在您拥有自定义绑定元素的某些少数情形下，将使用自定义绑定文件。 自定义绑定元素将为应用程序创建发送端口。 双击**OrderProcessServiceType.BindingInfo.xml**文件并搜索**发送端口**定义行，并查看到文件导入此绑定时将创建发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
        ```  
        <SendPort Name="WCFSendPort_OrderProcessServiceType_ServiceEndpoint" …  >  
        ```  
  
    -   这些文件将用于使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器的发送端口，以使用元数据中描述的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务示例。  
  
## <a name="deploy-the-sample-biztalk-solution-biztalkapp"></a>部署示例 BizTalk 解决方案，BizTalkApp  
  
1.  部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，如下所示：  
  
    1.  在 Visual Studio 中，在解决方案资源管理器，右键单击**BizTalkApp**，然后单击**属性**。  
  
    2.  在**项目设计器**窗口中，单击**部署**选项卡上，然后更改**服务器**属性，如果你使用不同的数据库的服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。 请确保应用程序名称 **WCFBasicHttpSendAdapter**。  
  
    3.  在 Visual Studio 中，在解决方案资源管理器，右键单击**BizTalkApp**，然后单击**重新生成**。  
  
    4.  在 Visual Studio 中，在解决方案资源管理器，右键单击**BizTalkApp**，然后单击**部署**。  这将 Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp 程序集部署到 GAC 中和项目到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]名为应用程序**WCFBasicHttpSendAdapter**。  
  
2.  在 BizTalk 应用程序中配置 WCF-BasicHttp 发送端口，如下所示：  
  
    1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
    2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，右键单击**WCFBasicHttpSendAdapter**，指向**导入**，然后单击**绑定**。  
  
    3.  在 **导入绑定** 对话框中，转到 **C:\WCFBasicHttpSendAdapter\BizTalkApp** 文件夹，选择 **OrderProcessServiceType.BindingInfo.xml**, ，然后单击 **打开**。 这是一个创建的绑定文件 **BizTalk WCF 服务使用向导** 以前。 这将创建 **WCFSendPort_OrderProcessServiceType_ServiceEndpoint** 发送端口。  
  
    4.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，然后单击**发送端口**。  
  
    5.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在右窗格中，双击**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**，这由导入绑定文件OrderProcessServiceType.BindingInfo.xml。 这将显示 **发送端口属性** 对话框。  
  
    6.  在 **发送端口属性** 对话框中，单击 **配置**。  
  
    7.  上 **常规** 选项卡上查看 **Address(URI)** 字段 **http://localhost/BasicHttpWcfServiceConsuming/OrderProcess.svc**。 此为 WCF-BasicHttp 适配器将调用的 IIS 中承载的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的地址。  
  
    8.  查看中的内容 **SOAP 操作标头/操作** 文本框︰  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Submit" Action="http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming/IOrderProcess/Submit" />  
        </BtsActionMapping>  
        ```  
  
         此字段指示传出 SOAP HTTP 请求消息的目的。 此处用来在 IOrderProcess 接口上从 Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWcfServiceConsuming 命名空间来调用“提交”操作。  
  
        > [!NOTE]
        >  绑定文件 **BizTalk WCF 服务使用向导** 产生映射格式的操作、 使用 **StaticAction** 属性。 在使用基于内容的路由为 WCF 发送适配器，以将消息发送到 WCF 服务时，你需要设置 **BTS。操作** 操作映射格式与字段要用于基于内容的路由的管道组件中的属性。 或者，您也可以选择将单一操作格式用于基于内容的路由。 在本演练中，您将使用单一操作格式。 有关单个操作格式和操作映射格式的详细信息，请参阅**WCF BasicHttp 传输属性对话框中，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
    9. 单击**确定**两次以返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3.  创建单向静态接收端口和 FILE 接收位置。 接收端口是一个或多个接收位置的逻辑容器。 此处您将丢出一个示例 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息，该消息将由文件适配器拾取，然后发送至 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
    2.  在 **接收端口属性** 对话框中，在 **名称** 文本框中，键入 `WCFBasicSendAdapter.ReceivePurchaseOrder`, ，然后单击 **确定**。  
  
    3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFBasicHttpSendAdapter.ReceivePurchaseOrder**，指向**新建**，然后单击**接收位置**.  
  
    4.  在 **接收位置属性** 对话框中，在 **名称** 文本框中，键入 `WCFBasicSendAdapter.ReceivePurchaseOrder.FILE`。  
  
    5.  在 **接收位置属性** 对话框中，在 **传输** 旁边部分 **类型**, ，选择 **文件** 从下拉列表，然后单击 **配置**。  
  
    6.  在 **文件传输属性** 对话框中，在 **常规**  选项卡上，在 **接收文件夹** 文本框中，键入 `C:\WCFBasicHttpSendAdapter\OrderRequestIn`, ，然后单击 **确定**。  
  
    7.  在 **接收位置属性** 对话框中，单击 **确定**。  
  
4.  创建一个筛选器，将消息从上一步中创建的 FILE 接收位置路由至 WCF-BasicHttp 发送端口。 与端口关联的筛选器作用与 SQL“where”子句相似，如果其值为真，则将消息发送至该端口。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，单击**发送端口**，然后双击**WCFSendPort_OrderProcessServiceType_ServiceEndpoint**。  
  
    2.  在 **发送端口属性** 对话框中，在 **筛选器** 选项卡上，选择 **BTS。ReceivePortName** 中 **属性** 字段中，键入 `WCFBasicSendAdapter.ReceivePurchaseOrder` 中 **值** 字段，然后再单击 **确定**。 此筛选器表达式将从 WCFBasicSendAdapter.ReceivePurchaseOrder 接收端口将传入消息路由至此 WCF-BasicHttp 发送端口。  
  
5.  为示例应用程序创建两个 FILE 发送端口。 第一个发送端口将输出响应消息从 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务发送至 FILE 端口。 第二个发送端口用来处理从 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务发送至客户端的错误消息。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
    2.  在 **发送端口属性** 对话框中，在 **名称** 文本框中，键入 `WCFBasicSendAdapter.SendPurchaseOrder.FILE`。  
  
    3.  在 **发送端口属性** 对话框中，在 **传输** 类型，选择旁边的部分 **文件** 从下拉列表，然后单击 **配置**。  
  
    4.  在 **文件传输属性** 对话框中，在 **常规** 选项卡上，在 **目标文件夹** 文本框中，键入 `C:\WCFBasicHttpSendAdapter\OrderResponseOut`, ，然后单击 **确定**。  
  
    5.  在**发送端口属性**对话框中，在**筛选器**选项卡上，选择**BTS。MessageType**中**属性**字段中，键入`http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse`中**值**字段来指定从示例的响应消息类型[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，并然后单击**确定**。 此筛选器表达式将响应消息从示例 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务路由至此 FILE 发送端口。 此发送端口通过在筛选器属性中指定类型来订阅 OrderResponse 类型的消息。 这是来自 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的响应消息的消息类型。  
  
    6.  在 **发送端口属性** 对话框中，单击 **确定**。  
  
    7.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
    8.  在 **发送端口属性** 对话框中，在 **名称** 文本框中，键入 `WCFAdapterErrorSend.FILE`。  
  
    9. 在 **发送端口属性** 对话框中，在 **传输** 旁边部分 **类型**, ，选择 **文件** 从下拉列表，然后单击 **配置**。  
  
    10. 在 **文件传输属性** 对话框中，在 **常规** 选项卡上，在 **目标文件夹** 文本框中，键入 `C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut\`, ，然后单击 **确定**。  
  
    11. 在 **发送端口属性** 对话框中，在 **筛选器** 选项卡上，选择 **WCF。IsFault** 中 **属性** 字段中，键入 `True` 中 **值** 字段，然后再单击 **确定**。 可以通过检查应用程序内检测异常或错误 **WCF。IsFault** 发送回调用方的消息的属性。 此属性将设置为 **True** 如果发送的消息的 SOAP 错误消息。 此筛选器表达式将错误消息从示例 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务路由至此 FILE 发送端口。  
  
6.  指定的主机名和示例应用程序的绑定，如下所示︰  
  
     在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFBasicHttpSendAdapter**，展开**业务流程**，右键单击**Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BizTalkApp.OrderProcessServiceTypeClient**业务流程，单击**属性**，单击**绑定**，设置**主机**到**BizTalkServerApplication**，然后单击**确定**保存配置。  
  
## <a name="test-the-sample-solution-with-the-wcf-basichttp-send-adapter"></a>测试的示例解决方案与 WCF BasicHttp 发送适配器  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFBasicHttpSendAdapter**，然后单击**启动**。  
  
2.  在 **启动** 对话框中，单击 **启动**。  
  
3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**或另一个适当的主机实例，然后单击**重新启动**。  
  
4.  打开命令提示符，键入 **iisreset** 回收 IIS 和其依赖的服务，然后按 enter 键。  
  
5.  在命令提示符下，复制 **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Sample.xml** 到 **C:\WCFBasicHttpSendAdapter\OrderRequestIn** 文件夹。 此消息路由到双向 **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** 静态请求-响应发送端口。  这是双向的发送端发送端口调用**提交**方法[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在 IIS 中承载的服务。 默认情况下，返回到的响应端口 **WcfSendPort_OrderProcessServiceType_ServiceEndpoint** 发送端口。  **WCFBasicSendAdapter.SendPurchaseOrder.FILE**发送端口都具有消息的类型时，将触发订阅**http://Microsoft.Samples.BizTalk.WCF.BasicHttpSendAdapter.BasicHttpWCFServiceConsuming#OrderResponse**。它将获取已成功处理的消息并将其写出到**C:\WCFBasicHttpSendAdapter\OrderResponseOut**文件夹。  
  
6.  检查**C:\WCFBasicHttpSendAdapter\OrderResponseOut**文件夹中的响应消息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
7.  在命令提示符下， **C:\WCFBasicHttpSendAdapter\TestData\WCFBasicSendAdapter.OrderRequest.Invalid.xml** 到 **C:\WCFBasicHttpSendAdapter\OrderRequestIn** 文件夹。 此消息包含无效的命名空间，以便[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务返回的错误消息。  
  
8.  检查**C:\WCFBasicHttpSendAdapter\WCFAdapterErrorOut**包含来自的错误消息的 XML 文件的文件夹[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 查看\< **faultstring** \>字段显示为一个无效的消息正文，其中的错误消息的原因。  
  
## <a name="see-also"></a>另请参阅  
 [演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)   
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)