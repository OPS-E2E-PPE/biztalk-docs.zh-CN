---
title: 如何删除发送端口组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ddecbe657b8ea52a47133c5237bbad6a10b2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248893"
---
# <a name="how-to-delete-a-send-port-group"></a><span data-ttu-id="0bde6-102">如何删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="0bde6-102">How to Delete a Send Port Group</span></span>
<span data-ttu-id="0bde6-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口组。</span><span class="sxs-lookup"><span data-stu-id="0bde6-103">This topic describes how use the BizTalk Server Administration console to delete a send port group from a BizTalk application.</span></span> <span data-ttu-id="0bde6-104">执行此操作时，该组的 BizTalk 管理数据库中的发送端口组也会被删除。</span><span class="sxs-lookup"><span data-stu-id="0bde6-104">When you do this, the send port group is also deleted from the BizTalk Management database for the group.</span></span> <span data-ttu-id="0bde6-105">删除发送端口组不会删除该组包含的任何发送端口。</span><span class="sxs-lookup"><span data-stu-id="0bde6-105">Deleting a send port group does not delete any send ports that it contains.</span></span>  
  
 <span data-ttu-id="0bde6-106">发送端口组只在符合以下条件时才可以删除：</span><span class="sxs-lookup"><span data-stu-id="0bde6-106">You can delete a send port group only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="0bde6-107">没有业务流程绑定到该发送端口组。</span><span class="sxs-lookup"><span data-stu-id="0bde6-107">An orchestration is not bound to the send port group.</span></span> <span data-ttu-id="0bde6-108">如果出现这种情况，您可以通过执行中的说明删除绑定[如何取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="0bde6-108">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="0bde6-109">发送端口组已停止并已取消登记。</span><span class="sxs-lookup"><span data-stu-id="0bde6-109">The send port group is both stopped and unenlisted.</span></span> <span data-ttu-id="0bde6-110">有关停止和取消登记发送端口的说明，请参阅[如何发送端口或发送端口组中取消](../core/how-to-unenlist-a-send-port-or-send-port-group.md)和[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="0bde6-110">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="0bde6-111">没有参与方引用该发送端口组。</span><span class="sxs-lookup"><span data-stu-id="0bde6-111">The send port group is not referenced by a party.</span></span> <span data-ttu-id="0bde6-112">有关删除从方对发送端口组的引用的说明，请参阅[如何查看或编辑方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。</span><span class="sxs-lookup"><span data-stu-id="0bde6-112">For instructions on removing a reference to a send port group from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bde6-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="0bde6-113">Prerequisites</span></span>  
 <span data-ttu-id="0bde6-114">若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="0bde6-114">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0bde6-115">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0bde6-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port-group"></a><span data-ttu-id="0bde6-116">删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="0bde6-116">To delete a send port group</span></span>  
  
1.  <span data-ttu-id="0bde6-117">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0bde6-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0bde6-118">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的发送端口组的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0bde6-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the send port group that you want to delete.</span></span>  
  
3.  <span data-ttu-id="0bde6-119">单击**发送端口组**，右键单击发送端口组，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="0bde6-119">Click **Send Port Groups**, right-click the send port group, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bde6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bde6-120">See Also</span></span>  
 [<span data-ttu-id="0bde6-121">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="0bde6-121">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)