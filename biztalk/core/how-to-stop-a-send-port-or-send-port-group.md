---
title: "如何停止发送端口或发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="a6f11-102">如何停止发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="a6f11-102">How to Stop a Send Port or Send Port Group</span></span>
<span data-ttu-id="a6f11-103">本主题将介绍如何使用 BizTalk Server 管理控制台停止发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="a6f11-103">This topic describes how to use the BizTalk Server Administration console to stop a send port or send port group.</span></span> <span data-ttu-id="a6f11-104">停止发送端口或发送端口组时，它不再处理消息。</span><span class="sxs-lookup"><span data-stu-id="a6f11-104">When you stop a send port or send port group, it no longer processes messages.</span></span> <span data-ttu-id="a6f11-105">BizTalk Server 挂起所有发往已停止的发送端口或发送端口组的激活消息。</span><span class="sxs-lookup"><span data-stu-id="a6f11-105">BizTalk Server suspends all activation messages to a stopped send port or send port group.</span></span> <span data-ttu-id="a6f11-106">停止发送端口组不会影响其包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="a6f11-106">Stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6f11-107">默认情况下，启动 BizTalk 应用程序将启动其包含的所有项目。</span><span class="sxs-lookup"><span data-stu-id="a6f11-107">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="a6f11-108">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f11-108">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6f11-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a6f11-109">Prerequisites</span></span>  
 <span data-ttu-id="a6f11-110">若要执行本主题中描述的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="a6f11-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a6f11-111">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f11-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="a6f11-112">停止发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="a6f11-112">To stop a send port or send port group</span></span>  
  
1.  <span data-ttu-id="a6f11-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a6f11-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6f11-114">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送到所需的端口组的应用程序停止。</span><span class="sxs-lookup"><span data-stu-id="a6f11-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to stop.</span></span>  
  
3.  <span data-ttu-id="a6f11-115">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口，，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="a6f11-115">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f11-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f11-116">See Also</span></span>  
 [<span data-ttu-id="a6f11-117">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="a6f11-117">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)