---
title: 演练：使用 Wcf-nettcp 适配器使用消息安全模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f6e892-34ce-4132-8867-54cc3bbfe507
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52936b6110e5e04610e1a215103b558dcbe4c1e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399439"
---
# <a name="walkthrough-using-the-message-security-mode-with-the-wcf-nettcp-adapter"></a>演练：使用 Wcf-nettcp 适配器使用消息安全模式

> [!NOTE]
>  有关适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  

## <a name="introduction"></a>简介

 本演练演示如何配置 WCF NetTcp 适配器以使用[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]消息安全模式，它使用 Ws-security 规范来保护适配器传输的消息。 本规范描述 SOAP 邮件协议实现保密性、 完整性和 SOAP 消息级别的身份验证的增强功能。 消息安全模式需要为操作，如加密/解密和签名/验证，具体取决于安全模式组合指定将服务证书。  

 Wcf-nettcp 适配器使用 NetTcpBinding 绑定之间进行通信[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]远程服务。 它提供了 SOAP 安全性、 可靠性和事务功能的完全访问权限。 它允许业务流程和架构发布为[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务，并且还提供用于使用外部 WCF 服务的业务流程的功能。 此适配器使用 TCP 传输和消息采用二进制编码。 Wcf-nettcp 适配器由发送适配器和接收适配器组成。  

 本演练演示如何使用 Active Directory 证书服务创建消息安全模式的证书。 将创建证书服务器和客户端，并配置的 Wcf-nettcp 接收位置，以便在消息安全模式下使用的证书。 通过使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端，将发送到的接收位置的消息按照 XML 加密语法和处理以加密状态。  

 完成此演练后，你将了解如何执行以下任务：  

- 使用 Active Directory 证书服务创建证书申请并颁发证书完成该过程。  

- 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，配置 WCF NetTcp 适配器以使用消息安全模式。  

## <a name="prerequisites"></a>先决条件  
 若要执行此示例中的步骤，请确保你的环境安装以下必备组件;  

- 运行本示例的计算机和生成程序集和运行部署过程的计算机需要 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，与 Microsoft BizTalk Server。  

- 用于生成程序集和运行部署过程的计算机需要 Microsoft Visual Studio。  

- 运行示例的计算机需要[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]管理工具。 这些是用于安装 Microsoft BizTalk Server 安装过程的选项。  

- 在计算机上用于执行管理任务，您必须运行的成员的用户帐户作为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组以配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内的应用程序设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 此用户帐户还必须是管理主机实例和其他任务所需的应用程序部署的本地管理员组的成员。  

- 需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在示例[ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510)。  

- 运行示例并将一个绑定或到某一.msi 文件导入的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保主机不受信任的主机或导入将失败。  

- 运行示例的计算机上确保已安装 Active Directory 证书服务。  

- 你必须下载演练代码并将其解压缩到您的计算机。  本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 您可以下载文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心， [ http://go.microsoft.com/fwlink/?LinkId=194140 ](http://go.microsoft.com/fwlink/?LinkId=194140)。  

## <a name="create-the-certificates-for-this-walkthrough"></a>为本演练创建证书  

1. 在本部分中将请求服务和客户端证书，颁发证书，并将它们安装到适当的存储区。 Active Directory 证书服务用于创建使用受信任的证书链的证书。 如果您未安装 Active Directory 证书服务作为必备组件的一部分，然后在计算机上安装 Active Directory 证书服务。 如果已安装，请转到步骤 2。  

   1.  单击**启动**，依次指向**管理工具**，然后单击**服务器管理器**。  

   2.  下**服务器管理器**节点中，单击**添加**，然后单击**角色**。  

   3.  这将显示**在开始之前**对话框**添加角色向导**。 单击“下一步” 。  

   4.  上**选择服务器角色**页上，选择**Active Directory 证书服务**，单击**下一步**，然后按照屏幕说明完成安装。  

2. 创建进行服务身份验证证书申请，如下所示：  

   1. 在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。 上**欢迎**页上，单击**申请一个证书**，然后单击**高级的证书申请**上**申请一个证书**页。  

      > [!NOTE]
      >  使用时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]作为证书颁发机构并请求从一个证书申请[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机，可能会收到错误 **"若要完成证书注册，CA 的网站必须将配置为使用 HTTPS身份验证"**。 如果发生此错误，注册网站需要使用 Web 证书 (SSL) 进行配置。 请参阅下面的链接中完成此任务的详细信息：  
      > 
      >  [AD CS:Web 注册](http://technet.microsoft.com/library/cc732517.aspx)  
      > 
      >  [IIS 服务器证书安装说明](http://msdn.microsoft.com/library/ms751408.aspx)  

   2. 上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。  

   3. 上**高级证书申请**页上，键入`localhost`中**名称**文本框中，选择**服务器身份验证证书**从**需要的证书类型**下拉列表，再单击**提交**。  

3. 创建客户端身份验证的证书申请，如下所示：  

   1.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。 上**欢迎**页上，单击**申请一个证书**，然后单击**高级的证书申请**上**申请一个证书**页。  

   2.  上**高级证书申请**页上，单击**创建并向此 CA 提交一个申请**。  

   3.  上**高级证书申请**页上，键入`contoso`中**名称**文本框中，选择**客户端身份验证证书**从**需要的证书类型**下拉列表，再单击**提交**。  

   > [!NOTE]
   >  如果在域控制器以外的计算机上运行 BizTalk Server，则使用客户端身份验证证书。 这将在适配器的属性对话框中配置。  

4. 按以下方式使用证书颁发机构管理控制台颁发的证书：  

   1.  单击**启动**，依次指向**管理工具**，然后单击**证书颁发机构**。  

   2.  在中**证书颁发机构**管理控制台中，展开证书颁发机构的名称，然后双击**挂起的申请**。  

   3.  在右窗格中**证书颁发机构**管理控制台中，右键单击服务身份验证证书的申请，指向**的所有任务**，然后单击**问题**.  

   4.  在右窗格中**证书颁发机构**管理控制台中，右键单击客户端身份验证证书的申请，指向**的所有任务**，然后单击**问题**.  

   5.  关闭**证书颁发机构**管理控制台。  

5. 在计算机上安装颁发的证书，如下所示：  

   1.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。  

   2.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  

   3.  上**查看挂起的证书申请的状态**页上，单击服务器身份验证证书。  

   4.  上**证书颁发**页上，单击**安装此证书**。  

   5.  在 Internet Explorer 中，请访问网站`http://localhost/certsrv`。  

   6.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  

   7.  上**查看挂起的证书申请的状态**页上，单击客户端身份验证证书。  

   8.  上**证书颁发**页上，单击**安装此证书**。  

6. 请确保颁发的证书安装正确，如下所示：  

   1.  打开 Microsoft 管理控制台 (MMC)。 若要执行此操作，请单击**启动**，单击**运行**，类型`mmc`，然后单击**确定**。  

   2.  在 MMC 中，在**文件**菜单上，单击**添加/删除管理单元中**。  

   3.  在“添加/删除管理单元”对话框中，单击“添加”。  

   4.  在中**添加独立管理单元**对话框中，选择**证书**从**可用的独立管理单元中**列表，并单击**添加**.  

   5.  在中**管理单元中的证书**对话框中，选择**我的用户帐户**选项，并单击**完成**。  

   6.  关闭所有打开的对话框。  

   7.  在 MMC 中，在控制台根目录窗口中，展开**证书-当前用户**，展开**个人**，展开**证书**，并请务必证书，安装在上一步中显示。  

## <a name="create-the-biztalk-application-for-this-walkthrough"></a>创建在本演练中的 BizTalk 应用程序  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，右键单击**应用程序**，指向**新建**，然后单击**应用程序**.  

3. 在中**应用程序属性**对话框中，在**常规**选项卡上，键入`WcfMessageSecurity`，然后单击**确定**。  

4. 创建 BizTalk 应用程序，如下所示使用 Wcf-nettcp 适配器的接收位置：  

   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WcfMessageSecurity**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  

   2. 在中**接收端口属性**对话框中**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Receive`，然后单击**确定**。 此名称的接收端口是任意，但此名称具有逻辑意义。  

   3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端将发送[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息与此接收位置。 选择**WcfMessageSecurity.OrderRequest.Receive**接收端口，并单击**确定**。  

   4. 在中**接收位置属性**对话框中**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Receive.NetTcp`。 此名称的接收位置是任意，但此名称具有逻辑意义。  

   5. 在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**WCF NetTcp**从下拉列表列表中，然后依次**配置**。  

   6. 在中**Wcf-nettcp 传输属性**对话框中，在**常规**选项卡上，在**地址 (URI)** 文本框中，键入`net.tcp://localhost/WcfMessageSecurity`。  

   7. 在中**Wcf-nettcp 传输属性**对话框中，在**安全**选项卡上，选择**消息**从**安全模式**下拉列表列表，并选择**证书**从**消息客户端凭据类型**下拉列表。 这会配置 WCF NetTcp 适配器以使用消息安全模式。  

   8. 配置要使用消息安全模式下的服务证书。 在中**Wcf-nettcp 传输属性**对话框中**服务认证**部分中，单击**浏览**。 在中**选择服务证书**对话框中，选择在上一过程中，安装的服务器身份验证证书，然后单击**确定**关闭对话框并保存所做的更改。  

   9. 关闭所有打开的对话框。  

      > [!NOTE]
      >  客户端证书进行身份验证[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]接收适配器，客户端证书的 CA 证书链必须安装在运行主机实例的计算机的受信任的根证书颁发机构证书存储有关[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器。 因为本演练假定为在同一台计算机上是否安装了证书服务[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端和[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器，您无需在计算机上安装的 CA 证书链。  

5. 创建 FILE 发送端口的 BizTalk 应用程序。 这是通过业务流程表示发送订单请求输出消息的位置[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  

   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WcfMessageSecurity**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**  

   2. 在中**发送端口属性**对话框中，在**常规**选项卡上，在**名称**文本框中，键入`WcfMessageSecurity.OrderRequest.Send.FILE`。  

   3. 在**发送端口属性**对话框中**传输**部分旁边**类型**，选择**文件**从下拉列表中，然后单击**配置**。  

   4. 在中**FILE 传输属性**对话框中，在**常规**选项卡上，键入`C:\WCFMessageSecurity\OrderRequestOut`中**目标文件夹**文本框中，，然后单击**确定**.  

   5. 在中**发送端口属性**对话框中，在**筛选器**选项卡上，选择**BTS。ReceivePortName**有关**属性**字段中，输入`WcfMessageSecurity.OrderRequest.Receive`有关**值**字段，，然后单击**确定**。 此筛选器表达式将路由传入[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]到客户端的消息**WcfMessageSecurity.OrderRequest.Receive**接收到此发送端口的端口。  

## <a name="test-the-wcf-client-against-the-biztalk-application"></a>测试 WCF 客户端对 BizTalk 应用程序  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WcfMessageSecurity**，然后单击**启动**。 在中**启动**对话框中，单击**启动**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**或另一个相应的主机实例，然后依次**重新启动**。  

3. 创建名为的文件夹**C:\WCFMessageSecurity**文件夹对于此演练的工作文件夹。 演练文件解压缩到此文件夹。  

4. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**WcfMessageSecurity.sln**中的文件**C:\WCFMessageSecurity**文件夹。  

5. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**WcfClient**，然后打开**Program.cs**查看。  

   - 客户端将消息发送到 Wcf-nettcp 接收位置在前面的过程中创建。  

   - 客户端创建与通道**NetTcpBinding**，然后配置要使用证书进行客户端凭据类型的绑定。  

   - 客户端配置终结点行为，以便使用客户端身份验证在上一过程中安装的客户端身份验证证书。  

   - 类中，**程序**，实现**IClientMessageInspector**并**IEndpointBehavior**接口，以便显示传出[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]从此消息在命令提示符下的客户端。  

6. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**WcfMessageSecurity**解决方案，，然后单击**重新生成**。  

7. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**调试**菜单中，单击**启动但不调试**以运行 WcfClient，从而发送消息到 Wcf-nettcp 接收位置。 在命令提示符下将出现以显示执行结果。  

   1. 在命令提示符下，查看订单请求消息。 注意**OrderId**字段和消息的结构。  

   2. 在命令提示符处，转至`C:\WCFMessageSecurity\OrderRequestOut`文件夹，然后确保订单请求消息发送的[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]客户端将出现。  

   3. 关闭命令提示符。
