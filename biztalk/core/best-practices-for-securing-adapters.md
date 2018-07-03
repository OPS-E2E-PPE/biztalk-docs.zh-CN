---
title: 确保适配器安全的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc38ddedf1b71cba0df4306359df9bdb5c96c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966310"
---
# <a name="best-practices-for-securing-adapters"></a><span data-ttu-id="a31b3-102">确保适配器安全的最佳实践</span><span class="sxs-lookup"><span data-stu-id="a31b3-102">Best Practices for Securing Adapters</span></span>
<span data-ttu-id="a31b3-103">本主题提供了适配器安全性最佳实践的列表。</span><span class="sxs-lookup"><span data-stu-id="a31b3-103">This topic provides a list of best practices for adapter security.</span></span>  
  
 <span data-ttu-id="a31b3-104">**在您的计算机; 上未安装不受信任的适配器仅使用经认证的适配器开发合作伙伴。**</span><span class="sxs-lookup"><span data-stu-id="a31b3-104">**Do not install untrusted adapters on your computer; use only certified adapter development partners.**</span></span>  
  
 <span data-ttu-id="a31b3-105">**在默认适配器架构中存储敏感的客户数据。**</span><span class="sxs-lookup"><span data-stu-id="a31b3-105">**Do not store sensitive customer data in the default adapter schema.**</span></span>  
  
 <span data-ttu-id="a31b3-106">应当只在部署适配器之后才配置用户名和密码信息。</span><span class="sxs-lookup"><span data-stu-id="a31b3-106">You should configure the user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="a31b3-107">这样可以确保将信息存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="a31b3-107">This ensures that the information gets stored in the SSO database.</span></span> <span data-ttu-id="a31b3-108">有关 SSO 数据库的详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="a31b3-108">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
 <span data-ttu-id="a31b3-109">**授予用于提取和存放文件使用的文件和 EDI 适配器的共享文件夹 （接收文件夹和发送文件夹） 上的以下权限：**</span><span class="sxs-lookup"><span data-stu-id="a31b3-109">**Grant the following permissions on the shared folders (the Receive folder and Send folder) that are used to pick up and drop files using the File and EDI adapters:**</span></span>  
  
- <span data-ttu-id="a31b3-110">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="a31b3-110">**Receive  folder**</span></span>  
  
   <span data-ttu-id="a31b3-111">文件适配器的接收文件夹可在接收位置上进行配置。</span><span class="sxs-lookup"><span data-stu-id="a31b3-111">The receive folder for the File adapter is configurable on the receive location.</span></span> <span data-ttu-id="a31b3-112">EDI 适配器的接收文件夹可在接收处理程序上进行配置。</span><span class="sxs-lookup"><span data-stu-id="a31b3-112">The receive folder for the EDI adapter is configurable on the receive handler.</span></span> <span data-ttu-id="a31b3-113">提取文件的 BizTalk 主机的服务帐户应在文件系统级别具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="a31b3-113">The service account for the BizTalk Host that picks up the file should have the following permissions at the file-system level:</span></span>  
  
  - <span data-ttu-id="a31b3-114">列出文件夹/读取数据</span><span class="sxs-lookup"><span data-stu-id="a31b3-114">List Folder / Read Data</span></span>  
  
  - <span data-ttu-id="a31b3-115">删除子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="a31b3-115">Delete SubFolder and Files</span></span>  
  
    <span data-ttu-id="a31b3-116">如果接收文件夹位于网络共享上，则必须在文件共享级别授予以下权限：</span><span class="sxs-lookup"><span data-stu-id="a31b3-116">If the receive folder is on a network share, the following permissions must be granted at the file-share level:</span></span>  
  
  - <span data-ttu-id="a31b3-117">提取文件的 BizTalk 主机的服务帐户必须具有“完全控制”权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-117">The service account for the BizTalk Host that picks up the file must have Full Control permissions.</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a31b3-118"> 管理员必须具有“完全控制”权限，才能进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="a31b3-118"> administrators must have Full Control permissions for troubleshooting.</span></span>  
  
  - <span data-ttu-id="a31b3-119">将文件存放到此位置的外部用户或程序必须具有写权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-119">The external user or programs that drop files to this location must have Write permissions.</span></span>  
  
- <span data-ttu-id="a31b3-120">**发送文件夹**</span><span class="sxs-lookup"><span data-stu-id="a31b3-120">**Send folder**</span></span>  
  
   <span data-ttu-id="a31b3-121">文件适配器和 EDI 适配器的发送文件夹可在发送端口上进行配置。</span><span class="sxs-lookup"><span data-stu-id="a31b3-121">The send folder for the File and EDI adapters are configurable on the send port.</span></span>  
  
  - <span data-ttu-id="a31b3-122">BizTalk 主机或在将文件存放在此处的主机的服务帐户必须具有写权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-122">The service account for the BizTalk Host or Hosts that drop files here must have Write permissions.</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a31b3-123"> 管理员必须具有“完全控制”权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-123"> administrators must have Full Control permissions.</span></span>  
  
  - <span data-ttu-id="a31b3-124">提取文件的外部用户或程序必须具有读权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-124">The external user or program that picks up files must have Read permissions.</span></span>  
  
  <span data-ttu-id="a31b3-125">**将添加到 BTS_HOST_USERS SQL 角色运行 EDI 服务在其下的用户帐户。**</span><span class="sxs-lookup"><span data-stu-id="a31b3-125">**Add the user account under which the EDI service is running to the BTS_HOST_USERS SQL role.**</span></span>  
  
  <span data-ttu-id="a31b3-126">此项为必需操作，以便可在不具有管理权限的情况下获取 BizTalk 浏览器对象管理 (OM) 访问权限。</span><span class="sxs-lookup"><span data-stu-id="a31b3-126">This is required so that you can obtain BizTalk Explorer Object Management (OM) Access without administrative permissions.</span></span> <span data-ttu-id="a31b3-127">若要执行此操作，请将“EDI Subsystem Users”添加到 BizTalk 管理数据库 (BizTalkMgmtDb) 的 BTS_HOST_USERS 角色中。</span><span class="sxs-lookup"><span data-stu-id="a31b3-127">To do this, add "EDI Subsystem Users" to the BTS_HOST_USERS role in the BizTalk Management database, BizTalkMgmtDb.</span></span>  
  
  <span data-ttu-id="a31b3-128">若要在 SQL Server 2005 上将“EDI Subsystem Users”添加到 BTS_HOST_USERS 角色中，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a31b3-128">To add "EDI Subsystem Users" to the BTS_HOST_USERS role on SQL Server 2005, complete the following steps:</span></span>  
  
1. <span data-ttu-id="a31b3-129">启动从 SQL Server Management Studio**开始，程序，Microsoft SQL Server 2008**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-129">Launch SQL Server Management Studio from **Start, Programs, Microsoft SQL Server 2008**.</span></span>  
  
2. <span data-ttu-id="a31b3-130">连接到 BizTalk 管理数据库所在的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a31b3-130">Connect to the SQL Server that houses your BizTalk Management database.</span></span>  
  
3. <span data-ttu-id="a31b3-131">展开对象资源管理器中的此服务器。</span><span class="sxs-lookup"><span data-stu-id="a31b3-131">Expand this server in the Object Explorer.</span></span>  
  
4. <span data-ttu-id="a31b3-132">展开**数据库**，然后展开 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="a31b3-132">Expand **Databases**, and then expand the BizTalk Management database.</span></span>  
  
5. <span data-ttu-id="a31b3-133">展开**安全**，展开**角色**，然后单击以选择**数据库角色**</span><span class="sxs-lookup"><span data-stu-id="a31b3-133">Expand **Security**, expand **Roles**, and then click to select **Database Roles**</span></span>  
  
6. <span data-ttu-id="a31b3-134">在细节窗格中，右键单击 BTS_HOST_USERS 角色，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-134">In the details pane, right-click the BTS_HOST_USERS role, and then click **Properties**.</span></span>  
  
7. <span data-ttu-id="a31b3-135">在 BTS_HOST_USERS 对话框中，单击**外**，单击**浏览**，然后选中要将其添加的 EDI Subsystem Users 组旁边的框。</span><span class="sxs-lookup"><span data-stu-id="a31b3-135">In the BTS_HOST_USERS dialog box, click **Add**, click **Browse**, and then check the box next to the EDI Subsystem Users group to add it.</span></span>  
  
    <span data-ttu-id="a31b3-136">如果 EDI Subsystem Users 组没有显示在要添加的用户列表中，则必须将 EDI Subsystem Users 组作为新数据库用户添加到 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="a31b3-136">If the EDI Subsystem Users group is not available in the list of users to add, you must add the EDI Subsystem Users group as a new database user to the BizTalk Management database.</span></span> <span data-ttu-id="a31b3-137">若要将 EDI Subsystem Users 组添加为新的数据库用户，完成 SQL Server Management Studio 中的以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a31b3-137">To add the EDI Subsystem Users group as a new database user, complete the following steps in SQL Server Management Studio:</span></span>  
  
   1.  <span data-ttu-id="a31b3-138">展开 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="a31b3-138">Expand the BizTalk Management database.</span></span>  
  
   2.  <span data-ttu-id="a31b3-139">展开**安全**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-139">Expand **Security**.</span></span>  
  
   3.  <span data-ttu-id="a31b3-140">右键单击**用户**然后单击**新用户**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-140">Right-click **Users** and click **New User**.</span></span>  
  
   4.  <span data-ttu-id="a31b3-141">单击文本框旁边的省略号 （...） 按钮**登录名**以显示**选择登录名**对话框。</span><span class="sxs-lookup"><span data-stu-id="a31b3-141">Click the ellipses (…) button next to the text box for **Login name** to display the **Select Login** dialog box.</span></span>  
  
   5.  <span data-ttu-id="a31b3-142">单击浏览按钮，输入**EDI Subsystem Users**组，然后依次**确定。**</span><span class="sxs-lookup"><span data-stu-id="a31b3-142">Click the Browse button, enter the **EDI Subsystem Users** group, and then click **OK.**</span></span> <span data-ttu-id="a31b3-143">如果出现提示**找到多个对象**对话框中，选择**EDI Subsystem Users**登录名并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-143">If prompted with the **Multiple Objects Found** dialog box, select the **EDI Subsystem Users** login and click **OK**.</span></span>  
  
   6.  <span data-ttu-id="a31b3-144">上**数据库用户-新建**对话框中输入**EDI Subsystem Users**有关**用户名**文本框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-144">On the **Database User - New** dialog box enter **EDI Subsystem Users** for the **User name** textbox and click **OK**.</span></span>  
  
   <span data-ttu-id="a31b3-145">**添加到 EDI Subsystem Users 组运行 BizTalk 服务的用户帐户。**</span><span class="sxs-lookup"><span data-stu-id="a31b3-145">**Add the user account under which the BizTalk service is running to the EDI Subsystem Users group.**</span></span>  
  
   <span data-ttu-id="a31b3-146">请按照下列步骤将 BizTalk 服务的用户帐户添加到 EDI Subsystem Users 组。</span><span class="sxs-lookup"><span data-stu-id="a31b3-146">Follow these steps to add the user account for the BizTalk service to the EDI Subsystem Users group.</span></span>  
  
-   <span data-ttu-id="a31b3-147">**如果 BizTalk Server 配置为使用域组：**</span><span class="sxs-lookup"><span data-stu-id="a31b3-147">**If BizTalk Server is configured to use domain groups:**</span></span>  
  
    1.  <span data-ttu-id="a31b3-148">登录到域中的 Windows Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="a31b3-148">Logon to a Windows Server computer in the domain.</span></span>  
  
    2.  <span data-ttu-id="a31b3-149">单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-149">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a31b3-150">必须具有相应的域级权限，才能修改中的对象**Active Directory 用户和计算机**接口。</span><span class="sxs-lookup"><span data-stu-id="a31b3-150">You must have appropriate domain level permissions to modify objects in the **Active Directory Users and Computers** interface.</span></span>  
  
    3.  <span data-ttu-id="a31b3-151">单击此项可展开域容器，然后单击以展开**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="a31b3-151">Click to expand the domain container and click to expand the **Users** container.</span></span>  
  
    4.  <span data-ttu-id="a31b3-152">双击**EDI Subsystem Users**组，以显示此组的属性。</span><span class="sxs-lookup"><span data-stu-id="a31b3-152">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="a31b3-153">单击**成员**选项卡**EDI Subsystem Users**组对话框。</span><span class="sxs-lookup"><span data-stu-id="a31b3-153">Click the **Members** tab of the **EDI Subsystem Users** group dialog.</span></span>  
  
    6.  <span data-ttu-id="a31b3-154">单击**添加**按钮将为 BizTalk 服务的用户帐户添加到此组。</span><span class="sxs-lookup"><span data-stu-id="a31b3-154">Click the **Add** button to add the user account for the BizTalk Service to this group.</span></span>  
  
    7.  <span data-ttu-id="a31b3-155">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a31b3-155">Click **OK**.</span></span>  
  
-   <span data-ttu-id="a31b3-156">**如果 BizTalk Server 配置为使用本地组：**</span><span class="sxs-lookup"><span data-stu-id="a31b3-156">**If BizTalk Server is configured to use local groups:**</span></span>  
  
    1.  <span data-ttu-id="a31b3-157">登录到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="a31b3-157">Logon to the BizTalk Server.</span></span>  
  
    2.  <span data-ttu-id="a31b3-158">单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-158">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
    3.  <span data-ttu-id="a31b3-159">单击此项可展开**系统工具**，单击此项可展开**本地用户和组**，并单击以展开**组**。</span><span class="sxs-lookup"><span data-stu-id="a31b3-159">Click to expand **System Tools**, click to expand **Local Users and Groups**, and click to expand **Groups**.</span></span>  
  
    4.  <span data-ttu-id="a31b3-160">双击**EDI Subsystem Users**组，以显示此组的属性。</span><span class="sxs-lookup"><span data-stu-id="a31b3-160">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="a31b3-161">单击**添加**按钮将 BizTalk 服务的用户帐户添加到此组。</span><span class="sxs-lookup"><span data-stu-id="a31b3-161">Click the **Add** button to add the user account for the BizTalk service to this group.</span></span>  
  
    6.  <span data-ttu-id="a31b3-162">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a31b3-162">Click **OK**.</span></span>