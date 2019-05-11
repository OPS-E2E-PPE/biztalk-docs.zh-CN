---
title: 如何管理密码同步 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7c9b7485584c102b925b51d26ab11d37f4b8f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387211"
---
# <a name="how-to-administer-password-synchronization"></a><span data-ttu-id="b325e-102">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="b325e-102">How to Administer Password Synchronization</span></span>
<span data-ttu-id="b325e-103">你可以管理通过 MMC 管理单元或命令行的密码同步。</span><span class="sxs-lookup"><span data-stu-id="b325e-103">You can administer Password Synchronization through either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="b325e-104">MMC 管理单元中显示适配器及其属性的列表。</span><span class="sxs-lookup"><span data-stu-id="b325e-104">The MMC Snap-In displays a list of adapters and their properties.</span></span> <span data-ttu-id="b325e-105">您可以右键单击适配器，然后使用菜单来执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b325e-105">You can right-click an adapter and use the menu to perform the following commands:</span></span>  
  
- <span data-ttu-id="b325e-106">创建适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-106">Create adapters</span></span>  
  
- <span data-ttu-id="b325e-107">设置属性</span><span class="sxs-lookup"><span data-stu-id="b325e-107">Set properties</span></span>  
  
- <span data-ttu-id="b325e-108">Update</span><span class="sxs-lookup"><span data-stu-id="b325e-108">Update</span></span>  
  
- <span data-ttu-id="b325e-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="b325e-109">Delete</span></span>  
  
- <span data-ttu-id="b325e-110">启用</span><span class="sxs-lookup"><span data-stu-id="b325e-110">Enable</span></span>  
  
- <span data-ttu-id="b325e-111">Disable</span><span class="sxs-lookup"><span data-stu-id="b325e-111">Disable</span></span>  
  
- <span data-ttu-id="b325e-112">向适配器添加应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-112">Add applications to an adapter</span></span>  
  
- <span data-ttu-id="b325e-113">从适配器删除应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-113">Delete applications from an adapter</span></span>  
  
- <span data-ttu-id="b325e-114">重置通知</span><span class="sxs-lookup"><span data-stu-id="b325e-114">Reset notification</span></span>  
  
- <span data-ttu-id="b325e-115">将适配器添加到适配器组</span><span class="sxs-lookup"><span data-stu-id="b325e-115">Add an adapter to an adapter group</span></span>  
  
- <span data-ttu-id="b325e-116">从适配器组删除适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-116">Delete an adapter from an adapter group</span></span>  
  
  <span data-ttu-id="b325e-117">SSOPS 命令行实用程序还可用于管理密码同步。</span><span class="sxs-lookup"><span data-stu-id="b325e-117">You can also use the SSOPS command line utility to administer your password synchronization.</span></span> <span data-ttu-id="b325e-118">大多数命令在本部分中由管理员仅适用于使用。</span><span class="sxs-lookup"><span data-stu-id="b325e-118">Most of commands in this section are intended for use by an administrator only.</span></span>  
  
  <span data-ttu-id="b325e-119">对于多数命令，命令输出显示在两个列在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="b325e-119">For many commands, the command output is displayed on the screen in two columns.</span></span> <span data-ttu-id="b325e-120">因为某些屏幕设置可能会导致数据被截断，为获得最佳结果，应更改屏幕缓冲区大小/Windows 大小超过 120 个字符。</span><span class="sxs-lookup"><span data-stu-id="b325e-120">As certain screen settings may cause truncation of data, for best results you should change the screen buffer size/Windows size to 120 characters.</span></span>  
  
  <span data-ttu-id="b325e-121">下表列出了各种 SSOPS 命令。</span><span class="sxs-lookup"><span data-stu-id="b325e-121">The SSOPS commands are listed in the following table.</span></span> <span data-ttu-id="b325e-122">本主题的其余部分位于过程和更多说明。</span><span class="sxs-lookup"><span data-stu-id="b325e-122">Procedures and further explanation are located throughout the rest of this topic.</span></span>  
  
|<span data-ttu-id="b325e-123">Command</span><span class="sxs-lookup"><span data-stu-id="b325e-123">Command</span></span>|<span data-ttu-id="b325e-124">函数</span><span class="sxs-lookup"><span data-stu-id="b325e-124">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="b325e-125">-list</span><span class="sxs-lookup"><span data-stu-id="b325e-125">-list</span></span>|<span data-ttu-id="b325e-126">列出现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-126">Lists existing adapters</span></span>|  
|<span data-ttu-id="b325e-127">-display</span><span class="sxs-lookup"><span data-stu-id="b325e-127">-display</span></span>|<span data-ttu-id="b325e-128">显示适配器信息</span><span class="sxs-lookup"><span data-stu-id="b325e-128">Displays adapter information</span></span>|  
|<span data-ttu-id="b325e-129">-create</span><span class="sxs-lookup"><span data-stu-id="b325e-129">-create</span></span>|<span data-ttu-id="b325e-130">创建新的适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-130">Creates new adapter(s)</span></span>|  
|<span data-ttu-id="b325e-131">-setprops</span><span class="sxs-lookup"><span data-stu-id="b325e-131">-setprops</span></span>|<span data-ttu-id="b325e-132">适配器的设置属性</span><span class="sxs-lookup"><span data-stu-id="b325e-132">Sets properties for adapter</span></span>|  
|<span data-ttu-id="b325e-133">-update</span><span class="sxs-lookup"><span data-stu-id="b325e-133">-update</span></span>|<span data-ttu-id="b325e-134">更新现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-134">Updates existing adapter(s)</span></span>|  
|<span data-ttu-id="b325e-135">-delete</span><span class="sxs-lookup"><span data-stu-id="b325e-135">-delete</span></span>|<span data-ttu-id="b325e-136">删除现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-136">Deletes an existing adapter</span></span>|  
|<span data-ttu-id="b325e-137">-enable</span><span class="sxs-lookup"><span data-stu-id="b325e-137">-enable</span></span>|<span data-ttu-id="b325e-138">启用适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-138">Enables adapter</span></span>|  
|<span data-ttu-id="b325e-139">-disable</span><span class="sxs-lookup"><span data-stu-id="b325e-139">-disable</span></span>|<span data-ttu-id="b325e-140">禁用适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-140">Disables adapter</span></span>|  
|<span data-ttu-id="b325e-141">-addapp</span><span class="sxs-lookup"><span data-stu-id="b325e-141">-addapp</span></span>|<span data-ttu-id="b325e-142">添加适配器的应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-142">Adds application for adapter</span></span>|  
|<span data-ttu-id="b325e-143">-deleteapp</span><span class="sxs-lookup"><span data-stu-id="b325e-143">-deleteapp</span></span>|<span data-ttu-id="b325e-144">删除适配器的应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-144">Deletes application for adapter</span></span>|  
|<span data-ttu-id="b325e-145">-reset</span><span class="sxs-lookup"><span data-stu-id="b325e-145">-reset</span></span>|<span data-ttu-id="b325e-146">重置通知或阻止队列</span><span class="sxs-lookup"><span data-stu-id="b325e-146">Resets notification or damping queues</span></span>|  
|<span data-ttu-id="b325e-147">-addtogroup</span><span class="sxs-lookup"><span data-stu-id="b325e-147">-addtogroup</span></span>|<span data-ttu-id="b325e-148">添加适配器向适配器组</span><span class="sxs-lookup"><span data-stu-id="b325e-148">Adds adapter to adapter group</span></span>|  
|<span data-ttu-id="b325e-149">-deletefromgroup</span><span class="sxs-lookup"><span data-stu-id="b325e-149">-deletefromgroup</span></span>|<span data-ttu-id="b325e-150">从适配器组中删除适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-150">Deletes adapter from adapter group</span></span>|  
  
### <a name="to-list-existing-adapters"></a><span data-ttu-id="b325e-151">若要列出现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-151">To list existing adapters</span></span>  
  
1.  <span data-ttu-id="b325e-152">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-152">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-153">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-153">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-154">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-154">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-155">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-155">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-156">类型**ssops-列表**然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-156">Type **ssops -list** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-157">将列出各适配器及其说明。</span><span class="sxs-lookup"><span data-stu-id="b325e-157">Adapters and descriptions will be listed.</span></span> <span data-ttu-id="b325e-158">（E） 表示适配器已启用，(D) 表示已禁用。</span><span class="sxs-lookup"><span data-stu-id="b325e-158">(E) denotes that the adapter is enabled, (D) denotes that it is disabled.</span></span>  
  
### <a name="to-display-adapter-information"></a><span data-ttu-id="b325e-159">若要显示适配器信息</span><span class="sxs-lookup"><span data-stu-id="b325e-159">To display adapter information</span></span>  
  
1.  <span data-ttu-id="b325e-160">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-160">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-161">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-161">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-162">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-162">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-163">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-163">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-164">类型**ssops-显示\<适配器名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-164">Type **ssops -display \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-165">屏幕输出将显示指定的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="b325e-165">The screen output will display information for the specified adapter.</span></span>  
  
     <span data-ttu-id="b325e-166">除了名称、 类型、 说明、 计算机和帐户，显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="b325e-166">In addition to name, type, description, computer, and accounts, the following information is displayed.</span></span>  
  
    |<span data-ttu-id="b325e-167">适配器标志</span><span class="sxs-lookup"><span data-stu-id="b325e-167">Adapter Flag</span></span>|<span data-ttu-id="b325e-168">详细信息</span><span class="sxs-lookup"><span data-stu-id="b325e-168">Details</span></span>|  
    |------------------|-------------|  
    |<span data-ttu-id="b325e-169">适配器已启用</span><span class="sxs-lookup"><span data-stu-id="b325e-169">Adapter enabled</span></span>|<span data-ttu-id="b325e-170">确定启用该适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-170">Determines whether or not the adapter is enabled.</span></span><br /><br /> <span data-ttu-id="b325e-171">标志：SSO_FLAG_ENABLED</span><span class="sxs-lookup"><span data-stu-id="b325e-171">Flag: SSO_FLAG_ENABLED</span></span><br /><br /> <span data-ttu-id="b325e-172">属性名称： enableApp</span><span class="sxs-lookup"><span data-stu-id="b325e-172">Attribute Name: enableApp</span></span><br /><br /> <span data-ttu-id="b325e-173">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-173">Default: No</span></span>|  
    |<span data-ttu-id="b325e-174">允许本地帐户</span><span class="sxs-lookup"><span data-stu-id="b325e-174">Allow local accounts</span></span>|<span data-ttu-id="b325e-175">确定 App Admin 或 App Users 帐户可以是本地帐户。</span><span class="sxs-lookup"><span data-stu-id="b325e-175">Determines whether or not the App Admin or App Users accounts can be local accounts.</span></span><br /><br /> <span data-ttu-id="b325e-176">标志：SSO_FLAG_APP_ALLOW_LOCAL</span><span class="sxs-lookup"><span data-stu-id="b325e-176">Flag: SSO_FLAG_APP_ALLOW_LOCAL</span></span><br /><br /> <span data-ttu-id="b325e-177">属性名称： allowLocalAccounts</span><span class="sxs-lookup"><span data-stu-id="b325e-177">Attribute Name: allowLocalAccounts</span></span><br /><br /> <span data-ttu-id="b325e-178">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-178">Default: No</span></span>|  
    |<span data-ttu-id="b325e-179">从适配器接收密码更改</span><span class="sxs-lookup"><span data-stu-id="b325e-179">Receive password changes from adapter</span></span>|<span data-ttu-id="b325e-180">确定允许适配器接收外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="b325e-180">Determines whether or not the adapter is allowed to receive external password changes.</span></span><br /><br /> <span data-ttu-id="b325e-181">标志：SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span><span class="sxs-lookup"><span data-stu-id="b325e-181">Flag: SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span></span><br /><br /> <span data-ttu-id="b325e-182">属性名称： syncFromAdapter</span><span class="sxs-lookup"><span data-stu-id="b325e-182">Attribute Name: syncFromAdapter</span></span><br /><br /> <span data-ttu-id="b325e-183">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-183">Default: No</span></span>|  
    |<span data-ttu-id="b325e-184">验证旧密码</span><span class="sxs-lookup"><span data-stu-id="b325e-184">Verify old password</span></span>|<span data-ttu-id="b325e-185">确定是否接收外部密码更改时，适配器将验证旧密码。</span><span class="sxs-lookup"><span data-stu-id="b325e-185">Determines whether the adapter will verify the old password when an external password change is received.</span></span> <span data-ttu-id="b325e-186">如果设置此标志在外部密码更改的外部适配器必须提供旧的外部密码以及新的外部密码。</span><span class="sxs-lookup"><span data-stu-id="b325e-186">If this flag is set then with an external password change the external adapter must supply the old external password as well as the new external password.</span></span> <span data-ttu-id="b325e-187">旧的外部密码然后与该外部帐户在 SSO 数据库中的现有外部密码进行比较。</span><span class="sxs-lookup"><span data-stu-id="b325e-187">The old external password is then compared with the existing external password in the SSO database for that external account.</span></span> <span data-ttu-id="b325e-188">如果它们匹配，则接受密码更改。</span><span class="sxs-lookup"><span data-stu-id="b325e-188">If they match, the password change is accepted.</span></span> <span data-ttu-id="b325e-189">如果不匹配，则拒绝密码更改。</span><span class="sxs-lookup"><span data-stu-id="b325e-189">If they do not match, the password change is rejected.</span></span><br /><br /> <span data-ttu-id="b325e-190">标志：SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="b325e-190">Flag: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="b325e-191">属性名称： verifyOldPassword</span><span class="sxs-lookup"><span data-stu-id="b325e-191">Attribute Name: verifyOldPassword</span></span><br /><br /> <span data-ttu-id="b325e-192">默认值：是</span><span class="sxs-lookup"><span data-stu-id="b325e-192">Default: Yes</span></span>|  
    |<span data-ttu-id="b325e-193">更改 Windows 密码</span><span class="sxs-lookup"><span data-stu-id="b325e-193">Change Windows password</span></span>|<span data-ttu-id="b325e-194">确定在 Windows 的外部密码更改时，还将更改密码收到 （完全同步）。</span><span class="sxs-lookup"><span data-stu-id="b325e-194">Determines whether or not the Windows password will also be changed when an external password change is received (full sync).</span></span> <span data-ttu-id="b325e-195">ENTSSO 始终使用旧 Windows 密码存储在 SSO 数据库中的 Windows 密码更改为新值 （Windows 需要旧的和新密码才能更改用户密码），因此这必须初始化之前 Windows 密码更改可能会成功.</span><span class="sxs-lookup"><span data-stu-id="b325e-195">ENTSSO always uses the old Windows password stored in the SSO database to change the Windows password to the new value (Windows requires both the old and new password to change a users password), so this must be initialized before the Windows password change can succeed.</span></span> <span data-ttu-id="b325e-196">如果为特定映射配置密码同步，然后通过管理工具 (ssomanage 或 ssoclient-setcredentials) 设置外部凭据时存储在 SSO 数据库中的 Windows 密码也将会。标志：SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span><span class="sxs-lookup"><span data-stu-id="b325e-196">If password sync is configured for a particular mapping, then when the external credentials are set via administrative tools (ssomanage or ssoclient -setcredentials) the Windows password stored in the SSO database will also be set.Flag: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span></span><br /><br /> <span data-ttu-id="b325e-197">属性名称： changeWindowsPassword</span><span class="sxs-lookup"><span data-stu-id="b325e-197">Attribute Name: changeWindowsPassword</span></span><br /><br /> <span data-ttu-id="b325e-198">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-198">Default: No</span></span>|  
    |<span data-ttu-id="b325e-199">将 Windows 密码更改发送到适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-199">Send Windows password changes to adapter</span></span>|<span data-ttu-id="b325e-200">确定将 Windows 密码更改发送到外部适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-200">Determines whether or not Windows password changes will be sent to the external adapter.</span></span><br /><br /> <span data-ttu-id="b325e-201">标志：SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="b325e-201">Flag: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span></span><br /><br /> <span data-ttu-id="b325e-202">属性名称： syncToAdapter</span><span class="sxs-lookup"><span data-stu-id="b325e-202">Attribute Name: syncToAdapter</span></span><br /><br /> <span data-ttu-id="b325e-203">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-203">Default: No</span></span>|  
    |<span data-ttu-id="b325e-204">将旧密码发送到适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-204">Send old password to adapter</span></span>|<span data-ttu-id="b325e-205">如果是，（从 SSO 数据库中） 的旧密码值也将发送到外部适配器，以及新的密码值。</span><span class="sxs-lookup"><span data-stu-id="b325e-205">If Yes, the old password value (from the SSO database) will also be sent to the external adapter as well as the new password value.</span></span> <span data-ttu-id="b325e-206">某些外部系统可能需要这两个旧的和新密码值更改的密码。</span><span class="sxs-lookup"><span data-stu-id="b325e-206">Some external systems might require both the old and new password values to change the password.</span></span><br /><br /> <span data-ttu-id="b325e-207">标志：SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="b325e-207">Flag: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="b325e-208">属性名称： sendOldPassword</span><span class="sxs-lookup"><span data-stu-id="b325e-208">Attribute Name: sendOldPassword</span></span><br /><br /> <span data-ttu-id="b325e-209">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-209">Default: No</span></span>|  
    |<span data-ttu-id="b325e-210">允许映射冲突</span><span class="sxs-lookup"><span data-stu-id="b325e-210">Allow mapping conflicts</span></span>|<span data-ttu-id="b325e-211">确定适配器将允许映射冲突。</span><span class="sxs-lookup"><span data-stu-id="b325e-211">Determines whether or not the adapter will allow mapping conflicts.</span></span><br /><br /> <span data-ttu-id="b325e-212">映射不唯一时，将发生映射冲突。</span><span class="sxs-lookup"><span data-stu-id="b325e-212">A mapping conflict occurs when mappings are not unique.</span></span> <span data-ttu-id="b325e-213">在单个 SSO 单个应用程序中，映射始终是一对一： 一个 Windows 帐户映射到一个外部帐户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="b325e-213">In a single SSO Individual application, mappings are always one-to-one: one Windows account is mapped to exactly one external account and vice versa.</span></span><br /><br /> <span data-ttu-id="b325e-214">但是，就可以分配给适配器的多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b325e-214">However, it is possible to assign more than one application to an adapter.</span></span> <span data-ttu-id="b325e-215">因此，就可以有一个与在另一个映射冲突的应用程序中的映射。</span><span class="sxs-lookup"><span data-stu-id="b325e-215">Thus, it is possible to have a mapping in one application that conflicts with a mapping in the other.</span></span><br /><br /> <span data-ttu-id="b325e-216">此标志的目的就是防止此情况发生。</span><span class="sxs-lookup"><span data-stu-id="b325e-216">This purpose of this flag is to prevent this from occurring.</span></span> <span data-ttu-id="b325e-217">它是更安全，除非有特定明确要求，此行为不允许映射冲突。</span><span class="sxs-lookup"><span data-stu-id="b325e-217">It is more secure to not allow mapping conflicts unless there is a specific, well understood requirement for this behavior.</span></span><br /><br /> <span data-ttu-id="b325e-218">标志：SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span><span class="sxs-lookup"><span data-stu-id="b325e-218">Flag: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span></span><br /><br /> <span data-ttu-id="b325e-219">属性名称： allowMappingConflicts</span><span class="sxs-lookup"><span data-stu-id="b325e-219">Attribute Name: allowMappingConflicts</span></span><br /><br /> <span data-ttu-id="b325e-220">默认值：否</span><span class="sxs-lookup"><span data-stu-id="b325e-220">Default: No</span></span>|  
  
    |<span data-ttu-id="b325e-221">适配器描述</span><span class="sxs-lookup"><span data-stu-id="b325e-221">Adapter Description</span></span>|<span data-ttu-id="b325e-222">详细信息</span><span class="sxs-lookup"><span data-stu-id="b325e-222">Details</span></span>|  
    |-------------------------|-------------|  
    |<span data-ttu-id="b325e-223">通知重试次数</span><span class="sxs-lookup"><span data-stu-id="b325e-223">Notification retry count</span></span>|<span data-ttu-id="b325e-224">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="b325e-224">Default is 1.</span></span>|  
    |<span data-ttu-id="b325e-225">通知重试延迟时间 （分钟）</span><span class="sxs-lookup"><span data-stu-id="b325e-225">Notification retry delay (in mins)</span></span>|<span data-ttu-id="b325e-226">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="b325e-226">Default is 5.</span></span>|  
    |<span data-ttu-id="b325e-227">最大挂起通知数</span><span class="sxs-lookup"><span data-stu-id="b325e-227">Maximum pending notifications</span></span>|<span data-ttu-id="b325e-228">默认值为 8。</span><span class="sxs-lookup"><span data-stu-id="b325e-228">Default is 8.</span></span>|  
    |<span data-ttu-id="b325e-229">存储通知 （脱机时）</span><span class="sxs-lookup"><span data-stu-id="b325e-229">Store notifications (when offline)</span></span>|<span data-ttu-id="b325e-230">True/False。</span><span class="sxs-lookup"><span data-stu-id="b325e-230">True/False.</span></span>|  
    |<span data-ttu-id="b325e-231">服务器名称</span><span class="sxs-lookup"><span data-stu-id="b325e-231">Server name</span></span>|<span data-ttu-id="b325e-232">服务器名称。</span><span class="sxs-lookup"><span data-stu-id="b325e-232">Server name.</span></span>|  
    |<span data-ttu-id="b325e-233">端口号</span><span class="sxs-lookup"><span data-stu-id="b325e-233">Port number</span></span>|<span data-ttu-id="b325e-234">端口号。</span><span class="sxs-lookup"><span data-stu-id="b325e-234">Port number.</span></span>|  
    |<span data-ttu-id="b325e-235">此适配器的应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-235">Applications for this adapter</span></span>|<span data-ttu-id="b325e-236">当前分配给适配器的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="b325e-236">List of applications currently assigned to the adapter.</span></span>|  
  
### <a name="to-create-new-adapters"></a><span data-ttu-id="b325e-237">若要创建新的适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-237">To create new adapters</span></span>  
  
1.  <span data-ttu-id="b325e-238">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-238">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-239">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-239">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-240">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-240">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-241">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-241">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-242">类型**ssops-创建\<适配器文件\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-242">Type **ssops -create \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-243">屏幕输出将显示新创建的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="b325e-243">The screen output will display information for the newly created adapter.</span></span>  
  
### <a name="to-set-properties-for-an-adapter"></a><span data-ttu-id="b325e-244">若要为适配器设置属性</span><span class="sxs-lookup"><span data-stu-id="b325e-244">To set properties for an adapter</span></span>  
  
1.  <span data-ttu-id="b325e-245">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-245">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-246">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-246">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-247">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-247">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-248">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-248">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-249">类型**ssops-setprops\<适配器名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-249">Type **ssops -setprops \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-250">屏幕输出将显示指定的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="b325e-250">The screen output will display the properties for the specified adapter.</span></span> <span data-ttu-id="b325e-251">您可以编辑; 如有必要，但不是会验证新值。</span><span class="sxs-lookup"><span data-stu-id="b325e-251">You can edit them if necessary, but new values are not validated.</span></span>  
  
### <a name="to-update-existing-adapters"></a><span data-ttu-id="b325e-252">若要更新现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-252">To update existing adapters</span></span>  
  
1.  <span data-ttu-id="b325e-253">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-253">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-254">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-254">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-255">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-255">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-256">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-256">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-257">类型**ssops-更新\<适配器文件\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-257">Type **ssops -update \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-258">使用此命令更新的设置和指定适配器的标志。</span><span class="sxs-lookup"><span data-stu-id="b325e-258">Use this command to update the settings and flags for a specified adapter.</span></span> <span data-ttu-id="b325e-259">不使用此命令设置属性;改为使用-setprops 命令。</span><span class="sxs-lookup"><span data-stu-id="b325e-259">Do not use this command to set properties; use instead the -setprops command.</span></span>  
  
### <a name="to-delete-an-existing-adapter"></a><span data-ttu-id="b325e-260">若要删除现有适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-260">To delete an existing adapter</span></span>  
  
1.  <span data-ttu-id="b325e-261">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-261">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-262">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-262">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-263">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-263">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-264">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-264">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-265">类型**ssops-删除\<适配器名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-265">Type **ssops -delete \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-266">将删除指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-266">The specified adapter will be deleted.</span></span>  
  
### <a name="to-enable-an-adapter"></a><span data-ttu-id="b325e-267">若要启用适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-267">To enable an adapter</span></span>  
  
1.  <span data-ttu-id="b325e-268">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-268">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-269">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-269">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-270">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-270">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-271">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-271">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-272">类型**ssops-启用\<适配器名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-272">Type **ssops -enable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-273">将启用指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-273">The specified adapter will be enabled.</span></span>  
  
### <a name="to-disable-an-adapter"></a><span data-ttu-id="b325e-274">若要禁用适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-274">To disable an adapter</span></span>  
  
1.  <span data-ttu-id="b325e-275">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-275">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-276">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-276">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-277">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-277">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-278">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-278">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-279">类型**ssops-禁用\<适配器名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-279">Type **ssops -disable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-280">指定的适配器将被禁用。</span><span class="sxs-lookup"><span data-stu-id="b325e-280">The specified adapter will be disabled.</span></span>  
  
### <a name="to-add-an-application-to-an-adapter"></a><span data-ttu-id="b325e-281">若要向适配器添加应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-281">To add an application to an adapter</span></span>  
  
1.  <span data-ttu-id="b325e-282">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-282">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-283">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-283">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-284">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-284">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-285">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-285">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-286">类型**ssops-addapp\<适配器名称\>\<应用程序名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-286">Type **ssops -addapp \<adapter name\> \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-287">指定的 SSO 应用程序将分配给指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-287">The specified SSO application will be assigned to the specified adapter.</span></span> <span data-ttu-id="b325e-288">这意味着，密码的映射，因为现在将同步应用程序使用此适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-288">This means that the passwords for the mappings in that application will now be synchronized using this adapter.</span></span>  
  
     <span data-ttu-id="b325e-289">虽然可以给一个适配器分配多个应用程序，但任何给定应用程序只能分配给一个适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-289">While multiple applications can be assigned to one adapter, any given application can only be assigned to one adapter.</span></span>  
  
### <a name="to-delete-an-application-from-an-adapter"></a><span data-ttu-id="b325e-290">若要从适配器删除应用程序</span><span class="sxs-lookup"><span data-stu-id="b325e-290">To delete an application from an adapter</span></span>  
  
1.  <span data-ttu-id="b325e-291">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-291">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-292">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-292">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-293">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-293">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-294">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-294">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-295">类型**ssops-deleteapp\<应用程序名称\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-295">Type **ssops -deleteapp \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-296">将从适配器中删除指定的 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b325e-296">The specified SSO application will be removed from an adapter.</span></span> <span data-ttu-id="b325e-297">（应用程序只能分配给一个适配器，因为它不需要指定适配器名称。）</span><span class="sxs-lookup"><span data-stu-id="b325e-297">(Since an application can only be assigned to one adapter, it is not necessary to specify the adapter name.)</span></span>  
  
### <a name="to-reset-notification"></a><span data-ttu-id="b325e-298">若要重置通知</span><span class="sxs-lookup"><span data-stu-id="b325e-298">To reset notification</span></span>  
  
1.  <span data-ttu-id="b325e-299">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-299">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-300">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-300">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-301">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-301">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-302">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-302">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-303">类型**ssops-重置\<适配器名称&#124;所有&#124;阻止\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-303">Type **ssops -reset \<adapter name &#124; all &#124; damping\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-304">此命令可清除单个适配器或所有适配器，指定阻止的表和/或通知队列。</span><span class="sxs-lookup"><span data-stu-id="b325e-304">This command clears the damping table and/or notification queues for a single adapter or all adapters, as specified.</span></span> <span data-ttu-id="b325e-305">阻止表可存储 10 分钟的密码更改历史记录。</span><span class="sxs-lookup"><span data-stu-id="b325e-305">The damping table stores a 10-minute history of password changes.</span></span> <span data-ttu-id="b325e-306">企业 SSO 系统地接受或发送密码更改之前，它会检查阻止表以查看最近是否执行相同的更改。</span><span class="sxs-lookup"><span data-stu-id="b325e-306">Before the Enterprise SSO system accepts or sends a password change, it checks the damping table to see if it has performed the same change recently.</span></span> <span data-ttu-id="b325e-307">如果是，而放弃新的更改。</span><span class="sxs-lookup"><span data-stu-id="b325e-307">If it has, the new change is discarded.</span></span>  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a><span data-ttu-id="b325e-308">若要将适配器添加到适配器组</span><span class="sxs-lookup"><span data-stu-id="b325e-308">To add an adapter to an adapter group</span></span>  
  
1.  <span data-ttu-id="b325e-309">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-309">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-310">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-310">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-311">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-311">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-312">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-312">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-313">类型**ssops-addtogroup\<适配器名称\>\<适配器组\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-313">Type **ssops -addtogroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-314">此命令将指定的适配器添加到指定的适配器组。</span><span class="sxs-lookup"><span data-stu-id="b325e-314">This command adds the specified adapter to the specified adapter group.</span></span> <span data-ttu-id="b325e-315">适配器只能属于一个适配器组，一个适配器组包含多个适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-315">While an adapter can belong to only one adapter group, an adapter group can contain multiple adapters.</span></span>  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a><span data-ttu-id="b325e-316">若要从适配器组删除适配器</span><span class="sxs-lookup"><span data-stu-id="b325e-316">To delete an adapter from an adapter group</span></span>  
  
1.  <span data-ttu-id="b325e-317">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="b325e-317">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b325e-318">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b325e-318">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b325e-319">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b325e-319">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b325e-320">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="b325e-320">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b325e-321">类型**ssops-deletefromgroup\<适配器名称\>\<适配器组\>** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b325e-321">Type **ssops -deletefromgroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="b325e-322">此命令从指定的适配器组中删除指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="b325e-322">This command deletes the specified adapter from the specified adapter group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b325e-323">请参阅</span><span class="sxs-lookup"><span data-stu-id="b325e-323">See Also</span></span>  
 [<span data-ttu-id="b325e-324">密码同步</span><span class="sxs-lookup"><span data-stu-id="b325e-324">Password Synchronization</span></span>](../core/password-synchronization2.md)