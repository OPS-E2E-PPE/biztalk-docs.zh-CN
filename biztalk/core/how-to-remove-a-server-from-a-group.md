---
title: 如何从一个组中删除服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- managing [groups], deleting servers
- servers, deleting
- deleting, groups
- servers
- managing [servers], deleting from groups
- groups, deleting
- servers, groups
- deleting, servers
ms.assetid: 85596e18-fa17-4f44-bc20-2e4cb578e109
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b8be9a991e70c3f1f4fb30673f2c1456a6fe3d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384343"
---
# <a name="how-to-remove-a-server-from-a-group"></a><span data-ttu-id="15f75-102">如何从一个组中删除服务器</span><span class="sxs-lookup"><span data-stu-id="15f75-102">How to Remove a Server from a Group</span></span>
<span data-ttu-id="15f75-103">一台服务器只能与一个 BizTalk 组相关联。</span><span class="sxs-lookup"><span data-stu-id="15f75-103">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="15f75-104">如果服务器已属于另一个组，则必须首先删除该服务器从其当前组之前可以将其添加到新的组。</span><span class="sxs-lookup"><span data-stu-id="15f75-104">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15f75-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="15f75-105">Prerequisites</span></span>  
 <span data-ttu-id="15f75-106">若要执行此过程，必须以 Windows 管理员组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="15f75-106">To perform this procedure, you must be logged on as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-remove-a-server-from-a-group"></a><span data-ttu-id="15f75-107">若要从组中删除服务器</span><span class="sxs-lookup"><span data-stu-id="15f75-107">To remove a server from a group</span></span>  
  
1. <span data-ttu-id="15f75-108">在你想要从 BizTalk Server 组中删除的计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.</span><span class="sxs-lookup"><span data-stu-id="15f75-108">On the computer that you want to remove from a BizTalk Server group, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="15f75-109">在菜单栏上，单击**取消对功能**。</span><span class="sxs-lookup"><span data-stu-id="15f75-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3. <span data-ttu-id="15f75-110">在中**取消对功能**对话框中，选择**组**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="15f75-110">In the **Unconfigure Features** dialog box, select **Group**, and then click **OK**.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="15f75-111">取消组配置还将取消已在该计算机配置的所有依存功能。</span><span class="sxs-lookup"><span data-stu-id="15f75-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4. <span data-ttu-id="15f75-112">单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="15f75-112">Click **Yes**.</span></span>  
  
5. <span data-ttu-id="15f75-113">在 Microsoft BizTalk Server 配置向导中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="15f75-113">In the Microsoft BizTalk Server Configuration Wizard, click **Next**.</span></span>  
  
    <span data-ttu-id="15f75-114">未配置组和它依赖的功能。</span><span class="sxs-lookup"><span data-stu-id="15f75-114">The Group and its dependent features are unconfigured.</span></span>  
  
6. <span data-ttu-id="15f75-115">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="15f75-115">Click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f75-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="15f75-116">See Also</span></span>  
 <span data-ttu-id="15f75-117">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="15f75-117">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="15f75-118">[BizTalk 组](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="15f75-118">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="15f75-119">[如何将服务器添加到组](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="15f75-119">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="15f75-120">[如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="15f75-120">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="15f75-121">[如何修改组属性](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="15f75-121">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="15f75-122">管理服务器</span><span class="sxs-lookup"><span data-stu-id="15f75-122">Managing Servers</span></span>](../core/managing-servers.md)