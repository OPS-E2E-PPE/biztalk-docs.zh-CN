---
title: 如何管理 BizTalk Server Administrators 组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b22fff1ff8216021ba11038d5ee275f4dd0bb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336714"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a><span data-ttu-id="b5c40-102">如何管理 BizTalk Server Administrators 组</span><span class="sxs-lookup"><span data-stu-id="b5c40-102">How to Manage the BizTalk Server Administrators Group</span></span>
<span data-ttu-id="b5c40-103">BizTalk Server Administrators 组具有执行管理任务所需的最少权限。</span><span class="sxs-lookup"><span data-stu-id="b5c40-103">The BizTalk Server Administrators group has the fewest privileges necessary to perform administrative tasks.</span></span> <span data-ttu-id="b5c40-104">将用户添加到 BizTalk Server Administrators 组，以便他们可以通过使用 BizTalk Server 管理控制台或 WMI 提供程序执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="b5c40-104">You add users to the BizTalk Server Administrators group so that they can perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span> <span data-ttu-id="b5c40-105">您还用户从组中删除 BizTalk Server 管理员不再需要使用 BizTalk Server 管理控制台或 WMI 提供程序执行管理任务时。</span><span class="sxs-lookup"><span data-stu-id="b5c40-105">You also remove users from the BizTalk Server Administrators group when they no longer need to perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5c40-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="b5c40-106">Prerequisites</span></span>  
 <span data-ttu-id="b5c40-107">必须是要执行此过程的 Administrators 或 Domain Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b5c40-107">You must be a member of the Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a><span data-ttu-id="b5c40-108">若要将用户添加到本地 BizTalk Server Administrators 组</span><span class="sxs-lookup"><span data-stu-id="b5c40-108">To add users to the local BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="b5c40-109">单击**启动**，依次指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-109">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="b5c40-110">展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5c40-110">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="b5c40-111">详细信息窗格中显示该文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="b5c40-111">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="b5c40-112">在详细信息窗格中，单击**BizTalk Server Administrators**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-112">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="b5c40-113">上**操作**菜单，依次指向**的所有任务**，然后单击**将添加到组**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-113">On the **Action** menu, point to **All Tasks**, and then click **Add to Group**.</span></span>  
  
5.  <span data-ttu-id="b5c40-114">在中**BizTalk Server Administrators 属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-114">In the **BizTalk Server Administrators Properties** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="b5c40-115">在中**查找**列表中，选择你的域或计算机名称。</span><span class="sxs-lookup"><span data-stu-id="b5c40-115">In the **Look in** list, select your domain or computer name.</span></span>  
  
7.  <span data-ttu-id="b5c40-116">在列表中包含的用户和计算机与域或在步骤 6 中所选的计算机关联，选择要添加，请单击用户帐户**外**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-116">In the list that contains the users and computers associated with the domain or computer you selected in step 6, select the user account to add, click **Add**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b5c40-117">单击**确定**以关闭**BizTalk Server Administrators 属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="b5c40-117">Click **OK** to close the **BizTalk Server Administrators Properties** dialog box.</span></span>  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a><span data-ttu-id="b5c40-118">若要从本地 BizTalk Server Administrators 组中删除用户</span><span class="sxs-lookup"><span data-stu-id="b5c40-118">To remove users from local the BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="b5c40-119">单击**启动**，依次指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-119">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="b5c40-120">展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5c40-120">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="b5c40-121">详细信息窗格中显示该文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="b5c40-121">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="b5c40-122">在详细信息窗格中，单击**BizTalk Server Administrators**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-122">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="b5c40-123">上**操作**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-123">On the **Action** menu, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="b5c40-124">在中**BizTalk Server Administrators 属性**对话框中，选择的用户的帐户是你想要删除，并单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-124">In the **BizTalk Server Administrators Properties** dialog box, select the user account you want to remove, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="b5c40-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b5c40-125">Click **OK**.</span></span>  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="b5c40-126">若要将用户添加到域 BizTalk Server Administrators 组</span><span class="sxs-lookup"><span data-stu-id="b5c40-126">To add users to the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="b5c40-127">登录到其中的 SQL Server 数据库联接使用域管理员帐户的域控制器上。</span><span class="sxs-lookup"><span data-stu-id="b5c40-127">Log on to the domain controller where the SQL Server databases are joined by using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="b5c40-128">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="b5c40-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="b5c40-129">在控制台树中，单击包含你想要将成员添加的 BizTalk Server Administrators 组的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5c40-129">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="b5c40-130">在细节窗格中，右键单击 BizTalk Server Administrators 组，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-130">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="b5c40-131">上**成员**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-131">On the **Members** tab, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="b5c40-132">在中**输入要选择的对象名称**，键入用户的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-132">In **Enter the object names to select**, type the name of the user, and then click **OK**.</span></span>  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="b5c40-133">若要从域 BizTalk Server Administrators 组中删除用户</span><span class="sxs-lookup"><span data-stu-id="b5c40-133">To remove users from the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="b5c40-134">登录到域控制器的 SQL 数据库联接使用域管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="b5c40-134">Log on to the domain controller where SQL databases are joined using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="b5c40-135">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="b5c40-135">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="b5c40-136">在控制台树中，单击包含你想要将成员添加的 BizTalk Server Administrators 组的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5c40-136">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="b5c40-137">在细节窗格中，右键单击 BizTalk Server Administrators 组，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-137">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="b5c40-138">上**成员**选项卡上，单击你想要删除，然后单击的成员**删除**。</span><span class="sxs-lookup"><span data-stu-id="b5c40-138">On the **Members** tab, click the member you want to remove, and then click **Remove**.</span></span>  
  
    4.  <span data-ttu-id="b5c40-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b5c40-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c40-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5c40-140">See Also</span></span>  
 <span data-ttu-id="b5c40-141">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="b5c40-141">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="b5c40-142">[管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="b5c40-142">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="b5c40-143">[管理 Windows 组和用户帐户的最佳实践](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="b5c40-143">[Best Practices for Managing Windows Groups and User Accounts](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span></span>  
 <span data-ttu-id="b5c40-144">[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5c40-144">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b5c40-145">管理 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="b5c40-145">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)