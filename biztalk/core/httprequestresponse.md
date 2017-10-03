---
title: "HTTPRequestResponse |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 81c66f61-d86c-49cf-8d24-21c67c68bc5a
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad45e80cac2a398507b4288c9ac6f35c887e71b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="httprequestresponse"></a>HTTPRequestResponse
HTTPRequestResponse 示例演示如何使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet 服务器应用程序编程接口 (ISAPI) 筛选器允许 ASP.NET 应用程序与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程通信。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 在此示例中，ASP.NET 应用程序将请求提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ISAPI 筛选器。 然后业务流程使用此消息，并使用异步响应将其返回给 ASP.NET 应用程序。 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI 筛选器，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程和 ASP.NET 应用程序之间集成。  
  
 在本示例中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 ASP.NET 应用程序使用以下一系列步骤来交换采购订单 (PO) 和 PO 回执消息：  
  
1.  ASP.NET 应用程序使用 HTTP 请求向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交 XML PO 消息。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收此 XML PO 消息，并构造 XML PO 回执消息，然后以 HTTP 响应的形式向 ASP.NET 应用程序发回此消息。  
  
 ASP.NET 应用程序接收此 XML PO 回执响应，并使用从此响应中提取的状态信息刷新 Web 窗体。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\AdaptersUsage\HTTPRequestResponse\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|HTTPRequestResponse.btproj、HTTPRequestResponse.sln|提供接收 HTTP 请求、处理 PO 消息并发出响应的 BizTalk 项目的项目和源文件。|  
|HTTPRequestResponseBinding.xml|提供自动设置，如端口绑定。|  
|POAck.xsd、POSchema.xsd|分别提供 PO 回执和 PO .xml 文件的架构。|  
|POReceiveOrchestration.odx|提供用于接收 PO、处理 PO 并发出 PO 回执的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。|  
|Setup.bat|生成并初始化本示例。|  
|\RequestResponse 文件夹的内容：<br /><br /> AssemblyInfo.cs、default.aspx、default.aspx.cs、Global.asax、Global.asax.cs、RequestResponse.csproj、RequestResponse.csproj.webinfo、RequestResponse.sln 和 Web.config|包含用作本示例的驱动程序的 ASP.NET 应用程序的组成文件，其中包括项目和解决方案文件、ASPX 文件和 Microsoft Visual C# .NET 源文件等。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程可以生成并初始化 HTTPRequestResponse 示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \AdaptersUsage\HTTPRequestResponse  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   编译并配置用于驱动本示例的 ASP.NET 应用程序。  
  
        > [!NOTE]
        >  在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本**.Net Framework v4.0**。  
  
    -   编译并部署本示例中使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。  
  
    -   编译和部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。  
  
    -   创建并绑定必要的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 端口。  
  
    -   启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。  
  
        > [!IMPORTANT]
        >  必须更改实现 Web 应用程序 (Default.aspx.cs) 的示例代码，使其反映您的环境：  
        >   
        >  http://\<*服务器名称*>/\<*虚拟 dir*> /BTSHTTPReceive.dll 其中`<servername>`是您要发布到，Web 服务器和的名称`<`*虚拟 dir* `>`是此文件所在的虚拟目录。  
  
        > [!NOTE]
        >  在尝试运行本示例之前，应确认在生成和初始化过程中 BizTalk 未报告任何错误。  
  
        > [!NOTE]
        >  如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。 使用该密钥对可以对生成的程序集签名。 同时，在尝试生成该项目之前，您还必须从 RequestResponse.csproj 文件中手动删除对 default.aspx.resx 和 Global.asax.resx 的引用。  
  
        > [!NOTE]
        >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
        > [!NOTE]
        >  必须配置并启用 IIS 以使用 HTTP 接收适配器。 有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
3.  setup.bat 文件将本示例的虚拟目录配置为在与默认网站相关联的 IIS 应用程序池中运行。  若要配置此示例中的用户的上下文中运行的虚拟目录**BizTalk 独立主机用户**和**IIS_IURS**用户组，你应配置要运行在新的虚拟目录IIS 应用程序池。 通过完成以下步骤，可将虚拟目录配置为在新的 IIS 应用程序池中运行：  
  
    > [!NOTE]
    >  如果已经为另一个 SDK 示例创建了新的应用程序池，可继续进行下面的最后一步。  
  
    1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
    2.  在**Internet Information Services (IIS) Manager**，导航到**应用程序池**文件夹。  
  
    3.  右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**  
  
    4.  输入的名称**应用程序池 ID:** BizTalkSDKSamples，如验证**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。  
  
    5.  右键单击新的应用程序池，然后单击**属性**。  
  
    6.  单击**标识**选项卡的属性对话框框中，并将更改此应用程序池运行是的成员的用户的标识**BizTalk 独立主机用户**用户组。  此用户还应属于本地**IIS_IURS**用户组。  
  
    7.  将本 SDK 示例的虚拟目录配置为在新应用程序池下运行。 **应用程序池**设置位于**虚拟目录**虚拟目录属性对话框中的选项卡。 为本示例创建的虚拟目录为 HttpRequestResponseSample。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 HTTPRequestResponse 示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在 Internet Explorer 中，导航至 http://localhost/RequestResponse/。  
  
2.  填写 Web 窗体中的必需字段，然后单击**下订单**提交你的订单。  
  
3.  查看 Web 窗体在收到响应后进行刷新时的订单状态。  
  
## <a name="comments"></a>注释  
 **BTSHTTPReceiveISAPI**扩展此示例中使用已配置为在单台计算机默认的安装。 若要扩展此示例以供其他配置，请参阅[HTTP 适配器](../core/http-adapter.md)。  
  
 您可以将本示例扩展为通常通过 Web 窗体或 HTTP 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交数据所需的应用程序。 通过扩展本示例的 ASP.NET 应用程序部分，您可以在向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交数据之前查询更多信息并执行其他预处理。  
  
## <a name="see-also"></a>另请参阅  
 [HTTP 适配器示例](../core/http-adapter-samples.md)