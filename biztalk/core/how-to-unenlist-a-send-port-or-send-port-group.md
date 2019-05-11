---
title: 如何取消登记发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dbd8a3a7c3450fcf36d66467cd95a38e39583dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333779"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="78b3e-102">如何取消登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="78b3e-102">How to Unenlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="78b3e-103">本主题介绍如何使用 BizTalk Server 管理控制台来取消登记发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="78b3e-103">This topic describes how to use the BizTalk Server Administration console to unenlist a send port or send port group.</span></span> <span data-ttu-id="78b3e-104">取消登记发送端口或发送端口组可消除与该发送端口关联的所有订阅，或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="78b3e-104">Unenlisting a send port or send port group eliminates all subscriptions associated with that send port or send port group.</span></span> <span data-ttu-id="78b3e-105">你可以取消登记正在运行和已停止的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="78b3e-105">You can unenlist both running and stopped send ports or send port groups.</span></span> <span data-ttu-id="78b3e-106">自动取消登记发送端口或发送端口组将停止它。</span><span class="sxs-lookup"><span data-stu-id="78b3e-106">Unenlisting a send port or send port group automatically stops it.</span></span>  
  
 <span data-ttu-id="78b3e-107">例如，你可能想要取消登记发送端口或发送端口组，若要编辑其绑定，或者如果你想要删除发送端口或发送端口组从 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="78b3e-107">For example, you may want to unenlist a send port or send port group to edit its bindings, or if you want to remove the send port or send port group from the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="78b3e-108">无法取消登记发送端口组，或运行中的最后一个已登记的发送端口。</span><span class="sxs-lookup"><span data-stu-id="78b3e-108">You cannot unenlist the last enlisted send port within a send port group that is enlisted or running.</span></span> <span data-ttu-id="78b3e-109">取消登记发送端口组不会更改它所包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="78b3e-109">Unenlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="78b3e-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="78b3e-110">Prerequisites</span></span>  
 <span data-ttu-id="78b3e-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="78b3e-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="78b3e-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="78b3e-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="78b3e-113">若要取消登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="78b3e-113">To unenlist a send port or send port group</span></span>  
  
1. <span data-ttu-id="78b3e-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="78b3e-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="78b3e-115">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序取消登记。</span><span class="sxs-lookup"><span data-stu-id="78b3e-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="78b3e-116">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="78b3e-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b3e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="78b3e-117">See Also</span></span>  
 [<span data-ttu-id="78b3e-118">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="78b3e-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)