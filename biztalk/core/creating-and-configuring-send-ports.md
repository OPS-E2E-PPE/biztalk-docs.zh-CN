---
title: "若要创建和配置的快速链接发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b26ed07-b7ed-48a5-9bd9-dfba9c1d3c02
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31361c9a6dff1d35c21bede4a82d513c6a073218
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-configuring-send-ports"></a><span data-ttu-id="b544e-102">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="b544e-102">Creating and Configuring Send Ports</span></span>

## <a name="overview"></a><span data-ttu-id="b544e-103">概述</span><span class="sxs-lookup"><span data-stu-id="b544e-103">Overview</span></span>
<span data-ttu-id="b544e-104">此部分提供有关使用说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建和配置 BizTalk 应用程序的发送端口。</span><span class="sxs-lookup"><span data-stu-id="b544e-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create and configure send ports for a BizTalk application.</span></span> <span data-ttu-id="b544e-105">发送端口是接收和发送消息的位置，它是由名称唯一标识的。</span><span class="sxs-lookup"><span data-stu-id="b544e-105">A send port is a location to which messages are sent or from which messages are received and is uniquely identified by its name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b544e-106">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="b544e-106">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="b544e-107">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="b544e-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b544e-108">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b544e-108">Next steps</span></span>
  
-   [<span data-ttu-id="b544e-109">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="b544e-109">Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="b544e-110">发送端口的视图实例信息</span><span class="sxs-lookup"><span data-stu-id="b544e-110">View Instance Information for a Send Port</span></span>](../core/how-to-view-instance-information-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-111">配置每个实例管道发送端口属性</span><span class="sxs-lookup"><span data-stu-id="b544e-111">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-112">将发送端口添加到发送端口组</span><span class="sxs-lookup"><span data-stu-id="b544e-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="b544e-113">从发送端口组中删除发送端口</span><span class="sxs-lookup"><span data-stu-id="b544e-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="b544e-114">配置用于发送端口的高级选项的传输</span><span class="sxs-lookup"><span data-stu-id="b544e-114">Configure Transport Advanced Options for a Send Port</span></span>](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-115">配置发送端口的备份传输选项</span><span class="sxs-lookup"><span data-stu-id="b544e-115">Configure Backup Transport Options for a Send Port</span></span>](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-116">配置为发送端口的入站的映射</span><span class="sxs-lookup"><span data-stu-id="b544e-116">Configure Inbound Maps for a Send Port</span></span>](../core/how-to-configure-inbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-117">配置为发送端口的出站映射</span><span class="sxs-lookup"><span data-stu-id="b544e-117">Configure Outbound Maps for a Send Port</span></span>](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-118">配置为发送端口的筛选器</span><span class="sxs-lookup"><span data-stu-id="b544e-118">Configure Filters for a Send Port</span></span>](../core/how-to-configure-filters-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-119">将证书分配给发送端口</span><span class="sxs-lookup"><span data-stu-id="b544e-119">Assign a Certificate to a Send Port</span></span>](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-120">从发送端口中删除证书</span><span class="sxs-lookup"><span data-stu-id="b544e-120">Remove a Certificate from a Send Port</span></span>](../core/how-to-remove-a-certificate-from-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-121">配置为发送端口的跟踪</span><span class="sxs-lookup"><span data-stu-id="b544e-121">Configure Tracking for a Send Port</span></span>](../core/how-to-configure-tracking-for-a-send-port.md)  
  
-   [<span data-ttu-id="b544e-122">删除发送端口</span><span class="sxs-lookup"><span data-stu-id="b544e-122">Delete a Send Port</span></span>](../core/how-to-delete-a-send-port.md)