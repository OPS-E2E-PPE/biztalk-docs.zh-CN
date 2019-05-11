---
title: 创建和配置发送端口组 |Microsoft Docs
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
ms.openlocfilehash: 882322d6f8197868ee81e95e3a7809d15266356d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389963"
---
# <a name="creating-and-configuring-send-port-groups"></a><span data-ttu-id="47fc9-102">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="47fc9-102">Creating and Configuring Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="47fc9-103">概述</span><span class="sxs-lookup"><span data-stu-id="47fc9-103">Overview</span></span>
<span data-ttu-id="47fc9-104">本部分介绍如何使用 BizTalk Server 管理控制台添加发送端口组到 BizTalk 应用程序配置和删除发送端口组。</span><span class="sxs-lookup"><span data-stu-id="47fc9-104">This section provides instructions on using the BizTalk Server Administration console to add send port groups to a BizTalk application as well as to configure and delete send port groups.</span></span> <span data-ttu-id="47fc9-105">发送端口组是可用于将同一消息发送到多个目标的发送端口的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="47fc9-105">A send port group is a named collection of send ports that can be used to send the same message to multiple destinations.</span></span> <span data-ttu-id="47fc9-106">可以将发送端口组绑定到业务流程端口，或将其用于基于内容的路由 (CBR)，就像您可以使用单个发送端口。</span><span class="sxs-lookup"><span data-stu-id="47fc9-106">You can bind send port groups to orchestration ports or use them for content-based routing (CBR) just as you can for a single send port.</span></span> <span data-ttu-id="47fc9-107">发送端口组的背景信息，请参阅[发送端口和发送端口组](../core/send-ports-and-send-port-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="47fc9-107">For background information on send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47fc9-108">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="47fc9-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="47fc9-109">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="47fc9-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="47fc9-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="47fc9-110">Next steps</span></span>
  
-   [<span data-ttu-id="47fc9-111">创建发送端口组</span><span class="sxs-lookup"><span data-stu-id="47fc9-111">Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="47fc9-112">向发送端口组添加发送端口</span><span class="sxs-lookup"><span data-stu-id="47fc9-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="47fc9-113">从发送端口组中删除发送端口</span><span class="sxs-lookup"><span data-stu-id="47fc9-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="47fc9-114">为发送端口组配置筛选器</span><span class="sxs-lookup"><span data-stu-id="47fc9-114">Configure Filters for a Send Port Group</span></span>](../core/how-to-configure-filters-for-a-send-port-group.md)  
  
-   [<span data-ttu-id="47fc9-115">删除发送端口组</span><span class="sxs-lookup"><span data-stu-id="47fc9-115">Delete a Send Port Group</span></span>](../core/how-to-delete-a-send-port-group.md)