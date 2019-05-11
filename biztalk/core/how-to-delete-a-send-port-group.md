---
title: 如何删除发送端口组 |Microsoft Docs
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
ms.openlocfilehash: c3edf36e0e7d8eaa512b8495e53097261e5c9be6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385349"
---
# <a name="how-to-delete-a-send-port-group"></a><span data-ttu-id="902f4-102">如何删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="902f4-102">How to Delete a Send Port Group</span></span>
<span data-ttu-id="902f4-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口组。</span><span class="sxs-lookup"><span data-stu-id="902f4-103">This topic describes how use the BizTalk Server Administration console to delete a send port group from a BizTalk application.</span></span> <span data-ttu-id="902f4-104">执行此操作，发送端口组是还从该组的 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="902f4-104">When you do this, the send port group is also deleted from the BizTalk Management database for the group.</span></span> <span data-ttu-id="902f4-105">删除发送端口组不会删除它包含任何发送端口。</span><span class="sxs-lookup"><span data-stu-id="902f4-105">Deleting a send port group does not delete any send ports that it contains.</span></span>  
  
 <span data-ttu-id="902f4-106">可以删除发送端口组，仅当满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="902f4-106">You can delete a send port group only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="902f4-107">业务流程未绑定到发送端口组。</span><span class="sxs-lookup"><span data-stu-id="902f4-107">An orchestration is not bound to the send port group.</span></span> <span data-ttu-id="902f4-108">如果是这样，您可以通过执行中的说明删除绑定[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="902f4-108">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="902f4-109">发送端口组是同时停止并取消登记。</span><span class="sxs-lookup"><span data-stu-id="902f4-109">The send port group is both stopped and unenlisted.</span></span> <span data-ttu-id="902f4-110">有关停止和取消登记发送端口的说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)并[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="902f4-110">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="902f4-111">参与方未引用的发送端口组。</span><span class="sxs-lookup"><span data-stu-id="902f4-111">The send port group is not referenced by a party.</span></span> <span data-ttu-id="902f4-112">删除对发送端口组从参与方的引用的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。</span><span class="sxs-lookup"><span data-stu-id="902f4-112">For instructions on removing a reference to a send port group from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="902f4-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="902f4-113">Prerequisites</span></span>  
 <span data-ttu-id="902f4-114">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="902f4-114">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="902f4-115">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="902f4-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port-group"></a><span data-ttu-id="902f4-116">若要删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="902f4-116">To delete a send port group</span></span>  
  
1. <span data-ttu-id="902f4-117">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="902f4-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="902f4-118">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的发送端口组的应用程序。</span><span class="sxs-lookup"><span data-stu-id="902f4-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the send port group that you want to delete.</span></span>  
  
3. <span data-ttu-id="902f4-119">单击**发送端口组**，右键单击发送端口组，并单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="902f4-119">Click **Send Port Groups**, right-click the send port group, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902f4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="902f4-120">See Also</span></span>  
 [<span data-ttu-id="902f4-121">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="902f4-121">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)