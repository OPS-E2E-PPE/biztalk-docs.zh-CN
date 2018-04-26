---
title: 设置和安装 BizTalk Server 2016 系统必备组件 |Microsoft 文档
description: 安装和配置的所需的软件和设置 BizTalk Server 2016 的分步说明
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: 11
ms.author: mandia
ms.openlocfilehash: 666cddaab4d23fa69b0ae488f665e2eda5182c05
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a><span data-ttu-id="9b22a-103">设置和安装 BizTalk Server 2016 的必备组件</span><span class="sxs-lookup"><span data-stu-id="9b22a-103">Set up and install prerequisites for BizTalk Server 2016</span></span>
<span data-ttu-id="9b22a-104">设置服务器，然后安装和配置软件必备组件。</span><span class="sxs-lookup"><span data-stu-id="9b22a-104">Set up the server, and install and configure the software prerequisites.</span></span>

## <a name="join-the-administrators-group"></a><span data-ttu-id="9b22a-105">加入管理员组</span><span class="sxs-lookup"><span data-stu-id="9b22a-105">Join the Administrators Group</span></span>
<span data-ttu-id="9b22a-106">若要安装并配置 BizTalk Server，在本地计算机上使用管理员帐户登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="9b22a-106">To install and configure BizTalk Server, sign in to the server using an administrator account on the local computer.</span></span> <span data-ttu-id="9b22a-107">向本地管理员组添加任何管理 BizTalk Server 的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="9b22a-107">Add any user accounts that are administering the BizTalk Server to the local Administrators group:</span></span>

1.  <span data-ttu-id="9b22a-108">在开始菜单中，打开“计算机管理”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-108">In the Start menu, open **Computer Management**.</span></span>

    * <span data-ttu-id="9b22a-109">或者，打开“管理工具”，然后选择“计算机管理”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-109">Or, open **Administrative Tools**, and then select **Computer Management**.</span></span>
    * <span data-ttu-id="9b22a-110">或者，打开“服务器管理器”，选择“工具”，然后选择“计算机管理”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-110">Or, open **Server Manager**, select **Tools**, and then select **Computer Management**.</span></span>
  
2.  <span data-ttu-id="9b22a-111">展开“本地用户和组”，然后选择“组”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-111">Expand **Local Users and Groups**, and select **Groups**.</span></span>
3.  <span data-ttu-id="9b22a-112">右键单击“管理员”组，然后选择“添加到组”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-112">Right-click the **Administrators** group, and select **Add to Group**.</span></span> <span data-ttu-id="9b22a-113">**添加**帐户，然后选择“确定”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="9b22a-113">**Add** your accounts, and select **OK** to save your changes.</span></span> 

## <a name="change-the-computer-name-optional"></a><span data-ttu-id="9b22a-114">更改计算机名称 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-114">Change the computer name (optional)</span></span>
<span data-ttu-id="9b22a-115">如果您的计算机名称的长度超过 15 个字符，BizTalk Server 配置将失败。</span><span class="sxs-lookup"><span data-stu-id="9b22a-115">If your computer name is longer than 15 characters, then BizTalk Server configuration fails.</span></span> <span data-ttu-id="9b22a-116">若要将计算机名称更改为少于 15 个字符：</span><span class="sxs-lookup"><span data-stu-id="9b22a-116">To change the computer name to less than 15 characters:</span></span>

1.  <span data-ttu-id="9b22a-117">在“服务器管理器” > “仪表板”中，选择“本地服务器”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-117">In **Server Manager** > **Dashboard**, select **Local Server**.</span></span> 
2.  <span data-ttu-id="9b22a-118">在“属性”中，选择“计算机名称”属性以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="9b22a-118">In **Properties**, select the Computer name property to change it.</span></span>
3. <span data-ttu-id="9b22a-119">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-119">Restart the computer.</span></span> 

<span data-ttu-id="9b22a-120">**另请参阅**：Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)</span><span class="sxs-lookup"><span data-stu-id="9b22a-120">**SEE ALSO** : Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)</span></span>

## <a name="enable-network-dtc-access"></a><span data-ttu-id="9b22a-121">启用网络 DTC 访问</span><span class="sxs-lookup"><span data-stu-id="9b22a-121">Enable Network DTC Access</span></span>
<span data-ttu-id="9b22a-122">如果 BizTalk 和 SQL Server 安装在不同的计算机上，则对 BizTalk Server 和 SQL Server启用网络 DTC 访问。</span><span class="sxs-lookup"><span data-stu-id="9b22a-122">If BizTalk and SQL Server are installed on separate computers, then enable Network DTC Access on the BizTalk Server and the SQL Server.</span></span> 

1. <span data-ttu-id="9b22a-123">在“开始”菜单中，打开 "dcomcnfg"。</span><span class="sxs-lookup"><span data-stu-id="9b22a-123">In the Start menu, open "dcomcnfg".</span></span>

    * <span data-ttu-id="9b22a-124">或者，打开“管理工具”，然后选择“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-124">Or, open **Administrative Tools**, and then select **Component Services**.</span></span>
    * <span data-ttu-id="9b22a-125">或者，打开“服务器管理器”，选择“工具”，然后选择“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-125">Or, open **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>
  
2. <span data-ttu-id="9b22a-126">依次展开“组件服务”、“计算机”、“我的电脑”和“分布式事务处理协调器”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-126">Expand **Component Services**, expand **Computers**, expand **My Computer**,  and expand **Distributed Transaction Coordinator**.</span></span>
3. <span data-ttu-id="9b22a-127">右键单击“本地 DTC”，再选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-127">Right-click **Local DTC**, and select **Properties**.</span></span>
4. <span data-ttu-id="9b22a-128">转到“安全”选项卡，然后检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b22a-128">Go to the **Security** tab, and check the following:</span></span>  
    * <span data-ttu-id="9b22a-129">网络 DTC 访问</span><span class="sxs-lookup"><span data-stu-id="9b22a-129">Network DTC Access</span></span>
    * <span data-ttu-id="9b22a-130">允许入站</span><span class="sxs-lookup"><span data-stu-id="9b22a-130">Allow Inbound</span></span>
    * <span data-ttu-id="9b22a-131">允许出站</span><span class="sxs-lookup"><span data-stu-id="9b22a-131">Allow Outbound</span></span>
    * <span data-ttu-id="9b22a-132">不要求进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9b22a-132">No Authentication Required</span></span>
5. <span data-ttu-id="9b22a-133">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-133">Select **OK**.</span></span> <span data-ttu-id="9b22a-134">如果系统提示您重新启动 MS DTC，则选择**是**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-134">If prompted to restart MS DTC, select **Yes**.</span></span> 

<span data-ttu-id="9b22a-135">有关可能需要的其他设置，请参阅 [MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>

## <a name="configure-application-event-log-optional"></a><span data-ttu-id="9b22a-136">配置应用程序事件日志 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-136">Configure Application Event Log (optional)</span></span>

<span data-ttu-id="9b22a-137">BizTalk Server 安装程序会将事件记录保留在应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="9b22a-137">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="9b22a-138">日志中所需的空间量可能会超出其限制，具体取决于已安装的 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-138">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="9b22a-139">如果在应用程序事件日志在安装期间出现空间不足，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="9b22a-139">If the application event log runs out of space during the setup, the installation fails.</span></span> <span data-ttu-id="9b22a-140">更改“应用程序事件日志”设置可防止此故障。</span><span class="sxs-lookup"><span data-stu-id="9b22a-140">Changing the Application Event Log settings prevents this failure.</span></span>

1. <span data-ttu-id="9b22a-141">在“开始”菜单中，打开“事件查看器”：</span><span class="sxs-lookup"><span data-stu-id="9b22a-141">In the Start menu, open **Event Viewer**:</span></span>

    * <span data-ttu-id="9b22a-142">或者，打开“管理工具”，然后选择“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-142">Or, open **Administrative Tools**, and then select **Event Viewer**.</span></span>
    * <span data-ttu-id="9b22a-143">或者，打开“服务器管理器”，选择“工具”，然后选择“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-143">Or, open **Server Manager**, select **Tools**, and then select **Event Viewer**.</span></span>
  
2. <span data-ttu-id="9b22a-144">展开“Windows 日志”，右键单击“应用程序”，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-144">Expand **Windows Logs**, right-click **Application**, and then select **Properties**.</span></span> 
3. <span data-ttu-id="9b22a-145">若要确定可用空间，请比较“日志大小”和“最大日志大小”属性。</span><span class="sxs-lookup"><span data-stu-id="9b22a-145">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span> 

    * <span data-ttu-id="9b22a-146">若要添加空间，请在“日志最大大小”中输入一个更大的值。</span><span class="sxs-lookup"><span data-stu-id="9b22a-146">To add space, enter a higher number in **Maximum log size**.</span></span>
    * <span data-ttu-id="9b22a-147">若要在日志变满时启用对旧事件的覆盖功能，请选择“按需要覆盖事件”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-147">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>
    * <span data-ttu-id="9b22a-148">若要清除日志事件，请选择“清除日志”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-148">To clear the log events, select **Clear log**.</span></span>

4. <span data-ttu-id="9b22a-149">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-149">Select **OK**.</span></span>

## <a name="edge-cant-be-opened-optional"></a><span data-ttu-id="9b22a-150">无法打开边缘 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-150">Edge can’t be opened (optional)</span></span>

<span data-ttu-id="9b22a-151">使用 Edge 时，会显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="9b22a-151">When using Edge, the following message displays:</span></span>  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

<span data-ttu-id="9b22a-152">若要允许使用内置的管理员帐户打开 Edge：</span><span class="sxs-lookup"><span data-stu-id="9b22a-152">To allow Edge to open using the built-in administrator account:</span></span>

1. <span data-ttu-id="9b22a-153">在“开始”菜单中，打开“本地安全策略”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-153">In the Start menu, open **Local Security Policy**.</span></span> <span data-ttu-id="9b22a-154">或者，打开“服务器管理器”，选择“工具”，然后选择“本地安全策略”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-154">Or, open **Server Manager**, select **Tools**, and then select **Local Security Policy**.</span></span>
2.  <span data-ttu-id="9b22a-155">展开“本地策略”，然后选择“安全选项”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-155">Expand **Local Policies**, and select **Security Options**.</span></span> 
3.  <span data-ttu-id="9b22a-156">转到“用户帐户控制：内置管理员帐户的管理员批准模式”策略，然后“启用”该策略。</span><span class="sxs-lookup"><span data-stu-id="9b22a-156">Go to the **User Account Control: Admin Approval Mode for the Built-in Administrator account** policy, and **Enable** the policy.</span></span> 
4. <span data-ttu-id="9b22a-157">选择“确定”，然后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-157">Select **OK**, and restart your computer.</span></span>

## <a name="install-windows-updates"></a><span data-ttu-id="9b22a-158">安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="9b22a-158">Install Windows Updates</span></span>

<span data-ttu-id="9b22a-159">请务必安装 Windows 最新重要更新。</span><span class="sxs-lookup"><span data-stu-id="9b22a-159">Be sure to install the latest critical Windows updates.</span></span> 

1. <span data-ttu-id="9b22a-160">在“开始”菜单上，打开“Windows 更新”，然后检查更新。</span><span class="sxs-lookup"><span data-stu-id="9b22a-160">On the Start menu, open **Windows Updates**, and check for updates.</span></span> <span data-ttu-id="9b22a-161">还可以打开“设置”，然后选择“更新和安全”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-161">You can also open **Settings**, and select **Update and security**.</span></span>
2. <span data-ttu-id="9b22a-162">安装更新之后，你可能需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-162">After installing updates, you may need to restart the computer.</span></span>

## <a name="enable-iis"></a><span data-ttu-id="9b22a-163">启用 IIS</span><span class="sxs-lookup"><span data-stu-id="9b22a-163">Enable IIS</span></span>
<span data-ttu-id="9b22a-164">BizTalk Server 的下列功能需要 IIS：</span><span class="sxs-lookup"><span data-stu-id="9b22a-164">BizTalk Server requires IIS for the following features:</span></span>

- <span data-ttu-id="9b22a-165">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="9b22a-165">HTTP adapter</span></span>
- <span data-ttu-id="9b22a-166">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="9b22a-166">SOAP adapter</span></span>
- <span data-ttu-id="9b22a-167">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="9b22a-167">Windows SharePoint Services adapter</span></span>
- <span data-ttu-id="9b22a-168">安全套接字层 (SSL) 加密</span><span class="sxs-lookup"><span data-stu-id="9b22a-168">Secure Sockets Layer (SSL) encryption</span></span>
- <span data-ttu-id="9b22a-169">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="9b22a-169">BAM Portal</span></span>
- <span data-ttu-id="9b22a-170">EDI</span><span class="sxs-lookup"><span data-stu-id="9b22a-170">EDI</span></span>

<span data-ttu-id="9b22a-171">IIS 是作为“角色”或“功能”随附于操作系统，具体取决于 OS。</span><span class="sxs-lookup"><span data-stu-id="9b22a-171">IIS is included with the operating system as a **Role** or a **Feature**, depending on the OS.</span></span> <span data-ttu-id="9b22a-172">安装步骤：</span><span class="sxs-lookup"><span data-stu-id="9b22a-172">To install:</span></span>

1. <span data-ttu-id="9b22a-173">在“开始”菜单中，打开“打开或关闭 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-173">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="9b22a-174">或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-174">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="9b22a-175">选择“Internet Information Services”或“Web 服务器 (IIS)”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-175">Select **Internet Information Services** or **Web Server (IIS)**.</span></span> <span data-ttu-id="9b22a-176">除了已默认选中的选项之外，还应选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="9b22a-176">In addition to the default checked options, also select the following:</span></span> 

    <span data-ttu-id="9b22a-177">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="9b22a-177">**Windows 10**</span></span>
    - <span data-ttu-id="9b22a-178">在“Web 管理工具”中，还需检查：</span><span class="sxs-lookup"><span data-stu-id="9b22a-178">In **Web Management Tools**, also check:</span></span>  
        - <span data-ttu-id="9b22a-179">IIS 6 管理兼容性</span><span class="sxs-lookup"><span data-stu-id="9b22a-179">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="9b22a-180">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9b22a-180">IIS 6 Management Console</span></span>
        - <span data-ttu-id="9b22a-181">IIS 6 脚本工具（安装 adsutil.vbs）</span><span class="sxs-lookup"><span data-stu-id="9b22a-181">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>
        - <span data-ttu-id="9b22a-182">IIS 元数据库和 IIS 6 配置兼容性</span><span class="sxs-lookup"><span data-stu-id="9b22a-182">IIS Metabase and IIS 6 configuration compatibility</span></span>
        - <span data-ttu-id="9b22a-183">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9b22a-183">IIS Management Console</span></span>
    - <span data-ttu-id="9b22a-184">在“万维网服务”中，展开“安全性”，同时检查：</span><span class="sxs-lookup"><span data-stu-id="9b22a-184">In **World Wide Web Services**, expand **Security** and also check:</span></span>
        - <span data-ttu-id="9b22a-185">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="9b22a-185">Basic Authentication</span></span>
        - <span data-ttu-id="9b22a-186">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="9b22a-186">Windows Authentication</span></span>    

    <span data-ttu-id="9b22a-187">**Windows 服务器**</span><span class="sxs-lookup"><span data-stu-id="9b22a-187">**Windows Server**</span></span>
    - <span data-ttu-id="9b22a-188">在“安全性”中，还需检查：</span><span class="sxs-lookup"><span data-stu-id="9b22a-188">In **Security**, also check:</span></span> 
        - <span data-ttu-id="9b22a-189">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="9b22a-189">Basic Authentication</span></span>
        - <span data-ttu-id="9b22a-190">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="9b22a-190">Windows Authentication</span></span>    
    - <span data-ttu-id="9b22a-191">在“管理工具”中，还需检查：</span><span class="sxs-lookup"><span data-stu-id="9b22a-191">In **Management Tools**, also check:</span></span>  
        - <span data-ttu-id="9b22a-192">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9b22a-192">IIS Management Console</span></span>
        - <span data-ttu-id="9b22a-193">IIS 6 管理兼容性</span><span class="sxs-lookup"><span data-stu-id="9b22a-193">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="9b22a-194">IIS 6 元数据库兼容性</span><span class="sxs-lookup"><span data-stu-id="9b22a-194">IIS 6 Metabase compatibility</span></span>
        - <span data-ttu-id="9b22a-195">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9b22a-195">IIS 6 Management Console</span></span>
        - <span data-ttu-id="9b22a-196">IIS 6 脚本工具（安装 adsutil.vbs）</span><span class="sxs-lookup"><span data-stu-id="9b22a-196">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>

3. <span data-ttu-id="9b22a-197">继续进行安装，并且在系统提示时重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-197">Continue with the installation, and restart the computer if prompted.</span></span> 

<span data-ttu-id="9b22a-198">**另请参阅**：在 [Windows 8 或 Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012) 上安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="9b22a-198">**SEE ALSO** : Install IIS on [Windows 8 or Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012).</span></span>


## <a name="run-64-bit-bam-portal-optional"></a><span data-ttu-id="9b22a-199">运行 64 位 BAM 门户 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-199">Run 64-bit BAM portal (optional)</span></span>
<span data-ttu-id="9b22a-200">如果不使用 BAM 门户，则可以跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-200">If you don't use the BAM portal, then you can skip this section.</span></span> 

<span data-ttu-id="9b22a-201">在 32 位模式下运行 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="9b22a-201">The BAM Portal runs in 32-bit mode.</span></span> <span data-ttu-id="9b22a-202">如果在 64 位环境中使用 Internet 信息服务 (IIS)，然后设置要在 32 位模式下运行的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="9b22a-202">If you are using Internet Information Services (IIS) in a 64-bit environment, then set the application pool to run in 32-bit mode.</span></span> 

#### <a name="using-adsutilvbs"></a><span data-ttu-id="9b22a-203">使用 adsutil.vbs</span><span class="sxs-lookup"><span data-stu-id="9b22a-203">Using adsutil.vbs</span></span>
1.  <span data-ttu-id="9b22a-204">以管理员身份打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9b22a-204">Open a command prompt as administrator.</span></span> 
2.  <span data-ttu-id="9b22a-205">在命令提示符下，输入：</span><span class="sxs-lookup"><span data-stu-id="9b22a-205">In the command prompt, type:</span></span>  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. <span data-ttu-id="9b22a-206">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9b22a-206">Select Enter.</span></span>

#### <a name="using-iis-manager"></a><span data-ttu-id="9b22a-207">使用 IIS 管理器</span><span class="sxs-lookup"><span data-stu-id="9b22a-207">Using IIS Manager</span></span>
1. <span data-ttu-id="9b22a-208">在“开始”菜单中，打开 "inetmgr"。</span><span class="sxs-lookup"><span data-stu-id="9b22a-208">In the Start menu, open "inetmgr".</span></span>
2.  <span data-ttu-id="9b22a-209">展开计算机名称，然后选择“应用程序池”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-209">Expand the computer name, and select **Application Pools**.</span></span>
3.  <span data-ttu-id="9b22a-210">右键单击“DefaultAppPool”，然后选择“高级设置”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-210">Right-click **DefaultAppPool**, and select **Advanced Settings**.</span></span> 
4.  <span data-ttu-id="9b22a-211">将“启用 32 位应用程序”的值更改为 **True**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-211">Change the value of **Enable 32-bit Applications** to **True**.</span></span> 
5.  <span data-ttu-id="9b22a-212">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-212">Select **OK**.</span></span>

## <a name="install-windows-identity-foundation-wif-optional"></a><span data-ttu-id="9b22a-213">安装 Windows Identity Foundation (WIF)（可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-213">Install Windows Identity Foundation (WIF) (optional)</span></span>
<span data-ttu-id="9b22a-214">如果你使用 SharePoint Services 适配器，BizTalk Server 要求 WIF。</span><span class="sxs-lookup"><span data-stu-id="9b22a-214">If you use the SharePoint Services adapter, BizTalk Server requires WIF.</span></span> <span data-ttu-id="9b22a-215">如果不使用 SharePoint Services 适配器，则可跳过本部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-215">If you don't use the SharePoint Services adapter, you can skip this section.</span></span>

<span data-ttu-id="9b22a-216">Windows Identity Foundation 作为一项**功能**包括在操作系统中。</span><span class="sxs-lookup"><span data-stu-id="9b22a-216">Windows Identity Foundation is included with the operating system as a **Feature**.</span></span>

1. <span data-ttu-id="9b22a-217">在“开始”菜单中，打开“打开或关闭 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-217">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="9b22a-218">或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-218">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="9b22a-219">选择“Windows Identity Foundation 3.5”，然后继续进行安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-219">Select **Windows Identity Foundation 3.5**, and continue with the installation.</span></span> 
3. <span data-ttu-id="9b22a-220">如果系统提示，则重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-220">Restart the computer if prompted.</span></span>

## <a name="install--configure-smtp-server-optional"></a><span data-ttu-id="9b22a-221">安装并配置 SMTP 服务器 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-221">Install & configure SMTP Server (optional)</span></span>
<span data-ttu-id="9b22a-222">如果你使用 BAM 警报，BizTalk 服务器要求 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="9b22a-222">If you use BAM Alerts, BizTalk Server requires SMTP Server.</span></span> <span data-ttu-id="9b22a-223">如果不使用 BAM 警报，则可跳过本部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-223">If you don't use BAM Alerts, you can skip this section.</span></span>

<span data-ttu-id="9b22a-224">SQL Server 数据库邮件使用 SMTP 服务器发送 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="9b22a-224">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="9b22a-225">SMTP 服务器可以本地安装在 BizTalk Server 上，也可以安装在其他已安装 IIS 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="9b22a-225">SMTP Server can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span> <span data-ttu-id="9b22a-226">SMTP 服务器在客户端操作系统上不可用，例如 Windows 8.1 或 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="9b22a-226">SMTP Server is not available on client operating systems, such as Windows 8.1 or Windows 10.</span></span> 

<span data-ttu-id="9b22a-227">SMTP 服务器作为一项**功能**包括在服务器操作系统中。</span><span class="sxs-lookup"><span data-stu-id="9b22a-227">SMTP Server is included with server operating systems as a **Feature**.</span></span>

1. <span data-ttu-id="9b22a-228">在“开始”菜单中，打开“打开或关闭 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-228">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="9b22a-229">或者，打开“服务器管理器”，选择“管理”，然后选择“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-229">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="9b22a-230">选择“SMTP 服务器”，然后继续进行安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-230">Select **SMTP Server**, and continue with the installation.</span></span> 
3. <span data-ttu-id="9b22a-231">如果系统提示，则重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-231">Restart the computer if prompted.</span></span>

## <a name="install-excel-2016-or-2013-optional"></a><span data-ttu-id="9b22a-232">安装 Excel 2016 或 2013 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-232">Install Excel 2016 or 2013 (optional)</span></span>
<span data-ttu-id="9b22a-233">如果你使用业务活动监视 (BAM)，BizTalk Server 要求 Excel。</span><span class="sxs-lookup"><span data-stu-id="9b22a-233">If you use Business Activity Monitoring (BAM), BizTalk Server requires Excel.</span></span> <span data-ttu-id="9b22a-234">如果不使用 BAM，则可跳过本部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-234">If you don't use BAM, you can skip this section.</span></span>

<span data-ttu-id="9b22a-235">可以使用 BAM Office Excel 工作簿来定义要监视的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9b22a-235">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="9b22a-236">还可以使用 BAM Excel 工作簿定义业务用户查看 BAM 所收集的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="9b22a-236">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>

> [!IMPORTANT] 
> * <span data-ttu-id="9b22a-237">BizTalk Server 仅支持 32 位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="9b22a-237">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span> 
> * <span data-ttu-id="9b22a-238">若要成功将 BAM.xla 加载到 Excel 中，请在“Office 共享功能”下安装“Visual Basic for Applications”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-238">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** (under **Office Shared Features**).</span></span> <span data-ttu-id="9b22a-239">否则，可能会出现错误：`This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span><span class="sxs-lookup"><span data-stu-id="9b22a-239">Otherwise, you may get error: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span></span>

#### <a name="install-excel-2016"></a><span data-ttu-id="9b22a-240">安装 Excel 2016</span><span class="sxs-lookup"><span data-stu-id="9b22a-240">Install Excel 2016</span></span>

<span data-ttu-id="9b22a-241">Office 2016 是使用“即点即用”或“C2R 安装程序”进行安装的。</span><span class="sxs-lookup"><span data-stu-id="9b22a-241">Office 2016 is installed using "Click-to-Run" or "C2R Installer".</span></span> <span data-ttu-id="9b22a-242">C2R 安装下载并安装 Office 中的所有程序。</span><span class="sxs-lookup"><span data-stu-id="9b22a-242">The C2R installation downloads and installs all programs within Office.</span></span> <span data-ttu-id="9b22a-243">对于 BAM，我们只需要 Excel。</span><span class="sxs-lookup"><span data-stu-id="9b22a-243">For BAM, we only need Excel.</span></span> <span data-ttu-id="9b22a-244">若要解决此问题，请下载并安装 [Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)以自定义 C2R 安装程序。</span><span class="sxs-lookup"><span data-stu-id="9b22a-244">To work around this, download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) to customize the C2R installer.</span></span>

1. <span data-ttu-id="9b22a-245">下载并安装 [Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-245">Download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>
2. <span data-ttu-id="9b22a-246">在具有提取的 Office 2016 部署工具文件的文件夹中，使用文本编辑器，如记事本，打开 **configuration.xml**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-246">In the folder with the Office 2016 Deployment Tool files you extracted, open the **configuration.xml** file with a text editor, such as notepad.</span></span>
3. <span data-ttu-id="9b22a-247">将 `<Configuration>` 部分替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b22a-247">Replace the `<Configuration>` section with the following:</span></span>  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    <span data-ttu-id="9b22a-248">将 "SourcePath" 替换为 Office 2016 ISO 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9b22a-248">Replace “SourcePath” with the location of your Office 2016 ISO file.</span></span>
4. <span data-ttu-id="9b22a-249">在具有 Office 2016 部署工具文件的文件夹中，按住 **SHIFT** 键，然后右键单击该文件夹中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="9b22a-249">In the folder with the Office 2016 Deployment Tool files, hold down the **SHIFT** key, and right-click an empty area in the folder.</span></span> <span data-ttu-id="9b22a-250">选择“在此处打开命令窗口”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-250">Select **Open command window here**.</span></span> 
5. <span data-ttu-id="9b22a-251">输入以下内容，以开始 Excel 安装：</span><span class="sxs-lookup"><span data-stu-id="9b22a-251">Start the Excel installation by entering the following:</span></span>  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > <span data-ttu-id="9b22a-252">`setup.exe /download configuration.xml` 下载所需的 Office 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="9b22a-252">`setup.exe /download configuration.xml` downloads the required office setup files.</span></span>
 
6. <span data-ttu-id="9b22a-253">选择“Excel”，然后继续安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-253">Select Excel, and continue with the installation.</span></span> 
 
<span data-ttu-id="9b22a-254">**另请参阅**：[Office 部署工具的配置选项](https://technet.microsoft.com/library/jj219426.aspx)和[安装 Office 2016 或 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="9b22a-254">**SEE ALSO** : [Configuration options for the Office Deployment Tool](https://technet.microsoft.com/library/jj219426.aspx) and [Install Office 2016 or 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)</span></span>

#### <a name="install-excel-2013"></a><span data-ttu-id="9b22a-255">安装 Excel 2013</span><span class="sxs-lookup"><span data-stu-id="9b22a-255">Install Excel 2013</span></span>
1. <span data-ttu-id="9b22a-256">运行 Microsoft Office 安装程序。</span><span class="sxs-lookup"><span data-stu-id="9b22a-256">Run the Microsoft Office setup.</span></span>
2. <span data-ttu-id="9b22a-257">选择“自定义安装”，然后选择“Excel”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-257">Select a **Custom Install**, and select Excel.</span></span>
3. <span data-ttu-id="9b22a-258">继续安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-258">Continue with the installation.</span></span>   

## <a name="install-visual-c-redistributable-package"></a><span data-ttu-id="9b22a-259">安装 Visual c + + 可再发行组件包</span><span class="sxs-lookup"><span data-stu-id="9b22a-259">Install Visual C++ redistributable package</span></span>

<span data-ttu-id="9b22a-260">下载并安装[Visual c + + 可再发行组件包](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-260">Download and install the [Visual C++ redistributable package](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package).</span></span> <span data-ttu-id="9b22a-261">即使使用的是 Visual Studio 2015，也需要 2013 版本。</span><span class="sxs-lookup"><span data-stu-id="9b22a-261">The 2013 version is required, even though Visual Studio 2015 is used.</span></span>

<span data-ttu-id="9b22a-262">[Visual c + + 下载](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)列出所有可用版本。</span><span class="sxs-lookup"><span data-stu-id="9b22a-262">The [Visual C++ downloads](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads) lists all the available versions.</span></span>

## <a name="install-visual-studio-2015-optional"></a><span data-ttu-id="9b22a-263">安装 Visual Studio 2015（可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-263">Install Visual Studio 2015 (optional)</span></span>
<span data-ttu-id="9b22a-264">BizTalk Server 需要 Visual Studio，以使用开发工具创建 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="9b22a-264">BizTalk Server requires Visual Studio to create BizTalk projects using the development tools.</span></span> <span data-ttu-id="9b22a-265">如果这是临时或生产服务器，或没有在进行任何 BizTalk 开发，则跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-265">If this is a staging or production server, or you're not doing any BizTalk development, then skip this section.</span></span>

<span data-ttu-id="9b22a-266">建议使用 Visual Studio 企业版，但也支持专业版和社区版。</span><span class="sxs-lookup"><span data-stu-id="9b22a-266">Visual Studio Enterprise Edition is recommended, but Professional and Community editions are also supported.</span></span> 

1. <span data-ttu-id="9b22a-267">以管理员身份运行 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="9b22a-267">Run the Visual Studio setup as Administrator.</span></span>
2. <span data-ttu-id="9b22a-268">选择“默认”安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-268">Select a **Default** installation.</span></span> <span data-ttu-id="9b22a-269">BizTalk Server 不需要任何可选功能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-269">BizTalk Server does not require any of the optional features.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b22a-270">如果对多个 BizTalk 项目使用 Visual Studio，则选择“自定义”安装来安装其他功能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-270">If you use Visual Studio for more than BizTalk projects, then select the **Custom** installation to install other features.</span></span> <span data-ttu-id="9b22a-271">一些常用功能包括 Microsoft Web 开发人员工具、Microsoft Office 开发人员工具、适用于 Visual Studio 的 PowerShell 工具以及 ClickOnce 发布工具。</span><span class="sxs-lookup"><span data-stu-id="9b22a-271">Some commonly-used features include Microsoft Web Developer Tools, Microsoft Office Developer Tools, PowerShell Tools for Visual Studio, and ClickOnce Publishing Tools.</span></span>
 
3. <span data-ttu-id="9b22a-272">继续进行安装，并且在系统提示时重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-272">Continue with the installation, and restart your computer if prompted.</span></span>

<span data-ttu-id="9b22a-273">**另请参阅**：[安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)</span><span class="sxs-lookup"><span data-stu-id="9b22a-273">**SEE ALSO** : [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="9b22a-274">如果在安装 BizTalk Server 之前安装 Visual Studio，然后升级到 Visual Studio Team Explorer，可能需要修复 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-274">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation.</span></span>
> - <span data-ttu-id="9b22a-275">Visual Studio 会自动安装 Microsoft SQL Server Express；而 BizTalk Server 并不使用它。</span><span class="sxs-lookup"><span data-stu-id="9b22a-275">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="9b22a-276">卸载 Microsoft SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="9b22a-276">Uninstall Microsoft SQL Server Express.</span></span> <span data-ttu-id="9b22a-277">还可以卸载 Microsoft SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="9b22a-277">You can also uninstall Microsoft SQL Server Compact.</span></span>  
> - <span data-ttu-id="9b22a-278">BizTalk Server 开发工具基于 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="9b22a-278">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="9b22a-279">在安装 BizTalk Server 开发人员工具和 SDK 之前，至少需安装 Microsoft Visual C#® .NET 组件。</span><span class="sxs-lookup"><span data-stu-id="9b22a-279">At a minimum, install the Microsoft Visual C#® .NET component before you install the BizTalk Server Developer Tools and SDK.</span></span>
> - <span data-ttu-id="9b22a-280">BizTalk Server 运行时组件需要 .NET Framework 4.6。</span><span class="sxs-lookup"><span data-stu-id="9b22a-280">The BizTalk Server runtime requires .NET Framework 4.6.</span></span> <span data-ttu-id="9b22a-281">如果安装了 Windows Communication Foundation (WCF) 适配器或 WCF 侦听器，则需要.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="9b22a-281">If the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed, then .NET Framework 3.0 is required</span></span>

#### <a name="uninstall-sql-server-express"></a><span data-ttu-id="9b22a-282">卸载 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="9b22a-282">Uninstall SQL Server Express</span></span>
1. <span data-ttu-id="9b22a-283">在“开始”菜单中，打开“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-283">In the Start menu, open **Programs and Features**.</span></span> <span data-ttu-id="9b22a-284">或者，打开“控制面板”，然后选择“卸载程序”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-284">Or, open the **Control Panel**, and select **Uninstall a program**.</span></span>
2. <span data-ttu-id="9b22a-285">卸载：</span><span class="sxs-lookup"><span data-stu-id="9b22a-285">Uninstall:</span></span> 
    - <span data-ttu-id="9b22a-286">Microsoft SQL Server 2014 Express LocalDb</span><span class="sxs-lookup"><span data-stu-id="9b22a-286">Microsoft SQL Server 2014 Express LocalDb</span></span>
    - <span data-ttu-id="9b22a-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span><span class="sxs-lookup"><span data-stu-id="9b22a-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span></span>
    - <span data-ttu-id="9b22a-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span><span class="sxs-lookup"><span data-stu-id="9b22a-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span></span>
    
3. <span data-ttu-id="9b22a-289">继续进行卸载，并且在系统提示时重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-289">Continue with the uninstall, and restart your computer if prompted.</span></span> 

## <a name="install-sql-server-2016"></a><span data-ttu-id="9b22a-290">安装 SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="9b22a-290">Install SQL Server 2016</span></span>
<span data-ttu-id="9b22a-291">BizTalk Server 需要 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="9b22a-291">BizTalk Server requires SQL Server.</span></span> <span data-ttu-id="9b22a-292">SQL Server 可以和 BizTalk 安装在同一台计算机上，也可以安装在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9b22a-292">SQL Server can be installed on the same computer as BizTalk, or on a different computer.</span></span> <span data-ttu-id="9b22a-293">大多数生产环境在不同的服务器上安装 BizTalk 和 SQL。</span><span class="sxs-lookup"><span data-stu-id="9b22a-293">Most production environments install BizTalk and SQL on separate servers.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="9b22a-294">不建议使用或不支持 SQL Server Express Edition。</span><span class="sxs-lookup"><span data-stu-id="9b22a-294">SQL Server Express Edition is not recommended or supported.</span></span> <span data-ttu-id="9b22a-295">Express Edition 不包括 BizTalk Server 需要的某些功能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-295">The Express edition does not include certain features needed by BizTalk Server.</span></span>
> - <span data-ttu-id="9b22a-296">BizTalk Server 支持 SQL 标准版。</span><span class="sxs-lookup"><span data-stu-id="9b22a-296">BizTalk Server supports SQL Standard Edition.</span></span> <span data-ttu-id="9b22a-297">但是，为使用业务活动监视实时聚合 (BAM RTA)，需安装 SQL Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="9b22a-297">However, to use Business Activity Monitoring real-time aggregation (BAM RTA), install SQL Server Enterprise Edition.</span></span> <span data-ttu-id="9b22a-298">SQL Server 标准版中不支持 BAM 实时聚合 (RTA)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-298">BAM real-time aggregation (RTA) is not supported in the Standard Edition of SQL Server.</span></span>
> - <span data-ttu-id="9b22a-299">若要从 Visual Studio 全面使用 BizTalk Server SDK 或部署 BizTalk Server 应用程序，请安装 SQL Server 开发工具。</span><span class="sxs-lookup"><span data-stu-id="9b22a-299">To fully use the BizTalk Server SDK or deploy BizTalk Server applications from a Visual Studio, install the SQL Server Development Tools.</span></span>
> - <span data-ttu-id="9b22a-300">BizTalk Server 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。</span><span class="sxs-lookup"><span data-stu-id="9b22a-300">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="9b22a-301">不支持二进制排序规则。</span><span class="sxs-lookup"><span data-stu-id="9b22a-301">Binary collations are not supported.</span></span>

<span data-ttu-id="9b22a-302">**有关特定的安装步骤，请参阅**[安装 SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)或[安装 SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-302">**For specific install steps, see** [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) or [Install SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).</span></span>

1. <span data-ttu-id="9b22a-303">开始 SQL Server 安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-303">Start the SQL Server installation.</span></span> 
2. <span data-ttu-id="9b22a-304">“功能”设置期间，选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b22a-304">During the Feature setup, select the following:</span></span>
    - <span data-ttu-id="9b22a-305">数据库引擎服务</span><span class="sxs-lookup"><span data-stu-id="9b22a-305">Database Engine Services</span></span>
        - <span data-ttu-id="9b22a-306">SQL Server 复制</span><span class="sxs-lookup"><span data-stu-id="9b22a-306">SQL Server Replication</span></span>
        - <span data-ttu-id="9b22a-307">R Services （数据库） (**可选**; 在信息[SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span><span class="sxs-lookup"><span data-stu-id="9b22a-307">R Services (in-Database) (**optional**; info at [SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span></span>
        - <span data-ttu-id="9b22a-308">用于搜索的全文和语义提取</span><span class="sxs-lookup"><span data-stu-id="9b22a-308">Full-Text and Semantic Extractions for Search</span></span>
    - <span data-ttu-id="9b22a-309">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9b22a-309">Analysis Services</span></span>
    - <span data-ttu-id="9b22a-310">Reporting Services - 本机</span><span class="sxs-lookup"><span data-stu-id="9b22a-310">Reporting Services - Native</span></span>
    - <span data-ttu-id="9b22a-311">共享功能</span><span class="sxs-lookup"><span data-stu-id="9b22a-311">Shared Features</span></span>
        - <span data-ttu-id="9b22a-312">客户端工具连接</span><span class="sxs-lookup"><span data-stu-id="9b22a-312">Client Tools Connectivity</span></span>
        - <span data-ttu-id="9b22a-313">Integration Services</span><span class="sxs-lookup"><span data-stu-id="9b22a-313">Integration Services</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b22a-314">**SQL Server Data Tools** 未包含在 SQL Server 的默认安装中。</span><span class="sxs-lookup"><span data-stu-id="9b22a-314">**SQL Server Data Tools** is not included in the default installation of SQL Server.</span></span> <span data-ttu-id="9b22a-315">它不是必需的但可以从以下网址下载[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-315">It isn't required, but can be downloaded at [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).</span></span> <span data-ttu-id="9b22a-316">下载可与所有 SQL Server 的支持版本兼容的 [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)，其中包括 Azure SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="9b22a-316">Download [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) that works with all supported versions of SQL Server, including Azure SQL Database.</span></span> <span data-ttu-id="9b22a-317">但是，若要连接到远程 SSIS 使用 BAM 时，你需要为目标 SSIS 服务器安装相同版本的 SSMS。</span><span class="sxs-lookup"><span data-stu-id="9b22a-317">However, to connect to remote SSIS when using BAM, you need to install the same version of SSMS as the destination SSIS server.</span></span> <span data-ttu-id="9b22a-318">例如，[安装 SSMS 16。*x* ](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases)安装要连接到 SQL 2016 SSIS 的相关驱动程序。</span><span class="sxs-lookup"><span data-stu-id="9b22a-318">For example, [install SSMS 16.*x*](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases) to install the related drivers to connect to SQL 2016 SSIS.</span></span> <span data-ttu-id="9b22a-319">SSMS 17。*x*无法连接到 SQL 2016 SSIS。</span><span class="sxs-lookup"><span data-stu-id="9b22a-319">SSMS 17.*x* cannot connect to SQL 2016 SSIS.</span></span> <span data-ttu-id="9b22a-320">你可以具有多个版本的 SSMS 安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-320">You can have multiple versions of SSMS installed.</span></span> 

3. <span data-ttu-id="9b22a-321">继续进行安装，并且在系统提示时重启计算机。</span><span class="sxs-lookup"><span data-stu-id="9b22a-321">Continue with the installation, and restart the computer if prompted.</span></span>

## <a name="disable-shared-memory"></a><span data-ttu-id="9b22a-322">禁用共享的内存</span><span class="sxs-lookup"><span data-stu-id="9b22a-322">Disable Shared Memory</span></span>

1. <span data-ttu-id="9b22a-323">打开 **SQL Server 配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-323">Open **SQL Server Configuration Manager**.</span></span>
2. <span data-ttu-id="9b22a-324">在 SQL Server 配置管理器中，展开**SQL Server 网络配置**，然后选择**MSSQLSERVER 的协议**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-324">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>
3. <span data-ttu-id="9b22a-325">右键单击“共享内存”，然后选择“禁用”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-325">Right-click **Shared Memory**, and then select **Disable**.</span></span>
4. <span data-ttu-id="9b22a-326">选择**SQL Server Services**，右键单击 SQL **Server (MSSQLSERVER)**，然后选择**停止**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-326">Select **SQL Server Services**, right-click SQL **Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="9b22a-327">服务已停止后，右键单击**SQL Server (MSSQLSERVER)**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="9b22a-327">After the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and then select **Start**.</span></span>
5. <span data-ttu-id="9b22a-328">关闭“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-328">Close **SQL Server Configuration Manager**.</span></span>

<span data-ttu-id="9b22a-329">通常情况下，Shared Memory 协议只会影响在 SQL Server 所在的计算机上安装客户端 (BizTalk Server)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-329">Typically, the Shared Memory protocol only impacts clients (BizTalk Server) that are installed on the same computer as SQL Server.</span></span> <span data-ttu-id="9b22a-330">在任务繁忙时（例如，客户端从同一计算机访问 SQL Server 时），SQL Server Shared Memory 协议可能会降低 BizTalk Server 性能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-330">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="9b22a-331">禁用 Shared Memory 网络协议解决此问题。</span><span class="sxs-lookup"><span data-stu-id="9b22a-331">Disabling the Shared Memory network protocol resolves this.</span></span>

> [!TIP]
> <span data-ttu-id="9b22a-332">如果 SQL Server 代理无法启动后禁用共享内存，然后确认[ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339)安装。</span><span class="sxs-lookup"><span data-stu-id="9b22a-332">If SQL Server Agent fails to start after disabling Shared Memory, then confirm [ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) is installed.</span></span>

## <a name="install-sql-xml-4"></a><span data-ttu-id="9b22a-333">安装 SQL XML 4</span><span class="sxs-lookup"><span data-stu-id="9b22a-333">Install SQL XML 4</span></span>
<span data-ttu-id="9b22a-334">这是 BizTalk Server 运行时、管理工具和 BAM 所必需的。</span><span class="sxs-lookup"><span data-stu-id="9b22a-334">Required for BizTalk Server Runtime, Administrative Tools, and BAM.</span></span> 

<span data-ttu-id="9b22a-335">下载并安装[SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-335">Download and install [SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403).</span></span>

## <a name="configure-sql-database-mail-optional"></a><span data-ttu-id="9b22a-336">配置 SQL 数据库邮件 （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-336">Configure SQL Database Mail (optional)</span></span>
<span data-ttu-id="9b22a-337">如果你使用 BAM 警报，BizTalk 服务器需要 SQL Server 数据库邮件。</span><span class="sxs-lookup"><span data-stu-id="9b22a-337">If you use BAM Alerts, BizTalk Server requires SQL Server Database Mail.</span></span> <span data-ttu-id="9b22a-338">如果未使用 BAM 警报，则跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-338">If you don't use BAM Alerts, then skip this section.</span></span> 

<span data-ttu-id="9b22a-339">**另请参阅**：[Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9b22a-339">**SEE ALSO** : More on [Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="9b22a-340">需要知道 SMTP 服务器的服务器名称和 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="9b22a-340">You need to know the server name and TCP port number for the SMTP Server.</span></span> <span data-ttu-id="9b22a-341">如果在此同一台计算机上安装 IIS 和 SMTP 服务器，则使用本地 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="9b22a-341">If you installed IIS and SMTP Server on this same computer, then you use the local SMTP Server.</span></span> <span data-ttu-id="9b22a-342">如果 SMTP 服务器需要身份验证，则准备好 SMTP 服务器名称和密码。</span><span class="sxs-lookup"><span data-stu-id="9b22a-342">If the SMTP server requires authentication, then have the user name and password ready.</span></span>
> - <span data-ttu-id="9b22a-343">BAM 门户和 BAM 警报是不同的功能。</span><span class="sxs-lookup"><span data-stu-id="9b22a-343">The BAM portal and BAM Alerts are separate features.</span></span> <span data-ttu-id="9b22a-344">如果使用 BAM 警报，则需要 SQL Server Database Mail。</span><span class="sxs-lookup"><span data-stu-id="9b22a-344">If you are using BAM Alerts, then SQL Server Database Mail is required.</span></span> <span data-ttu-id="9b22a-345">如果不使用 BAM 警报，则不需要 SQL Server Database Mail。</span><span class="sxs-lookup"><span data-stu-id="9b22a-345">If you are not using BAM Alerts, then SQL Server Database Mail is not required.</span></span>

<span data-ttu-id="9b22a-346">**有关特定的配置步骤，请参阅**： 配置[SQL Server 2016 数据库邮件](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail)或[SQL Server 2014 数据库邮件](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-346">**For specific configuration steps, see**: Configure [SQL Server 2016 Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail) or [SQL Server 2014 Database Mail](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx).</span></span>

   
<span data-ttu-id="9b22a-347">若要发送测试电子邮件：</span><span class="sxs-lookup"><span data-stu-id="9b22a-347">To send a test email:</span></span> 
1.  <span data-ttu-id="9b22a-348">右键单击“Database Mail”，然后选择“发送测试电子邮件”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-348">Right-click **Database Mail**, and select **Send Test E-Mail**.</span></span> 
2.  <span data-ttu-id="9b22a-349">输入“收件人：”电子邮件地址，然后选择“发送测试电子邮件”。</span><span class="sxs-lookup"><span data-stu-id="9b22a-349">Enter a **To:** email address, and select **Send Test E-Mail**.</span></span>  
 
<span data-ttu-id="9b22a-350">如果“收件人:”收到该电子邮件，则已配置 Database Mail。</span><span class="sxs-lookup"><span data-stu-id="9b22a-350">If the **To:** recipient receives the email, then Database Mail is configured.</span></span> 

## <a name="install-winscp-optional"></a><span data-ttu-id="9b22a-351">安装 WinSCP （可选）</span><span class="sxs-lookup"><span data-stu-id="9b22a-351">Install WinSCP (optional)</span></span>
<span data-ttu-id="9b22a-352">FTP 适配器所需。</span><span class="sxs-lookup"><span data-stu-id="9b22a-352">Required by the FTP adapter.</span></span> <span data-ttu-id="9b22a-353">如果不使用 FTP 适配器，然后跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="9b22a-353">If you don't use the FTP adapter, then skip this section.</span></span> 

<span data-ttu-id="9b22a-354">下载并安装[WinSCP](http://winscp.net)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-354">Download and install [WinSCP](http://winscp.net).</span></span> 

## <a name="next-step"></a><span data-ttu-id="9b22a-355">下一步</span><span class="sxs-lookup"><span data-stu-id="9b22a-355">Next step</span></span>
<span data-ttu-id="9b22a-356">安装 [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="9b22a-356">Install [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md).</span></span>
