---
title: 演练： 创建 BizTalk 应用程序使用 POP3 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3bd79682f78591b066fe1e6db671c3dab4a8333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985302"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a>演练： 创建使用 POP3 适配器的 BizTalk 应用程序
本部分将指导您创建一个使用 POP3 适配器的简单 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。  
  
> [!NOTE]
>  该应用程序假设您有权限访问安装并配置了电子邮件服务的 Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 运行所在的计算机。 有关配置具有电子邮件服务的 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的信息，请参阅 Windows Server 帮助。  
> 
> [!NOTE]
>  在本示例中，Microsoft Outlook Express 用作电子邮件客户端，[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 用作电子邮件服务器。 不过，任何 POP3 电子邮件客户端和符合 RFC 的 POP3 服务器均可用于此方案。  
  
 此应用程序假设您尚未创建任何发送端口或接收位置。 如果已存在发送端口或接收位置，请在执行以下步骤时替换相应的名称。  
  
 该应用程序是一个简单的基于内容的路由应用程序，仅使用一个接收位置和一个发送端口。 接收位置从运行的服务器上的邮箱中读取[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)。 发送端口从该接收位置获取消息，并将其发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 本地文件系统的文件夹中。  
  
 若要创建该应用程序，您必须执行以下操作：创建邮箱、设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置和发送端口、启动发送端口并启用接收位置，以及向邮箱发送测试邮件。 请遵循以下步骤来创建应用程序。  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a>在 Windows Server 2003 上创建邮箱  
 若要在安装了电子邮件服务的 Windows Server 2003 上创建邮箱，请执行以下步骤：  
  
1. 单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**POP3 服务**。  
  
2. 展开*\<servername\>* 单击你想要创建邮箱的域。  
  
3. 在中**POP3 服务**对话框中，在右窗格中，单击**添加邮箱**选项。  
  
4. 在中**添加邮箱**对话框中**邮箱名称**框中，键入**EmailTest**。  
  
5. 选择**创建相关的用户提供此邮箱**复选框。  
  
6. 在中**密码**并**确认密码**框中，键入一个密码，然后单击**确定**。  
  
7. 请记下的**帐户名称**并**邮件服务器**登录信息显示的用于明文形式中的身份验证**POP3 服务**对话框中，然后单击**确定**。 为 POP3 传输类型配置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置将使用此信息。  
  
## <a name="create-the-receive-location"></a>创建接收位置  
 请遵循以下步骤创建接收位置：  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中双击默认数据库**\<** <em>m a c h</em>**\>。BizTalkMgmtDb.dbo**，其中*m a c h*是您的计算机的名称。 单击**应用程序**，然后单击**BizTalk.Application.1**。  
  
2. 右键单击**接收端口**，单击**新建**，单击**单向接收端口**。  
  
3. 在中**接收端口属性**对话框中**名称**框中，键入**POP3Receive**。  
  
4. 单击**接收位置**，然后单击**新建**。  在中**接收位置属性**对话框中**名称**框中，键入**POP3Receive**。  
  
5. 在中**传输类型**框中，选择**POP3**。  
  
6. 在中**接收处理程序**框中，选择**BizTalkServerApplication**。  
  
7. 在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。  
  
8. 在中**传输**框中，单击**配置**按钮。  
  
9. 在中**POP3 传输属性**对话框中**应用 MIME 解码**框中，选择**False**。  
  
10. 在中**邮件服务器**框中，键入创建邮箱的基于 Windows Server 的服务器的名称。  
  
11. 在中**身份验证方案**框中，选择**基本**。  
  
12. 在中**密码**框中，单击下拉箭头，然后键入该邮箱的密码。  
  
13. 在中**用户名**框中，键入该邮箱的完全限定的用户名，例如 <em>username@host.domain.toplevel_domain。</em>  
  
14. 在中**轮询间隔**框中，键入**1**，单击**确定**，然后单击**确定**试。  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a>在 BizTalk Server 上创建发送端口和目标文件夹  
 请遵循以下步骤在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上创建发送端口和目标文件夹：  
  
1. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文件系统上创建一个文件夹。 它将成为发送端口的目标文件夹。  
  
2. 右键单击**发送端口**，单击**新建，** 然后单击**静态单向发送端口。**  
  
3. 在中**发送端口属性**对话框中**传输类型**框中，选择**文件**。  
  
4. 在中**名称**框中，键入**SendToFile**。  
  
5. 在中**传输**框中，单击**配置**按钮。  
  
6. 下一步**目标文件夹**框中，单击**浏览**，选择创建的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**确定**。  
  
7. 在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。  
  
8. 在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
9. 单击 **“筛选器”**。  
  
10. 在中**属性**框中，选择**BTS。ReceivePortName**。  
  
11. 在中**值**框中，键入**POP3Receive**，然后单击**确定**。  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a>启用接收位置并启动发送端口  
 请遵循以下步骤来启用接收位置和启动发送端口：  
  
1. 右键单击**POP3Receive**接收位置，然后依次**启用**。  
  
2. 右键单击**SendToFile**发送端口，然后依次**启动**。  
  
   下一步就是通过向接收位置监视的邮箱发送测试邮件来测试该应用程序。  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a>配置 Outlook Express 以便向邮箱发送电子邮件  
 请遵循以下步骤来配置 Outlook Express 向邮箱发送一封电子邮件：  
  
1.  单击**启动**，依次指向**程序**，然后单击**Outlook Express**。  
  
2.  在 Outlook Express 中，在**工具**菜单上，单击**帐户**。  
  
3.  单击**外**，然后单击**邮件**。  
  
4.  在中**显示名称**框中，键入显示名称，然后单击**下一步**。  
  
5.  在中**Internet 电子邮件地址**对话框中**电子邮件地址**框中，键入**EmailTest @< 域名 >**，然后单击**下一步**.  
  
     请务必输入适当的值 *< 域名 >*。 此值应与在 Windows 服务器上 POP3 服务管理用户界面中创建此邮箱使用的域名匹配。  
  
6.  在中**电子邮件服务器名称**对话框中**传入邮件**并**传出邮件**框中，键入服务器名称或 IP 地址的 Windows 服务器，然后单击**下一步**。  
  
7.  在中**Internet 邮件登录**对话框中**帐户名称**框中，键入**EmailTest**。  
  
8.  在中**密码**框中，键入 EmailTest 帐户，请选择的密码**记住密码**选项，单击**下一步**，然后单击**完成**.  
  
9. 单击以选择刚创建的帐户，然后单击**属性**。  
  
10. 在**属性**对话框中，单击**高级**选项卡中，单击以选择选项**保留消息的副本服务器上**，然后单击**确定**.  
  
11. 在中**Internet 帐户**对话框中，单击**关闭**。  
  
12. 使用 Outlook Express 撰写测试消息，类型**测试**成**主题**字段中，然后键入**EmailTest @< 域名 >** 到**到**字段。  
  
13. 单击**发送**发送测试消息。 若要确保，Outlook Express 立即发送测试消息，请单击**发送/接收**Outlook Express 工具栏中的按钮。  
  
## <a name="view-the-message"></a>查看邮件  
 请遵循以下步骤查看消息：  
  
1.  使用 Windows 资源管理器中打开指定为的文件夹**目标文件夹**发送端口。  
  
2.  双击该文件夹中的文档，以便用记事本查看该文档的内容。  
  
## <a name="see-also"></a>请参阅  
 [POP3 适配器概述](../core/what-is-the-pop3-adapter.md)