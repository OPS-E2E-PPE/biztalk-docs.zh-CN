---
title: "演练： 使用 WCF NetTcp 适配器使用消息安全模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7f6e892-34ce-4132-8867-54cc3bbfe507
caps.latest.revision: "47"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850d0ee715984c7465063addd778828c727e0233
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="walkthrough-using-the-message-security-mode-with-the-wcf-nettcp-adapter"></a>演练： 使用 WCF NetTcp 适配器使用消息安全模式
  
> [!NOTE]
>  有关适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
## <a name="introduction"></a>简介
  
 本演练显示如何配置 WCF-NetTcp 适配器以使用 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 消息安全模式，该模式使用 WS-Security 规范来帮助保护适配器传输的消息。 此规范描述 SOAP 邮件协议的增强功能，以实现机密性、完整性，以及在 SOAP 消息级别进行身份验证。 消息安全模式需要指定服务证书才能进行加密/解密和签名/验证等操作，具体取决于安全模式组合。  
  
 WCF-NetTcp 适配器使用 NetTcpBinding 绑定在 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 远程服务之间通信。 它提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。 允许业务流程和架构发布为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务，同时为业务流程提供使用外部 WCF 服务的能力。 此适配器使用 TCP 传输，消息采用二进制编码。 WCF-NetTcp 适配器由一个发送适配器和一个接收适配器组成。  
  
 本演练显示如何使用 Active Directory 证书服务为消息安全模式创建证书。 您将为服务器和客户端创建证书，然后配置 WCF-NetTcp 接收位置以在消息安全模式下使用证书。 通过使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端，您将按照 XML 加密语法和处理将消息发送到处于已加密状态的该接收位置。  
  
 在完成本演练后，你将了解如何执行以下任务：  
  
-   使用 Active Directory 证书服务创建证书申请，并通过颁发证书完成该过程。  
  
-   从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，配置 WCF NetTcp 适配器以使用消息安全模式。  
  
## <a name="prerequisites"></a>先决条件  
 要执行此示例中的步骤，请确保您的环境安装了以下必备组件；  
  
-   生成程序集并运行在部署过程的计算机和运行此示例中，计算机需要 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，和 Microsoft BizTalk Server。  
  
-   用于构建程序集和运行部署过程的计算机需要安装 Microsoft Visual Studio。  
  
-   运行示例的计算机需要 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理工具。 这些是用于安装 Microsoft BizTalk 服务器安装过程的选项。  
  
-   在用于执行管理任务的计算机上，你必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的用户帐户运行，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序设置。 此用户帐户还必须是本地管理员组的成员，才能部署应用程序，管理主机实例以及其他可能需要的任务。  
  
-   需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]示例在[http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)。  
  
-   在运行示例并将绑定或 .msi 文件导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上，确保主机不是受信任主机，否则导入将失败。  
  
-   在运行示例的计算机上确保已安装 Active Directory 证书服务。  
  
-   你必须下载演练代码并将其解压缩到你的计算机。  本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 你可以下载该文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心， [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)。  
  
## <a name="create-the-certificates-for-this-walkthrough"></a>创建在本演练中的证书  
  
1.  在本部分中，您将请求服务和客户端证书，颁发这些证书，并将其安装到适当的存储中。 Active Directory 证书服务用于创建具有受信任证书链的证书。 如果没有将 Active Directory 证书服务作为必备组件的一部分安装，则在计算机上安装 Active Directory 证书服务。 如果已安装，则转到步骤 2。  
  
    1.  单击**启动**，指向**管理工具**，然后单击**服务器管理器**。  
  
    2.  下**服务器管理器**节点，单击**添加**，然后单击**角色**。  
  
    3.  这将显示**在开始之前**对话框**添加角色向导**。 单击 **“下一步”**。  
  
    4.  上**选择服务器角色**页上，选择**Active Directory 证书服务**，单击**下一步**，然后按照屏幕说明完成安装。  
  
2.  创建服务验证的证书申请，如下所示：  
  
    1.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。 上**欢迎**页上，单击**请求证书**，然后单击**高级的证书申请**上**请求证书**页。  
  
        > [!NOTE]
        >  使用时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]以及证书颁发机构请求证书请求从[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机，你可能会收到错误**"若要完成证书注册，ca 必须将网站配置为使用 HTTPS身份验证"**。 如果发生此错误，注册网站需要配置使用 Web 证书 (SSL)。 有关完成此任务的详细信息，请参阅以下链接：  
        >   
        >  [AD CS: Web 注册](http://technet.microsoft.com/library/cc732517.aspx)  
        >   
        >  [IIS 服务器证书安装说明](http://msdn.microsoft.com/library/ms751408.aspx)  
  
    2.  上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。  
  
    3.  上**高级证书申请**页上，键入`localhost`中**名称**文本框中，选择**服务器身份验证证书**从**需要的证书类型**下拉列表，然后单击**提交**。  
  
3.  创建客户端验证的证书申请，如下所示：  
  
    1.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。 上**欢迎**页上，单击**请求证书**，然后单击**高级的证书申请**上**请求证书**页。  
  
    2.  上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。  
  
    3.  上**高级证书申请**页上，键入`contoso`中**名称**文本框中，选择**客户端身份验证证书**从**需要的证书类型**下拉列表，然后单击**提交**。  
  
    > [!NOTE]
    >  如果你正在计算机域控制器以外的计算机上运行 BizTalk Server，则使用客户端身份验证证书。 这将在适配器的属性对话框中进行配置。  
  
4.  使用证书颁发机构管理控制台颁发证书，如下所示：  
  
    1.  单击**启动**，指向**管理工具**，然后单击**证书颁发机构**。  
  
    2.  在**证书颁发机构**管理控制台中，展开证书颁发机构的名称，然后双击**挂起的请求**。  
  
    3.  在右窗格中**证书颁发机构**管理控制台中，右键单击服务身份验证证书的请求，指向**所有任务**，然后单击**问题**.  
  
    4.  在右窗格中**证书颁发机构**管理控制台中，右键单击客户端身份验证证书的申请，指向**所有任务**，然后单击**问题**.  
  
    5.  关闭**证书颁发机构**管理控制台。  
  
5.  在您的计算机上安装颁发的证书，如下所示：  
  
    1.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。  
  
    2.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  
  
    3.  上**查看挂起的证书申请的状态**页上，单击服务器身份验证证书。  
  
    4.  上**颁发证书**页上，单击**安装此证书**。  
  
    5.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。  
  
    6.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  
  
    7.  上**查看挂起的证书申请的状态**页上，单击客户端身份验证证书。  
  
    8.  上**颁发证书**页上，单击**安装此证书**。  
  
6.  按如下方式确保已正确安装颁发的证书：  
  
    1.  打开 Microsoft 管理控制台 (MMC)。 若要执行此操作，请单击**启动**，单击**运行**，类型`mmc`，然后单击**确定**。  
  
    2.  在 MMC 中，在**文件**菜单上，单击**添加/删除管理单元中**。  
  
    3.  在“添加/删除管理单元”对话框中，单击“添加”。  
  
    4.  在**添加独立管理单元中**对话框中，选择**证书**从**可用的独立管理单元中**列表，，然后单击**添加**.  
  
    5.  在**证书管理单元中**对话框中，选择**我的用户帐户**选项，并依次**完成**。  
  
    6.  关闭所有打开的对话框。  
  
    7.  在 MMC 中，在控制台根节点窗口中，展开**证书-当前用户**，展开**个人**，展开**证书**，那么请确保和证书你安装上一步中显示。  
  
## <a name="create-the-biztalk-application-for-this-walkthrough"></a>创建 BizTalk 应用程序对于本演练  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，右键单击**应用程序**，指向**新建**，然后单击**应用程序**.  
  
3.  在**应用程序属性**对话框中，在**常规**选项卡上，键入`WcfMessageSecurity`，然后单击**确定**。  
  
4.  为 BizTalk 应用程序创建使用 WCF-NetTcp 适配器的接收位置，如下所示：  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WcfMessageSecurity**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
    2.  在**接收端口属性**对话框中，在**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Receive`，然后单击**确定**。 此接收端口的名称是任意的，但此名称具有逻辑意义。  
  
    3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端将向此接收位置发送一条 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息。 选择**WcfMessageSecurity.OrderRequest.Receive**接收端口，然后单击**确定**。  
  
    4.  在**接收位置属性**对话框中，在**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Receive.NetTcp`。 此接收位置的名称是任意的，但此名称具有逻辑意义。  
  
    5.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**WCF NetTcp**从下拉列表列表，，然后单击**配置**。  
  
    6.  在**Wcf-nettcp 传输属性**对话框中，在**常规**选项卡上，在**地址 (URI)**文本框中，键入`net.tcp://localhost/WcfMessageSecurity`。  
  
    7.  在**Wcf-nettcp 传输属性**对话框中，在**安全**选项卡上，选择**消息**从**安全模式**下拉列表列表，然后再选择**证书**从**消息客户端凭据类型**下拉列表。 将配置 WCF-NetTcp 适配器以使用消息安全模式。  
  
    8.  配置服务证书以在消息安全模式下使用。 在**Wcf-nettcp 传输属性**对话框中，在**服务证书颁发**部分中，单击**浏览**。 在**选择的服务证书**对话框中，选择您在前一过程中，安装的服务器身份验证证书，然后单击**确定**关闭对话框并保存所做的更改。  
  
    9. 关闭所有打开的对话框。  
  
        > [!NOTE]
        >  若要向 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 接收适配器验证客户端证书，必须将客户端证书的 CA 证书链安装到运行 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器的主机实例的计算机的“受信任根证书颁发机构”证书存储中。 由于本演练假设证书服务和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端以及 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器安装在同一计算机上，因此，您无需在您的计算机上安装 CA 证书链。  
  
5.  为 BizTalk 应用程序创建 FILE 发送端口。 此位置是代表 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的业务流程将发送订单请求输出消息的位置。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WcfMessageSecurity**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**  
  
    2.  在**发送端口属性**对话框中，在**常规**选项卡上，在**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Send.FILE`。  
  
    3.  在**发送端口属性**对话框中，在**传输**旁边部分**类型**，选择**文件**从下拉列表中，然后单击**配置**。  
  
    4.  在**文件传输属性**对话框中，在**常规**选项卡上，键入`C:\WCFMessageSecurity\OrderRequestOut`中**目标文件夹**文本中，然后单击**确定**.  
  
    5.  在**发送端口属性**对话框中，在**筛选器**选项卡上，选择**BTS。ReceivePortName**为**属性**字段中，输入`WcfMessageSecurity.OrderRequest.Receive`为**值**字段，然后再单击**确定**。 此筛选器表达式将路由传入[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息从客户端进入**WcfMessageSecurity.OrderRequest.Receive**接收到此发送端口的端口。  
  
## <a name="test-the-wcf-client-against-the-biztalk-application"></a>测试 WCF 客户端针对 BizTalk 应用程序  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WcfMessageSecurity**，然后单击**启动**。 在**启动**对话框中，单击**启动**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**或另一个适当的主机实例，然后单击**重新启动**。  
  
3.  创建名为的文件夹**C:\WCFMessageSecurity**本演练的工作文件夹。 将演练文件解压缩到此文件夹。  
  
4.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**WcfMessageSecurity.sln**文件中**C:\WCFMessageSecurity**文件夹。  
  
5.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**WcfClient**，然后打开**Program.cs**查看。  
  
    -   客户端将消息发送到您在前面过程中创建的 WCF-NetTcp 接收位置。  
  
    -   客户端创建的通道**NetTcpBinding**，然后配置要使用证书进行客户端凭据类型的绑定。  
  
    -   客户端配置终结点行为，以便使用在前面过程中安装的客户端验证证书，从而进行客户端验证。  
  
    -   类，**程序**，实现**IClientMessageInspector**和**IEndpointBehavior**接口，以便显示传出[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]从此消息在命令提示符下的客户端。  
  
6.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击**WcfMessageSecurity**解决方案，然后再单击**重新生成**。  
  
7.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**调试**菜单上，单击**启动但不调试**运行 WcfClient 发送到 WCF NetTcp 消息接收位置。 此时将出现一个命令提示符窗口，显示执行结果。  
  
    1.  在命令提示符下，查看订单请求消息。 请注意**OrderId**字段和消息的结构。  
  
    2.  在命令提示符下，请转到`C:\WCFMessageSecurity\OrderRequestOut`文件夹，并确保发送的订单请求消息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端将出现。  
  
    3.  关闭命令提示符。