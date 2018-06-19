---
title: 如何启动发送端口或发送端口组 |Microsoft 文档
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
ms.openlocfilehash: 558a9b8444a38607f18757ff09196e44a3ae0b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255597"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="fd151-102">如何启动发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="fd151-102">How to Start a Send Port or Send Port Group</span></span>
<span data-ttu-id="fd151-103">本主题将介绍如何使用 BizTalk Server 管理控制台启动发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="fd151-103">This topic describes how to use the BizTalk Server Administration console to start a send port or send port group.</span></span> <span data-ttu-id="fd151-104">必须先启动发送端口或发送端口组，才能处理消息。</span><span class="sxs-lookup"><span data-stu-id="fd151-104">You must start a send port or send port group before it can process messages.</span></span> <span data-ttu-id="fd151-105">如果启动已取消登记的发送端口或发送端口组，则 BizTalk 将先登记该发送端口或发送端口组，然后再启动它。</span><span class="sxs-lookup"><span data-stu-id="fd151-105">If you start an unenlisted send port or send port group, BizTalk enlists the send port or send port group before starting it.</span></span> <span data-ttu-id="fd151-106">发送端口组中必须至少包含一个处于登记状态的发送端口，才能启动。</span><span class="sxs-lookup"><span data-stu-id="fd151-106">A send port group must contain at least one send port in an enlisted state before you can start the send port group.</span></span> <span data-ttu-id="fd151-107">启动和停止发送端口组不影响它所包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="fd151-107">Starting and stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd151-108">默认情况下，启动 BizTalk 应用程序将启动其包含的所有项目。</span><span class="sxs-lookup"><span data-stu-id="fd151-108">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="fd151-109">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fd151-109">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd151-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="fd151-110">Prerequisites</span></span>  
 <span data-ttu-id="fd151-111">若要执行本主题中的过程，则必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="fd151-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="fd151-112">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fd151-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="fd151-113">启动发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="fd151-113">To start a send port or send port group</span></span>  
  
1.  <span data-ttu-id="fd151-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="fd151-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fd151-115">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送到所需的端口组的应用程序开始日期。</span><span class="sxs-lookup"><span data-stu-id="fd151-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to start.</span></span>  
  
3.  <span data-ttu-id="fd151-116">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="fd151-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd151-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd151-117">See Also</span></span>  
 [<span data-ttu-id="fd151-118">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="fd151-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)