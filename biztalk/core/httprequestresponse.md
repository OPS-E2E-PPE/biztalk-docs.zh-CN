---
title: HTTPRequestResponse |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 81c66f61-d86c-49cf-8d24-21c67c68bc5a
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a06084320a9b02c548528f2bab7806bf9000569f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332530"
---
# <a name="httprequestresponse"></a>HTTPRequestResponse
HTTPRequestResponse 示例演示如何使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet 服务器应用程序编程接口 (ISAPI) 筛选器允许 ASP.NET 应用程序要与其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程。  

## <a name="what-this-sample-does"></a>本示例的用途  
 在此示例中，ASP.NET 应用程序将请求提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ISAPI 筛选器。 然后，业务流程使用此消息，并将其返回给使用同步响应的 ASP.NET 应用程序。 实现之间的集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程和 ASP.NET 应用程序使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ISAPI 筛选器。  

 在此示例中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 ASP.NET 应用程序交换采购订单 (PO) 和 PO 回执消息使用以下步骤序列：  

1. 使用 HTTP 请求的 ASP.NET 应用程序提交 XML PO 消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收此 XML PO 消息并构造 XML PO 回执消息，然后将该消息发送回的 HTTP 响应中的 ASP.NET 应用程序。  

   ASP.NET 应用程序接收 XML PO 回执响应，并从响应中提取的状态信息刷新 Web 窗体。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \AdaptersUsage\HTTPRequestResponse\  

 下表显示了本示例中的文件及其用途说明：  


|                                                                                                     文件                                                                                                      |                                                                                             Description                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                   Cleanup.bat                                                                                                    |  取消部署程序集，并将其从全局程序集缓存 (GAC) 中;删除发送和接收端口;根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。   |
|                                                                               HTTPRequestResponse.btproj, HTTPRequestResponse.sln                                                                                |                            提供接收 HTTP 请求、 处理 PO 消息，并发出响应的 BizTalk 项目的项目和源代码文件。                             |
|                                                                                          HTTPRequestResponseBinding.xml                                                                                          |                                                                           提供自动的设置，如端口绑定。                                                                            |
|                                                                                             POAck.xsd, POSchema.xsd                                                                                              |                                                            分别提供 PO 回执和 PO.xml 文件的架构。                                                             |
|                                                                                            POReceiveOrchestration.odx                                                                                            |         提供了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程的接收 PO、 处理它，并发出 PO 回执。          |
|                                                                                                    Setup.bat                                                                                                     |                                                                                 生成并初始化本示例。                                                                                 |
| \RequestResponse 文件夹的位置：<br /><br /> AssemblyInfo.cs、 default.aspx、 default.aspx.cs、 Global.asax、 Global.asax.cs、 RequestResponse.csproj、 RequestResponse.csproj.webinfo、 requestresponse.sln 和、 Web.config | 包含构成可作为此示例中，其中包括项目和解决方案文件、 ASPX 文件、 Microsoft Visual C#.NET 源文件等的驱动程序的 ASP.NET 应用程序的文件。 |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程生成并初始化 HTTPRequestResponse 示例。  

#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*示例路径*\>\AdaptersUsage\HTTPRequestResponse  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 编译并配置用于驱动本示例的 ASP.NET 应用程序。  

     > [!NOTE]
     >  在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本 **.Net Framework v4.0**。  

   - 编译并部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此示例中使用的业务流程。  

   - 编译并部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  

   - 创建并绑定必需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]端口。  

   - 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程。  

     > [!IMPORTANT]
     >  必须更改实现 Web 应用程序 (Default.aspx.cs) 以反映你环境的示例代码：  
     >   
     >  http://\<*服务器名称*\>/\<*虚拟 dir*\>/BTSHTTPReceive.dll 其中`<servername>`是 Web 的名称您要发布到，服务器和`<`*虚拟 dir* `>`是此文件所在的位置的虚拟目录。  

     > [!NOTE]
     >  您应确认，BizTalk 未报告任何错误在生成和初始化过程中尝试运行此示例之前。  

     > [!NOTE]
     >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。 您还必须手动删除对 default.aspx.resx 和 Global.asax.resx 的引用从 RequestResponse.csproj 文件然后再尝试生成该项目。  

     > [!NOTE]
     >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

     > [!NOTE]
     >  必须配置和启用 IIS 以便使用 HTTP 接收适配器。 有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  

3. Setup.bat 文件将配置此示例中使用默认网站相关联的 IIS 应用程序池运行的虚拟目录。  若要配置本示例中的用户上下文中运行的虚拟目录**BizTalk Isolated Host Users**并**IIS_IURS**用户组，应配置要运行在新的虚拟目录IIS 应用程序池。 配置要通过完成以下步骤在新的 IIS 应用程序池中运行的虚拟目录：  

   > [!NOTE]
   >  如果已创建一个新的应用程序池的另一个 SDK 示例然后就可以继续到最后一个步骤。  

   1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  

   2.  在中**Internet 信息服务 (IIS) 管理器**，导航到**应用程序池**文件夹。  

   3.  右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**  

   4.  输入的名称**应用程序池 ID:** 如 BizTalkSDKSamples，确认**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。  

   5.  右键单击新的应用程序池，然后单击**属性**。  

   6.  单击**标识**选项卡的属性对话框并更改用于成员的用户运行此应用程序池标识**BizTalk Isolated Host Users**用户组。  此用户还应是本地组成员的**IIS_IURS**用户组。  

   7.  配置此 SDK 示例的新应用程序池下运行的虚拟目录。 **应用程序池**设置位于**虚拟目录**选项卡的虚拟目录属性对话框。 此示例创建的虚拟目录为 HttpRequestResponseSample。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 HTTPRequestResponse 示例。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  在 Internet Explorer 中，导航到 http://localhost/RequestResponse/ 。  

2.  填写 Web 窗体中所需的字段，再单击**下订单**提交你的订单。  

3.  收到响应后刷新 Web 窗体时，观察到你的订单的状态。  

## <a name="comments"></a>注释  
 **BTSHTTPReceiveISAPI**配置此示例中使用的扩展，以在单台计算机默认安装中工作。 若要扩展其他配置，此示例，请参阅[HTTP 适配器](../core/http-adapter.md)。  

 你可以扩展此示例将数据提交到所需的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过 Web 窗体，或在常规的 HTTP。 通过扩展本示例的 ASP.NET 应用程序部分，您可以查询有关详细信息和执行其他预处理提交到数据之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="see-also"></a>请参阅  
 [HTTP 适配器示例](../core/http-adapter-samples.md)