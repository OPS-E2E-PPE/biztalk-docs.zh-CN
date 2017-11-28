---
title: "如何管理 BizTalk Server Administrators 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a><span data-ttu-id="c4290-102">如何管理 BizTalk Server Administrators 组</span><span class="sxs-lookup"><span data-stu-id="c4290-102">How to Manage the BizTalk Server Administrators Group</span></span>
<span data-ttu-id="c4290-103">BizTalk Server 管理员组具有执行管理任务所需的最低权限。</span><span class="sxs-lookup"><span data-stu-id="c4290-103">The BizTalk Server Administrators group has the fewest privileges necessary to perform administrative tasks.</span></span> <span data-ttu-id="c4290-104">您可以使用 BizTalk Server 管理控制台或 WMI 提供程序将用户添加到 BizTalk Server Administrators 组中，以便用户可以执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="c4290-104">You add users to the BizTalk Server Administrators group so that they can perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span> <span data-ttu-id="c4290-105">当不再需要用户执行管理任务时，也可以使用 BizTalk Server 管理控制台或 WMI 提供程序将用户从 BizTalk Server Administrators 组中删除。</span><span class="sxs-lookup"><span data-stu-id="c4290-105">You also remove users from the BizTalk Server Administrators group when they no longer need to perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4290-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="c4290-106">Prerequisites</span></span>  
 <span data-ttu-id="c4290-107">此过程必须由 Administrators 组或域 Admins 组的成员来执行。</span><span class="sxs-lookup"><span data-stu-id="c4290-107">You must be a member of the Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a><span data-ttu-id="c4290-108">向本地 BizTalk Server Administrators 组中添加用户</span><span class="sxs-lookup"><span data-stu-id="c4290-108">To add users to the local BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="c4290-109">单击**启动**，指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="c4290-109">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="c4290-110">展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4290-110">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="c4290-111">该文件夹的内容将出现在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="c4290-111">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="c4290-112">在详细信息窗格中，单击**BizTalk Server Administrators**。</span><span class="sxs-lookup"><span data-stu-id="c4290-112">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="c4290-113">上**操作**菜单上，指向**所有任务**，然后单击**将添加到组**。</span><span class="sxs-lookup"><span data-stu-id="c4290-113">On the **Action** menu, point to **All Tasks**, and then click **Add to Group**.</span></span>  
  
5.  <span data-ttu-id="c4290-114">在**BizTalk 服务器管理员属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c4290-114">In the **BizTalk Server Administrators Properties** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="c4290-115">在**查找**列表中，选择你的域或计算机名称。</span><span class="sxs-lookup"><span data-stu-id="c4290-115">In the **Look in** list, select your domain or computer name.</span></span>  
  
7.  <span data-ttu-id="c4290-116">在列表中包含的用户和计算机与域或在步骤 6 中所选的计算机关联，选择要添加，请单击的用户帐户**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c4290-116">In the list that contains the users and computers associated with the domain or computer you selected in step 6, select the user account to add, click **Add**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="c4290-117">单击**确定**关闭**BizTalk 服务器管理员属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="c4290-117">Click **OK** to close the **BizTalk Server Administrators Properties** dialog box.</span></span>  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a><span data-ttu-id="c4290-118">从本地 BizTalk Server Administrators 组中删除用户</span><span class="sxs-lookup"><span data-stu-id="c4290-118">To remove users from local the BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="c4290-119">单击**启动**，指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="c4290-119">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="c4290-120">展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4290-120">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="c4290-121">该文件夹的内容将出现在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="c4290-121">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="c4290-122">在详细信息窗格中，单击**BizTalk Server Administrators**。</span><span class="sxs-lookup"><span data-stu-id="c4290-122">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="c4290-123">上**操作**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c4290-123">On the **Action** menu, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="c4290-124">在**BizTalk 服务器管理员属性**对话框中，选择的用户的帐户是你想要删除，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="c4290-124">In the **BizTalk Server Administrators Properties** dialog box, select the user account you want to remove, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="c4290-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c4290-125">Click **OK**.</span></span>  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="c4290-126">向域 BizTalk Server Administrators 组中添加用户</span><span class="sxs-lookup"><span data-stu-id="c4290-126">To add users to the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="c4290-127">使用域 Admins 帐户登录到与 SQL Server 数据库联接的域控制器。</span><span class="sxs-lookup"><span data-stu-id="c4290-127">Log on to the domain controller where the SQL Server databases are joined by using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="c4290-128">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="c4290-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="c4290-129">在控制台树中，单击要向其中添加成员的 BizTalk Server Administrators 组所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4290-129">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="c4290-130">在细节窗格中，右键单击 BizTalk Server Administrators 组中，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c4290-130">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="c4290-131">上**成员**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c4290-131">On the **Members** tab, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="c4290-132">在**输入要选择的对象名称**，键入用户的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c4290-132">In **Enter the object names to select**, type the name of the user, and then click **OK**.</span></span>  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="c4290-133">从域 BizTalk Server 管理员组中删除用户</span><span class="sxs-lookup"><span data-stu-id="c4290-133">To remove users from the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="c4290-134">使用域 Admins 帐户登录到与 SQL 数据库联接的域控制器。</span><span class="sxs-lookup"><span data-stu-id="c4290-134">Log on to the domain controller where SQL databases are joined using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="c4290-135">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="c4290-135">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="c4290-136">在控制台树中，单击要向其中添加成员的 BizTalk Server Administrators 组所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4290-136">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="c4290-137">在细节窗格中，右键单击 BizTalk Server Administrators 组中，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c4290-137">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="c4290-138">上**成员**选项卡上，单击你想要删除，，然后单击的成员**删除**。</span><span class="sxs-lookup"><span data-stu-id="c4290-138">On the **Members** tab, click the member you want to remove, and then click **Remove**.</span></span>  
  
    4.  <span data-ttu-id="c4290-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c4290-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4290-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4290-140">See Also</span></span>  
 <span data-ttu-id="c4290-141">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="c4290-141">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="c4290-142">[管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="c4290-142">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="c4290-143">[管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="c4290-143">[Best Practices for Managing Windows Groups and User Accounts](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span></span>  
 <span data-ttu-id="c4290-144">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="c4290-144">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="c4290-145">管理 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="c4290-145">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)