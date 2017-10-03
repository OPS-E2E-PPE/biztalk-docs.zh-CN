---
title: "添加 A4SWIFT 用户和更新 Windows 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a><span data-ttu-id="613ae-102">添加 A4SWIFT 用户和更新 Windows 组</span><span class="sxs-lookup"><span data-stu-id="613ae-102">Adding A4SWIFT Users and Updating Windows Groups</span></span>
<span data-ttu-id="613ae-103">创建和安装适用于消息修复和新提交角色的证书之后，你必须创建[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户并添加[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]到组的用户。</span><span class="sxs-lookup"><span data-stu-id="613ae-103">After you create and install certificates for Message Repair and New Submission roles, you must create [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and add [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] users to groups.</span></span>  
  
 <span data-ttu-id="613ae-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="613ae-104">**Summary**</span></span>  
  
 <span data-ttu-id="613ae-105">创建消息修复和新提交用户并添加到本地或域帐户[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户组，，如下所示：</span><span class="sxs-lookup"><span data-stu-id="613ae-105">Create Message Repair and New Submission users and add local or domain accounts to [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] user groups, as follows:</span></span>  
  
-   <span data-ttu-id="613ae-106">在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台中，你需要创建任意多个用户与你消息修复和新提交进程的工作流阶段角色。</span><span class="sxs-lookup"><span data-stu-id="613ae-106">In the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console, you need to create as many users as there are roles in the workflow stages of your Message Repair and New Submission process.</span></span> <span data-ttu-id="613ae-107">将不同的证书与每个这些用户相关联。</span><span class="sxs-lookup"><span data-stu-id="613ae-107">Associate a distinct certificate with each of these users.</span></span>  
  
-   <span data-ttu-id="613ae-108">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用工具，添加创建，修复，每个本地用户验证，或批准 A4SWIFT 用户到一条消息。</span><span class="sxs-lookup"><span data-stu-id="613ae-108">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add each local user who is creating, repairing, verifying, or approving a message to the A4SWIFT Users.</span></span>  
  
-   <span data-ttu-id="613ae-109">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用程序添加到 BizTalk 服务 BizTalk 组服务的登录为字段中列出的本地用户[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。</span><span class="sxs-lookup"><span data-stu-id="613ae-109">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add the local user that is listed in the Log On As field for the BizTalk Service BizTalk Group service to the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Users group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="613ae-110">有关详细信息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户和角色，请参阅[创建部门和适用于消息修复和新提交角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="613ae-110">For more information about [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and roles, see [Creating Departments and Roles for Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).</span></span>  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a><span data-ttu-id="613ae-111">若要将用户帐户添加到 A4SWIFT 用户组</span><span class="sxs-lookup"><span data-stu-id="613ae-111">To add User Accounts to the A4SWIFT Users Group</span></span>  
  
1.  <span data-ttu-id="613ae-112">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="613ae-112">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="613ae-113">在**计算机管理**对话框中，在左窗格中，展开**本地用户和组**，然后单击**组**。</span><span class="sxs-lookup"><span data-stu-id="613ae-113">In the **Computer Management** dialog box, in the left pane, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="613ae-114">在**计算机管理**对话框中，在右窗格中，双击**A4SWIFT 用户**。</span><span class="sxs-lookup"><span data-stu-id="613ae-114">In the **Computer Management** dialog box, in the right pane, double-click **A4SWIFT Users**.</span></span>  
  
4.  <span data-ttu-id="613ae-115">在**A4SWIFT 用户属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="613ae-115">In the **A4SWIFT Users Properties** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="613ae-116">在**选择用户、 计算机或组**对话框中，在**输入要选择的对象名称**窗格中，键入创建、 修复、 验证，或批准一条消息，本地用户的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="613ae-116">In the **Select Users, Computers, or Groups** dialog box, in the **Enter the object names to select** pane, type the name of a local user who is creating, repairing, verifying, or approving a message, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="613ae-117">对于每个本地用户创建、 修复、 验证，或批准一条消息重复步骤 5。</span><span class="sxs-lookup"><span data-stu-id="613ae-117">Repeat step 5 for each local user who is creating, repairing, verifying, or approving a message.</span></span>  
  
7.  <span data-ttu-id="613ae-118">在 A4SWIFT 用户属性对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="613ae-118">In the A4SWIFT Users Properties dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="613ae-119">在计算机管理对话框中，在左窗格中，展开服务和应用程序，，然后单击服务。</span><span class="sxs-lookup"><span data-stu-id="613ae-119">In the Computer Management dialog box, in the left pane, expand Services and Applications, and then click Services.</span></span> <span data-ttu-id="613ae-120">在右窗格中，单击**BizTalk 服务 BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="613ae-120">In the right pane, click **BizTalk Service BizTalk Group**.</span></span> <span data-ttu-id="613ae-121">请注意有关的登录为列中列出的用户**BizTalk 服务 BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="613ae-121">Note the user listed in the Log On As column for **BizTalk Service BizTalk Group**.</span></span>  
  
9. <span data-ttu-id="613ae-122">在左窗格中**计算机管理**对话框框中，展开**本地用户和组**，然后单击**组**。</span><span class="sxs-lookup"><span data-stu-id="613ae-122">In the left pane of the **Computer Management** dialog box, expand **Local Users and Groups**, and then click **Groups**.</span></span> <span data-ttu-id="613ae-123">双击**A4SWIFT 用户**。</span><span class="sxs-lookup"><span data-stu-id="613ae-123">Double-click **A4SWIFT Users**.</span></span> <span data-ttu-id="613ae-124">确保日志作为列中列出的用户**BizTalk 服务 BizTalk 组**属于**A4SWIFT 用户**组。</span><span class="sxs-lookup"><span data-stu-id="613ae-124">Ensure that the user listed in the Log On As column for **BizTalk Service BizTalk Group** is part of the **A4SWIFT Users** group.</span></span> <span data-ttu-id="613ae-125">否则，请添加到该用户**A4SWIFT 用户**组。</span><span class="sxs-lookup"><span data-stu-id="613ae-125">If not, add that user to the **A4SWIFT Users** group.</span></span>  
  
10. <span data-ttu-id="613ae-126">注销服务器，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="613ae-126">Log off the server, and then log back on.</span></span>