---
title: '演练 (AS2): 使用同步 MDN 通过 AS2 发送 EDI |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21891d29-eb22-4b31-9258-14b72ae675dc
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b5417adfd53498891eccb2845b815f475e861a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982326"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn"></a>演练 (AS2)：使用同步 MDN 通过 AS2 发送 EDI
本演练将介绍创建一个通过 AS2 用同步 MDN 发送 EDI 消息的解决方案的分步操作过程。 您可以在单台计算机上创建并测试本演练中的完整解决方案。  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  
  
- 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
- 运行演练的计算机必须安装了 Internet 信息服务 (IIS)。  
  
- 如果运行此演练的计算机安装了 64 位版本的 Windows，则您必须确保 BizTalk 主机标记只能为 32 位。 您还必须确保 IIS 已将“为应用程序池启用 32 位应用程序设置”设置为 True。  有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-a-synchronous-mdn"></a>解决方案如何发送 EDI/AS2 消息并返回同步 MDN  
 该解决方案将执行以下操作：  
  
1. 一个单向 FILE 接收端口从 Contoso 接收 EDI 交换。  
  
   > [!NOTE]
   >  此列表中的事件可能不会按所示顺序发生。  
  
2. 使用直通接收管道时，接收端口会将测试消息原封不动地放入 MeassageBox。  
  
3. 静态双向发送端口提取 EDI 交换并将其编码为 AS2 格式。  
  
4. 发送端口通过 AS2 传输将 AS2 编码的 EDI 交换发送至 Fabrikam 参与方。  
  
5. Fabrikam 的双向接收端口使用 Fabrikam 虚拟目录接收 AS2 消息。 接收管道将来自 AS2 的 EDI 交换解码并放入 MessageBox。  
  
6. 与双向接收端口关联的发送端口返回同步 MDN。  
  
7. 与双向发送端口关联的接收端口接收 MDN 并将其放入 MessageBox。  
  
8. 带有直通发送管道的静态单向发送端口提取 MDN。  
  
9. 该单向发送端口将 MDN 发送至本地文件夹。  
  
10. 带有直通发送管道的静态单向发送端口提取 EDI 消息。  
  
11. 单向发送端口将 EDI 消息发送至一个本地文件夹。  
  
    下图显示出此解决方案的结构。  
  
    ![使用同步 MDN 的 AS2 发送](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")  
  
## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 本演练的功能具有以下特点：  
  
-   本演练针对的是 AS2 功能，而非 EDI 功能。 因此，AS2 处理所涉及的所有端口使用的是 AS2Receive 或 AS2Send 管道，而非 AS2EdiReceive 和 AS2EdiSend。 AS2 处理未涉及到的端口使用 PassThruReceive 或 PassThruTransmit 管道。  
  
-   状态报告未启用。  
  
-   此解决方案不在不可否认数据库中配置签名、压缩、加密或消息存储。 有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  
  
- 使用所需的消息架构生成并部署 BizTalk 项目，并将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置为在处理接收的交换时使用这些架构。  
  
- 启用接收 AS2 消息时使用的 BTS ISAPI 筛选器。  
  
- 按照接收位置中的配置，创建一个用于从 Contoso 接收 AS2 消息的 Fabrikam 虚拟目录。  
  
- 指定 Fabrikam 虚拟目录不由 Windows SharePoint Services 托管。  
  
- 创建一个单向 FILE 接收端口接收通过 AS2 传输方法发送的 EDI 测试消息。 创建接收测试消息的本地文件夹。  
  
- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个静态双向 HTTP 发送端口，以将包含 EDI 业务文档的 AS2 消息发送至 Fabrikam 并接收 MDN 响应。 将发送管道配置为 AS2Send 管道，将接收管道配置为 AS2Receive 管道。  
  
- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个双向 HTTP 接收端口，用于接收 AS2 消息和发送 MDN 响应。 将接收管道配置为 AS2Receive 管道，将发送管道配置为 AS2Send 管道。 配置用于接收经 Fabrikam 虚拟目录发送的 AS2 消息的接收位置。  
  
  > [!NOTE]
  >  此解决方案在单台计算机上执行；因此用于从 Contoso 发送 AS2 消息的双向发送端口和作为 Fabrikam 接收 AS2 消息的双向接收端口都在同一计算机上。  
  
- 创建一个带有直通发送管道的单向 FILE 发送端口以将 MDN 路由至本地文件夹。 创建本地文件夹。  
  
- 创建一个带有直通发送管道的单向 FILE 发送端口以将消息负载路由至本地文件夹。 创建本地文件夹。  
  
  > [!NOTE]
  >  如果没有用于订阅该消息负载的发送端口，它将会在 MessageBox 中挂起。   
  
- 为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。  
  
- 为这两个贸易参与方创建业务配置文件每个。  
  
- 在 Fabrikam 和 Contoso 的业务配置文件之间创建一个 AS2 协议。 AS2 协议中将包含要发送的 AS2 消息并接收返回同步 MDN 的属性。  
  
- 使用测试 EDI 交换测试演练。  
  
  > [!NOTE]
  >  对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。 该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ 文件夹。 这是一个 X12 850 消息。  
  
### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  
  
##### <a name="to-deploy-the-message-schema"></a>部署消息架构  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  
  
   > [!NOTE]
   >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
2. 右键单击你的项目，指向**外**，然后单击**现有项**。 要使用 SamplePO.txt 文件测试您的解决方案，请访问 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。 选择 X12_00401_850.xsd 架构，然后单击**添加**。  
  
   > [!NOTE]
   >  若要使用其他 EDI 架构，请转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI 文件夹。 如果 EDI 架构尚未解压缩到 XSD_SchemaEDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹将架构解压缩到默认文件夹中的文件。  
  
3. 设置程序集密钥文件，然后生成并部署该程序集。  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>启用 BTS ISAPI 筛选器  
  
1. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
   > [!TIP]
   >  根据操作系统，管理工具启动菜单选项可能不可用。 在这种情况下，单击**启动**，单击**运行**，然后输入`inetmgr`打开 Internet 信息服务 (IIS) 管理器。  
  
2. 选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在操作窗格中的单击**添加脚本映射**。  
  
   > [!NOTE]
   >  在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。 如果你想要将映射限制到特定的网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。  
  
3. 在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。  
  
4. 在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。 选择 BtsHttpReceive.dll，然后单击**确定**。  
  
5. 输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。  
  
6. 在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。 输入`POST`作为谓词。  
  
7. 上**访问**选项卡上，选择**脚本**，然后单击**确定**。  
  
8. 单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>配置 Fabrikam 网页  
  
1. 在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。  
  
2. 在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。 单击“确定” 。  
  
   > [!NOTE]
   >  根据计算机上安装的 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 版本，.NET Framework 的版本可能会有所不同。  
  
3. 选择**应用程序池**，在**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。  
  
4. 在中**高级设置**对话框中，选择**标识**，然后单击省略号 （...） 按钮。  
  
5. 在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。  
  
6. 输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。  
  
7. 在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site**节点，并选择**添加应用程序**。  
  
8. 在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。  
  
9. 在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。  
  
10. 单击省略号 （...） 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。  
  
11. 单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
12. 在 IIS 管理器中，选择 Fabrikam 虚拟目录并在**功能视图**，双击**身份验证**。  
  
13. 在中**身份验证**页上，选择**匿名身份验证**，并验证**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>指定虚拟目录不由 Windows SharePoint Services 托管  
  
1.  如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。  
  
    > [!NOTE]
    >  如果用于设置演练的同一计算机上还安装了 Windows SharePoint Server，则此过程是必需的。 在该情况下，您必须指定 IIS 虚拟目录不由 Windows SharePoint Server 托管。  
  
2.  上**Central Administration**页面上，在**管理中心**，单击**应用程序管理**。  
  
3.  上**应用程序管理**页上，单击**定义管理路径**。  
  
4.  中**定义管理路径**页面上，在**添加新路径**，在**路径**文字框中，输入`Fabrikam`。 下**类型**，单击**排除的路径**，然后单击**确定**。  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a>创建接收 EDI 测试消息的接收端口  
  
1. 在 Windows 资源管理器中，创建一个用于从 Contoso 接收 EDI 交换的本地文件夹。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。  
  
3. 为接收端口的名称**RecvISAFromCont**，然后单击**接收位置**在控制台树中。  
  
4. 单击 **“新建”**。  
  
5. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  
  
6. 有关**接收文件夹**，输入在步骤 1 中创建的文件夹的名称。  
  
7. 有关**文件掩码**，输入你的文件的扩展名。 如果您使用的 SamplePO.txt 文件作为测试消息，请输入 **\*.txt**。 单击“确定” 。  
  
8. 有关**接收管道**，接受默认值为**PassThruReceive**。  
  
9. 单击**确定**，然后单击**确定**试。  
  
10. 单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。  
  
##### <a name="to-create-a-two-way-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam-and-receive-an-mdn-response"></a>创建通过 AS2 将 EDI 交换发送至 Fabrikam 并接收 MDN 响应的双向发送端口  
  
1. > [!NOTE]
   >  静态双向发送端口提取 EDI 交换并将其编码为 AS2 格式。 然后通过 AS2 传输将 AS2 编码的 EDI 交换发送到 Fabrikam 参与方。 其后，与双向发送端口关联的接收端口接收来自 Fabrikam 的 MDN 并将其放入 MessageBox。  
  
    在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态要求响应发送端口**。  
  
2. 在中**发送端口属性**对话框中，发送端口名称。 对于此解决方案，发送端口命名为**SendISAToFab_RecMDN**。  
  
3. 在中**传输**部分中，选择**HTTP**有关**类型**，然后单击**配置**。  
  
4. 在中**HTTP 传输属性**对话框中，对于**目标 URL**，输入**http://localhost/Fabrikam/BTSHttpReceive.dll**。  
  
5. 清除**启用 Chunked 编码**，然后单击**确定**。  
  
6. 在中**发送管道**，选择**AS2Send**。  
  
7. 在中**接收管道**，选择**AS2Receive**。  
  
8. 在控制台树中，选择**筛选器**。 有关**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**输入将接收 EDI 的接收端口的名称交换 (`RecvISAFromCont`)。  
  
9. 单击“确定” 。  
  
10. 单击**发送端口**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击您的发送端口，然后单击**启动**。  
  
##### <a name="to-create-a-two-way-receive-port-to-receive-the-as2-message-and-return-an-mdn"></a>创建接收 AS2 消息并返回 MDN 的双向接收端口  
  
1. > [!NOTE]
   >  Fabrikam 的双向接收端口使用 Fabrikam 虚拟目录接收 AS2 消息。 接收管道将来自 AS2 的 EDI 交换解码并放入 MessageBox。 与双向接收端口关联的发送端口返回同步 MDN。  
  
    在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**BizTalk Application 1**节点，右键单击**接收端口**，指向**新建**，然后单击**请求响应接收端口**。  
  
2. 为接收端口的名称**RecvAS2ForFab**，然后单击**接收位置**在控制台树中。  
  
3. 单击 **“新建”**。  
  
4. 在**接收位置属性**对话框中，名称在接收位置中，选择**HTTP**有关**类型**，然后单击**配置**。  
  
5. 在中**HTTP 传输属性**对话框框中，输入 **/Fabrikam/BTSHttpReceive.dll**有关**虚拟目录和 ISAPI 扩展**。 清除**成功后的返回相关句柄**，然后选择**挂起失败的请求**。 单击“确定” 。  
  
6. 选择**AS2Receive**有关**接收管道**，并**AS2Send**有关**发送管道**。 单击**确定**，然后单击**确定**试。  
  
7. 单击**接收位置**节点，右键单击将接收位置，然后依次**启用**。  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>创建用于将 EDI 负载发送到本地文件夹的发送端口  
  
1. 在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
3. 在中**发送端口属性**对话框，为发送端口的名称**SendEDIMsg**。 选择**文件**有关**类型**，然后单击**配置**。  
  
4. 在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入为 EDI 负载创建的本地文件夹。  
  
5. 有关**文件名**，输入文件名称。 如果您使用的 SamplePO.txt 文件作为测试消息，请输入 **%MessageID%.txt**。 单击“确定” 。  
  
6. 接受默认值为**PassThruTransmit**有关**发送管道**。  
  
7. 单击**筛选器**在控制台树，并添加用于提取 EDI 负载的筛选器属性。 在第一行，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**，输入接收 AS2 的接收端口的名称消息 (`RecvAS2ForFab`); 对于**分组依据**，接受**和**。 在第二行，对于**属性**，输入**EdiIntAS.IsAS2PayloadMessage**; 对于**运算符**，输入**==**; 以及**值**，输入**True**。  
  
8. 单击“确定” 。  
  
9. 单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a>创建用于将 MDN 发送到本地文件夹的发送端口  
  
1. 在 Windows 资源管理器中，创建一个用于接收 MDN 的本地文件夹。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
3. 在中**发送端口属性**对话框，为发送端口的名称**SendMDN**。 选择**文件**有关**类型**，然后单击**配置**。  
  
4. 在中**FILE 传输属性**对话框中，对于**目标文件夹**，输入您创建的用于接收 MDN 的本地文件夹。  
  
5. 有关**文件名**，输入 **%MessageID%.msg**。单击**确定**。  
  
6. 接受默认值为**PassThruTransmit**有关**发送管道**。  
  
7. 单击**筛选器**在控制台树中。 有关**属性**，输入**BTS。SPName**; 对于**运算符**，输入**==**; 对于**值**，输入将发送 AS2 消息的发送端口的名称 (`SendISAToFab_RecMDN`);对于**分组依据**，接受**和**。 在第二个行中，对于**属性**，输入**EdiIntAS.IsAS2MdnResponseMessage**; 对于**运算符**，输入**==**; 对于**值**，输入**True**。  
  
8. 单击“确定” 。  
  
9. 单击**发送端口**节点，右键单击您的发送端口，然后依次**启动**。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>创建 Fabrikam 参与方和业务配置文件  
  
1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  
  
   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  
  
3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  
  
4. 在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。  
  
   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>为 Contoso 创建参与方和业务配置文件  
  
1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  
  
   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  
  
3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  
  
4. 在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。  
  
   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>在两个业务配置文件之间创建 AS2 协议  
  
1.  右键单击**Contoso_Profile**，依次指向**新建**，然后单击**协议**。  
  
2.  在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  
  
3.  从**协议**下拉列表中，选择**AS2**。  
  
4.  在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Fabrikam**。  
  
5.  在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Fabrikam_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。  
  
6.  在执行以下任务**Contoso-> Fabrikam**选项卡。  
  
    1.  上**标识符**页上，输入值**AS2-从**并**AS2-到**。 有关**AS2-从**，输入`Contoso`。 有关**AS2-To**，输入`Fabrikam`。  
  
    2.  在中**确认 (Mdn)** 页上，执行以下操作：  
  
        1.  选择**到 MessageBox 中处理入站的 MDN 以进行路由/传递**复选框。  
  
            > [!NOTE]
            >  检查**到 MessageBox 中处理入站的 MDN 以进行路由/传递**需要本演练中，测试，因为只有这样将返回的 MDN 才能放入 MessageBox。 这样，便可创建一个用于订阅 MDN 并将 MDN 发送至本地目录的发送端口，从而可以验证 AS2 传输。  
  
        2.  选择**请求 MDN**复选框。  
  
        3.  请确保**请求经过签名的 MDN**清除复选框。  
  
        4.  将保留**请求异步 MDN**清除。  
  
        5.  在中**处置-到通知**，输入任何值。 在 AS2 处理期间，不会使用该字段的值，但该字段中必须输入值。  
  
    3.  上**发送端口**页上，将会将 EDI 交换发送到 Fabrikam 的双向发送端口相关联。 在中**发送端口**网格下**名称**列中，单击空单元格，并从下拉列表中，选择发送端口**SendISAToFab_RecMDN**。  
  
7.  在执行以下任务**Fabrikam-> Contoso**选项卡。  
  
    > [!NOTE]
    >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**AS2_From**并**AS2-到**。  
  
    1.  上**标识符**页上，输入值**AS2-从**并**AS2-到**。 有关**AS2-从**，输入`Fabrikam`。 有关**AS2-To**，输入`Contoso`。  
  
8.  单击 **“应用”**。  
  
9. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  
  
##### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1. 在 Windows 资源管理器中，转到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员教程。 复制**SamplePO.txt**文件。  
  
2. 粘贴**SamplePO.txt**文件到您创建的用于从 Contoso 接收测试消息的本地文件夹。  
  
3. 转到您创建的用于接收 EDI 负载的本地文件夹。 确认文件夹中含有一个 EDI 文件。 打开该文件和原始测试消息，验证它们的内容是否相同。  
  
4. 转到您创建的用于接收生成的 MDN 的本地文件夹。 确认文件夹中含有一个文件；打开该文件并确认它是一个 MDN 文件。  
  
## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)