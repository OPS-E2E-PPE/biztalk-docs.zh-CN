---
title: 如何启动发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1749862ee78c549d3aa3fd79a62eedd1ecba144
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334041"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="1470a-102">如何启动发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="1470a-102">How to Start a Send Port or Send Port Group</span></span>
<span data-ttu-id="1470a-103">本主题介绍如何使用 BizTalk Server 管理控制台启动发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="1470a-103">This topic describes how to use the BizTalk Server Administration console to start a send port or send port group.</span></span> <span data-ttu-id="1470a-104">必须启动发送端口或发送端口组，然后才能处理消息。</span><span class="sxs-lookup"><span data-stu-id="1470a-104">You must start a send port or send port group before it can process messages.</span></span> <span data-ttu-id="1470a-105">如果启动某个已取消登记的发送端口或发送端口组，BizTalk 将登记发送端口或发送端口组，然后再启动它。</span><span class="sxs-lookup"><span data-stu-id="1470a-105">If you start an unenlisted send port or send port group, BizTalk enlists the send port or send port group before starting it.</span></span> <span data-ttu-id="1470a-106">发送端口组必须包含至少一个发送端口处于登记状态，然后才能启动发送端口组。</span><span class="sxs-lookup"><span data-stu-id="1470a-106">A send port group must contain at least one send port in an enlisted state before you can start the send port group.</span></span> <span data-ttu-id="1470a-107">启动和停止发送端口组不会影响它所包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="1470a-107">Starting and stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1470a-108">默认情况下，启动 BizTalk 应用程序启动的所有项目，它包含。</span><span class="sxs-lookup"><span data-stu-id="1470a-108">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="1470a-109">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1470a-109">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1470a-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="1470a-110">Prerequisites</span></span>  
 <span data-ttu-id="1470a-111">若要执行本主题中的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="1470a-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="1470a-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1470a-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="1470a-113">若要启动的发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="1470a-113">To start a send port or send port group</span></span>  
  
1. <span data-ttu-id="1470a-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1470a-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="1470a-115">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序开始日期。</span><span class="sxs-lookup"><span data-stu-id="1470a-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to start.</span></span>  
  
3. <span data-ttu-id="1470a-116">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1470a-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1470a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1470a-117">See Also</span></span>  
 [<span data-ttu-id="1470a-118">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="1470a-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)