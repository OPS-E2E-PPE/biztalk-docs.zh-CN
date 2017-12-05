---
title: "演练： 模块 1-发送和接收消息与 Windows SharePoint Services 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8e83297233c4f8ac51ad90f488437a6c259691a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a>演练： 模块 1-发送和接收消息与 Windows SharePoint Services Adapter
本演练介绍如何配置 Windows SharePoint Services 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以便可以使用 Windows SharePoint Services 适配器和基于内容的路由 (CBR) 来发送和接收消息。 基于内容的路由消除了订阅明确绑定到特定端口的消息的必要。 同时为那些需要根据信封属性或仅根据接收端口配置属性路由消息的用户提供了更多的灵活性。 Windows SharePoint Services 适配器的简介，请参阅[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   你必须具有 BizTalk Server 上运行的完整安装的单一服务器部署[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。  
  
 有关在多服务器部署中使用的 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="configure-windows-sharepoint-services"></a>配置 Windows SharePoint Services  
 在此过程中，将创建一个包含三个文档库的 SharePoint 顶级网站。 Windows SharePoint Services 适配器使用这些库将消息从源库移动到目标库。 此消息还会在文档库中存档。 必须执行此过程，以提供 Windows Sharepoint Services 适配器在本演练中所访问的 Windows Sharepoint Services 站点，并设置用户权限使用户能访问此站点。  
  
#### <a name="create-a-windows-sharepoint-services-site"></a>创建 Windows SharePoint Services 站点  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心。**  
  
2.  下**虚拟服务器配置**，单击**创建顶级网站**。  
  
3.  下**虚拟服务器列表**，选择在安装 Windows SharePoint Services Adapter 的网站。 例如， `Default Web Site`。  
  
4.  在**网站地址**部分中，在**URL 名称**字段中，键入`WSSAdapterWalkthrough`。  
  
5.  在**网站集所有者**部分中，在**用户名字段中，**键入用户名。 此用户将是该网站的所有者，不需要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中具有特殊权限。  
  
6.  在**网站集所有者**部分中，在**电子邮件**字段中，键入一个电子邮件地址。  
  
7.  单击 **“确定”**。  
  
8.  上**顶层站点已成功创建**页上，单击你刚刚创建了新的顶级网站。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
9. 选择**团队站点**中模板，然后单击该列表中的模板**确定**。 这将打开工作组网站主页。  
  
#### <a name="create-a-source-document-library"></a>创建“Source”文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在**名称和描述**部分中，在**名称字段中，**类型`Source`。  
  
4.  在**导航**部分中，选择**是**在快速启动栏上显示此窗体库。  
  
5.  在**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 此时将创建该文档库，并且您将重定向到该空库。  
  
#### <a name="create-a-destination-document-library"></a>创建“Destination”文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在**名称和描述**部分中，在**名称字段**，类型`Destination`。  
  
4.  在**导航**部分中，选择**是**在快速启动栏上显示此窗体库。  
  
5.  在**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 此时将创建该文档库，并且您将重定向到该空库。  
  
#### <a name="create-an-archive-document-library"></a>创建“Archive”文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在**名称**和描述部分，在**名称字段**，类型`Archive`。  
  
4.  在**导航**部分中，选择**是**在快速启动栏上显示此窗体库。  
  
5.  在**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 此时将创建该文档库，并且您将重定向到该空库。  
  
7.  关闭 `WSSAdapterWalkthrough` 网站。  
  
8.  关闭**SharePoint 管理中心**Web 站点。  
  
#### <a name="configure-windows-security"></a>配置 Windows 安全性  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  在控制台树中，展开**本地用户和组**，然后单击**组**。  
  
3.  右键单击**SharePoint 启用主机**组中，单击**将添加到组**，然后单击**添加**。  
  
4.  在**选择用户、 计算机或组对话框**下**输入要选择的对象名称**，键入配置 BizTalk Server 主机实例以运行下，然后单击的帐户的名称**确定**。  
  
5.  在控制台树中，展开**服务和应用程序**，然后单击**服务**。  
  
6.  右键单击**BizTalk 服务 BizTalk 组： < BizTalk_Host_Name >**，然后单击**重新启动**。  
  
    > [!NOTE]
    >  < BizTalk_Host_Name > 是主机的你的名称。 默认情况下，这是`BizTalkServerApplication`。  
  
    > [!NOTE]
    >  在重新启动服务之前，成员身份将不会生效。  
  
7.  关闭**计算机管理**。  
  
#### <a name="configure-sharepoint-security"></a>配置 SharePoint 安全性  
  
1.  打开 Web 浏览器并导航到所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在团队网站主页上，在顶部导航栏上，单击**站点设置**。  
  
3.  下**管理**，单击**管理用户**。  
  
4.  单击 **“添加用户”**。  
  
5.  在**步骤 1： 选择用户**，键入帐户的名称，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例下运行。  
  
6.  在**步骤 2： 选择站点组**，选择**读取器**和**参与者**复选框。  
  
7.  单击 **“下一步”**。  
  
8.  清除**发送以下电子邮件以通知这些用户现在他们已被添加**复选框，并依次**完成**。  
  
9. 关闭 `WSSAdapterWalkthrough` 网站。  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a>创建和配置 BizTalk Server 端口  
 在此过程中，您将为 Windows SharePoint Services 适配器创建和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收端口、接收位置和发送端口。 这些端口是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的出入点，Windows Sharepoint Services 适配器通过它们来接收和发送文档。  
  
#### <a name="create-the-receive-port"></a>创建接收端口  
  
1.  单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理。**  
  
2.  展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，右键单击**接收端口**，单击**新建**，然后单击**单向接收端口...**  
  
3.  在**接收端口属性**对话框中，在**常规**，类型`FromSource`中**名称**字段。  
  
4.  单击 **“确定”**。  
  
#### <a name="create-the-receive-location"></a>创建接收位置  
  
1.  在**BizTalk 管理控制台**，右键单击**接收位置**节点，单击**新建**，然后单击**单向接收位置**.  
  
2.  在**选择接收端口**对话框中，选择`FromSource`，然后单击**确定**。  
  
3.  在**接收位置属性**对话框中，在**常规**，类型`SourceLocation`中**名称**字段。  
  
4.  在**传输**部分中，在**类型**下拉列表中，选择`Windows``SharePoint``Services`。  
  
5.  单击**配置**配置 Windows SharePoint Services 适配器属性。  
  
6.  在**适配器 Web 服务端口**属性，键入安装 Windows SharePoint Services 适配器 Web 服务的位置的虚拟服务器的端口号。 默认情况下，此端口为端口 80。  
  
7.  类型`Archive`中**存档位置**属性。  
  
8.  类型`10`中**轮询间隔**属性。  
  
9. 键入指向 SharePoint 站点中的 URL **ShareP**oint 站点 Url 属性。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
10. 类型`Source`为**源文档库**属性。  
  
11. 单击 **“确定”**。  
  
12. 在**接收位置属性**对话框中，选择`BizTalkServerApplication`作为**接收处理程序**。  
  
13. 在**接收管道**下拉列表中，选择`PassThruReceive`。  
  
14. 单击 **“确定”**。  
  
#### <a name="create-the-send-port"></a>创建发送端口  
  
1.  在**BizTalk 管理控制台**，右键单击**发送端口**节点，单击**新建**，然后单击**静态单向发送端口**.  
  
2.  在**发送端口属性**对话框中，在**常规**，类型`SendToDestination`中**名称**字段。  
  
3.  在**传输**部分中，选择`Windows SharePoint Services`类型。  
  
4.  单击**配置**配置 Windows SharePoint Services 适配器属性。  
  
5.  在**适配器 Web 服务端口**属性，键入安装 Windows SharePoint Services 适配器 Web 服务的位置的虚拟服务器的端口号。 默认情况下，此端口为端口 80。  
  
6.  键入`Destination`为**目标文件夹**属性。  
  
7.  键入`PurchaseOrder1-%MessageID%.xml`为**Filename**属性。  
  
8.  设置**覆盖**属性`Yes`。  
  
9. 中的 SharePoint 站点的 URL 中的类型**SharePoint 站点 Url**属性。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
10. 设置**Microsoft Office 集成**属性`No`。  
  
11. 单击 **“确定”**。  
  
12. 在**发送端口属性对话框中**中**发送处理程序**下拉列表中，选择`BizTalkServerApplication`。  
  
13. 在**发送管道**下拉列表中，选择`PassThruTransmit`。  
  
14. 单击**筛选器**选项卡。  
  
15. 选择`WSS.InListName`中**属性**字段。  
  
16. 选择`==`中**运算符**字段。  
  
17. 类型`Source`中**值**字段。  
  
18. 单击 **“确定”**。  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a>启用并启动接收位置和接收端口  
 在以下过程中，您将启用接收位置并启动接收端口。 必须完成此过程，以使 Windows Sharepoint Services 适配器能够通过指定的发送端口和接收位置发送和接收消息。  
  
#### <a name="enable-the-receive-location"></a>启用接收位置  
  
1.  在**BizTalk 管理控制台**，单击**接收位置**节点。  
  
2.  右键单击`SourceLocation`，然后单击**启用**。  
  
#### <a name="start-the-send-port"></a>启动发送端口  
  
1.  在**BizTalk 管理控制台**，单击**发送端口**节点。  
  
2.  右键单击`SendToDestination`，然后单击**启动**。  
  
3.  关闭**BizTalk 管理控制台**。  
  
## <a name="sending-a-message-through-the-system"></a>通过系统发送消息  
 在此过程中，您将创建一个 XML 文档并将其上载到 Windows SharePoint Services 网站。 Windows SharePoint Services 适配器将接受该消息并将其存档在存档文档库中，然后将其发送到目标文档库。 此过程说明文档是如何通过 Windows Sharepoint Services 适配器，从 Sharepoint 网站流出，通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，到达 Sharepoint Services 网站的。  
  
#### <a name="create-a-working-directory"></a>创建工作目录  
  
-   调用计算机上创建一个目录**WSSAdapterWalkthrough**。 例如， `C:\WSSAdapterWalkthrough`。  
  
#### <a name="create-an-xml-file"></a>创建 XML 文件  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**记事本。**  
  
2.  键入以下命令：  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  将该文件保存在工作目录中，名称为 `PurchaseOrder1.xml`。 例如， `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`。  
  
#### <a name="upload-the-xml-file"></a>上载 XML 文件  
  
1.  打开 Web 浏览器并导航到上一任务中所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在左侧下,**文档**，单击**源**。  
  
3.  单击**将文档上载**。  
  
4.  在**名称**框中，键入或浏览到 XML 文件创建。 例如， `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`，然后单击**保存并关闭**。 现在您应该可以在列表中看到该文件。  
  
5.  刷新浏览器窗口。 `PurchaseOrder1.xml` 文件将不会再在此库中列出。  
  
    > [!NOTE]
    >  由于轮询间隔设置为 10 秒钟，因此，您可能需要刷新浏览器数次。  
  
6.  在顶部导航栏上，单击**文档和列表**。  
  
7.  下**文档库**，单击**目标**。  
  
8.  在目标文档库中，现在您将看到您的消息已列出。 您还将在存档文档库中找到存档副本。  
  
    > [!NOTE]
    >  如果目标文档库中未显示消息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的“Windows SharePoint Services 适配器疑难解答”。  
  
## <a name="summary"></a>摘要  
 在本演练中，您学习了如何配置 Windows SharePoint Services 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以便可以使用 Windows SharePoint Services 适配器和基于内容的路由 (CBR) 来发送和接收消息。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练中，执行[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)演练中，你已完成此演练和显示的工作进行扩展你如何将 Office 集成了 Windows SharePoint Services 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)