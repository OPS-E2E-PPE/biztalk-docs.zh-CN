---
title: 将主机实例添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ba10a6-c5e7-4dec-98f1-4e6ba44c2851
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 072aa728eddf99c62fe83ed19e3fef82ba3f612a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387420"
---
# <a name="add-a-host-instance"></a><span data-ttu-id="c15db-102">添加主机实例</span><span class="sxs-lookup"><span data-stu-id="c15db-102">Add a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="c15db-103">概述</span><span class="sxs-lookup"><span data-stu-id="c15db-103">Overview</span></span>
<span data-ttu-id="c15db-104">可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来添加主机实例。</span><span class="sxs-lookup"><span data-stu-id="c15db-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console or Windows Management Instrumentation (WMI) to add host instances.</span></span> <span data-ttu-id="c15db-105">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您可以仅将主机实例添加到一台服务器一次。</span><span class="sxs-lookup"><span data-stu-id="c15db-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can only add a host instance to one server at a time.</span></span> <span data-ttu-id="c15db-106">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="c15db-106">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="c15db-107">有关使用 WMI 添加主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c15db-107">For information about using WMI to add a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="c15db-108">添加主机实例映射到 BizTalk Server 的实例在给定主机的实例。</span><span class="sxs-lookup"><span data-stu-id="c15db-108">Adding a host instance maps the instance of a given host to an instance of BizTalk Server.</span></span> <span data-ttu-id="c15db-109">如果您有必须修复现有主机实例，可以更新主机实例属性。</span><span class="sxs-lookup"><span data-stu-id="c15db-109">If you have an existing host instance that you must repair, you can update the host instance properties.</span></span> <span data-ttu-id="c15db-110">必须先停止现有的主机实例，才能再次添加。</span><span class="sxs-lookup"><span data-stu-id="c15db-110">You must stop an existing host instance before you can add it again.</span></span> <span data-ttu-id="c15db-111">有关停止主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="c15db-111">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15db-112">如果你想要创建更多 26 主机实例，必须按照知识库文章 184802，"User32.dll 或 Kernel32.dll 无法初始化，"可在中的说明[ http://go.microsoft.com/fwlink/?LinkId=26176 ](http://go.microsoft.com/fwlink/?LinkId=26176)。</span><span class="sxs-lookup"><span data-stu-id="c15db-112">If you want to create more that 26 host instances, you must follow the instructions in Knowledge Base article 184802, "User32.dll or Kernel32.dll Fails to Initialize," which is available at [http://go.microsoft.com/fwlink/?LinkId=26176](http://go.microsoft.com/fwlink/?LinkId=26176).</span></span> <span data-ttu-id="c15db-113">如果应用此知识库文章中的建议后，您需要其他主机实例，可以尝试减少可为每个 BTSNTSvc 服务实例的内存量。</span><span class="sxs-lookup"><span data-stu-id="c15db-113">If you require additional host instances after you apply the recommendations in this Knowledge Base article, you can try reducing the amount of memory available for each instance of the BTSNTSvc service.</span></span> <span data-ttu-id="c15db-114">这将提供额外的内存来创建更多实例。</span><span class="sxs-lookup"><span data-stu-id="c15db-114">This will provide additional memory necessary to create more instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15db-115">服务帐户将自动被授予日志上作为服务安装主机实例的服务器上的权限。</span><span class="sxs-lookup"><span data-stu-id="c15db-115">The service account will automatically be granted log on as service permissions on the server where the host instance is installed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c15db-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="c15db-116">Prerequisites</span></span>  
 <span data-ttu-id="c15db-117">若要执行此过程，必须以 Administrators 组和 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c15db-117">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="c15db-118">此外，您还必须是 db_securityadmin SQL Server 数据库角色和以下数据库所在的服务器上的 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="c15db-118">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="c15db-119">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="c15db-119">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="c15db-120">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="c15db-120">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="c15db-121">BizTalk MessageBox (BizTalkMsgBoxDb) （全部）</span><span class="sxs-lookup"><span data-stu-id="c15db-121">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="c15db-122">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="c15db-122">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="c15db-123">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="c15db-123">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c15db-124">我们建议使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 脚本更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="c15db-124">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="c15db-125">这可确保 BizTalk Server 可以更新 BizTalk Server 数据库中的帐户信息并保持数据库和同步的主机实例之间的安全配置。</span><span class="sxs-lookup"><span data-stu-id="c15db-125">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="c15db-126">步骤</span><span class="sxs-lookup"><span data-stu-id="c15db-126">Steps</span></span>
  
1. <span data-ttu-id="c15db-127">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c15db-127">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c15db-128">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 BizTalk 组，然后依次**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="c15db-128">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then click **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="c15db-129">右键单击**主机实例**，单击**新建**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="c15db-129">Right-click **Host Instances**, click **New**, and then click **Host Instance**.</span></span>  
  
4. <span data-ttu-id="c15db-130">在中**主机实例属性**对话框中，执行以下操作，然后依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="c15db-130">In the **Host Instance Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="c15db-131">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c15db-131">Use this</span></span>|<span data-ttu-id="c15db-132">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c15db-132">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="c15db-133">**主机名**</span><span class="sxs-lookup"><span data-stu-id="c15db-133">**Host name**</span></span>|<span data-ttu-id="c15db-134">显示与所选服务器关联的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="c15db-134">Displays the name of the host associated with the selected server.</span></span>|  
   |<span data-ttu-id="c15db-135">**Server**</span><span class="sxs-lookup"><span data-stu-id="c15db-135">**Server**</span></span>|<span data-ttu-id="c15db-136">显示与所选主机关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="c15db-136">Displays the server associated with the selected host.</span></span>|  
   |<span data-ttu-id="c15db-137">**登录**</span><span class="sxs-lookup"><span data-stu-id="c15db-137">**Logon**</span></span>|<span data-ttu-id="c15db-138">显示新的主机实例将运行的服务帐户的帐户名。</span><span class="sxs-lookup"><span data-stu-id="c15db-138">Displays the account name of the new service account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="c15db-139">**配置**</span><span class="sxs-lookup"><span data-stu-id="c15db-139">**Configure**</span></span>|<span data-ttu-id="c15db-140">单击此项可显示**登录凭据**对话框框中，您可以在其中输入帐户名称和主机实例将运行的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="c15db-140">Click to display the **Logon Credentials** dialog box, where you can enter the account name and password of the account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="c15db-141">**禁止主机实例启动**</span><span class="sxs-lookup"><span data-stu-id="c15db-141">**Disable host instance from starting**</span></span>|<span data-ttu-id="c15db-142">选择此复选框可从所选主机的状态更改为已禁用已启用。</span><span class="sxs-lookup"><span data-stu-id="c15db-142">Select this check box to change the status of the selected host from enabled to disabled.</span></span> <span data-ttu-id="c15db-143">如果您不希望主机实例，若要开始，但要保留其设置，禁用主机实例非常有用。</span><span class="sxs-lookup"><span data-stu-id="c15db-143">Disabling a host instance is useful if you do not want the host instance to start, but you do want to preserve its settings.</span></span>|  
  
   <span data-ttu-id="c15db-144">安装主机实例后，您必须启动它，以便它可以将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="c15db-144">After you install a host instance, you must start it so that it can route messages to the MessageBox databases.</span></span> <span data-ttu-id="c15db-145">有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="c15db-145">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c15db-146">已知问题</span><span class="sxs-lookup"><span data-stu-id="c15db-146">Known Issues</span></span>  
  
#### <a name="a-biztalk-host-instance-is-created-with-a-status-of-uninstall-failed-if-the-designated-biztalk-server-runtime-computer-is-not-available-during-host-instance-creation"></a><span data-ttu-id="c15db-147">如果主机实例创建期间指定的 BizTalk Server 运行时计算机不可用，创建一个 BizTalk 主机实例的状态为"卸载失败"</span><span class="sxs-lookup"><span data-stu-id="c15db-147">A BizTalk Host instance is created with a status of "Uninstall failed" if the designated BizTalk Server runtime computer is not available during host instance creation</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c15db-148">问题</span><span class="sxs-lookup"><span data-stu-id="c15db-148">Problem</span></span>  
 <span data-ttu-id="c15db-149">如果在对远程计算机上安装 BizTalk 管理控制台[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，则可以尝试在远程数据库上创建主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机即使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可用。</span><span class="sxs-lookup"><span data-stu-id="c15db-149">If the BizTalk Administration Console is installed on a machine that is remote to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computer, it is possible to attempt to create a host instance on the remote [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer even if the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is unavailable.</span></span>  
  
 <span data-ttu-id="c15db-150">如果你尝试创建 BizTalk 主机的实例上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可用，并显示以下错误消息对话框中显示：</span><span class="sxs-lookup"><span data-stu-id="c15db-150">If you attempt to create an instance of a BizTalk host on a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer that is unavailable, a dialog box with the following error message is displayed:</span></span>  
  
 <span data-ttu-id="c15db-151">主机实例的安装\<*主机名*\>服务器上\<*服务器名称*\>失败。</span><span class="sxs-lookup"><span data-stu-id="c15db-151">Installation of instace of host \<*host name*\> on server \<*server name*\> failed.</span></span>  
  
 <span data-ttu-id="c15db-152">其他信息：</span><span class="sxs-lookup"><span data-stu-id="c15db-152">Additional information:</span></span>  
  
 <span data-ttu-id="c15db-153">RPC 服务器不可用。</span><span class="sxs-lookup"><span data-stu-id="c15db-153">The RPC server is unavailable.</span></span> <span data-ttu-id="c15db-154">(WinMgmt)</span><span class="sxs-lookup"><span data-stu-id="c15db-154">(WinMgmt)</span></span>  
  
 <span data-ttu-id="c15db-155">当您单击确定以关闭该对话框时，显示一个对话框，并显示以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="c15db-155">When you click OK to dismiss the dialog box, a dialog box with the following error message is displayed:</span></span>  
  
 <span data-ttu-id="c15db-156">清理已中止的主机安装\<*主机名*\>服务器上\<*服务器名称*\>失败。</span><span class="sxs-lookup"><span data-stu-id="c15db-156">Cleaning up aborted installation of host \<*host name*\> on server \<*server name*\> failed.</span></span>  
  
 <span data-ttu-id="c15db-157">其他信息：</span><span class="sxs-lookup"><span data-stu-id="c15db-157">Additional information:</span></span>  
  
 <span data-ttu-id="c15db-158">故障发生时正在删除 Windows NT 服务 BTSSvc {*\<GUID\>*}。</span><span class="sxs-lookup"><span data-stu-id="c15db-158">A failure occurred when deleting the Windows NT service BTSSvc{*\<GUID\>*}.</span></span> <span data-ttu-id="c15db-159">(WinMgmt)</span><span class="sxs-lookup"><span data-stu-id="c15db-159">(WinMgmt)</span></span>  
  
 <span data-ttu-id="c15db-160">当您单击**确定**以关闭此对话框中，会显示在 BizTalk 管理控制台中使用的 BizTalk 主机实例**状态**的**卸载失败**.</span><span class="sxs-lookup"><span data-stu-id="c15db-160">When you click **OK** to dismiss this dialog box, the instance of the BizTalk host will be visible in the BizTalk Administration Console with a **Status** of **Uninstall failed**.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c15db-161">原因</span><span class="sxs-lookup"><span data-stu-id="c15db-161">Cause</span></span>  
 <span data-ttu-id="c15db-162">安装主机实例之前创建的主机实例时，BizTalk 管理数据库中生成一个条目拖到指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="c15db-162">When a host instance is created, an entry is made in the BizTalk Management database before the host instance is installed onto the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="c15db-163">如果安装主机实例上指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机发生故障，BizTalk 管理程序将尝试卸载主机实例，但由于指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可作为卸载失败嗯。</span><span class="sxs-lookup"><span data-stu-id="c15db-163">If the installation of the host instance onto the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer fails, the BizTalk Administration program will attempt to uninstall the host instance but since the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is unavailable the uninstall fails as well.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c15db-164">解决方法</span><span class="sxs-lookup"><span data-stu-id="c15db-164">Resolution</span></span>  
 <span data-ttu-id="c15db-165">如果在状态为在 BizTalk 管理控制台中创建的 BizTalk 主机实例**卸载失败**、 删除主机实例和指定的 BizTalk Server 计算机变为可用后重新创建主机实例。</span><span class="sxs-lookup"><span data-stu-id="c15db-165">If a BizTalk host instance is created in the BizTalk Admininstration Console with a status of **Uninstall failed**, delete the host instance and recreate the host instance after the designated BizTalk Server computer becomes available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15db-166">如果 BizTalk 管理控制台中创建 BizTalk 主机实例时**状态**的**卸载失败**主机实例之后将不可功能甚至指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机再次变为可用。</span><span class="sxs-lookup"><span data-stu-id="c15db-166">If a BizTalk host instance is created in the BizTalk Administration Console with a **Status** of **Uninstall failed** the host instance will not be functional even after the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer becomes available again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15db-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="c15db-167">See Also</span></span>  
 <span data-ttu-id="c15db-168">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="c15db-168">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="c15db-169">[启动主机实例](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c15db-169">[Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="c15db-170">[停止主机实例](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c15db-170">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="c15db-171">[删除主机实例](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c15db-171">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="c15db-172">修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="c15db-172">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)