---
title: 转换和路由到多个终结点的一条消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c0fc2b3b9893607f760c564d03fc6090a7f1ea0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010238"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a><span data-ttu-id="8b377-102">转换和路由到多个终结点的一条消息</span><span class="sxs-lookup"><span data-stu-id="8b377-102">Transforming and Routing a Message to Multiple Endpoints</span></span>
<span data-ttu-id="8b377-103">在此用例，ESB 上执行转换，通过路线 Web 服务上的负载增加提交一条消息。</span><span class="sxs-lookup"><span data-stu-id="8b377-103">In this use case, the ESB performs a transformation on a message submitted through the Itinerary Web service on-ramp.</span></span> <span data-ttu-id="8b377-104">动态解析查找确定映射名称，并将转换入站的消息。</span><span class="sxs-lookup"><span data-stu-id="8b377-104">A dynamic resolution lookup determines the map name and transforms the inbound message.</span></span> <span data-ttu-id="8b377-105">此外，路线指定 n 数动态解析路线服务和它会将已转换的消息路由到的目标终结点。</span><span class="sxs-lookup"><span data-stu-id="8b377-105">Additionally, the itinerary specifies n number of target endpoints that the Itinerary service will dynamically resolve and to which it will route the transformed message.</span></span> <span data-ttu-id="8b377-106">所有操作都发生在消息层上，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="8b377-106">All operations occur at the messaging layer, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="8b377-107">![转换多个终结点](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")</span><span class="sxs-lookup"><span data-stu-id="8b377-107">![Transforming Multiple Endpoints](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span></span>  
  
 <span data-ttu-id="8b377-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="8b377-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="8b377-109">**将转换以及消息路由到多个终结点**</span><span class="sxs-lookup"><span data-stu-id="8b377-109">**Transforming and routing a message to multiple endpoints**</span></span>  
  
 <span data-ttu-id="8b377-110">包含动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="8b377-110">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="8b377-111">它演示如何使用 ESB 管道组件，具体而言 ESB 调度反汇编程序组件，可动态解析终结点的位置、 设置路由的属性，并解析和执行 BizTalk Server 映射在消息级别，而无需使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b377-111">It shows how to use ESB pipeline components, specifically the ESB Dispatch Disassembler component, to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="8b377-112">它还演示了单向和双向消息模式。</span><span class="sxs-lookup"><span data-stu-id="8b377-112">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="8b377-113">有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)和[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="8b377-113">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) and [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>