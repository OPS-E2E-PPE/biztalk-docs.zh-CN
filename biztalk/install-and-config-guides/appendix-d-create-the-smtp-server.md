---
title: 附录 D：创建 SMTP 服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7441ba9-a498-42ec-a04d-7f2731407373
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41bc8cc1e86dcf125640ad9997ed4bd8e315d85f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401468"
---
# <a name="appendix-d-create-the-smtp-server"></a>附录 D：创建 SMTP 服务器
创建使用 SQL Server 数据库邮件的 SMTP 服务器。  
  
使用任何以下的 SQL 版本时配置 BAM 警报需要 SQL Server 数据库邮件： 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
  SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。 使用 Internet 信息服务 (IIS) 中包含 SMTP 服务器。 SMTP 可以本地安装 BizTalk Server 上或在另一台服务器上已安装 iis。  
  
> [!IMPORTANT]
>  通常情况下，客户端操作系统，例如 Windows 10、 Windows 7 等，不包括 SMTP 服务器功能。 可以连接到 Windows Server 使用现有的 SMTP 服务器*SMTP 电子邮件*IIS 中的功能。 *SMTP 电子邮件*功能不是 SMTP 服务器时，所需的 SQL Server Database Mail。 因此，本主题不包括安装和配置客户端操作系统上的 SMTP 服务器的步骤。  

## <a name="install-and-configure-the-smtp-server"></a>安装和配置 SMTP 服务器  
  
这些步骤适用于：

* Windows Server 2016
* Windows Server 2012 R2
* Windows Server 2012
  
### <a name="install-smtp-server"></a>安装 SMTP 服务器  
   
1.  在中**服务器管理器**，选择**仪表板**的左窗格中。  
  
3.  选择**添加角色和功能**。 **添加角色和功能**也可以从打开**管理**中右上角的菜单。  
  
4.  在中**开始之前**，选择**下一步**。  
  
5.  选择**基于角色或基于功能的安装**，然后选择**下一步**。  
  
6.  选择**从服务器池中选择服务器**，选择所需的服务器，然后选择**下一步**。 **服务器选择**窗口中列出了使用已添加的服务器**添加服务器**中**服务器管理器**。 默认情况下，它将选择本地服务器。  
  
7.  在中**服务器角色**，选择**下一步**。  
  
8.  在中**功能**，检查**SMTP 服务器**。 如果系统提示，请选择**添加功能**。 选择“**下一步**”。  
  
9. 在中**确认**，选择**如果需要自动重新启动目标服务器**，然后选择**安装**。 完成后，选择**关闭**。  

### <a name="configure-the-smtp-server"></a>配置 SMTP 服务器  
 以下步骤配置 SMTP 虚拟服务器使用 IIS 6.0 管理器：  
  
1.  打开 IIS 管理器：在入门中，搜索**inetmgr6.exe**，并将其打开。  
  
2.  展开计算机名称。 右键单击 **[SMTP 虚拟服务器 #1]**，然后选择**属性**。  
  
3.  在中**访问**选项卡上，选择**中继**按钮。  
  
4.  选择 **添加** 。 有关**台计算机**，输入`127.0.0.1`，然后选择**确定**。  
  
     通过添加 127.0.0.1，我们允许本地服务器从此 SMTP 服务器发送消息。 如果希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。  
  
5.  在中**交付**选项卡上，选择**出站安全**。 选择以下选项：  
  
     **匿名访问**:帐户名或密码不是必需的。 此选项将禁用 SMTP 服务器的身份验证。  
  
     **基本身份验证**:帐户名称和密码以明文形式发送要连接的服务器。 你输入此帐户用于传输电子邮件。 将电子邮件发送到个人帐户或 Exchange 帐户时，可以选择基本身份验证。 因为凭据将以明文形式传递，建议启用**TLS 加密**。  
  
     **集成 Windows 身份验证**:使用 Windows 域帐户名和密码进行身份验证。 你输入的帐户用于传输电子邮件。  
  
     **TLS 加密**:与 SSL 相似，TLS 用于保护安全连接。 需要有效的 SSL 服务器证书安装在此服务器上。  
  
    > [!TIP]
    >  若要使用个人电子邮件帐户，包括 Exchange 帐户，测试核心 SMTP 功能选择**匿名访问**。 选择基本身份验证后，SMTP 使用 AUTH 命令。 某些电子邮件提供商由于 AUTH 命令可能会失败。 如果 AUTH 命令失败，则可能在 SMTP 服务器上的 Windows 事件日志中记录错误。  
  
6.  在中**交付**选项卡上，选择**的出站连接**。 默认情况下，TCP 端口为 25。 如果在防火墙内打开，则可以输入其他端口。 选择 **确定**。  
  
7.  在中**交付**选项卡上，选择**高级**。 默认情况下**完全限定域名**会列出本地服务器。 Internet 提供商，根据**智能主机**属性可以留空。 您可能需要与 internet 提供商联系以确认是否需要智能主机。 否则，可能无法输入 smtp。*EMailProvider*。 com。  
  
    > [!NOTE]
    >  一个**智能主机**，也称为中继主机是专用的服务器将 Exchange Server 用于路由所有传出消息。 当**智能主机**收到消息之后，**智能主机**将消息转发到远程域。 目标**智能主机**是提高 Exchange Server 的性能。 Exchange Server 仅将传输到智能主机;而不是反复联系远程域，直至建立连接。  
  
8.  选择**确定**关闭所有窗口。  
  
9. 重新启动 SMTP 服务器：右键单击 **[SMTP 虚拟服务器 #1]**，选择**停止**，然后选择**启动**。 重启才能应用 SMTP 服务器设置。 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a>Windows Server 2008 R2:安装和配置 SMTP 服务器  
  
### <a name="install-smtp-server"></a>安装 SMTP 服务器  
 以下步骤安装 SMTP 服务器功能：  
  
1.  在中**服务器管理器**，选择**功能**，然后选择**添加功能**。  
  
3.  在中**添加功能**，选择**SMTP 服务器**。 如果系统提示，请选择**添加所需的角色服务**，然后选择**下一步**。  
  
4.  通过选择继续进行安装**下一步**。  
  
5.  在中**确认安装选择**窗口中，选择**安装**。 完成后，选择**关闭**。  
  
### <a name="configure-the-smtp-server"></a>配置 SMTP 服务器  
 以下步骤配置 SMTP 虚拟服务器使用 IIS 6.0 管理器：  
  
1.  打开 IIS 6.0 管理器：在中**启动**，搜索**IIS**，然后选择**Internet 信息服务 (IIS) 6.0 管理器**。  
  
2.  展开计算机名称。 右键单击 **[SMTP 虚拟服务器 #1]**，然后选择**属性**。  
  
3.  在中**访问**选项卡上，选择**中继**按钮。  
  
4.  选择 **添加** 。 有关**台计算机**，输入`127.0.0.1`，然后选择**确定**。  
  
     通过添加 127.0.0.1，我们允许本地服务器从此 SMTP 服务器发送消息。 如果希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。  
  
5.  在中**交付**选项卡上，选择**出站安全**。 选择以下选项：  
  
     **匿名访问**:帐户名或密码不是必需的。 此选项将禁用 SMTP 服务器的身份验证。  
  
     **基本身份验证**:帐户名称和密码以明文形式发送要连接的服务器。 将电子邮件发送到个人帐户或 Exchange 帐户时，可以选择基本身份验证。 因为凭据将以明文形式传递，建议启用**TLS 加密**。  
  
     **集成 Windows 身份验证**:使用 Windows 域帐户名和密码进行身份验证。 你输入的帐户用于传输电子邮件。  
  
     **TLS 加密**:与 SSL 相似，TLS 用于保护安全连接。 需要有效的 SSL 服务器证书安装在此服务器上。  
  
    > [!TIP]
    >  若要使用个人电子邮件帐户，包括 Exchange 帐户，测试核心 SMTP 功能选择**匿名访问**。 选择基本身份验证后，SMTP 使用 AUTH 命令。 某些电子邮件提供商由于 AUTH 命令可能会失败。 如果 AUTH 命令失败，则可能在 SMTP 服务器上的 Windows 事件日志中记录错误。  
  
6.  在中**交付**选项卡上，选择**的出站连接**。 默认情况下，TCP 端口为 25。 如果在防火墙内打开，则可以输入其他端口。 选择 **确定**。  
  
    > [!TIP]
    >  TCP 端口可用于入站的连接和出站连接。  
  
7.  在中**交付**选项卡上，选择**高级**。 默认情况下**完全限定域名**会列出本地服务器。 Internet 提供商，根据**智能主机**属性可以留空。 您可能需要与 internet 提供商联系以确认是否需要智能主机。 否则，可能无法输入 smtp。*EMailProvider*。 com。  
  
    > [!NOTE]
    >  一个**智能主机**，也称为中继主机是专用的服务器将 Exchange Server 用于路由所有传出消息。 当**智能主机**收到消息之后，**智能主机**将消息转发到远程域。 目标**智能主机**是提高 Exchange Server 的性能。 Exchange Server 仅将传输到智能主机;而不是反复联系远程域，直至建立连接。  
  
8.  选择**确定**关闭所有窗口。  
  
9. 重启才能应用 SMTP 服务器设置。 若要重新启动 SMTP 服务器：右键单击 **[SMTP 虚拟服务器 #1]**，选择**停止**，然后选择**启动**。  
  
  
## <a name="test-the-smtp-server"></a>测试 SMTP 服务器  
 可以使用 Telnet 测试 SMTP 服务器的配置。 以下步骤将发送到电子邮件地址配置的 SMTP 服务器使用的消息。 [http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) 提供了 telnet 命令的说明。  
  
1. 以管理员身份打开命令窗口。
  
2. 在命令提示符下键入：  
  
    `telnet localhost 25`  
  
    如果未安装 telnet，请通过键入来安装它：  
  
    `pkgmgr /iu:"TelnetClient"`  
  
3. 通过键入启动通信：  
  
    `EHLO server`  
  
4. 输入的发件人地址：  
  
    `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
    例如，输入：  
  
    `MAIL FROM: EmailAddress@outlook.com`  
  
5. 输入发送到地址：  
  
    `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
    例如，输入：  
  
    `RCPT TO: EmailAddress@outlook.com`  
  
6. 告知你已准备好发送数据，通过键入 SMTP 服务器：  
  
    `DATA`  
  
7. 通过键入输入主题：  
  
    `Subject: Test Message`  
  
8. 按 Enter 两次。  
  
9. 通过键入来输入消息正文：  
  
     `This is the message body of the test message.`  
  
10. 按 Enter，键入句点 （.），并按 Enter。  
  
    检查电子邮件的 RCPT TO 地址。 如果电子邮件未送达 （检查收件箱和垃圾邮件文件夹），则消息未成功发送，而可能驻留在 SMTP 队列文件夹中 (C:\inetpub\mailroot\Queue)。  
  