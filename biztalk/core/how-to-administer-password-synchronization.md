---
title: "如何管理密码同步 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], applications
- Password Synchronization [SSO], notifications
- applications, Password Synchronization [SSO]
- SSOPS command line utility [SSO]
- administering, Password Synchronization [SSO]
- Password Synchronization [SSO], adapters
- Password Synchronization [SSO], administering
- notifications [SSO]
- Password Synchronization [SSO], SSOPS command line utility
ms.assetid: e5568cc2-7530-452c-9902-d7ffcad66088
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd696da8b4cab24a8de6a4b5d8ac8f26856f7e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-administer-password-synchronization"></a><span data-ttu-id="cafc8-102">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="cafc8-102">How to Administer Password Synchronization</span></span>
<span data-ttu-id="cafc8-103">您可以通过 MMC 管理单元或命令行管理密码同步。</span><span class="sxs-lookup"><span data-stu-id="cafc8-103">You can administer Password Synchronization through either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="cafc8-104">MMC 管理单元可显示适配器及其属性的列表。</span><span class="sxs-lookup"><span data-stu-id="cafc8-104">The MMC Snap-In displays a list of adapters and their properties.</span></span> <span data-ttu-id="cafc8-105">使用右键单击适配器后显示的菜单可执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cafc8-105">You can right-click an adapter and use the menu to perform the following commands:</span></span>  
  
-   <span data-ttu-id="cafc8-106">创建适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-106">Create adapters</span></span>  
  
-   <span data-ttu-id="cafc8-107">设置属性</span><span class="sxs-lookup"><span data-stu-id="cafc8-107">Set properties</span></span>  
  
-   <span data-ttu-id="cafc8-108">Update</span><span class="sxs-lookup"><span data-stu-id="cafc8-108">Update</span></span>  
  
-   <span data-ttu-id="cafc8-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="cafc8-109">Delete</span></span>  
  
-   <span data-ttu-id="cafc8-110">启用</span><span class="sxs-lookup"><span data-stu-id="cafc8-110">Enable</span></span>  
  
-   <span data-ttu-id="cafc8-111">Disable</span><span class="sxs-lookup"><span data-stu-id="cafc8-111">Disable</span></span>  
  
-   <span data-ttu-id="cafc8-112">向适配器添加应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-112">Add applications to an adapter</span></span>  
  
-   <span data-ttu-id="cafc8-113">从适配器删除应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-113">Delete applications from an adapter</span></span>  
  
-   <span data-ttu-id="cafc8-114">重置通知</span><span class="sxs-lookup"><span data-stu-id="cafc8-114">Reset notification</span></span>  
  
-   <span data-ttu-id="cafc8-115">将适配器添加到适配器组</span><span class="sxs-lookup"><span data-stu-id="cafc8-115">Add an adapter to an adapter group</span></span>  
  
-   <span data-ttu-id="cafc8-116">从适配器组删除适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-116">Delete an adapter from an adapter group</span></span>  
  
 <span data-ttu-id="cafc8-117">您还可以使用 SSOPS 命令行实用工具管理密码同步。</span><span class="sxs-lookup"><span data-stu-id="cafc8-117">You can also use the SSOPS command line utility to administer your password synchronization.</span></span> <span data-ttu-id="cafc8-118">此部分的大多数命令仅供管理员使用。</span><span class="sxs-lookup"><span data-stu-id="cafc8-118">Most of commands in this section are intended for use by an administrator only.</span></span>  
  
 <span data-ttu-id="cafc8-119">对于多数命令，将在屏幕上按两列显示命令输出。</span><span class="sxs-lookup"><span data-stu-id="cafc8-119">For many commands, the command output is displayed on the screen in two columns.</span></span> <span data-ttu-id="cafc8-120">由于某些屏幕设置可能会引起数据显示不完整，因此应将屏幕缓冲区大小/Windows 大小更改为 120 个字符以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="cafc8-120">As certain screen settings may cause truncation of data, for best results you should change the screen buffer size/Windows size to 120 characters.</span></span>  
  
 <span data-ttu-id="cafc8-121">下表列出了各种 SSOPS 命令。</span><span class="sxs-lookup"><span data-stu-id="cafc8-121">The SSOPS commands are listed in the following table.</span></span> <span data-ttu-id="cafc8-122">本主题的其余部分介绍了相应的执行步骤并做了进一步说明。</span><span class="sxs-lookup"><span data-stu-id="cafc8-122">Procedures and further explanation are located throughout the rest of this topic.</span></span>  
  
|<span data-ttu-id="cafc8-123">Command</span><span class="sxs-lookup"><span data-stu-id="cafc8-123">Command</span></span>|<span data-ttu-id="cafc8-124">函数</span><span class="sxs-lookup"><span data-stu-id="cafc8-124">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="cafc8-125">-list</span><span class="sxs-lookup"><span data-stu-id="cafc8-125">-list</span></span>|<span data-ttu-id="cafc8-126">列出现有的适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-126">Lists existing adapters</span></span>|  
|<span data-ttu-id="cafc8-127">-display</span><span class="sxs-lookup"><span data-stu-id="cafc8-127">-display</span></span>|<span data-ttu-id="cafc8-128">显示适配器信息</span><span class="sxs-lookup"><span data-stu-id="cafc8-128">Displays adapter information</span></span>|  
|<span data-ttu-id="cafc8-129">-create</span><span class="sxs-lookup"><span data-stu-id="cafc8-129">-create</span></span>|<span data-ttu-id="cafc8-130">创建新的适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-130">Creates new adapter(s)</span></span>|  
|<span data-ttu-id="cafc8-131">-setprops</span><span class="sxs-lookup"><span data-stu-id="cafc8-131">-setprops</span></span>|<span data-ttu-id="cafc8-132">设置适配器的属性</span><span class="sxs-lookup"><span data-stu-id="cafc8-132">Sets properties for adapter</span></span>|  
|<span data-ttu-id="cafc8-133">-update</span><span class="sxs-lookup"><span data-stu-id="cafc8-133">-update</span></span>|<span data-ttu-id="cafc8-134">更新现有适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-134">Updates existing adapter(s)</span></span>|  
|<span data-ttu-id="cafc8-135">-delete</span><span class="sxs-lookup"><span data-stu-id="cafc8-135">-delete</span></span>|<span data-ttu-id="cafc8-136">删除现有适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-136">Deletes an existing adapter</span></span>|  
|<span data-ttu-id="cafc8-137">-enable</span><span class="sxs-lookup"><span data-stu-id="cafc8-137">-enable</span></span>|<span data-ttu-id="cafc8-138">启用适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-138">Enables adapter</span></span>|  
|<span data-ttu-id="cafc8-139">-disable</span><span class="sxs-lookup"><span data-stu-id="cafc8-139">-disable</span></span>|<span data-ttu-id="cafc8-140">禁用适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-140">Disables adapter</span></span>|  
|<span data-ttu-id="cafc8-141">-addapp</span><span class="sxs-lookup"><span data-stu-id="cafc8-141">-addapp</span></span>|<span data-ttu-id="cafc8-142">为适配器添加应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-142">Adds application for adapter</span></span>|  
|<span data-ttu-id="cafc8-143">-deleteapp</span><span class="sxs-lookup"><span data-stu-id="cafc8-143">-deleteapp</span></span>|<span data-ttu-id="cafc8-144">为适配器删除应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-144">Deletes application for adapter</span></span>|  
|<span data-ttu-id="cafc8-145">-reset</span><span class="sxs-lookup"><span data-stu-id="cafc8-145">-reset</span></span>|<span data-ttu-id="cafc8-146">重置通知或阻止队列</span><span class="sxs-lookup"><span data-stu-id="cafc8-146">Resets notification or damping queues</span></span>|  
|<span data-ttu-id="cafc8-147">-addtogroup</span><span class="sxs-lookup"><span data-stu-id="cafc8-147">-addtogroup</span></span>|<span data-ttu-id="cafc8-148">向适配器组添加适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-148">Adds adapter to adapter group</span></span>|  
|<span data-ttu-id="cafc8-149">-deletefromgroup</span><span class="sxs-lookup"><span data-stu-id="cafc8-149">-deletefromgroup</span></span>|<span data-ttu-id="cafc8-150">从适配器组中删除适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-150">Deletes adapter from adapter group</span></span>|  
  
### <a name="to-list-existing-adapters"></a><span data-ttu-id="cafc8-151">列出现有适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-151">To list existing adapters</span></span>  
  
1.  <span data-ttu-id="cafc8-152">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-152">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-153">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-153">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-154">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-154">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-155">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-155">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-156">类型**ssops-列表**，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-156">Type **ssops -list** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-157">此时，将列出各适配器及其说明。</span><span class="sxs-lookup"><span data-stu-id="cafc8-157">Adapters and descriptions will be listed.</span></span> <span data-ttu-id="cafc8-158">(E) 表示适配器已启用，(D) 表示适配器已禁用。</span><span class="sxs-lookup"><span data-stu-id="cafc8-158">(E) denotes that the adapter is enabled, (D) denotes that it is disabled.</span></span>  
  
### <a name="to-display-adapter-information"></a><span data-ttu-id="cafc8-159">显示适配器信息</span><span class="sxs-lookup"><span data-stu-id="cafc8-159">To display adapter information</span></span>  
  
1.  <span data-ttu-id="cafc8-160">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-160">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-161">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-161">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-162">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-162">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-163">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-163">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-164">类型**ssops-显示\<适配器名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-164">Type **ssops -display \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-165">屏幕输出将显示指定的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="cafc8-165">The screen output will display information for the specified adapter.</span></span>  
  
     <span data-ttu-id="cafc8-166">除了名称、类型、说明、计算机和帐户以外，还会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="cafc8-166">In addition to name, type, description, computer, and accounts, the following information is displayed.</span></span>  
  
    |<span data-ttu-id="cafc8-167">适配器标志</span><span class="sxs-lookup"><span data-stu-id="cafc8-167">Adapter Flag</span></span>|<span data-ttu-id="cafc8-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="cafc8-168">Details</span></span>|  
    |------------------|-------------|  
    |<span data-ttu-id="cafc8-169">适配器已启用</span><span class="sxs-lookup"><span data-stu-id="cafc8-169">Adapter enabled</span></span>|<span data-ttu-id="cafc8-170">确定适配器是否已启用。</span><span class="sxs-lookup"><span data-stu-id="cafc8-170">Determines whether or not the adapter is enabled.</span></span><br /><br /> <span data-ttu-id="cafc8-171">标志： SSO_FLAG_ENABLED</span><span class="sxs-lookup"><span data-stu-id="cafc8-171">Flag: SSO_FLAG_ENABLED</span></span><br /><br /> <span data-ttu-id="cafc8-172">属性名称： enableApp</span><span class="sxs-lookup"><span data-stu-id="cafc8-172">Attribute Name: enableApp</span></span><br /><br /> <span data-ttu-id="cafc8-173">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-173">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-174">允许本地帐户</span><span class="sxs-lookup"><span data-stu-id="cafc8-174">Allow local accounts</span></span>|<span data-ttu-id="cafc8-175">确定 App Admin 或 App Users 帐户是否可用作本地帐户。</span><span class="sxs-lookup"><span data-stu-id="cafc8-175">Determines whether or not the App Admin or App Users accounts can be local accounts.</span></span><br /><br /> <span data-ttu-id="cafc8-176">标志： SSO_FLAG_APP_ALLOW_LOCAL</span><span class="sxs-lookup"><span data-stu-id="cafc8-176">Flag: SSO_FLAG_APP_ALLOW_LOCAL</span></span><br /><br /> <span data-ttu-id="cafc8-177">属性名称： allowLocalAccounts</span><span class="sxs-lookup"><span data-stu-id="cafc8-177">Attribute Name: allowLocalAccounts</span></span><br /><br /> <span data-ttu-id="cafc8-178">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-178">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-179">从适配器接收密码更改</span><span class="sxs-lookup"><span data-stu-id="cafc8-179">Receive password changes from adapter</span></span>|<span data-ttu-id="cafc8-180">确定是否允许适配器接收外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="cafc8-180">Determines whether or not the adapter is allowed to receive external password changes.</span></span><br /><br /> <span data-ttu-id="cafc8-181">标志： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span><span class="sxs-lookup"><span data-stu-id="cafc8-181">Flag: SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span></span><br /><br /> <span data-ttu-id="cafc8-182">属性名称： syncFromAdapter</span><span class="sxs-lookup"><span data-stu-id="cafc8-182">Attribute Name: syncFromAdapter</span></span><br /><br /> <span data-ttu-id="cafc8-183">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-183">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-184">验证旧密码</span><span class="sxs-lookup"><span data-stu-id="cafc8-184">Verify old password</span></span>|<span data-ttu-id="cafc8-185">确定适配器在接收外部密码更改时是否验证旧密码。</span><span class="sxs-lookup"><span data-stu-id="cafc8-185">Determines whether the adapter will verify the old password when an external password change is received.</span></span> <span data-ttu-id="cafc8-186">如果设置此标志，则在外部密码发生更改时，外部适配器必须提供旧的外部密码以及新的外部密码。</span><span class="sxs-lookup"><span data-stu-id="cafc8-186">If this flag is set then with an external password change the external adapter must supply the old external password as well as the new external password.</span></span> <span data-ttu-id="cafc8-187">然后，旧的外部密码会与该外部帐户在 SSO 数据库中的现有外部密码进行比较。</span><span class="sxs-lookup"><span data-stu-id="cafc8-187">The old external password is then compared with the existing external password in the SSO database for that external account.</span></span> <span data-ttu-id="cafc8-188">如果匹配，则接受密码更改。</span><span class="sxs-lookup"><span data-stu-id="cafc8-188">If they match, the password change is accepted.</span></span> <span data-ttu-id="cafc8-189">如果不匹配，则拒绝密码更改。</span><span class="sxs-lookup"><span data-stu-id="cafc8-189">If they do not match, the password change is rejected.</span></span><br /><br /> <span data-ttu-id="cafc8-190">标志： SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="cafc8-190">Flag: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="cafc8-191">属性名称： verifyOldPassword</span><span class="sxs-lookup"><span data-stu-id="cafc8-191">Attribute Name: verifyOldPassword</span></span><br /><br /> <span data-ttu-id="cafc8-192">默认值: 是</span><span class="sxs-lookup"><span data-stu-id="cafc8-192">Default: Yes</span></span>|  
    |<span data-ttu-id="cafc8-193">更改 Windows 密码</span><span class="sxs-lookup"><span data-stu-id="cafc8-193">Change Windows password</span></span>|<span data-ttu-id="cafc8-194">确定在收到外部密码更改时是否同时更改 Windows 密码（完全同步）。</span><span class="sxs-lookup"><span data-stu-id="cafc8-194">Determines whether or not the Windows password will also be changed when an external password change is received (full sync).</span></span> <span data-ttu-id="cafc8-195">ENTSSO 始终需要使用 SSO 数据库中存储的旧 Windows 密码才能将 Windows 密码更改为新值（Windows 需要同时使用旧密码和新密码才能更改用户密码），因此，必须进行初始化才能成功地更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="cafc8-195">ENTSSO always uses the old Windows password stored in the SSO database to change the Windows password to the new value (Windows requires both the old and new password to change a users password), so this must be initialized before the Windows password change can succeed.</span></span> <span data-ttu-id="cafc8-196">如果密码同步配置为特定的映射，然后当通过管理工具 (ssomanage 或 ssoclient-setcredentials) 设置外部凭据存储在 SSO 数据库中的 Windows 密码将也可以设置。标志： SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span><span class="sxs-lookup"><span data-stu-id="cafc8-196">If password sync is configured for a particular mapping, then when the external credentials are set via administrative tools (ssomanage or ssoclient -setcredentials) the Windows password stored in the SSO database will also be set.Flag: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span></span><br /><br /> <span data-ttu-id="cafc8-197">属性名称： changeWindowsPassword</span><span class="sxs-lookup"><span data-stu-id="cafc8-197">Attribute Name: changeWindowsPassword</span></span><br /><br /> <span data-ttu-id="cafc8-198">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-198">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-199">将 Windows 密码更改发送到适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-199">Send Windows password changes to adapter</span></span>|<span data-ttu-id="cafc8-200">确定将 Windows 密码更改发送到的外部适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-200">Determines whether or not Windows password changes will be sent to the external adapter.</span></span><br /><br /> <span data-ttu-id="cafc8-201">标志： SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="cafc8-201">Flag: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span></span><br /><br /> <span data-ttu-id="cafc8-202">属性名称： syncToAdapter</span><span class="sxs-lookup"><span data-stu-id="cafc8-202">Attribute Name: syncToAdapter</span></span><br /><br /> <span data-ttu-id="cafc8-203">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-203">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-204">将旧密码发送到适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-204">Send old password to adapter</span></span>|<span data-ttu-id="cafc8-205">如果设置为“是”，则旧密码值（位于 SSO 数据库中）将同新密码值一起发送到外部适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-205">If Yes, the old password value (from the SSO database) will also be sent to the external adapter as well as the new password value.</span></span> <span data-ttu-id="cafc8-206">某些外部系统可能需要同时使用旧密码值和新密码值才能更改密码。</span><span class="sxs-lookup"><span data-stu-id="cafc8-206">Some external systems might require both the old and new password values to change the password.</span></span><br /><br /> <span data-ttu-id="cafc8-207">标志： SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="cafc8-207">Flag: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="cafc8-208">属性名称： sendOldPassword</span><span class="sxs-lookup"><span data-stu-id="cafc8-208">Attribute Name: sendOldPassword</span></span><br /><br /> <span data-ttu-id="cafc8-209">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-209">Default: No</span></span>|  
    |<span data-ttu-id="cafc8-210">允许映射冲突</span><span class="sxs-lookup"><span data-stu-id="cafc8-210">Allow mapping conflicts</span></span>|<span data-ttu-id="cafc8-211">确定适配器将允许映射冲突。</span><span class="sxs-lookup"><span data-stu-id="cafc8-211">Determines whether or not the adapter will allow mapping conflicts.</span></span><br /><br /> <span data-ttu-id="cafc8-212">当映射不唯一时，就会发生映射冲突。</span><span class="sxs-lookup"><span data-stu-id="cafc8-212">A mapping conflict occurs when mappings are not unique.</span></span> <span data-ttu-id="cafc8-213">在单个 SSO 单个应用中，映射是始终一对一： 一个 Windows 帐户映射到一个外部帐户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="cafc8-213">In a single SSO Individual application, mappings are always one-to-one: one Windows account is mapped to exactly one external account and vice versa.</span></span><br /><br /> <span data-ttu-id="cafc8-214">但是，可以将多个应用程序分配给一个适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-214">However, it is possible to assign more than one application to an adapter.</span></span> <span data-ttu-id="cafc8-215">因此，可能导致某个应用程序中的映射与其他应用程序中的映射产生冲突。</span><span class="sxs-lookup"><span data-stu-id="cafc8-215">Thus, it is possible to have a mapping in one application that conflicts with a mapping in the other.</span></span><br /><br /> <span data-ttu-id="cafc8-216">此标志的目的就是防止这种情况发生。</span><span class="sxs-lookup"><span data-stu-id="cafc8-216">This purpose of this flag is to prevent this from occurring.</span></span> <span data-ttu-id="cafc8-217">除非有明确要求，否则请不要允许映射冲突。</span><span class="sxs-lookup"><span data-stu-id="cafc8-217">It is more secure to not allow mapping conflicts unless there is a specific, well understood requirement for this behavior.</span></span><br /><br /> <span data-ttu-id="cafc8-218">标志： SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span><span class="sxs-lookup"><span data-stu-id="cafc8-218">Flag: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span></span><br /><br /> <span data-ttu-id="cafc8-219">属性名称： allowMappingConflicts</span><span class="sxs-lookup"><span data-stu-id="cafc8-219">Attribute Name: allowMappingConflicts</span></span><br /><br /> <span data-ttu-id="cafc8-220">默认： 否</span><span class="sxs-lookup"><span data-stu-id="cafc8-220">Default: No</span></span>|  
  
    |<span data-ttu-id="cafc8-221">适配器说明</span><span class="sxs-lookup"><span data-stu-id="cafc8-221">Adapter Description</span></span>|<span data-ttu-id="cafc8-222">详细信息</span><span class="sxs-lookup"><span data-stu-id="cafc8-222">Details</span></span>|  
    |-------------------------|-------------|  
    |<span data-ttu-id="cafc8-223">通知重试计数</span><span class="sxs-lookup"><span data-stu-id="cafc8-223">Notification retry count</span></span>|<span data-ttu-id="cafc8-224">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="cafc8-224">Default is 1.</span></span>|  
    |<span data-ttu-id="cafc8-225">通知重试延迟时间(分钟)</span><span class="sxs-lookup"><span data-stu-id="cafc8-225">Notification retry delay (in mins)</span></span>|<span data-ttu-id="cafc8-226">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="cafc8-226">Default is 5.</span></span>|  
    |<span data-ttu-id="cafc8-227">最大挂起通知</span><span class="sxs-lookup"><span data-stu-id="cafc8-227">Maximum pending notifications</span></span>|<span data-ttu-id="cafc8-228">默认值为 8。</span><span class="sxs-lookup"><span data-stu-id="cafc8-228">Default is 8.</span></span>|  
    |<span data-ttu-id="cafc8-229">存储通知 （在脱机时）</span><span class="sxs-lookup"><span data-stu-id="cafc8-229">Store notifications (when offline)</span></span>|<span data-ttu-id="cafc8-230">True/False。</span><span class="sxs-lookup"><span data-stu-id="cafc8-230">True/False.</span></span>|  
    |<span data-ttu-id="cafc8-231">服务器名称</span><span class="sxs-lookup"><span data-stu-id="cafc8-231">Server name</span></span>|<span data-ttu-id="cafc8-232">服务器名称。</span><span class="sxs-lookup"><span data-stu-id="cafc8-232">Server name.</span></span>|  
    |<span data-ttu-id="cafc8-233">端口号</span><span class="sxs-lookup"><span data-stu-id="cafc8-233">Port number</span></span>|<span data-ttu-id="cafc8-234">端口号。</span><span class="sxs-lookup"><span data-stu-id="cafc8-234">Port number.</span></span>|  
    |<span data-ttu-id="cafc8-235">此适配器的应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-235">Applications for this adapter</span></span>|<span data-ttu-id="cafc8-236">列出当前分配给适配器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cafc8-236">List of applications currently assigned to the adapter.</span></span>|  
  
### <a name="to-create-new-adapters"></a><span data-ttu-id="cafc8-237">若要创建新的适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-237">To create new adapters</span></span>  
  
1.  <span data-ttu-id="cafc8-238">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-238">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-239">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-239">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-240">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-240">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-241">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-241">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-242">类型**ssops-创建\<适配器文件\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-242">Type **ssops -create \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-243">屏幕输出将显示新创建的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="cafc8-243">The screen output will display information for the newly created adapter.</span></span>  
  
### <a name="to-set-properties-for-an-adapter"></a><span data-ttu-id="cafc8-244">若要为适配器设置属性</span><span class="sxs-lookup"><span data-stu-id="cafc8-244">To set properties for an adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-245">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-245">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-246">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-246">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-247">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-247">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-248">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-248">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-249">类型**ssops setprops\<适配器名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-249">Type **ssops -setprops \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-250">屏幕输出将显示指定的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="cafc8-250">The screen output will display the properties for the specified adapter.</span></span> <span data-ttu-id="cafc8-251">如果需要，可以对其进行编辑，但将不会对新值进行验证。</span><span class="sxs-lookup"><span data-stu-id="cafc8-251">You can edit them if necessary, but new values are not validated.</span></span>  
  
### <a name="to-update-existing-adapters"></a><span data-ttu-id="cafc8-252">若要更新现有的适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-252">To update existing adapters</span></span>  
  
1.  <span data-ttu-id="cafc8-253">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-253">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-254">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-254">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-255">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-255">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-256">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-256">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-257">类型**ssops-更新\<适配器文件\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-257">Type **ssops -update \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-258">使用此命令可更新指定的适配器的设置和标志。</span><span class="sxs-lookup"><span data-stu-id="cafc8-258">Use this command to update the settings and flags for a specified adapter.</span></span> <span data-ttu-id="cafc8-259">请不要使用此命令设置属性，而应使用 -setprops 命令来进行设置。</span><span class="sxs-lookup"><span data-stu-id="cafc8-259">Do not use this command to set properties; use instead the -setprops command.</span></span>  
  
### <a name="to-delete-an-existing-adapter"></a><span data-ttu-id="cafc8-260">若要删除现有适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-260">To delete an existing adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-261">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-261">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-262">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-262">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-263">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-263">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-264">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-264">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-265">类型**ssops-删除\<适配器名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-265">Type **ssops -delete \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-266">此时，将删除指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-266">The specified adapter will be deleted.</span></span>  
  
### <a name="to-enable-an-adapter"></a><span data-ttu-id="cafc8-267">若要启用适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-267">To enable an adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-268">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-268">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-269">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-269">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-270">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-270">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-271">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-271">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-272">类型**ssops-启用\<适配器名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-272">Type **ssops -enable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-273">此时，将启用指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-273">The specified adapter will be enabled.</span></span>  
  
### <a name="to-disable-an-adapter"></a><span data-ttu-id="cafc8-274">若要禁用适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-274">To disable an adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-275">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-275">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-276">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-276">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-277">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-277">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-278">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-278">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-279">类型**ssops-禁用\<适配器名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-279">Type **ssops -disable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-280">此时，将禁用指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-280">The specified adapter will be disabled.</span></span>  
  
### <a name="to-add-an-application-to-an-adapter"></a><span data-ttu-id="cafc8-281">若要添加到适配器的应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-281">To add an application to an adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-282">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-282">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-283">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-283">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-284">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-284">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-285">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-285">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-286">类型**ssops addapp\<适配器名称\>\<应用程序名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-286">Type **ssops -addapp \<adapter name\> \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-287">指定的 SSO 应用程序将分配给所指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-287">The specified SSO application will be assigned to the specified adapter.</span></span> <span data-ttu-id="cafc8-288">这意味着该应用程序中各映射的密码将使用此适配器进行同步。</span><span class="sxs-lookup"><span data-stu-id="cafc8-288">This means that the passwords for the mappings in that application will now be synchronized using this adapter.</span></span>  
  
     <span data-ttu-id="cafc8-289">虽然可以向一个适配器分配多个应用程序，但任何给定的应用程序都只能分配给一个适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-289">While multiple applications can be assigned to one adapter, any given application can only be assigned to one adapter.</span></span>  
  
### <a name="to-delete-an-application-from-an-adapter"></a><span data-ttu-id="cafc8-290">若要从适配器中删除的应用程序</span><span class="sxs-lookup"><span data-stu-id="cafc8-290">To delete an application from an adapter</span></span>  
  
1.  <span data-ttu-id="cafc8-291">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-291">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-292">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-292">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-293">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-293">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-294">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-294">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-295">类型**ssops-deleteapp\<应用程序名称\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-295">Type **ssops -deleteapp \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-296">指定的 SSO 应用程序将从适配器中删除。</span><span class="sxs-lookup"><span data-stu-id="cafc8-296">The specified SSO application will be removed from an adapter.</span></span> <span data-ttu-id="cafc8-297">（由于一个应用程序只能分配给一个适配器，因此无需指定适配器名称。）</span><span class="sxs-lookup"><span data-stu-id="cafc8-297">(Since an application can only be assigned to one adapter, it is not necessary to specify the adapter name.)</span></span>  
  
### <a name="to-reset-notification"></a><span data-ttu-id="cafc8-298">若要重置通知</span><span class="sxs-lookup"><span data-stu-id="cafc8-298">To reset notification</span></span>  
  
1.  <span data-ttu-id="cafc8-299">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-299">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-300">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-300">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-301">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-301">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-302">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-302">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-303">类型**ssops-重置\<适配器名称 &#124; 所有 &#124; 阻止\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-303">Type **ssops -reset \<adapter name &#124; all &#124; damping\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-304">此命令将根据指定清除单个适配器或所有适配器的阻止表和/或通知队列。</span><span class="sxs-lookup"><span data-stu-id="cafc8-304">This command clears the damping table and/or notification queues for a single adapter or all adapters, as specified.</span></span> <span data-ttu-id="cafc8-305">阻止表可存储 10 分钟的密码更改历史记录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-305">The damping table stores a 10-minute history of password changes.</span></span> <span data-ttu-id="cafc8-306">在接受或发送密码更改之前，企业 SSO 系统会检查阻止表以查看最近是否执行了同样的更改。</span><span class="sxs-lookup"><span data-stu-id="cafc8-306">Before the Enterprise SSO system accepts or sends a password change, it checks the damping table to see if it has performed the same change recently.</span></span> <span data-ttu-id="cafc8-307">如果已执行过，则会放弃新的更改。</span><span class="sxs-lookup"><span data-stu-id="cafc8-307">If it has, the new change is discarded.</span></span>  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a><span data-ttu-id="cafc8-308">要将适配器添加到适配器组</span><span class="sxs-lookup"><span data-stu-id="cafc8-308">To add an adapter to an adapter group</span></span>  
  
1.  <span data-ttu-id="cafc8-309">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-309">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-310">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-310">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-311">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-311">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-312">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-312">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-313">类型**ssops addtogroup\<适配器名称\>\<适配器组\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-313">Type **ssops -addtogroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-314">此命令将向所指定的适配器组添加指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-314">This command adds the specified adapter to the specified adapter group.</span></span> <span data-ttu-id="cafc8-315">虽然一个适配器只能属于一个适配器组，但一个适配器组可包含多个适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-315">While an adapter can belong to only one adapter group, an adapter group can contain multiple adapters.</span></span>  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a><span data-ttu-id="cafc8-316">若要从适配器组中删除适配器</span><span class="sxs-lookup"><span data-stu-id="cafc8-316">To delete an adapter from an adapter group</span></span>  
  
1.  <span data-ttu-id="cafc8-317">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-317">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="cafc8-318">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cafc8-318">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cafc8-319">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-319">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cafc8-320">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="cafc8-320">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="cafc8-321">类型**ssops deletefromgroup\<适配器名称\>\<适配器组\>** ，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="cafc8-321">Type **ssops -deletefromgroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="cafc8-322">此命令将从所指定的适配器组中删除指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="cafc8-322">This command deletes the specified adapter from the specified adapter group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafc8-323">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cafc8-323">See Also</span></span>  
 [<span data-ttu-id="cafc8-324">密码同步</span><span class="sxs-lookup"><span data-stu-id="cafc8-324">Password Synchronization</span></span>](../core/password-synchronization2.md)