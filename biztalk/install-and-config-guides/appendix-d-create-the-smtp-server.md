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
ms.locfileid: "22300133"
---
# <a name="appendix-d-create-the-smtp-server"></a><span data-ttu-id="490d5-102">附录 D：创建 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-102">Appendix D: Create the SMTP Server</span></span>
<span data-ttu-id="490d5-103">创建供 SQL Server Database Mail 使用的 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-103">Create the SMTP Server used by SQL Server Database Mail.</span></span>  
  
<span data-ttu-id="490d5-104">使用以下任何版本的 SQL 时，需要 SQL Server Database Mail 才能配置 BAM 警报：</span><span class="sxs-lookup"><span data-stu-id="490d5-104">SQL Server Database Mail is required to configure BAM Alerts when using any of the following SQL versions:</span></span> 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
 <span data-ttu-id="490d5-105">SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="490d5-105">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="490d5-106">SMTP 服务器随 Internet 信息服务 (IIS) 一起提供。</span><span class="sxs-lookup"><span data-stu-id="490d5-106">SMTP Server is included with Internet Information Services (IIS).</span></span> <span data-ttu-id="490d5-107">SMTP 可以本地安装在 BizTalk Server 上，也可以安装在其他已安装 IIS 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="490d5-107">SMTP can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="490d5-108">通常情况下，类似 Windows 10、Windows 7 等的客户端操作系统不包括 SMTP 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="490d5-108">Typically, client operating systems like Windows 10, Windows 7, and so on, do not include SMTP Server capabilities.</span></span> <span data-ttu-id="490d5-109">可使用 IIS 中的 *SMTP 电子邮件*功能，连接到 Windows Server 上的现有 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-109">You can connect to an existing SMTP Server on a Windows Server using the *SMTP E-mail* feature within IIS.</span></span> <span data-ttu-id="490d5-110">*SMTP 电子邮件*功能不是 SMTP 服务器，但 SQL Server 数据库邮件需要 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-110">The *SMTP E-mail* feature is NOT an SMTP Server, which is required for SQL Server Database Mail.</span></span> <span data-ttu-id="490d5-111">因此，本主题不包括在客户端操作系统上安装和配置 SMTP 服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="490d5-111">As a result, this topic does not include the steps to install and configure an SMTP Server on client operating systems.</span></span>  

## <a name="install-and-configure-the-smtp-server"></a><span data-ttu-id="490d5-112">安装和配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-112">Install and configure the SMTP server</span></span>  
  
<span data-ttu-id="490d5-113">这些步骤适用于：</span><span class="sxs-lookup"><span data-stu-id="490d5-113">These steps apply to:</span></span>

* <span data-ttu-id="490d5-114">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="490d5-114">Windows Server 2016</span></span>
* <span data-ttu-id="490d5-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="490d5-115">Windows Server 2012 R2</span></span>
* <span data-ttu-id="490d5-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="490d5-116">Windows Server 2012</span></span>
  
### <a name="install-smtp-server"></a><span data-ttu-id="490d5-117">安装 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-117">Install SMTP Server</span></span>  
   
1.  <span data-ttu-id="490d5-118">打开“服务器管理器”，在左侧窗格中，选择“仪表板”。</span><span class="sxs-lookup"><span data-stu-id="490d5-118">In **Server Manager**, select **Dashboard** in the left pane.</span></span>  
  
3.  <span data-ttu-id="490d5-119">选择“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="490d5-119">Select **Add roles and features**.</span></span> <span data-ttu-id="490d5-120">也可从右上角的“管理”菜单打开“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="490d5-120">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
4.  <span data-ttu-id="490d5-121">在“开始之前”中，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-121">In **Before You Begin**, select **Next**.</span></span>  
  
5.  <span data-ttu-id="490d5-122">选择“基于角色或基于功能的安装”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-122">Select **Role-based or feature-based installation**, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="490d5-123">选择“从服务器池中选择服务器”，选中所需的服务器，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-123">Select **Select a server from the server pool**, select the desired server, and select **Next**.</span></span> <span data-ttu-id="490d5-124">“服务器选择”窗口中会列出“服务器管理器”中使用“添加服务器”添加的服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-124">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="490d5-125">默认情况下，本地服务器处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="490d5-125">By default, it selects the local server.</span></span>  
  
7.  <span data-ttu-id="490d5-126">在“服务器角色”中，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-126">In **Server Roles**, select **Next**.</span></span>  
  
8.  <span data-ttu-id="490d5-127">在“功能”中，选中“SMTP 服务器”。</span><span class="sxs-lookup"><span data-stu-id="490d5-127">In **Features**, check **SMTP Server**.</span></span> <span data-ttu-id="490d5-128">如果出现提示，请选择“添加功能”。</span><span class="sxs-lookup"><span data-stu-id="490d5-128">If prompted, select **Add Features**.</span></span> <span data-ttu-id="490d5-129">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-129">Select **Next**.</span></span>  
  
9. <span data-ttu-id="490d5-130">在“确认”中，选择“如果需要，自动重启目标服务器”，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="490d5-130">In **Confirmation**, select **Restart the destination server automatically if required**, and select **Install**.</span></span> <span data-ttu-id="490d5-131">完成后，选择“关闭”。</span><span class="sxs-lookup"><span data-stu-id="490d5-131">When complete, select **Close**.</span></span>  

### <a name="configure-the-smtp-server"></a><span data-ttu-id="490d5-132">配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-132">Configure the SMTP Server</span></span>  
 <span data-ttu-id="490d5-133">以下是使用 IIS 6.0 管理器配置 SMTP 虚拟服务器的步骤：</span><span class="sxs-lookup"><span data-stu-id="490d5-133">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="490d5-134">打开 IIS 管理器：在“启动”中，搜索“inetmgr6.exe”，然后将其打开。</span><span class="sxs-lookup"><span data-stu-id="490d5-134">Open the IIS Manager: In Start, search for **inetmgr6.exe**, and open it.</span></span>  
  
2.  <span data-ttu-id="490d5-135">展开计算机名。</span><span class="sxs-lookup"><span data-stu-id="490d5-135">Expand the computer name.</span></span> <span data-ttu-id="490d5-136">右键单击“[SMTP 虚拟服务器 #1]”，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="490d5-136">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="490d5-137">在“访问”选项卡中，选择“中继”按钮。</span><span class="sxs-lookup"><span data-stu-id="490d5-137">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="490d5-138">选择“添加”。</span><span class="sxs-lookup"><span data-stu-id="490d5-138">Select **Add**.</span></span> <span data-ttu-id="490d5-139">对于“单台计算机”，输入 `127.0.0.1`，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="490d5-139">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="490d5-140">通过添加 127.0.0.1，我们将允许本地服务器从此 SMTP 服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="490d5-140">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="490d5-141">如果你希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="490d5-141">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="490d5-142">在“传递”选项卡中，选择“出站安全”。</span><span class="sxs-lookup"><span data-stu-id="490d5-142">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="490d5-143">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="490d5-143">Choose from the following:</span></span>  
  
     <span data-ttu-id="490d5-144">**匿名访问**：不需要帐户名或密码。</span><span class="sxs-lookup"><span data-stu-id="490d5-144">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="490d5-145">此选项将禁用 SMTP 服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="490d5-145">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="490d5-146">**基本身份验证**：以明文形式发送要连接的服务器的帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="490d5-146">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="490d5-147">输入的帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="490d5-147">This account you enter transmits the e-mails.</span></span> <span data-ttu-id="490d5-148">向个人帐户或 Exchange 帐户发送电子邮件时，可以选择“基本身份验证”。</span><span class="sxs-lookup"><span data-stu-id="490d5-148">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="490d5-149">因为凭据将以明文形式传递，所以建议启用“TLS 加密”。</span><span class="sxs-lookup"><span data-stu-id="490d5-149">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="490d5-150">**集成身份验证**：Windows 域帐户名和密码用于进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="490d5-150">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="490d5-151">输入的帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="490d5-151">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="490d5-152">**TLS 加密**：与 SSL 相似，TLS 用于保护连接的安全。</span><span class="sxs-lookup"><span data-stu-id="490d5-152">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="490d5-153">需要在此服务器上安装一个有效的 SSL 服务器证书。</span><span class="sxs-lookup"><span data-stu-id="490d5-153">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="490d5-154">若要使用个人电子邮件帐户（包括 Exchange 帐户）测试核心 SMTP 功能，请选择“匿名访问”。</span><span class="sxs-lookup"><span data-stu-id="490d5-154">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="490d5-155">选择“基本身份验证”时，SMTP 使用 AUTH 命令。</span><span class="sxs-lookup"><span data-stu-id="490d5-155">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="490d5-156">一些电子邮件提供商由于 AUTH 命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="490d5-156">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="490d5-157">如果 AUTH 命令失败，则错误可能会记录到 SMTP 服务器上的 Windows 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="490d5-157">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="490d5-158">在“传递”选项卡中，选择“出站连接”。</span><span class="sxs-lookup"><span data-stu-id="490d5-158">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="490d5-159">默认情况下，TCP 端口为 25。</span><span class="sxs-lookup"><span data-stu-id="490d5-159">By default, the TCP Port is 25.</span></span> <span data-ttu-id="490d5-160">如果其他端口已在防火墙内打开，可输入其他端口。</span><span class="sxs-lookup"><span data-stu-id="490d5-160">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="490d5-161">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="490d5-161">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="490d5-162">在“传递”选项卡中，选择“高级”。</span><span class="sxs-lookup"><span data-stu-id="490d5-162">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="490d5-163">默认情况下，会列出本地服务器的“完全限定的域名”。</span><span class="sxs-lookup"><span data-stu-id="490d5-163">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="490d5-164">“智能主机”属性可以留空，具体取决于 Internet 提供商。</span><span class="sxs-lookup"><span data-stu-id="490d5-164">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="490d5-165">你可能需要联系 Internet 提供商来确认是否需要“智能主机”。</span><span class="sxs-lookup"><span data-stu-id="490d5-165">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="490d5-166">否则，可能无法进入 smtp.*EMailProvider*.com。</span><span class="sxs-lookup"><span data-stu-id="490d5-166">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="490d5-167">“智能主机”（也称为“中继主机”）是 Exchange Server 专用于路由所有传出消息的服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-167">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="490d5-168">“智能主机”收到消息之后，会将消息转发到远程域。</span><span class="sxs-lookup"><span data-stu-id="490d5-168">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="490d5-169">“智能主机”的目标是提高 Exchange Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="490d5-169">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="490d5-170">Exchange Server 只向智能主机进行传输；而不是反复联系远程域，直到建立连接。</span><span class="sxs-lookup"><span data-stu-id="490d5-170">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="490d5-171">单击“确定”以关闭所有窗口。</span><span class="sxs-lookup"><span data-stu-id="490d5-171">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="490d5-172">重启 SMTP 服务器：右键单击“[SMTP 虚拟服务器 #1]”，选择“停止”，然后选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="490d5-172">Restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span> <span data-ttu-id="490d5-173">必须重新启动才能应用 SMTP 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="490d5-173">A restart is needed to apply the SMTP Server settings.</span></span> 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a><span data-ttu-id="490d5-174">Windows Server 2008 R2：安装和配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-174">Windows Server 2008 R2: Install and Configure SMTP Server</span></span>  
  
### <a name="install-smtp-server"></a><span data-ttu-id="490d5-175">安装 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-175">Install SMTP Server</span></span>  
 <span data-ttu-id="490d5-176">以下是安装 SMTP 服务器功能的步骤：</span><span class="sxs-lookup"><span data-stu-id="490d5-176">The following steps install the SMTP Server feature:</span></span>  
  
1.  <span data-ttu-id="490d5-177">在“服务器管理器”中，选择“功能”，然后选择“添加功能”。</span><span class="sxs-lookup"><span data-stu-id="490d5-177">In **Server Manager**, select **Features**, and select **Add Features**.</span></span>  
  
3.  <span data-ttu-id="490d5-178">在“添加功能”中，选择“SMTP 服务器”。</span><span class="sxs-lookup"><span data-stu-id="490d5-178">In **Add Features**, select **SMTP Server**.</span></span> <span data-ttu-id="490d5-179">如果系统提示，请选择“添加必需的角色服务”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="490d5-179">If prompted, select **Add Required Role Services**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="490d5-180">选择“下一步”继续安装。</span><span class="sxs-lookup"><span data-stu-id="490d5-180">Continue with the installation by selecting **Next**.</span></span>  
  
5.  <span data-ttu-id="490d5-181">在“确认安装选择”窗口中，选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="490d5-181">In the **Confirm Installation Selections** window, select **Install**.</span></span> <span data-ttu-id="490d5-182">完成后，选择“关闭”。</span><span class="sxs-lookup"><span data-stu-id="490d5-182">When complete, select **Close**.</span></span>  
  
### <a name="configure-the-smtp-server"></a><span data-ttu-id="490d5-183">配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-183">Configure the SMTP Server</span></span>  
 <span data-ttu-id="490d5-184">以下是使用 IIS 6.0 管理器配置 SMTP 虚拟服务器的步骤：</span><span class="sxs-lookup"><span data-stu-id="490d5-184">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="490d5-185">打开 IIS 6.0 管理器：在“启动”中，搜索“IIS”，然后选择“Internet Information Services (IIS) 6.0 管理器”。</span><span class="sxs-lookup"><span data-stu-id="490d5-185">Open the IIS 6.0 Manager: In **Start**, search for **IIS**, and select **Internet Information Services (IIS) 6.0 Manager**.</span></span>  
  
2.  <span data-ttu-id="490d5-186">展开计算机名。</span><span class="sxs-lookup"><span data-stu-id="490d5-186">Expand the computer name.</span></span> <span data-ttu-id="490d5-187">右键单击“[SMTP 虚拟服务器 #1]”，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="490d5-187">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="490d5-188">在“访问”选项卡中，选择“中继”按钮。</span><span class="sxs-lookup"><span data-stu-id="490d5-188">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="490d5-189">选择“添加”。</span><span class="sxs-lookup"><span data-stu-id="490d5-189">Select **Add**.</span></span> <span data-ttu-id="490d5-190">对于“单台计算机”，输入 `127.0.0.1`，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="490d5-190">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="490d5-191">通过添加 127.0.0.1，我们将允许本地服务器从此 SMTP 服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="490d5-191">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="490d5-192">如果你希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="490d5-192">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="490d5-193">在“传递”选项卡中，选择“出站安全”。</span><span class="sxs-lookup"><span data-stu-id="490d5-193">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="490d5-194">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="490d5-194">Choose from the following:</span></span>  
  
     <span data-ttu-id="490d5-195">**匿名访问**：不需要帐户名或密码。</span><span class="sxs-lookup"><span data-stu-id="490d5-195">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="490d5-196">此选项将禁用 SMTP 服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="490d5-196">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="490d5-197">**基本身份验证**：以明文形式发送要连接的服务器的帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="490d5-197">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="490d5-198">向个人帐户或 Exchange 帐户发送电子邮件时，可以选择“基本身份验证”。</span><span class="sxs-lookup"><span data-stu-id="490d5-198">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="490d5-199">因为凭据将以明文形式传递，所以建议启用“TLS 加密”。</span><span class="sxs-lookup"><span data-stu-id="490d5-199">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="490d5-200">**集成身份验证**：Windows 域帐户名和密码用于进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="490d5-200">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="490d5-201">输入的帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="490d5-201">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="490d5-202">**TLS 加密**：与 SSL 相似，TLS 用于保护连接的安全。</span><span class="sxs-lookup"><span data-stu-id="490d5-202">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="490d5-203">需要在此服务器上安装一个有效的 SSL 服务器证书。</span><span class="sxs-lookup"><span data-stu-id="490d5-203">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="490d5-204">若要使用个人电子邮件帐户（包括 Exchange 帐户）测试核心 SMTP 功能，请选择“匿名访问”。</span><span class="sxs-lookup"><span data-stu-id="490d5-204">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="490d5-205">选择“基本身份验证”时，SMTP 使用 AUTH 命令。</span><span class="sxs-lookup"><span data-stu-id="490d5-205">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="490d5-206">一些电子邮件提供商由于 AUTH 命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="490d5-206">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="490d5-207">如果 AUTH 命令失败，则错误可能会记录到 SMTP 服务器上的 Windows 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="490d5-207">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="490d5-208">在“传递”选项卡中，选择“出站连接”。</span><span class="sxs-lookup"><span data-stu-id="490d5-208">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="490d5-209">默认情况下，TCP 端口为 25。</span><span class="sxs-lookup"><span data-stu-id="490d5-209">By default, the TCP Port is 25.</span></span> <span data-ttu-id="490d5-210">如果其他端口已在防火墙内打开，可输入其他端口。</span><span class="sxs-lookup"><span data-stu-id="490d5-210">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="490d5-211">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="490d5-211">Select **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="490d5-212">TCP 端口可用于入站连接和出站连接。</span><span class="sxs-lookup"><span data-stu-id="490d5-212">The TCP Port can be used for Inbound connections and Outbound connections.</span></span>  
  
7.  <span data-ttu-id="490d5-213">在“传递”选项卡中，选择“高级”。</span><span class="sxs-lookup"><span data-stu-id="490d5-213">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="490d5-214">默认情况下，会列出本地服务器的“完全限定的域名”。</span><span class="sxs-lookup"><span data-stu-id="490d5-214">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="490d5-215">“智能主机”属性可以留空，具体取决于 Internet 提供商。</span><span class="sxs-lookup"><span data-stu-id="490d5-215">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="490d5-216">你可能需要联系 Internet 提供商来确认是否需要“智能主机”。</span><span class="sxs-lookup"><span data-stu-id="490d5-216">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="490d5-217">否则，可能无法进入 smtp.*EMailProvider*.com。</span><span class="sxs-lookup"><span data-stu-id="490d5-217">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="490d5-218">“智能主机”（也称为“中继主机”）是 Exchange Server 专用于路由所有传出消息的服务器。</span><span class="sxs-lookup"><span data-stu-id="490d5-218">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="490d5-219">“智能主机”收到消息之后，会将消息转发到远程域。</span><span class="sxs-lookup"><span data-stu-id="490d5-219">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="490d5-220">“智能主机”的目标是提高 Exchange Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="490d5-220">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="490d5-221">Exchange Server 只向智能主机进行传输；而不是反复联系远程域，直到建立连接。</span><span class="sxs-lookup"><span data-stu-id="490d5-221">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="490d5-222">单击“确定”以关闭所有窗口。</span><span class="sxs-lookup"><span data-stu-id="490d5-222">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="490d5-223">必须重新启动才能应用 SMTP 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="490d5-223">A restart is needed to apply the SMTP Server settings.</span></span> <span data-ttu-id="490d5-224">若要重启 SMTP 服务器：右键单击“[SMTP 虚拟服务器 #1]”，选择“停止”，然后选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="490d5-224">To restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span>  
  
  
## <a name="test-the-smtp-server"></a><span data-ttu-id="490d5-225">测试 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="490d5-225">Test the SMTP Server</span></span>  
 <span data-ttu-id="490d5-226">可以使用 Telnet 测试 SMTP 服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="490d5-226">Telnet can be used to test the SMTP Server configuration.</span></span> <span data-ttu-id="490d5-227">以下步骤使用配置的 SMTP 服务器将消息发送到电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="490d5-227">The following steps send a message using your configured SMTP Server to an e-mail address.</span></span> <span data-ttu-id="490d5-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) 提供的 telnet 命令的说明。</span><span class="sxs-lookup"><span data-stu-id="490d5-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) provides descriptions of the telnet commands.</span></span>  
  
1.  <span data-ttu-id="490d5-229">以管理员身份打开命令窗口。</span><span class="sxs-lookup"><span data-stu-id="490d5-229">Open a command window as Administrator.</span></span>
  
2.  <span data-ttu-id="490d5-230">在命令提示符下，输入：</span><span class="sxs-lookup"><span data-stu-id="490d5-230">In the command prompt, type:</span></span>  
  
     `telnet localhost 25`  
  
     <span data-ttu-id="490d5-231">如果没有安装 telnet，则输入以下内容进行安装：</span><span class="sxs-lookup"><span data-stu-id="490d5-231">If telnet is not installed, install it by typing:</span></span>  
  
     `pkgmgr /iu:"TelnetClient"`  
  
3.  <span data-ttu-id="490d5-232">输入以下内容启动通信：</span><span class="sxs-lookup"><span data-stu-id="490d5-232">Start communication by typing:</span></span>  
  
     `EHLO server`  
  
4.  <span data-ttu-id="490d5-233">输入“发件人”地址：</span><span class="sxs-lookup"><span data-stu-id="490d5-233">Enter the Mail From address:</span></span>  
  
     `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
     <span data-ttu-id="490d5-234">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="490d5-234">For example, enter:</span></span>  
  
     `MAIL FROM: EmailAddress@outlook.com`  
  
5.  <span data-ttu-id="490d5-235">输入“收件人”地址：</span><span class="sxs-lookup"><span data-stu-id="490d5-235">Enter the Mail To address:</span></span>  
  
     `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
     <span data-ttu-id="490d5-236">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="490d5-236">For example, enter:</span></span>  
  
     `RCPT TO: EmailAddress@outlook.com`  
  
6.  <span data-ttu-id="490d5-237">输入以下内容，以告知 SMTP 服务器您已准备好发送数据：</span><span class="sxs-lookup"><span data-stu-id="490d5-237">Tell the SMTP Server you are ready to send data by typing:</span></span>  
  
     `DATA`  
  
7.  <span data-ttu-id="490d5-238">输入以下内容，以输入“主题”：</span><span class="sxs-lookup"><span data-stu-id="490d5-238">Enter the Subject by typing:</span></span>  
  
     `Subject: Test Message`  
  
8.  <span data-ttu-id="490d5-239">按 Enter 两次。</span><span class="sxs-lookup"><span data-stu-id="490d5-239">Hit Enter twice.</span></span>  
  
9. <span data-ttu-id="490d5-240">输入以下内容，以输入邮件正文：</span><span class="sxs-lookup"><span data-stu-id="490d5-240">Enter the message body by typing:</span></span>  
  
     `This is the message body of the test message.`  
  
10. <span data-ttu-id="490d5-241">按 Enter，输入句点 (.)，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="490d5-241">Hit Enter, type a period (.), and hit Enter.</span></span>  
  
 <span data-ttu-id="490d5-242">检查电子邮件的 RCPT TO 地址。</span><span class="sxs-lookup"><span data-stu-id="490d5-242">Check the RCPT TO address for the e-mail message.</span></span> <span data-ttu-id="490d5-243">如果电子邮件未送达（检查“收件箱”和“垃圾邮件”文件夹），则表示邮件发送失败，可能仍驻留在 SMTP 队列文件夹中 (C:\inetpub\mailroot\Queue)。</span><span class="sxs-lookup"><span data-stu-id="490d5-243">If the e-mail is not delivered (Check your Inbox and Spam folder), then the message was not successfully sent, and may reside in the SMTP Queue folder (C:\inetpub\mailroot\Queue).</span></span>  
  