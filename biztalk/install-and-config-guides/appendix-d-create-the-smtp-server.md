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
# <a name="appendix-d-create-the-smtp-server"></a><span data-ttu-id="81c56-102">附录 D：创建 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-102">Appendix D: Create the SMTP Server</span></span>
<span data-ttu-id="81c56-103">创建使用 SQL Server 数据库邮件的 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-103">Create the SMTP Server used by SQL Server Database Mail.</span></span>  
  
<span data-ttu-id="81c56-104">使用任何以下的 SQL 版本时配置 BAM 警报需要 SQL Server 数据库邮件：</span><span class="sxs-lookup"><span data-stu-id="81c56-104">SQL Server Database Mail is required to configure BAM Alerts when using any of the following SQL versions:</span></span> 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
  <span data-ttu-id="81c56-105">SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="81c56-105">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="81c56-106">使用 Internet 信息服务 (IIS) 中包含 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-106">SMTP Server is included with Internet Information Services (IIS).</span></span> <span data-ttu-id="81c56-107">SMTP 可以本地安装 BizTalk Server 上或在另一台服务器上已安装 iis。</span><span class="sxs-lookup"><span data-stu-id="81c56-107">SMTP can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81c56-108">通常情况下，客户端操作系统，例如 Windows 10、 Windows 7 等，不包括 SMTP 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="81c56-108">Typically, client operating systems like Windows 10, Windows 7, and so on, do not include SMTP Server capabilities.</span></span> <span data-ttu-id="81c56-109">可以连接到 Windows Server 使用现有的 SMTP 服务器*SMTP 电子邮件*IIS 中的功能。</span><span class="sxs-lookup"><span data-stu-id="81c56-109">You can connect to an existing SMTP Server on a Windows Server using the *SMTP E-mail* feature within IIS.</span></span> <span data-ttu-id="81c56-110">*SMTP 电子邮件*功能不是 SMTP 服务器时，所需的 SQL Server Database Mail。</span><span class="sxs-lookup"><span data-stu-id="81c56-110">The *SMTP E-mail* feature is NOT an SMTP Server, which is required for SQL Server Database Mail.</span></span> <span data-ttu-id="81c56-111">因此，本主题不包括安装和配置客户端操作系统上的 SMTP 服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="81c56-111">As a result, this topic does not include the steps to install and configure an SMTP Server on client operating systems.</span></span>  

## <a name="install-and-configure-the-smtp-server"></a><span data-ttu-id="81c56-112">安装和配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-112">Install and configure the SMTP server</span></span>  
  
<span data-ttu-id="81c56-113">这些步骤适用于：</span><span class="sxs-lookup"><span data-stu-id="81c56-113">These steps apply to:</span></span>

* <span data-ttu-id="81c56-114">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="81c56-114">Windows Server 2016</span></span>
* <span data-ttu-id="81c56-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="81c56-115">Windows Server 2012 R2</span></span>
* <span data-ttu-id="81c56-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="81c56-116">Windows Server 2012</span></span>
  
### <a name="install-smtp-server"></a><span data-ttu-id="81c56-117">安装 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-117">Install SMTP Server</span></span>  
   
1.  <span data-ttu-id="81c56-118">在中**服务器管理器**，选择**仪表板**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="81c56-118">In **Server Manager**, select **Dashboard** in the left pane.</span></span>  
  
3.  <span data-ttu-id="81c56-119">选择**添加角色和功能**。</span><span class="sxs-lookup"><span data-stu-id="81c56-119">Select **Add roles and features**.</span></span> <span data-ttu-id="81c56-120">**添加角色和功能**也可以从打开**管理**中右上角的菜单。</span><span class="sxs-lookup"><span data-stu-id="81c56-120">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
4.  <span data-ttu-id="81c56-121">在中**开始之前**，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-121">In **Before You Begin**, select **Next**.</span></span>  
  
5.  <span data-ttu-id="81c56-122">选择**基于角色或基于功能的安装**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-122">Select **Role-based or feature-based installation**, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="81c56-123">选择**从服务器池中选择服务器**，选择所需的服务器，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-123">Select **Select a server from the server pool**, select the desired server, and select **Next**.</span></span> <span data-ttu-id="81c56-124">**服务器选择**窗口中列出了使用已添加的服务器**添加服务器**中**服务器管理器**。</span><span class="sxs-lookup"><span data-stu-id="81c56-124">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="81c56-125">默认情况下，它将选择本地服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-125">By default, it selects the local server.</span></span>  
  
7.  <span data-ttu-id="81c56-126">在中**服务器角色**，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-126">In **Server Roles**, select **Next**.</span></span>  
  
8.  <span data-ttu-id="81c56-127">在中**功能**，检查**SMTP 服务器**。</span><span class="sxs-lookup"><span data-stu-id="81c56-127">In **Features**, check **SMTP Server**.</span></span> <span data-ttu-id="81c56-128">如果系统提示，请选择**添加功能**。</span><span class="sxs-lookup"><span data-stu-id="81c56-128">If prompted, select **Add Features**.</span></span> <span data-ttu-id="81c56-129">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="81c56-129">Select **Next**.</span></span>  
  
9. <span data-ttu-id="81c56-130">在中**确认**，选择**如果需要自动重新启动目标服务器**，然后选择**安装**。</span><span class="sxs-lookup"><span data-stu-id="81c56-130">In **Confirmation**, select **Restart the destination server automatically if required**, and select **Install**.</span></span> <span data-ttu-id="81c56-131">完成后，选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="81c56-131">When complete, select **Close**.</span></span>  

### <a name="configure-the-smtp-server"></a><span data-ttu-id="81c56-132">配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-132">Configure the SMTP Server</span></span>  
 <span data-ttu-id="81c56-133">以下步骤配置 SMTP 虚拟服务器使用 IIS 6.0 管理器：</span><span class="sxs-lookup"><span data-stu-id="81c56-133">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="81c56-134">打开 IIS 管理器：在入门中，搜索**inetmgr6.exe**，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="81c56-134">Open the IIS Manager: In Start, search for **inetmgr6.exe**, and open it.</span></span>  
  
2.  <span data-ttu-id="81c56-135">展开计算机名称。</span><span class="sxs-lookup"><span data-stu-id="81c56-135">Expand the computer name.</span></span> <span data-ttu-id="81c56-136">右键单击 **[SMTP 虚拟服务器 #1]**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="81c56-136">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="81c56-137">在中**访问**选项卡上，选择**中继**按钮。</span><span class="sxs-lookup"><span data-stu-id="81c56-137">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="81c56-138">选择 **添加** 。</span><span class="sxs-lookup"><span data-stu-id="81c56-138">Select **Add**.</span></span> <span data-ttu-id="81c56-139">有关**台计算机**，输入`127.0.0.1`，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="81c56-139">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="81c56-140">通过添加 127.0.0.1，我们允许本地服务器从此 SMTP 服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="81c56-140">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="81c56-141">如果希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="81c56-141">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="81c56-142">在中**交付**选项卡上，选择**出站安全**。</span><span class="sxs-lookup"><span data-stu-id="81c56-142">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="81c56-143">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="81c56-143">Choose from the following:</span></span>  
  
     <span data-ttu-id="81c56-144">**匿名访问**:帐户名或密码不是必需的。</span><span class="sxs-lookup"><span data-stu-id="81c56-144">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="81c56-145">此选项将禁用 SMTP 服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-145">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="81c56-146">**基本身份验证**:帐户名称和密码以明文形式发送要连接的服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-146">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="81c56-147">你输入此帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="81c56-147">This account you enter transmits the e-mails.</span></span> <span data-ttu-id="81c56-148">将电子邮件发送到个人帐户或 Exchange 帐户时，可以选择基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-148">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="81c56-149">因为凭据将以明文形式传递，建议启用**TLS 加密**。</span><span class="sxs-lookup"><span data-stu-id="81c56-149">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="81c56-150">**集成 Windows 身份验证**:使用 Windows 域帐户名和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-150">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="81c56-151">你输入的帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="81c56-151">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="81c56-152">**TLS 加密**:与 SSL 相似，TLS 用于保护安全连接。</span><span class="sxs-lookup"><span data-stu-id="81c56-152">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="81c56-153">需要有效的 SSL 服务器证书安装在此服务器上。</span><span class="sxs-lookup"><span data-stu-id="81c56-153">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="81c56-154">若要使用个人电子邮件帐户，包括 Exchange 帐户，测试核心 SMTP 功能选择**匿名访问**。</span><span class="sxs-lookup"><span data-stu-id="81c56-154">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="81c56-155">选择基本身份验证后，SMTP 使用 AUTH 命令。</span><span class="sxs-lookup"><span data-stu-id="81c56-155">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="81c56-156">某些电子邮件提供商由于 AUTH 命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="81c56-156">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="81c56-157">如果 AUTH 命令失败，则可能在 SMTP 服务器上的 Windows 事件日志中记录错误。</span><span class="sxs-lookup"><span data-stu-id="81c56-157">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="81c56-158">在中**交付**选项卡上，选择**的出站连接**。</span><span class="sxs-lookup"><span data-stu-id="81c56-158">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="81c56-159">默认情况下，TCP 端口为 25。</span><span class="sxs-lookup"><span data-stu-id="81c56-159">By default, the TCP Port is 25.</span></span> <span data-ttu-id="81c56-160">如果在防火墙内打开，则可以输入其他端口。</span><span class="sxs-lookup"><span data-stu-id="81c56-160">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="81c56-161">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="81c56-161">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="81c56-162">在中**交付**选项卡上，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="81c56-162">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="81c56-163">默认情况下**完全限定域名**会列出本地服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-163">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="81c56-164">Internet 提供商，根据**智能主机**属性可以留空。</span><span class="sxs-lookup"><span data-stu-id="81c56-164">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="81c56-165">您可能需要与 internet 提供商联系以确认是否需要智能主机。</span><span class="sxs-lookup"><span data-stu-id="81c56-165">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="81c56-166">否则，可能无法输入 smtp。*EMailProvider*。 com。</span><span class="sxs-lookup"><span data-stu-id="81c56-166">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81c56-167">一个**智能主机**，也称为中继主机是专用的服务器将 Exchange Server 用于路由所有传出消息。</span><span class="sxs-lookup"><span data-stu-id="81c56-167">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="81c56-168">当**智能主机**收到消息之后，**智能主机**将消息转发到远程域。</span><span class="sxs-lookup"><span data-stu-id="81c56-168">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="81c56-169">目标**智能主机**是提高 Exchange Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="81c56-169">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="81c56-170">Exchange Server 仅将传输到智能主机;而不是反复联系远程域，直至建立连接。</span><span class="sxs-lookup"><span data-stu-id="81c56-170">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="81c56-171">选择**确定**关闭所有窗口。</span><span class="sxs-lookup"><span data-stu-id="81c56-171">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="81c56-172">重新启动 SMTP 服务器：右键单击 **[SMTP 虚拟服务器 #1]**，选择**停止**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="81c56-172">Restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span> <span data-ttu-id="81c56-173">重启才能应用 SMTP 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="81c56-173">A restart is needed to apply the SMTP Server settings.</span></span> 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a><span data-ttu-id="81c56-174">Windows Server 2008 R2:安装和配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-174">Windows Server 2008 R2: Install and Configure SMTP Server</span></span>  
  
### <a name="install-smtp-server"></a><span data-ttu-id="81c56-175">安装 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-175">Install SMTP Server</span></span>  
 <span data-ttu-id="81c56-176">以下步骤安装 SMTP 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="81c56-176">The following steps install the SMTP Server feature:</span></span>  
  
1.  <span data-ttu-id="81c56-177">在中**服务器管理器**，选择**功能**，然后选择**添加功能**。</span><span class="sxs-lookup"><span data-stu-id="81c56-177">In **Server Manager**, select **Features**, and select **Add Features**.</span></span>  
  
3.  <span data-ttu-id="81c56-178">在中**添加功能**，选择**SMTP 服务器**。</span><span class="sxs-lookup"><span data-stu-id="81c56-178">In **Add Features**, select **SMTP Server**.</span></span> <span data-ttu-id="81c56-179">如果系统提示，请选择**添加所需的角色服务**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-179">If prompted, select **Add Required Role Services**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="81c56-180">通过选择继续进行安装**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81c56-180">Continue with the installation by selecting **Next**.</span></span>  
  
5.  <span data-ttu-id="81c56-181">在中**确认安装选择**窗口中，选择**安装**。</span><span class="sxs-lookup"><span data-stu-id="81c56-181">In the **Confirm Installation Selections** window, select **Install**.</span></span> <span data-ttu-id="81c56-182">完成后，选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="81c56-182">When complete, select **Close**.</span></span>  
  
### <a name="configure-the-smtp-server"></a><span data-ttu-id="81c56-183">配置 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-183">Configure the SMTP Server</span></span>  
 <span data-ttu-id="81c56-184">以下步骤配置 SMTP 虚拟服务器使用 IIS 6.0 管理器：</span><span class="sxs-lookup"><span data-stu-id="81c56-184">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="81c56-185">打开 IIS 6.0 管理器：在中**启动**，搜索**IIS**，然后选择**Internet 信息服务 (IIS) 6.0 管理器**。</span><span class="sxs-lookup"><span data-stu-id="81c56-185">Open the IIS 6.0 Manager: In **Start**, search for **IIS**, and select **Internet Information Services (IIS) 6.0 Manager**.</span></span>  
  
2.  <span data-ttu-id="81c56-186">展开计算机名称。</span><span class="sxs-lookup"><span data-stu-id="81c56-186">Expand the computer name.</span></span> <span data-ttu-id="81c56-187">右键单击 **[SMTP 虚拟服务器 #1]**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="81c56-187">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="81c56-188">在中**访问**选项卡上，选择**中继**按钮。</span><span class="sxs-lookup"><span data-stu-id="81c56-188">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="81c56-189">选择 **添加** 。</span><span class="sxs-lookup"><span data-stu-id="81c56-189">Select **Add**.</span></span> <span data-ttu-id="81c56-190">有关**台计算机**，输入`127.0.0.1`，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="81c56-190">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="81c56-191">通过添加 127.0.0.1，我们允许本地服务器从此 SMTP 服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="81c56-191">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="81c56-192">如果希望其他计算机从此 SMTP 服务器发送消息，请输入其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="81c56-192">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="81c56-193">在中**交付**选项卡上，选择**出站安全**。</span><span class="sxs-lookup"><span data-stu-id="81c56-193">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="81c56-194">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="81c56-194">Choose from the following:</span></span>  
  
     <span data-ttu-id="81c56-195">**匿名访问**:帐户名或密码不是必需的。</span><span class="sxs-lookup"><span data-stu-id="81c56-195">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="81c56-196">此选项将禁用 SMTP 服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-196">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="81c56-197">**基本身份验证**:帐户名称和密码以明文形式发送要连接的服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-197">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="81c56-198">将电子邮件发送到个人帐户或 Exchange 帐户时，可以选择基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-198">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="81c56-199">因为凭据将以明文形式传递，建议启用**TLS 加密**。</span><span class="sxs-lookup"><span data-stu-id="81c56-199">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="81c56-200">**集成 Windows 身份验证**:使用 Windows 域帐户名和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="81c56-200">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="81c56-201">你输入的帐户用于传输电子邮件。</span><span class="sxs-lookup"><span data-stu-id="81c56-201">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="81c56-202">**TLS 加密**:与 SSL 相似，TLS 用于保护安全连接。</span><span class="sxs-lookup"><span data-stu-id="81c56-202">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="81c56-203">需要有效的 SSL 服务器证书安装在此服务器上。</span><span class="sxs-lookup"><span data-stu-id="81c56-203">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="81c56-204">若要使用个人电子邮件帐户，包括 Exchange 帐户，测试核心 SMTP 功能选择**匿名访问**。</span><span class="sxs-lookup"><span data-stu-id="81c56-204">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="81c56-205">选择基本身份验证后，SMTP 使用 AUTH 命令。</span><span class="sxs-lookup"><span data-stu-id="81c56-205">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="81c56-206">某些电子邮件提供商由于 AUTH 命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="81c56-206">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="81c56-207">如果 AUTH 命令失败，则可能在 SMTP 服务器上的 Windows 事件日志中记录错误。</span><span class="sxs-lookup"><span data-stu-id="81c56-207">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="81c56-208">在中**交付**选项卡上，选择**的出站连接**。</span><span class="sxs-lookup"><span data-stu-id="81c56-208">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="81c56-209">默认情况下，TCP 端口为 25。</span><span class="sxs-lookup"><span data-stu-id="81c56-209">By default, the TCP Port is 25.</span></span> <span data-ttu-id="81c56-210">如果在防火墙内打开，则可以输入其他端口。</span><span class="sxs-lookup"><span data-stu-id="81c56-210">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="81c56-211">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="81c56-211">Select **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="81c56-212">TCP 端口可用于入站的连接和出站连接。</span><span class="sxs-lookup"><span data-stu-id="81c56-212">The TCP Port can be used for Inbound connections and Outbound connections.</span></span>  
  
7.  <span data-ttu-id="81c56-213">在中**交付**选项卡上，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="81c56-213">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="81c56-214">默认情况下**完全限定域名**会列出本地服务器。</span><span class="sxs-lookup"><span data-stu-id="81c56-214">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="81c56-215">Internet 提供商，根据**智能主机**属性可以留空。</span><span class="sxs-lookup"><span data-stu-id="81c56-215">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="81c56-216">您可能需要与 internet 提供商联系以确认是否需要智能主机。</span><span class="sxs-lookup"><span data-stu-id="81c56-216">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="81c56-217">否则，可能无法输入 smtp。*EMailProvider*。 com。</span><span class="sxs-lookup"><span data-stu-id="81c56-217">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81c56-218">一个**智能主机**，也称为中继主机是专用的服务器将 Exchange Server 用于路由所有传出消息。</span><span class="sxs-lookup"><span data-stu-id="81c56-218">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="81c56-219">当**智能主机**收到消息之后，**智能主机**将消息转发到远程域。</span><span class="sxs-lookup"><span data-stu-id="81c56-219">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="81c56-220">目标**智能主机**是提高 Exchange Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="81c56-220">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="81c56-221">Exchange Server 仅将传输到智能主机;而不是反复联系远程域，直至建立连接。</span><span class="sxs-lookup"><span data-stu-id="81c56-221">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="81c56-222">选择**确定**关闭所有窗口。</span><span class="sxs-lookup"><span data-stu-id="81c56-222">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="81c56-223">重启才能应用 SMTP 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="81c56-223">A restart is needed to apply the SMTP Server settings.</span></span> <span data-ttu-id="81c56-224">若要重新启动 SMTP 服务器：右键单击 **[SMTP 虚拟服务器 #1]**，选择**停止**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="81c56-224">To restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span>  
  
  
## <a name="test-the-smtp-server"></a><span data-ttu-id="81c56-225">测试 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="81c56-225">Test the SMTP Server</span></span>  
 <span data-ttu-id="81c56-226">可以使用 Telnet 测试 SMTP 服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="81c56-226">Telnet can be used to test the SMTP Server configuration.</span></span> <span data-ttu-id="81c56-227">以下步骤将发送到电子邮件地址配置的 SMTP 服务器使用的消息。</span><span class="sxs-lookup"><span data-stu-id="81c56-227">The following steps send a message using your configured SMTP Server to an e-mail address.</span></span> <span data-ttu-id="81c56-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) 提供了 telnet 命令的说明。</span><span class="sxs-lookup"><span data-stu-id="81c56-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) provides descriptions of the telnet commands.</span></span>  
  
1. <span data-ttu-id="81c56-229">以管理员身份打开命令窗口。</span><span class="sxs-lookup"><span data-stu-id="81c56-229">Open a command window as Administrator.</span></span>
  
2. <span data-ttu-id="81c56-230">在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="81c56-230">In the command prompt, type:</span></span>  
  
    `telnet localhost 25`  
  
    <span data-ttu-id="81c56-231">如果未安装 telnet，请通过键入来安装它：</span><span class="sxs-lookup"><span data-stu-id="81c56-231">If telnet is not installed, install it by typing:</span></span>  
  
    `pkgmgr /iu:"TelnetClient"`  
  
3. <span data-ttu-id="81c56-232">通过键入启动通信：</span><span class="sxs-lookup"><span data-stu-id="81c56-232">Start communication by typing:</span></span>  
  
    `EHLO server`  
  
4. <span data-ttu-id="81c56-233">输入的发件人地址：</span><span class="sxs-lookup"><span data-stu-id="81c56-233">Enter the Mail From address:</span></span>  
  
    `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="81c56-234">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="81c56-234">For example, enter:</span></span>  
  
    `MAIL FROM: EmailAddress@outlook.com`  
  
5. <span data-ttu-id="81c56-235">输入发送到地址：</span><span class="sxs-lookup"><span data-stu-id="81c56-235">Enter the Mail To address:</span></span>  
  
    `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="81c56-236">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="81c56-236">For example, enter:</span></span>  
  
    `RCPT TO: EmailAddress@outlook.com`  
  
6. <span data-ttu-id="81c56-237">告知你已准备好发送数据，通过键入 SMTP 服务器：</span><span class="sxs-lookup"><span data-stu-id="81c56-237">Tell the SMTP Server you are ready to send data by typing:</span></span>  
  
    `DATA`  
  
7. <span data-ttu-id="81c56-238">通过键入输入主题：</span><span class="sxs-lookup"><span data-stu-id="81c56-238">Enter the Subject by typing:</span></span>  
  
    `Subject: Test Message`  
  
8. <span data-ttu-id="81c56-239">按 Enter 两次。</span><span class="sxs-lookup"><span data-stu-id="81c56-239">Hit Enter twice.</span></span>  
  
9. <span data-ttu-id="81c56-240">通过键入来输入消息正文：</span><span class="sxs-lookup"><span data-stu-id="81c56-240">Enter the message body by typing:</span></span>  
  
     `This is the message body of the test message.`  
  
10. <span data-ttu-id="81c56-241">按 Enter，键入句点 （.），并按 Enter。</span><span class="sxs-lookup"><span data-stu-id="81c56-241">Hit Enter, type a period (.), and hit Enter.</span></span>  
  
    <span data-ttu-id="81c56-242">检查电子邮件的 RCPT TO 地址。</span><span class="sxs-lookup"><span data-stu-id="81c56-242">Check the RCPT TO address for the e-mail message.</span></span> <span data-ttu-id="81c56-243">如果电子邮件未送达 （检查收件箱和垃圾邮件文件夹），则消息未成功发送，而可能驻留在 SMTP 队列文件夹中 (C:\inetpub\mailroot\Queue)。</span><span class="sxs-lookup"><span data-stu-id="81c56-243">If the e-mail is not delivered (Check your Inbox and Spam folder), then the message was not successfully sent, and may reside in the SMTP Queue folder (C:\inetpub\mailroot\Queue).</span></span>  
  