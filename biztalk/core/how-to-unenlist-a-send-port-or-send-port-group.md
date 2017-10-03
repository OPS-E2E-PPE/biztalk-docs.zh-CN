---
title: "如何取消登记发送端口或发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2599ae3d06a75506de244a4f996a9e77cef6ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="36d1d-102">如何取消登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="36d1d-102">How to Unenlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="36d1d-103">本主题将介绍如何使用 BizTalk Server 管理控制台来取消登记发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="36d1d-103">This topic describes how to use the BizTalk Server Administration console to unenlist a send port or send port group.</span></span> <span data-ttu-id="36d1d-104">取消登记发送端口或发送端口组可取消与该发送端口或发送端口组相关联的所有订阅。</span><span class="sxs-lookup"><span data-stu-id="36d1d-104">Unenlisting a send port or send port group eliminates all subscriptions associated with that send port or send port group.</span></span> <span data-ttu-id="36d1d-105">正在运行的和已停止的发送端口或发送端口组都可以取消登记。</span><span class="sxs-lookup"><span data-stu-id="36d1d-105">You can unenlist both running and stopped send ports or send port groups.</span></span> <span data-ttu-id="36d1d-106">取消登记发送端口或发送端口组将自动停止端口或端口组。</span><span class="sxs-lookup"><span data-stu-id="36d1d-106">Unenlisting a send port or send port group automatically stops it.</span></span>  
  
 <span data-ttu-id="36d1d-107">例如，您可能需要取消登记发送端口或发送端口组以编辑其绑定，或者取消登记发送端口或发送端口组以将其从 BizTalk Server 环境中删除。</span><span class="sxs-lookup"><span data-stu-id="36d1d-107">For example, you may want to unenlist a send port or send port group to edit its bindings, or if you want to remove the send port or send port group from the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="36d1d-108">您不能取消登记发送端口组中最近登记或运行的发送端口。</span><span class="sxs-lookup"><span data-stu-id="36d1d-108">You cannot unenlist the last enlisted send port within a send port group that is enlisted or running.</span></span> <span data-ttu-id="36d1d-109">取消登记发送端口组不会改变其包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="36d1d-109">Unenlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="36d1d-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="36d1d-110">Prerequisites</span></span>  
 <span data-ttu-id="36d1d-111">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="36d1d-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="36d1d-112">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="36d1d-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="36d1d-113">取消登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="36d1d-113">To unenlist a send port or send port group</span></span>  
  
1.  <span data-ttu-id="36d1d-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="36d1d-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="36d1d-115">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送到所需的端口组的应用程序取消登记。</span><span class="sxs-lookup"><span data-stu-id="36d1d-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to unenlist.</span></span>  
  
3.  <span data-ttu-id="36d1d-116">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**Unenlist**。</span><span class="sxs-lookup"><span data-stu-id="36d1d-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d1d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36d1d-117">See Also</span></span>  
 [<span data-ttu-id="36d1d-118">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="36d1d-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)