---
title: 如何停止发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31efef1a958e7faa2e08eaaa59abf4c8dca472a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383824"
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="e1552-102">如何停止发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="e1552-102">How to Stop a Send Port or Send Port Group</span></span>
<span data-ttu-id="e1552-103">本主题介绍如何使用 BizTalk Server 管理控制台停止发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e1552-103">This topic describes how to use the BizTalk Server Administration console to stop a send port or send port group.</span></span> <span data-ttu-id="e1552-104">当您停止发送端口或发送端口组时，它不再处理消息。</span><span class="sxs-lookup"><span data-stu-id="e1552-104">When you stop a send port or send port group, it no longer processes messages.</span></span> <span data-ttu-id="e1552-105">BizTalk Server 将挂起所有激活消息到已停止的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e1552-105">BizTalk Server suspends all activation messages to a stopped send port or send port group.</span></span> <span data-ttu-id="e1552-106">停止发送端口组不会影响它所包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="e1552-106">Stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1552-107">默认情况下，启动 BizTalk 应用程序启动的所有项目，它包含。</span><span class="sxs-lookup"><span data-stu-id="e1552-107">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="e1552-108">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e1552-108">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1552-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="e1552-109">Prerequisites</span></span>  
 <span data-ttu-id="e1552-110">若要执行本主题中的过程，必须是 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e1552-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e1552-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e1552-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="e1552-112">若要停止的发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="e1552-112">To stop a send port or send port group</span></span>  
  
1. <span data-ttu-id="e1552-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e1552-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e1552-114">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序停止。</span><span class="sxs-lookup"><span data-stu-id="e1552-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to stop.</span></span>  
  
3. <span data-ttu-id="e1552-115">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="e1552-115">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1552-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1552-116">See Also</span></span>  
 [<span data-ttu-id="e1552-117">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="e1552-117">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)