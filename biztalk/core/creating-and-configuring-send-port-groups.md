---
title: 创建和配置发送端口组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dd1ac37-a6e4-4ea0-9eff-ee400b3f3d74
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 987b1e9fe780ad6841a13a477678d3b61556fac7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238133"
---
# <a name="creating-and-configuring-send-port-groups"></a><span data-ttu-id="7b01b-102">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="7b01b-102">Creating and Configuring Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="7b01b-103">概述</span><span class="sxs-lookup"><span data-stu-id="7b01b-103">Overview</span></span>
<span data-ttu-id="7b01b-104">本部分介绍如何使用 BizTalk Server 管理控制台来向 BizTalk 应用程序中添加发送端口组，以及配置和删除发送端口组。</span><span class="sxs-lookup"><span data-stu-id="7b01b-104">This section provides instructions on using the BizTalk Server Administration console to add send port groups to a BizTalk application as well as to configure and delete send port groups.</span></span> <span data-ttu-id="7b01b-105">发送端口组是可用于向多个目标发送相同消息的发送端口的命名集合。</span><span class="sxs-lookup"><span data-stu-id="7b01b-105">A send port group is a named collection of send ports that can be used to send the same message to multiple destinations.</span></span> <span data-ttu-id="7b01b-106">您可以像使用单个发送端口一样，将发送端口组绑定到业务流程端口，或将发送端口组用于基于内容的路由 (CBR)。</span><span class="sxs-lookup"><span data-stu-id="7b01b-106">You can bind send port groups to orchestration ports or use them for content-based routing (CBR) just as you can for a single send port.</span></span> <span data-ttu-id="7b01b-107">发送端口组上的背景信息，请参阅[发送端口和发送端口组](../core/send-ports-and-send-port-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="7b01b-107">For background information on send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b01b-108">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="7b01b-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="7b01b-109">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b01b-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7b01b-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7b01b-110">Next steps</span></span>
  
-   [<span data-ttu-id="7b01b-111">创建发送端口组</span><span class="sxs-lookup"><span data-stu-id="7b01b-111">Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="7b01b-112">将发送端口添加到发送端口组</span><span class="sxs-lookup"><span data-stu-id="7b01b-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="7b01b-113">从发送端口组中删除发送端口</span><span class="sxs-lookup"><span data-stu-id="7b01b-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="7b01b-114">为发送端口组配置筛选器</span><span class="sxs-lookup"><span data-stu-id="7b01b-114">Configure Filters for a Send Port Group</span></span>](../core/how-to-configure-filters-for-a-send-port-group.md)  
  
-   [<span data-ttu-id="7b01b-115">删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="7b01b-115">Delete a Send Port Group</span></span>](../core/how-to-delete-a-send-port-group.md)