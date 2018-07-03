---
title: 演练： 发布具有 Wcf-basichttp 适配器的 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, publishing
- WCF adapters, tutorials
- publishing, WCF services
- WCF-BasicHttp adapters, tutorials
- publishing, tutorials
- WCF services, publishing
- tutorials, WCF adapters
ms.assetid: 43b76215-9cb0-47ab-a085-c4cf265410f9
caps.latest.revision: 72
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3721080fa296ab5e44ee72c2757461843cfb52bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979774"
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter"></a>演练： 发布具有 Wcf-basichttp 适配器的 WCF 服务
## <a name="introduction"></a>简介  
 本演练使用 BizTalk WCF 服务发布向导和 WCF-BasicHttp 适配器将 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 服务发布为 BizTalk 业务流程。 通过使用 WCF-BasicHttp 适配器公开 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 终结点，BizTalk 业务流程对外部客户端（例如另一个 Web 服务或 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 应用程序）显示为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 WCF-BasicHttp 适配器由一个发送适配器和一个接收适配器组成。 在本示例中，你将仅使用此适配器的接收端从 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端应用程序通过 HTTP 或 HTTPS 协议接收 WCF 服务请求。  
  
 Wcf-basichttp 适配器将使用**BasicHttpBinding**绑定来提供 Web 服务作为之间的桥梁的初始版本兼容的传输/协议堆栈实现[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能。 它通过使用以文本编码的 HTTP 或 HTTPS 传输，提供与符合 WS-I 基本配置文件 1.1 的基于 ASMX 的早期 Web 服务和客户端进行通信的功能。 使用 WCF-BasicHttp 适配器，将无法利用 WS-* 协议支持的高级 Web 通信功能。 如果需要使用这些高级功能，请使用 WCF-WSHttp 适配器。  
  
 本演练介绍如何创建 WCF-BasicHttp 接收位置，以便将业务流程发布为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。  你将配置 Internet 信息服务 (IIS) 来提供对该 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的独立承载。  客户端应用程序调用已发布的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 业务流程，作为外部客户端如何通过 Internet 调用已发布的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务以使用其功能的示例。  
  
 在完成本演练后，你将了解如何执行以下任务：  
  
- 从 Visual Studio 中，使用**部署**命令来部署[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务中的 BizTalk 业务流程内的 BizTalk 程序集到本地实例中的窗体[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 从 Visual Studio 部署将创建一个 BizTalk 应用程序，其中填充有相关程序集，包含要在 BizTalk 解决方案中使用的业务流程、管道、架构和映射等资源。  
  
- 部署之后，你即可通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置和控制 BizTalk 业务流程。 在本演练中，你将配置 WCF-BasicHttp 接收位置，以接受发送到 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的传入消息，该服务由 BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务发布向导创建。 此接收位置在 IIS 中以 BizTalk 独立主机为宿主，并充当获取传入请求的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。  
  
> [!NOTE]
>  在本演练中，你将使用 BizTalk WCF 发布向导和/或 BizTalk Web Services 发布向导，通过 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器将 BizTalk 业务流程和架构发布为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 若要将业务流程和架构发布为 Web 服务使用 SOAP 适配器，请使用**BizTalk WCF 发布向导**和/或**BizTalk Web Services 发布向导**。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本示例中的步骤，请确保你的环境中安装了以下必备软件：  
  
- 这两个程序集将生成并运行部署过程中，并运行该示例的计算机的计算机需要 Microsoft Windows Server 2008 SP2 和/或 Windows Server 2008 R2、 Microsoft.NET Framework 4 和 Microsoft BizTalk Server。  
  
- 用于构建程序集和运行部署过程的计算机需要安装 Microsoft Visual Studio。  
  
- 运行示例的计算机需要 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理工具。 这些是用于安装 Microsoft BizTalk Server 安装过程的选项。  
  
- 在用于执行管理任务的计算机上，你必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的用户帐户运行，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序设置。 此用户帐户还必须是本地管理员组的成员，才能部署应用程序，管理主机实例以及其他可能需要的任务。  
  
- 需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在示例[ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510)。  
  
- 在运行示例并将绑定或 .msi 文件导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上，确保主机不是受信任主机，否则导入将失败。  
  
- 你必须下载演练代码并将其解压缩到您的计算机。 本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 您可以下载文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心， [ http://go.microsoft.com/fwlink/?LinkId=194140 ](http://go.microsoft.com/fwlink/?LinkId=194140)。  
  
### <a name="to-deploy-the-sample-biztalk-solution-biztalkapp"></a>部署 BizTalk 解决方案示例 BizTalkApp  
  
1. 运行自解压**WCFBasicHttpReceiveAdapter.exe**文件，并将文件提取到**C:\WCFBasicHttpReceiveAdapter**文件夹。  
  
2. 在 Microsoft Visual Studio 中打开**C:\WCFBasicHttpReceiveAdapter\WCFBasicHttpReceiveAdapter.sln**文件。  
  
3. **Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**程序集包含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程、 映射和两个架构。 必须安装到 GAC 中并将需要一个强名称密钥文件才能发生。 右键单击**BizTalkApp**项目，然后单击**属性**。 上**属性**页上，单击**签名**，然后选择**程序集签名**。 单击中的向下箭头**选择强名称密钥文件**下拉列表中，单击**\<新建\>**，然后输入`keyfile.snk`中**密钥文件名称**文本框中。 取消选中**保护密钥文件使用密码**，然后单击**确定**。  
  
4. 在解决方案资源管理器中右键单击**BizTalkApp**项目，并单击**重新生成**。  
  
   > [!NOTE]
   >  不要尝试**生成解决方案**，或要生成**WCFClient**此时应用程序。 **WCFClient**尚不可用于构建在此示例中的点。  
  
5. 展开**BizTalkApp**，然后打开**DeliveryProcess.odx**查看。 业务流程使用 WCF-BasicHttp 适配器通过 HTTP 接收 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 请求。 它通过转换映射修改该请求，并使用同一 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器再次发出响应。  
  
   1.  该业务流程具有将通过 WCF-BasicHttp 适配器发布的逻辑请求响应端口。 在稍后的步骤中，该端口将绑定到物理端口。  
  
   2.  右键单击顶级节点**DeliveryProcess.odx**在设计器窗口中，然后选择**属性**。 请确保**的类型修饰符**端口类型的属性是**公共**。  
  
6. 在解决方案资源管理器中右键单击**BizTalkApp**，然后单击**属性**。  
  
   1.  如果未在本地承载 BizTalk 管理数据库，修改**Server**属性，如果使用不同的数据库服务器。 单击**部署**选项卡，然后修改**Server**属性以指向数据库服务器。  
  
   2.  请确保**应用程序名称**属性设置为**WCFBasicHttpReceiveAdapter**。 这是将部署 BizTalk 解决方案的 BizTalk 应用程序的名称。  
  
   3.  在解决方案资源管理器中右键单击**BizTalkApp**，然后单击**部署**。 如果不在本地部署，你可能需要配置 SQL Server 以允许远程连接。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=194141 ](http://go.microsoft.com/fwlink/?LinkId=194141)。  
  
### <a name="to-publish-the-sample-orchestration-by-using-the-biztalk-wcf-service-publishing-wizard"></a>使用 BizTalk WCF 服务发布向导发布示例业务流程  
  
1. 在此步骤中，你将采用新部署的业务流程程序集，并将其发布为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 若要执行此操作，请单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk WCF 服务发布向导**.  
  
2. 上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。  
  
3. 上**WCF 服务类型**页上，执行以下操作以指定的类型[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务以发布，并接收 BizTalk 终结点[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息，并单击**下一步**:  
  
   1. 选择**服务终结点**选项，表明将发布[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务从业务流程的程序集中。 选择**Wcf-basichttp**从**适配器名称 （传输类型）** 下拉列表。  
  
   2. 选择**启用元数据终结点**复选框以使[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]接收由 IIS 承载的位置发布其[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务元数据。 选择此复选框用于设置**httpGetEnabled**的属性\< **serviceMetadata** \>元素`true`在 Web.Config 中。在 HTTP/GET 请求要求此元数据时将检索此元数据。 稍后将使用 SvcUtil.exe 工具获取此数据以生成代理类，客户端代码将使用此代理类调用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。  
  
   3. 选择**以下应用程序中的创建 BizTalk 接收位置**选项来创建接收端口和与 Wcf-basichttp 适配器的每个生成的.svc 文件对应的位置。 选择 BizTalk 应用程序名称， **WCFBasicHttpReceiveAdapter**，其中的接收端口和位置将生成，然后单击**下一步**。  
  
       向导将创建一个 Binding.XML 绑定文件，以表示关联的接收位置。 该文件位于 Web 目录中，稍后你可以通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台手动导入。  
  
      > [!NOTE]
      >  如果未在此处选择已部署的 BizTalk 应用程序，则选择默认应用程序。  
  
4. 上**创建 WCF 服务**页上，选择**BizTalk 业务流程发布为 WCF 服务**，然后单击**下一步**。 这将发布为下一步中指定的业务流程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
5. 选择包含要发布的业务流程的程序集。 上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，单击**浏览**以浏览到**C:\WCFBasicHttpReceiveAdapter\BizTalkApp\bin\Development**文件夹中，双击**Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**包含示例的程序集业务流程，以发布，请单击**开放**，然后单击**下一步**。  
  
6. 上**业务流程和端口**页上，请确保**端口： DeliveryRequestPort**节点的页上，选择，然后单击**下一步**。 选择此节点表示同时选中其相应更高级的节点。 此端口将通过承载 WCF-BasicHttp 适配器的请求-响应接收位置发布。  
  
7. 上**WCF 服务属性**页上，在**目标**的命名空间**WCF 服务**文本框中，键入此已发布的 URI[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务以使用，和然后单击**下一步**。 对于本演练中，保留默认的 URI"**<http://tempuri.org/>"** 的目标命名空间中[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务文本框。  
  
8. 上**WCF 服务位置**页上，执行以下操作以指定的位置[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务以创建，然后单击**下一步**:  
  
   1. 在中**位置**文本框中，键入 Web 目录名称[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务运行，或单击**浏览**并选择 Web 目录。 对于本演练中，由于程序集名称是相同的虚拟目录，请保留默认位置 (**<http://localhost/Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp>**) 中**位置**文本框。  
  
   2. 选择**允许匿名访问 WCF 服务**选项，并单击**下一步**。 此选项允许对已创建的虚拟目录进行匿名访问。 由于本演练使用不带身份验证的传输安全模式，此选项需要选择允许使用此向导将创建的 Web 应用程序的匿名身份验证。  
  
9. 上**WCF 服务摘要**页上，单击**创建**创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 此步骤将为通过指定 Web 目录提供的指定业务流程创建一个接收端口。  
  
10. 上**完成 BizTalk WCF 服务发布向导**页上，单击**完成**。  
  
### <a name="to-enable-the-sample-biztalk-application"></a>启用 BizTalk 示例应用程序  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**应用程序**，展开**WCFBasicHttpReceiveAdapter**，展开**业务流程**，右键单击**DeliveryProcess**业务流程中，单击**属性**，然后按如下所示配置绑定信息：  
  
   1. 在中**业务流程属性**对话框中，单击**绑定**，然后设置**主机**到**BizTalkServerApplication**。  
  
   2. 在中**业务流程属性**对话框中，选择一个接收端口**DeliveryRequestPort**绑定。 在本演练中，选择接收端口的 BizTalk[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导创建在上一过程中，然后依次**确定**。  
  
3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFBasicHttpReceiveAdapter**，单击**启动**，然后单击**启动**中**开始应用程序**对话框。  
  
### <a name="to-configure-the-web-application-hosting-the-published-wcf-service"></a>配置用于承载已发布 WCF 服务的 Web 应用程序  
  
1. 单击**启动**，依次指向**管理工具**，然后单击**Internet 信息服务 (IIS) 7.0 管理器**。  
  
2. 在 IIS 管理器中，展开**站点**，展开**Default Web Site**，然后展开 Web 应用程序**Microsoft.Samples.BizTalk.WCFBasicHttpReceiveAdapter.BizTalkApp**该**BizTalk WCF 服务发布向导**创建。  
  
3. 创建此服务将运行在其中的应用程序池。 右键单击**应用程序池**，单击**添加应用程序池**，输入应用程序池的名称，然后单击**确定**。  
  
4. 展开**应用程序池**，右键单击您刚的应用程序池创建，并选择**高级设置**。 下**过程模型**部分中，输入的帐户有权[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库下**标识**字段。  
  
5. 在 IIS 管理器中，单击**内容视图**。  在右窗格中，右键单击[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务.svc 文件， **BizTalk WCF 服务发布向导**创建，然后依次**浏览**。 这将打开 Internet Explorer 并显示一页，指示你已成功创建一个正在运行的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。 此页还包含一个完整的 WSDL 地址，你可以通过复制该地址并将其用于服务元数据工具 (svcutil.exe) 来检索可用于创建该服务客户端应用程序的代理代码和配置文件。  
  
6. 带有完整 WSDL 地址在上一步中显示的 Internet 资源管理器的页面上的 SvcUtil.exe 命令行复制到剪贴板。  
  
### <a name="to-create-the-proxy-class-for-the-sample-wcf-client-application-wcfclient"></a>为 WCF 客户端应用程序示例 WCFClient 创建代理类  
  
1. 创建一个代理类，因此[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端示例应用程序可以调用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 虽然不需要代理，但是手动编写代码非常复杂，因此推荐创建代理。 打开**Visual Studio 命令提示符**并转到**C:\WCFBasicHttpReceiveAdapter\WCFClient**将放置代理类和应用程序配置文件的文件夹。  
  
2. 粘贴**svcutil.exe**命令行的带有完整 WSDL 地址在上一步骤中复制，然后点击**Enter**创建代理类和应用程序配置文件。 此命令行创建**BizTalkServiceInstance.cs**的代理类和**output.config**的应用程序配置文件。  
  
3. 在 Visual Studio 中，在解决方案资源管理器中右键单击**WCFClient**，依次指向**添加**，然后单击**现有项**。  
  
4. 在中**添加现有项**对话框中，浏览到**WCFClient**文件夹，选择**的所有文件 (\*。\*)** 中**类型的文件**下拉列表中，选择**BizTalkServiceInstance.cs**并**output.config**文件，然后依次**添加**。  
  
5. 有关**WCFClient**项目中，展开**引用**，并请务必**WCFClient**项目具有**System.ServiceModel**作为其引用之一。  
  
6. 展开**WCFClient**项目，右键单击**output.config**，单击**重命名**，然后键入**App.config**的新名称。  
  
7. 双击**Program.cs**查看如何来调用已发布[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务中使用生成的代理类**Svcutil.exe**。 用于实例化和调用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务显示为本地调用中使用编码的简单性**Microsoft_Samples_BizTalk_WCFBasicHttpReceiveAdapter_BizTalkApp_DeliveryProcess_DeliveryRequestPortClient**类。 调用远程 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务无需额外代码。  
  
8. 在 Visual Studio 中，在**调试**菜单上，单击**启动但不调试**以运行 WCFClient。 客户端代码创建 DeliveryItem 消息并调用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务，传入地址、ProductID 和数量。  
  
   ```  
   DeliveryItem deliveryRequestItem = new DeliveryItem();  
   deliveryRequestItem.Address = "One Microsoft Way";  
   deliveryRequestItem.ProductID = "00A120c";  
   deliveryRequestItem.Amount = "300";  
   DeliveryRequestPortClient deliveryProcessClient = new DeliveryRequestPortClient("BasicHttpBinding_ITwoWayAsync");  
   DeliveryItem1 deliveryConfirmation = deliveryProcessClient.Submit(deliveryRequestItem);  
   ```  
  
    如果客户端成功接收来自已发布 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务返回的响应消息，则显示在响应消息中提供的送达确认编号（ProductID 和地址相连）。  
  
    **提交使用 deliveryrequestitem 调用的操作**  
  
    **发回的送达确认编号： 00A120c300One Microsoft Way**  
  
    **按任意键继续...**  
  
## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)