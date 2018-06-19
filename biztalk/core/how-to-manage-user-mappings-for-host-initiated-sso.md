---
title: 如何管理用户映射为主机启动的 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bf65bdb3de30d5b701946215b5c7ae7d40d828
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972379"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="1f179-102">如何管理用户映射为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="1f179-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="1f179-103">通过以下步骤可以创建映射、设置凭据以及启用或禁用映射。</span><span class="sxs-lookup"><span data-stu-id="1f179-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="1f179-104">使用 MMC 管理单元为主机启动的 SSO 管理用户映射</span><span class="sxs-lookup"><span data-stu-id="1f179-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="1f179-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="1f179-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="1f179-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="1f179-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="1f179-107">在作用域窗格中，单击**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1f179-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="1f179-108">在详细信息窗格中，右键单击相应的关联应用程序，然后选择适当的操作菜单项。</span><span class="sxs-lookup"><span data-stu-id="1f179-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="1f179-109">使用命令行在主机启动的 SSO 中创建映射</span><span class="sxs-lookup"><span data-stu-id="1f179-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-110">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-111">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-112">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-113">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-114">类型**ssomanage-createmappings\<映射文件\>**，其中**映射文件 >** 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1f179-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-115">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="1f179-116">下面是一个映射文件的示例：</span><span class="sxs-lookup"><span data-stu-id="1f179-116">A sample mapping file is shown below:</span></span>  
  
    ```  
    <SSO>  
      <mapping>  
        <windowsDomain>DomainName</windowsDomain>  
        <windowsUserId>UserA</windowsUserId>  
        <externalApplication>SSOApplication</externalApplication>  
    <externalUserId>ExternalUserID that corresponds to UserA</externalUserId>  
      </mapping>  
    </SSO>  
  
    ```  
  
 <span data-ttu-id="1f179-117">如果为关联应用程序启用了“验证密码”功能，则需要设置凭据，步骤如下：</span><span class="sxs-lookup"><span data-stu-id="1f179-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-118">使用命令行为“单项”类型的关联应用程序设置凭据</span><span class="sxs-lookup"><span data-stu-id="1f179-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-119">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-120">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-121">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-122">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-123">类型**ssomanage-setcredentials \<Windows 帐户名称\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-124">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-125">使用命令行为“主机组”类型的关联应用程序设置凭据</span><span class="sxs-lookup"><span data-stu-id="1f179-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-126">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-127">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-128">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-129">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-130">类型**ssomanage-setcredentials\<外部帐户名\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-131">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-132">使用命令行为“ 单项” 类型的关联应用程序启用映射</span><span class="sxs-lookup"><span data-stu-id="1f179-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-133">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-134">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-135">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-136">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-137">类型**ssomanage-enablemapping \<Windows 帐户名称\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-138">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-139">使用命令行为“单项”类型的关联应用程序禁用映射</span><span class="sxs-lookup"><span data-stu-id="1f179-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-140">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-141">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-142">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-143">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-144">类型**ssomanage-disablemapping \<Windows 帐户名称\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-145">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-146">使用命令行为“主机组”类型的关联应用程序启用映射</span><span class="sxs-lookup"><span data-stu-id="1f179-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-147">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-148">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-149">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-150">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-151">类型**ssomanage-enablemapping\<外部帐户名\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-152">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="1f179-153">使用命令行为“单项”类型的关联应用程序禁用映射</span><span class="sxs-lookup"><span data-stu-id="1f179-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="1f179-154">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="1f179-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f179-155">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f179-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f179-156">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1f179-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f179-157">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1f179-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f179-158">类型**ssomanage-disablemapping\<外部帐户名\>\<应用程序名称\>**。</span><span class="sxs-lookup"><span data-stu-id="1f179-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-159">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1f179-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f179-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f179-160">See Also</span></span>  
 [<span data-ttu-id="1f179-161">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="1f179-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)