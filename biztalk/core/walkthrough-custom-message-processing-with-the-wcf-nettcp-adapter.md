---
title: 演练： 自定义消息处理与 WCF NetTcp 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56b7492-2ea0-4c63-8f1b-430eb277517d
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f765e1e99363440d6c122f5e5f174ea50dd761
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826341"
---
# <a name="walkthrough-custom-message-processing-with-the-wcf-nettcp-adapter"></a>演练： 使用 Wcf-nettcp 适配器处理的自定义消息
在本演练中，[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 客户端将使用 WCF-NetTcp 适配器将包含嵌入的二进制 JPEG 图像数据的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息提交到 BizTalk 接收位置。 通过使用 XPath 语句 （带有 Base64 节点编码） 来提取的二进制编码的 JPEG 图像**入站消息正文**中适配器的配置设置。 XPath 处理方法与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用于处理传入消息的默认方法不同。 在默认方法中，适配器将获取的全部内容**正文**元素的[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息，然后将其提交到 BizTalk MessageBox 数据库。 XPath 消息处理提取传入 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息的特定部分以创建自定义 BizTalk 消息。 在此示例中，XPath 处理查找名为的 XML 元素**SendPicture**在传入[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息 （这是以 XML 格式）。 找到该元素之后，XPath 会提取该元素的值作为二进制 Base64 编码对象，并将该二进制值放在 BizTalk 消息中。 该消息会被发布到 MessageBox 数据库，然后借助发送端口筛选器订阅输出到 FILE 发送端口。 本示例中未使用任何业务流程，并且所有的处理都使用 XPath 通过 BizTalk 消息完成。  

 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器用于与 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 中的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 远程服务进行通信。  允许业务流程和架构发布为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务，同时为业务流程提供使用外部 WCF 服务的能力。 Wcf-nettcp 适配器将使用**NetTcpBinding**绑定，这意味着 TCP 传输使用优化的二进制消息编码。 WCF-NetTcp 适配器由一个发送适配器和一个接收适配器组成。 它提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。  

 在完成本演练后，你将了解如何执行以下任务：  

- 通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，导入 MSI 文件以创建发送端口、接收端口和接收位置。  

- 通过使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，配置[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]接收位置以运行 XPath 语句要从中提取数据**SendPicture**元素的[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息。  

> [!NOTE]
>  **Hosttrusted**元素指定与接收处理程序相关联的主机是否受信任。 在 bindings.xml 文件中，将该元素设置为其默认值 `false`，因为在本示例中，我们不关心 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 企业单一登录服务 (SSO)。 SSO 允许通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 传递用户凭据，将第三方应用程序与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 相集成。 `false` 设置会阻止 BizTalk 消息作为 SSO 处理的一部分通过 BizTalk 服务。  

## <a name="prerequisites"></a>必要条件  
 要执行此示例中的步骤，请确保您的环境安装了以下必备组件；  

- 运行本示例的计算机和生成程序集和运行部署过程的计算机需要 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，与 Microsoft BizTalk Server。  

- 用于构建程序集和运行部署过程的计算机需要安装 Microsoft Visual Studio。  

- 运行示例的计算机需要 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理工具。 这些是用于安装 Microsoft BizTalk Server 安装过程的选项。  

- 在用于执行管理任务的计算机上，你必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的用户帐户运行，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序设置。 此用户帐户还必须是本地管理员组的成员，才能部署应用程序，管理主机实例以及其他可能需要的任务。  

- 需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]在示例[ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510)。  

- 在运行示例并将 .msi 文件导入到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上，确保主机不是受信任的主机，否则导入将失败。  

- 你必须下载演练代码并将其解压缩到您的计算机。  本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 您可以下载文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心， [ http://go.microsoft.com/fwlink/?LinkId=194140 ](http://go.microsoft.com/fwlink/?LinkId=194140)。  

### <a name="configure-the-wcfcustommessageprocessing-application-and-artifacts"></a>配置 WCFCustomMessageProcessing 应用程序和项目  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**应用程序**，选择**导入**，然后选择**MSI 文件**。 转到**C:\WCFCustomMessageProcessing\WCFCustomMessageProcessing.msi**文件，，然后单击**打开**。 这会创建此应用程序的以下项目：  

   - **FileSP**发送端口： 上的本地文件系统位置**C:\WCFCustomMessageProcessing\Out**发送 JPEG 图像数据其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为示例处理的最终输出。 您可以查看发送端口筛选器的**BTS。ReceivePortName = NetTcpRP**中配置**FileSP 属性**对话框中的下**筛选器**。 该筛选器与 NetTcp 接收端口相关联。 任何消息的对 nettcprp 接收端口将发送到 FileSP 发送端口输出位置**C:\WCFCustomMessageProcessing\Out**接收位置执行 XPath 处理消息之后。  

   - **NetTcpRP**接收端口： 在逻辑上包含的端口**NetTcpRL**接收位置。  

   - **NetTcpRL**接收位置： 这将使用默认值**PassThroughTransmit**管道和 Wcf-nettcp 适配器运行 XPath 语句将 jpeg 图像数据从传入[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息。  

### <a name="alternative-steps-to-configure-the-wcfcustommessageprocessing-application"></a>配置 WCFCustomMessageProcessing 应用程序的备用步骤  

- 或者，以下是配置应用程序而无需使用的手动步骤**C:\WCFCustomMessageProcessing\bindings.xml**文件。 如果前面的绑定文件导入过程工作正常，则您不需要执行此操作。  但是阅读这些信息可能会增加您对 MSI 文件所发生变化的了解。  

- 创建一个单向接收端口 (**NetTcpRP**) 和接收位置 (**NetTcpRL**)。  

  1. 展开**WCFCustomMessageProcessing**应用程序中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**. 在中**接收端口属性**对话框框中，输入`NetTcpRP`有关**名称**，然后单击**确定**。  

  2. 右键单击**NetTcpRP**接收端口中，选择**新建**，然后选择**接收位置**。 在中**接收位置属性**对话框框中，输入`NetTcRL`有关**名称**。 在中**传输**部分中，单击**类型**下拉列表框中，选择**WCF NetTcp**从下拉列表中，然后单击**配置**.  

  3. 上**常规**选项卡上，输入**net.tcp: //localhost/nettcprl/image**中**地址 （uri)** 字段。  

  4. 上**安全**选项卡上，设置**安全模式**到**None。**  

  5. 上**消息**选项卡上，选择**路径**选项**入站 BizTalk 消息正文**，然后输入`/*[local-name()="SendPicture" and namespace-uri()='http://tempuri.org/']/*[local-name()="stream"]`正文路径表达式。 选择**Base64**作为**节点编码**。 **路径**选项设置为值，因为正文[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收采用以下格式：  **\<SendPicture xmlns ="http://tempuri.org/"\>\<流\>*实际 base64 编码的二进制图像数据*\</流式传输\>\</SendPicture\>**  

  6. 在中**接收位置属性**对话框中，单击**确定**。  

- 创建订阅 NetTcpRP 接收端口的单向文件发送端口 (FileSP)。  

  1.  右键单击**发送端口**，选择**新建**，然后选择**单向接收端口**。 选择**静态单向端口**。 输入`FileSP`有关**名称**。  

  2.  在中**传输**部分中，单击**类型**下拉列表框中，选择**文件**从下拉列表中，然后单击**配置**。  

  3.  下**目标文件夹**输入`C:\WCFCustomMessageProcessing\Out`，然后单击**确定**。  

  4.  单击**筛选器**，选择`BTS.ReceivePortName == NetTcpRP`，然后单击**确定。**  

### <a name="configure-the-send-port-and-run-the-application"></a>配置发送端口和运行应用程序  

1. 右键单击**WCFCustomMessageProcessing**应用程序并选择**启动**。 该操作会登记 NetTcpRL 接收位置并启动 FileSP 发送端口。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，请打开`Client.sln`文件从**C:WCFCustomMessageProcessing\Client**文件夹。 在解决方案资源管理器中右键单击**客户端**项目，然后选择**生成**。  

3. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**调试**，然后选择**启动但不调试**运行 Client.exe 应用程序。 将显示命令提示符，说明图像已提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

4. 观察到的发送端口文件文件夹成功 {GUID}.jpg 文件输出**C:\WCFCustomMessageProcessing\Out**。这里显示应用程序处理成功完成提取 JPEG 文件并将其写入到 FILE 发送端口。
