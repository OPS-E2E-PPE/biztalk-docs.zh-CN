---
title: 演练：模块 1-发送和接收消息与 Windows SharePoint Services 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ade2e87fc22e822c825654e158458f1544ba6986
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395347"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a>演练：模块 1-发送和接收消息与 Windows SharePoint Services 适配器
本演练演示如何配置 Windows SharePoint Services 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便可以发送和接收消息使用的 Windows SharePoint Services 适配器和基于内容的路由 (CBR)。 基于内容的路由消除了订阅明确绑定到特定端口的消息的需要。 为想要路由消息根据信封属性或仅根据用户接收端口配置属性，它还提供更大的灵活性。 Windows SharePoint Services 适配器的介绍，请参阅[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 以下是执行本主题中的过程的先决条件：  
  
- 必须具有 BizTalk Server 上运行的完整安装的单服务器部署[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。  
  
  在多服务器部署中使用的 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services 适配器](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="configure-windows-sharepoint-services"></a>配置 Windows SharePoint Services  
 在此过程中创建一个 SharePoint 顶级网站，其中包含三个文档库。 Windows SharePoint Services 适配器使用这些库将消息从源库移动到目标库。 此消息还存档文档库中。 提供可通过在本演练中的 Windows Sharepoint Services 适配器的 Windows Sharepoint Services 站点并设置用户权限以启用对此站点的访问，必须执行此过程。  
  
#### <a name="create-a-windows-sharepoint-services-site"></a>创建 Windows SharePoint Services 站点  
  
1. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心。**  
  
2. 下**虚拟服务器配置**，单击**创建一个顶级网站**。  
  
3. 下**虚拟服务器列表**，选择在安装 Windows SharePoint Services 适配器的 Web 站点。 例如，`Default Web Site`。  
  
4. 在中**网站地址**部分中，在**URL 名称**字段中，键入`WSSAdapterWalkthrough`。  
  
5. 在中**站点集合所有者**部分中，在**用户名字段中，** 键入用户名。 此用户将是网站的所有者，不需要特殊权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
6. 在中**站点集合所有者**部分中，在**电子邮件**字段中，键入电子邮件地址。  
  
7. 单击“确定” 。  
  
8. 上**顶层站点已成功创建**页上，单击刚创建的新的顶级网站。 例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
9. 选择**团队网站**的模板，并单击列表中的模板**确定**。 这将打开工作组网站主页。  
  
#### <a name="create-a-source-document-library"></a>创建"Source"文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在中**名称和描述**部分中，在**名称字段**类型`Source`。  
  
4.  在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。  
  
5.  在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 将创建文档库，并且你将重定向到该空库。  
  
#### <a name="create-a-destination-document-library"></a>创建"Destination"文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在中**名称和描述**部分中，在**名称字段**，类型`Destination`。  
  
4.  在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。  
  
5.  在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 将创建文档库，并且你将重定向到该空库。  
  
#### <a name="create-an-archive-document-library"></a>创建"Archive"文档库  
  
1.  在团队网站主页上，在顶部导航栏上，单击**创建**。  
  
2.  下**文档库**，单击**文档库**。  
  
3.  在中**名称**和描述部分，在**名称字段**，类型`Archive`。  
  
4.  在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。  
  
5.  在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。  
  
6.  单击 **“创建”**。 将创建文档库，并且你将重定向到该空库。  
  
7.  关闭`WSSAdapterWalkthrough`Web 站点。  
  
8.  关闭**SharePoint 管理中心**Web 站点。  
  
#### <a name="configure-windows-security"></a>配置 Windows 安全性  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  在控制台树中，展开**本地用户和组**，然后单击**组**。  
  
3.  右键单击**SharePoint Enabled Hosts**组中，单击**将添加到组**，然后单击**添加**。  
  
4.  在中**选择用户、 计算机或组对话框**下**输入要选择的对象名称**，键入配置下，运行，然后单击 BizTalk Server 主机实例的帐户的名称**确定**。  
  
5.  在控制台树中，展开**服务和应用程序**，然后单击**服务**。  
  
6.  右键单击**BizTalk 服务 BizTalk 组： < BizTalk_Host_Name >**，然后单击**重新启动**。  
  
    > [!NOTE]
    >  < BizTalk_Host_Name > 是主机的你的名称。 默认情况下，这是`BizTalkServerApplication`。  
  
    > [!NOTE]
    >  重新启动该服务，成员资格才会生效。  
  
7.  关闭**计算机管理**。  
  
#### <a name="configure-sharepoint-security"></a>配置 SharePoint 安全性  
  
1. 打开 Web 浏览器并导航到你创建的站点的 URL。 例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2. 在团队网站主页上，在顶部导航栏上，单击**站点设置**。  
  
3. 下**Administration**，单击**管理用户**。  
  
4. 单击 **“添加用户”**。  
  
5. 在**步骤 1:选择用户**，键入帐户的名称，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]下运行主机实例。  
  
6. 在“步骤 2：**选择网站用户组**，选择**读取器**并**参与者**复选框。  
  
7. 单击“下一步” 。  
  
8. 清除**发送以下电子邮件以通知这些用户现在他们已被添加**复选框，然后依次**完成**。  
  
9. 关闭`WSSAdapterWalkthrough`Web 站点。  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a>创建和配置 BizTalk Server 端口  
 在此过程将创建并配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收端口、 接收位置和 Windows SharePoint Services 适配器发送端口。 这些端口是输入和输出的入口点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于接收和 Windows Sharepoint Services 适配器发送的文档。  
  
#### <a name="create-the-receive-port"></a>创建接收端口  
  
1. 单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理。**  
  
2. 展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，右键单击**接收端口**，单击**新建**，然后单击**单向接收端口...**  
  
3. 在中**接收端口属性**对话框中的**常规**，类型`FromSource`中**名称**字段。  
  
4. 单击“确定” 。  
  
#### <a name="create-the-receive-location"></a>创建接收位置  
  
1.  在中**BizTalk 管理控制台**，右键单击**接收位置**节点中，单击**新建**，然后单击**单向接收位置**.  
  
2.  在中**选择接收端口**对话框中，选择`FromSource`，然后单击**确定**。  
  
3.  在中**接收位置属性**对话框中的**常规**，类型`SourceLocation`中**名称**字段。  
  
4.  在中**传输**部分中，在**类型**下拉列表中，选择`Windows``SharePoint``Services`。  
  
5.  单击**配置**配置 Windows SharePoint Services 适配器属性。  
  
6.  在中**适配器 Web 服务端口**属性中，键入已安装 Windows SharePoint Services 适配器 Web services 虚拟服务器的端口号。 默认情况下，这是端口 80。  
  
7.  类型`Archive`中**存档位置**属性。  
  
8.  类型`10`中**轮询间隔**属性。  
  
9. 键入指向 SharePoint 站点中的 URL **ShareP**oint 站点 Url 属性。 例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
10. 类型`Source`有关**源文档库**属性。  
  
11. 单击“确定” 。  
  
12. 在中**接收位置属性**对话框中，选择`BizTalkServerApplication`作为**接收处理程序**。  
  
13. 在中**接收管道**下拉列表中，选择`PassThruReceive`。  
  
14. 单击“确定” 。  
  
#### <a name="create-the-send-port"></a>创建发送端口  
  
1.  在中**BizTalk 管理控制台**，右键单击**发送端口**节点中，单击**新建**，然后单击**静态单向发送端口**.  
  
2.  在中**发送端口属性**对话框中的**常规**，类型`SendToDestination`中**名称**字段。  
  
3.  在中**传输**部分中，选择`Windows SharePoint Services`的类型。  
  
4.  单击**配置**配置 Windows SharePoint Services 适配器属性。  
  
5.  在中**适配器 Web 服务端口**属性中，键入已安装 Windows SharePoint Services 适配器 Web services 虚拟服务器的端口号。 默认情况下，这是端口 80。  
  
6.  在键入`Destination`有关**目标文件夹**属性。  
  
7.  在键入`PurchaseOrder1-%MessageID%.xml`有关**文件名**属性。  
  
8.  设置**覆盖**属性设置为`Yes`。  
  
9. 中的 SharePoint 站点的 URL 中的类型**SharePoint 站点 Url**属性。 例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
10. 设置**Microsoft Office 集成**属性设置为`No`。  
  
11. 单击“确定” 。  
  
12. 在中**发送端口属性对话框**，在**发送处理程序**下拉列表中，选择`BizTalkServerApplication`。  
  
13. 在中**发送管道**下拉列表中，选择`PassThruTransmit`。  
  
14. 单击**筛选器**选项卡。  
  
15. 选择`WSS.InListName`中**属性**字段。  
  
16. 选择`==`中**运算符**字段。  
  
17. 类型`Source`中**值**字段。  
  
18. 单击“确定” 。  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a>启用并启动接收位置和接收端口  
 在这些过程中启用接收位置并启动接收端口。 必须完成此过程，以允许 Windows Sharepoint Services 适配器发送和接收消息通过指定的发送端口和接收位置。  
  
#### <a name="enable-the-receive-location"></a>启用接收位置  
  
1.  在中**BizTalk 管理控制台**，单击**接收位置**节点。  
  
2.  右键单击`SourceLocation`，然后单击**启用**。  
  
#### <a name="start-the-send-port"></a>启动发送端口  
  
1.  在中**BizTalk 管理控制台**，单击**发送端口**节点。  
  
2.  右键单击`SendToDestination`，然后单击**启动**。  
  
3.  关闭**BizTalk 管理控制台**。  
  
## <a name="sending-a-message-through-the-system"></a>通过系统发送消息  
 在此过程中创建 XML 文档并将其上载到 Windows SharePoint Services 网站。 Windows SharePoint Services 适配器将接受该消息、 将其存档在存档文档库和将其发送给目标文档库中。 此过程说明了文档的流动方式从 Sharepoint 网站， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，到达 Sharepoint Services 网站使用 Windows Sharepoint Services 适配器。  
  
#### <a name="create-a-working-directory"></a>创建工作目录  
  
-   名为在计算机上创建一个目录**WSSAdapterWalkthrough**。 例如，`C:\WSSAdapterWalkthrough`。  
  
#### <a name="create-an-xml-file"></a>创建一个 XML 文件  
  
1.  单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**记事本。**  
  
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
  
3.  将文件保存在工作目录中为`PurchaseOrder1.xml`。 例如，`C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`。  
  
#### <a name="upload-the-xml-file"></a>上传 XML 文件  
  
1. 打开 Web 浏览器并导航到上一个任务中创建的站点的 URL。 例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2. 在左侧下,**文档**，单击**源**。  
  
3. 单击**上传文档**。  
  
4. 在中**名称**框中，键入或浏览到 XML 文件创建。 例如， `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`，然后单击**保存并关闭**。 现在应能够看到列表中的文件。  
  
5. 刷新浏览器窗口。 `PurchaseOrder1.xml`文件将不再在此库中列出。  
  
   > [!NOTE]
   >  您可能需要刷新浏览器几次，由于轮询间隔设置为 10 秒钟。  
  
6. 在顶部导航栏上，单击**文档和列表**。  
  
7. 下**文档库**，单击**目标**。  
  
8. 在目标文档库中，现在将看到你的消息已列出。 您还可以找到在存档文档库中存档的副本。  
  
   > [!NOTE]
   >  如果在目标文档库中不显示消息，请参阅"故障排除 Windows SharePoint Services 适配器"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="summary"></a>总结  
 在本演练中，你已了解如何配置 Windows SharePoint Services 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便可以发送和接收消息使用的 Windows SharePoint Services 适配器和基于内容的路由 (CBR)。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练：模块 2-Office 与 Windows SharePoint Services 适配器相集成](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)演练中，它扩展了本演练的工作并演示如何将 Office 与 Windows SharePoint Services 适配器相集成。  
  
## <a name="see-also"></a>请参阅  
 [什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)