---
title: 管理接收端口 |Microsoft Docs
description: 快速链接，可以使用在 BizTalk Server 中，包括创建，接收端口添加接收位置，配置映射，并启用跟踪
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 561649b1-66f5-4895-b7a0-92d0a01bfbfb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc31bdab9f3c538a571e3fd6b082a431343683fb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531119"
---
# <a name="manage-receive-ports"></a><span data-ttu-id="359d3-103">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="359d3-103">Manage Receive Ports</span></span>

## <a name="overview"></a><span data-ttu-id="359d3-104">概述</span><span class="sxs-lookup"><span data-stu-id="359d3-104">Overview</span></span>
<span data-ttu-id="359d3-105">本部分介绍如何创建、 配置和管理接收端口的 BizTalk 应用程序通过使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="359d3-105">This section describes how to create, configure, and manage receive ports for a BizTalk application by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="359d3-106">逻辑分组相似接收位置的接收端口。</span><span class="sxs-lookup"><span data-stu-id="359d3-106">A receive port is logical grouping of similar receive locations.</span></span> <span data-ttu-id="359d3-107">有关背景信息接收端口，请参阅[接收端口](../core/receive-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="359d3-107">For background information on receive ports, see [Receive Ports](../core/receive-ports.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="359d3-108">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="359d3-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="359d3-109">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="359d3-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="359d3-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="359d3-110">Next steps</span></span>
  
-   [<span data-ttu-id="359d3-111">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="359d3-111">Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-112">查看接收端口的实例信息</span><span class="sxs-lookup"><span data-stu-id="359d3-112">View Instance Information for a Receive Port</span></span>](../core/how-to-view-instance-information-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-113">为接收端口配置身份验证选项</span><span class="sxs-lookup"><span data-stu-id="359d3-113">Configure Authentication Options for a Receive Port</span></span>](../core/how-to-configure-authentication-options-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-114">为接收端口启用失败消息路由功能</span><span class="sxs-lookup"><span data-stu-id="359d3-114">Enable Routing for Failed Messages for a Receive Port</span></span>](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-115">将接收位置添加到接收端口</span><span class="sxs-lookup"><span data-stu-id="359d3-115">Add a Receive Location to a Receive Port</span></span>](../core/how-to-add-a-receive-location-to-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-116">为接收端口配置入站映射</span><span class="sxs-lookup"><span data-stu-id="359d3-116">Configure Inbound Maps for a Receive Port</span></span>](../core/how-to-configure-inbound-maps-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-117">为接收端口配置出站映射</span><span class="sxs-lookup"><span data-stu-id="359d3-117">Configure Outbound Maps for a Receive Port</span></span>](../core/how-to-configure-outbound-maps-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-118">为接收端口配置跟踪</span><span class="sxs-lookup"><span data-stu-id="359d3-118">Configure Tracking for a Receive Port</span></span>](../core/how-to-configure-tracking-for-a-receive-port.md)  
  
-   [<span data-ttu-id="359d3-119">删除接收端口</span><span class="sxs-lookup"><span data-stu-id="359d3-119">Delete a Receive Port</span></span>](../core/how-to-delete-a-receive-port.md)