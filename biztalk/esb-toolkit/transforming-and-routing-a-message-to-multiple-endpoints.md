---
title: 转换和一条消息路由到多个终结点 |Microsoft Docs
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
ms.openlocfilehash: 1c05d76c9f964ccfd326ed5091152545ee647a64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399615"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a><span data-ttu-id="18378-102">转换和一条消息路由到多个终结点</span><span class="sxs-lookup"><span data-stu-id="18378-102">Transforming and Routing a Message to Multiple Endpoints</span></span>
<span data-ttu-id="18378-103">在此用例，ESB 路线 Web 服务的途径，通过提交对消息执行的转换。</span><span class="sxs-lookup"><span data-stu-id="18378-103">In this use case, the ESB performs a transformation on a message submitted through the Itinerary Web service on-ramp.</span></span> <span data-ttu-id="18378-104">动态解析查找确定映射名称，并将入站的消息转换。</span><span class="sxs-lookup"><span data-stu-id="18378-104">A dynamic resolution lookup determines the map name and transforms the inbound message.</span></span> <span data-ttu-id="18378-105">此外，路线指定 n 个目标终结点的路线服务将动态解析并会将已转换的消息路由。</span><span class="sxs-lookup"><span data-stu-id="18378-105">Additionally, the itinerary specifies n number of target endpoints that the Itinerary service will dynamically resolve and to which it will route the transformed message.</span></span> <span data-ttu-id="18378-106">所有操作都发生在消息传送层上，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="18378-106">All operations occur at the messaging layer, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="18378-107">![转换多个终结点](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span><span class="sxs-lookup"><span data-stu-id="18378-107">![Transforming Multiple Endpoints](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")</span></span>  
  
 <span data-ttu-id="18378-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="18378-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="18378-109">**转换和消息路由到多个终结点**</span><span class="sxs-lookup"><span data-stu-id="18378-109">**Transforming and routing a message to multiple endpoints**</span></span>  
  
 <span data-ttu-id="18378-110">动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="18378-110">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="18378-111">它演示如何使用 ESB 管道组件，具体而言，ESB 调度拆装器组件、 动态解析终结点位置、 设置路由属性，并解析和执行 BizTalk Server 映射在消息级别，而无需使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="18378-111">It shows how to use ESB pipeline components, specifically the ESB Dispatch Disassembler component, to dynamically resolve endpoint location, set routing properties, and resolve and execute BizTalk Server maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="18378-112">它还演示了单向和双向消息传送模式。</span><span class="sxs-lookup"><span data-stu-id="18378-112">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="18378-113">有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)并[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="18378-113">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) and [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>