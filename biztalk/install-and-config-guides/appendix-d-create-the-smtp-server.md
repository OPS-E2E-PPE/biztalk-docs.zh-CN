---
title: 附录 d： 创建 SMTP 服务器 |Microsoft 文档
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
ms.openlocfilehash: 9f4d4acc35f5cb38be5f783ee7c4017c8ada83e2
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="appendix-d-create-the-smtp-server"></a>附录 D：创建 SMTP 服务器
创建供 SQL Server Database Mail 使用的 SMTP 服务器。  
  
使用以下任何版本的 SQL 时，需要 SQL Server Database Mail 才能配置 BAM 警报： 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
 SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。 SMTP 服务器随 Internet 信息服务 (IIS) 一起提供。 SMTP 可以本地安装在 BizTalk Server 上，也可以安装在其他已安装 IIS 的服务器上。  
  
> [!IMPORTANT]
>  通常情况下，类似 Windows 10、Windows 7 等的客户端操作系统不包括 SMTP 服务器功能。 可使用 IIS 中的 *SMTP 电子邮件*功能，连接到 Windows Server 上的现有 SMTP 服务器。 *SMTP 电子邮件*功能不是 SMTP 服务器，但 SQL Server 数据库邮件需要 SMTP 服务器。 因此，本主题不包括在客户端操作系统上安装和配置 SMTP 服务器的步骤。  

## <a name="install-and-configure-the-smtp-server"></a>安装和配置 SMTP 服务器  
  
这些步骤适用于：

* Windows Server 2016
* Windows Server 2012 R2
* Windows Server 2012
  
### <a name="install-smtp-server"></a>安装 SMTP 服务器  
   
1.  打开“服务器管理器”，在左侧窗格中，选择“仪表板”。  
  
3.  选择“添加角色和功能”。 也可从右上角的“管理”菜单打开“添加角色和功能”。  
  
4.  在“开始之前”中，选择“下一步”。  
  
5.  选择“基于角色或基于功能的安装”，然后选择“下一步”。  
  
6.  选择“从服务器池中选择服务器”，选中所需的服务器，然后选择“下一步”。 “服务器选择”窗口中会列出“服务器管理器”中使用“添加服务器”添加的服务器。 默认情况下，本地服务器处于选中状态。  
  
7.  在“服务器角色”中，选择“下一步”。  
  
8.  在“功能”中，选中“SMTP 服务器”。 如果出现提示，请选择“添加功能”。 选择“下一步”。  
  
9. 在“确认”中，选择“如果需要，自动重启目标服务器”，然后选择“安装”。 完成后，选择“关闭”。  

### <a name="configure-the-smtp-server"></a>配置 SMTP 服务器  
 以下是使用 IIS 6.0 管理器配置 SMTP 虚拟服务器的步骤：  
  
1.  打开 IIS 管理器：在“启动”中，搜索“inetmgr6.exe”，然后将其打开。  
  
2.  展开计算机名。 右键单击“[SMTP 虚拟服务器 #1]”，然后选择“属性”。  
  
3.  在“访问”选项卡中，选择“中继”按钮。  
  
4.  选择“添加”。 对于“单台计算机”，输入 `127.0.0.1`，然后选择“确定”。  
  
     通过添加 127.0.0.1，我们将允许本地服务器从此 SMTP 服务器发送消息。 如果你希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。  
  
5.  在“传递”选项卡中，选择“出站安全”。 选择以下选项：  
  
     **匿名访问**：不需要帐户名或密码。 此选项将禁用 SMTP 服务器身份验证。  
  
     **基本身份验证**：以明文形式发送要连接的服务器的帐户名和密码。 输入的帐户用于传输电子邮件。 向个人帐户或 Exchange 帐户发送电子邮件时，可以选择“基本身份验证”。 因为凭据将以明文形式传递，所以建议启用“TLS 加密”。  
  
     **集成身份验证**：Windows 域帐户名和密码用于进行身份验证。 输入的帐户用于传输电子邮件。  
  
     **TLS 加密**：与 SSL 相似，TLS 用于保护连接的安全。 需要在此服务器上安装一个有效的 SSL 服务器证书。  
  
    > [!TIP]
    >  若要使用个人电子邮件帐户（包括 Exchange 帐户）测试核心 SMTP 功能，请选择“匿名访问”。 选择“基本身份验证”时，SMTP 使用 AUTH 命令。 一些电子邮件提供商由于 AUTH 命令可能会失败。 如果 AUTH 命令失败，则错误可能会记录到 SMTP 服务器上的 Windows 事件日志中。  
  
6.  在“传递”选项卡中，选择“出站连接”。 默认情况下，TCP 端口为 25。 如果其他端口已在防火墙内打开，可输入其他端口。 选择“确定”。  
  
7.  在“传递”选项卡中，选择“高级”。 默认情况下，会列出本地服务器的“完全限定的域名”。 “智能主机”属性可以留空，具体取决于 Internet 提供商。 你可能需要联系 Internet 提供商来确认是否需要“智能主机”。 否则，可能无法进入 smtp.*EMailProvider*.com。  
  
    > [!NOTE]
    >  “智能主机”（也称为“中继主机”）是 Exchange Server 专用于路由所有传出消息的服务器。 “智能主机”收到消息之后，会将消息转发到远程域。 “智能主机”的目标是提高 Exchange Server 的性能。 Exchange Server 只向智能主机进行传输；而不是反复联系远程域，直到建立连接。  
  
8.  单击“确定”以关闭所有窗口。  
  
9. 重启 SMTP 服务器：右键单击“[SMTP 虚拟服务器 #1]”，选择“停止”，然后选择“启动”。 必须重新启动才能应用 SMTP 服务器设置。 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a>Windows Server 2008 R2：安装和配置 SMTP 服务器  
  
### <a name="install-smtp-server"></a>安装 SMTP 服务器  
 以下是安装 SMTP 服务器功能的步骤：  
  
1.  在“服务器管理器”中，选择“功能”，然后选择“添加功能”。  
  
3.  在“添加功能”中，选择“SMTP 服务器”。 如果系统提示，请选择“添加必需的角色服务”，然后选择“下一步”。  
  
4.  选择“下一步”继续安装。  
  
5.  在“确认安装选择”窗口中，选择“安装”。 完成后，选择“关闭”。  
  
### <a name="configure-the-smtp-server"></a>配置 SMTP 服务器  
 以下是使用 IIS 6.0 管理器配置 SMTP 虚拟服务器的步骤：  
  
1.  打开 IIS 6.0 管理器：在“启动”中，搜索“IIS”，然后选择“Internet Information Services (IIS) 6.0 管理器”。  
  
2.  展开计算机名。 右键单击“[SMTP 虚拟服务器 #1]”，然后选择“属性”。  
  
3.  在“访问”选项卡中，选择“中继”按钮。  
  
4.  选择“添加”。 对于“单台计算机”，输入 `127.0.0.1`，然后选择“确定”。  
  
     通过添加 127.0.0.1，我们将允许本地服务器从此 SMTP 服务器发送消息。 如果你希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。  
  
5.  在“传递”选项卡中，选择“出站安全”。 选择以下选项：  
  
     **匿名访问**：不需要帐户名或密码。 此选项将禁用 SMTP 服务器身份验证。  
  
     **基本身份验证**：以明文形式发送要连接的服务器的帐户名和密码。 向个人帐户或 Exchange 帐户发送电子邮件时，可以选择“基本身份验证”。 因为凭据将以明文形式传递，所以建议启用“TLS 加密”。  
  
     **集成身份验证**：Windows 域帐户名和密码用于进行身份验证。 输入的帐户用于传输电子邮件。  
  
     **TLS 加密**：与 SSL 相似，TLS 用于保护连接的安全。 需要在此服务器上安装一个有效的 SSL 服务器证书。  
  
    > [!TIP]
    >  若要使用个人电子邮件帐户（包括 Exchange 帐户）测试核心 SMTP 功能，请选择“匿名访问”。 选择“基本身份验证”时，SMTP 使用 AUTH 命令。 一些电子邮件提供商由于 AUTH 命令可能会失败。 如果 AUTH 命令失败，则错误可能会记录到 SMTP 服务器上的 Windows 事件日志中。  
  
6.  在“传递”选项卡中，选择“出站连接”。 默认情况下，TCP 端口为 25。 如果其他端口已在防火墙内打开，可输入其他端口。 选择“确定”。  
  
    > [!TIP]
    >  TCP 端口可用于入站连接和出站连接。  
  
7.  在“传递”选项卡中，选择“高级”。 默认情况下，会列出本地服务器的“完全限定的域名”。 “智能主机”属性可以留空，具体取决于 Internet 提供商。 你可能需要联系 Internet 提供商来确认是否需要“智能主机”。 否则，可能无法进入 smtp.*EMailProvider*.com。  
  
    > [!NOTE]
    >  “智能主机”（也称为“中继主机”）是 Exchange Server 专用于路由所有传出消息的服务器。 “智能主机”收到消息之后，会将消息转发到远程域。 “智能主机”的目标是提高 Exchange Server 的性能。 Exchange Server 只向智能主机进行传输；而不是反复联系远程域，直到建立连接。  
  
8.  单击“确定”以关闭所有窗口。  
  
9. 必须重新启动才能应用 SMTP 服务器设置。 若要重启 SMTP 服务器：右键单击“[SMTP 虚拟服务器 #1]”，选择“停止”，然后选择“启动”。  
  
  
## <a name="test-the-smtp-server"></a>测试 SMTP 服务器  
 可以使用 Telnet 测试 SMTP 服务器的配置。 以下步骤使用配置的 SMTP 服务器将消息发送到电子邮件地址。 [http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) 提供的 telnet 命令的说明。  
  
1.  以管理员身份打开命令窗口。
  
2.  在命令提示符下，输入：  
  
     `telnet localhost 25`  
  
     如果没有安装 telnet，则输入以下内容进行安装：  
  
     `pkgmgr /iu:"TelnetClient"`  
  
3.  输入以下内容启动通信：  
  
     `EHLO server`  
  
4.  输入“发件人”地址：  
  
     `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
     例如，输入：  
  
     `MAIL FROM: EmailAddress@outlook.com`  
  
5.  输入“收件人”地址：  
  
     `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
     例如，输入：  
  
     `RCPT TO: EmailAddress@outlook.com`  
  
6.  输入以下内容，以告知 SMTP 服务器您已准备好发送数据：  
  
     `DATA`  
  
7.  输入以下内容，以输入“主题”：  
  
     `Subject: Test Message`  
  
8.  按 Enter 两次。  
  
9. 输入以下内容，以输入邮件正文：  
  
     `This is the message body of the test message.`  
  
10. 按 Enter，输入句点 (.)，再按 Enter。  
  
 检查电子邮件的 RCPT TO 地址。 如果电子邮件未送达（检查“收件箱”和“垃圾邮件”文件夹），则表示邮件发送失败，可能仍驻留在 SMTP 队列文件夹中 (C:\inetpub\mailroot\Queue)。  
  