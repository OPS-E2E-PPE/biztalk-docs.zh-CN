---
title: "管理发送端口和发送端口组 |Microsoft 文档"
description: "链接来创建、 配置、 登记、 取消登记，以及开始和停止在 BizTalk Server 发送端口"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928160ed5b67602c8fc8d9d646459bf2425d7a01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-send-ports-and-send-port-groups"></a><span data-ttu-id="01454-103">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="01454-103">Manage Send Ports and Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="01454-104">概述</span><span class="sxs-lookup"><span data-stu-id="01454-104">Overview</span></span>
<span data-ttu-id="01454-105">本部分介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台创建、配置和管理 BizTalk 应用程序中的发送端口和发送端口组。</span><span class="sxs-lookup"><span data-stu-id="01454-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create, configure, and manage send ports and send port groups in a BizTalk application.</span></span> <span data-ttu-id="01454-106">发送端口指定消息发送到的位置，以及接收响应的位置（可选）。</span><span class="sxs-lookup"><span data-stu-id="01454-106">A send port specifies the location to which messages are sent and optionally responses are received.</span></span> <span data-ttu-id="01454-107">一条消息发送到发送端口，创建发送端口服务的新实例，这称为任何时间*服务实例*。</span><span class="sxs-lookup"><span data-stu-id="01454-107">Any time a message is sent to a send port, a new instance of the send port service is created, which is called a *service instance*.</span></span>  
  
 <span data-ttu-id="01454-108">发送端口组是发送端口的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="01454-108">A send port group is a logical grouping of send ports.</span></span> <span data-ttu-id="01454-109">消息发送到发送端口组后，会被路由到所有相关的发送端口。</span><span class="sxs-lookup"><span data-stu-id="01454-109">When a message is sent to a send port group, it is routed to all of the associated send ports.</span></span>  <span data-ttu-id="01454-110">发送端口和发送端口组有关背景信息，请参阅[发送端口和发送端口组](../core/send-ports-and-send-port-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="01454-110">For background information about send ports and send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01454-111">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="01454-111">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="01454-112">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="01454-112">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
> [!NOTE]
>  <span data-ttu-id="01454-113">开发 BizTalk 应用程序时，开发人员可使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 BizTalk 设计工具（例如业务流程设计器）来创建和配置发送端口和发送端口组。</span><span class="sxs-lookup"><span data-stu-id="01454-113">While developing a BizTalk application, the developer can use BizTalk design tools in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], such as Orchestration Designer, to create and configure send ports and send port groups.</span></span> <span data-ttu-id="01454-114">有关详细信息，请参阅[在业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="01454-114">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="01454-115">后续步骤</span><span class="sxs-lookup"><span data-stu-id="01454-115">Next steps</span></span>
  
-   [<span data-ttu-id="01454-116">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="01454-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)  
  
-   [<span data-ttu-id="01454-117">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="01454-117">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)  
  
-   [<span data-ttu-id="01454-118">登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="01454-118">Enlist a Send Port or Send Port Group</span></span>](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="01454-119">发送端口或发送端口组中取消</span><span class="sxs-lookup"><span data-stu-id="01454-119">Unenlist a Send Port or Send Port Group</span></span>](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="01454-120">启动发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="01454-120">Start a Send Port or Send Port Group</span></span>](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="01454-121">停止发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="01454-121">Stop a Send Port or Send Port Group</span></span>](../core/how-to-stop-a-send-port-or-send-port-group.md)