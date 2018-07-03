---
title: 如何启用的路由失败消息的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ac7ee9ef22ee3d0c452e47c886ff3298570d2c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974534"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="4ce2c-102">如何为接收端口启用失败消息路由功能</span><span class="sxs-lookup"><span data-stu-id="4ce2c-102">How to Enable Routing for Failed Messages for a Receive Port</span></span>
<span data-ttu-id="4ce2c-103">本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口所处理的消息启用路由功能。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-103">This topic describes how to use the BizTalk Server Administration console to enable routing for the messages processed by a receive port.</span></span> <span data-ttu-id="4ce2c-104">启用此选项后，BizTalk Server 将尝试把处理失败的所有消息路由至某个订阅应用程序（例如另一个接收端口或业务流程计划）。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-104">When you enable this option, BizTalk Server will attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="4ce2c-105">禁用此选项（默认情况）时，BizTalk Server 将挂起失败的消息并生成一个否定确认 (NACK)。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-105">When this option is not enabled (the default), BizTalk Server suspends failed messages and generates a negative acknowledgment (NACK).</span></span> <span data-ttu-id="4ce2c-106">有关管理失败的消息的背景信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-106">For background information about managing failed messages, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ce2c-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="4ce2c-107">Prerequisites</span></span>  
 <span data-ttu-id="4ce2c-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4ce2c-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a><span data-ttu-id="4ce2c-110">为接收端口启用失败消息路由功能</span><span class="sxs-lookup"><span data-stu-id="4ce2c-110">To enable routing for failed messages for a receive port</span></span>  
  
1. <span data-ttu-id="4ce2c-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4ce2c-112">在控制台树中，展开要为其配置失败消息路由的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure failed message routing for a receive port.</span></span>  
  
3. <span data-ttu-id="4ce2c-113">单击**接收端口**，右键单击接收端口，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-113">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="4ce2c-114">选择**失败消息启用路由功能**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="4ce2c-114">Select the **Enable routing for failed messages** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce2c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ce2c-115">See Also</span></span>  
 [<span data-ttu-id="4ce2c-116">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="4ce2c-116">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)