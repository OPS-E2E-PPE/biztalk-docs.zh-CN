---
title: "路由和处理路线基于 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8354538-e45c-487d-a380-59f497ea060f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5405e1e37834071bb4a1295b5e99bde3bf6ec846
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing-and-processing"></a><span data-ttu-id="ebf74-102">基于路线的路由和处理</span><span class="sxs-lookup"><span data-stu-id="ebf74-102">Itinerary-Based Routing and Processing</span></span>
<span data-ttu-id="ebf74-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]实现通过自定义管道组件使用的路由滑动模式。</span><span class="sxs-lookup"><span data-stu-id="ebf74-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a routing slip pattern through the use of custom pipeline components.</span></span> <span data-ttu-id="ebf74-104">消息元数据和其他因素用于确定适当的路由滑动也称为路线，要用于每个消息。</span><span class="sxs-lookup"><span data-stu-id="ebf74-104">Message metadata and other factors are used to determine the appropriate routing slip, also known as an itinerary, to be used for each message.</span></span> <span data-ttu-id="ebf74-105">此路由滑动即可执行消息转换、 调用业务流程服务，并定义邮件路由步骤[!INCLUDE[prague](../includes/prague-md.md)]将执行，有效地分离核心 BizTalk Server 引擎中的消息处理指令。</span><span class="sxs-lookup"><span data-stu-id="ebf74-105">This routing slip can perform message transformation, invoke orchestration services, and define message routing steps that [!INCLUDE[prague](../includes/prague-md.md)] will execute, effectively decoupling message processing instructions from the core BizTalk Server engine.</span></span>  
  
 <span data-ttu-id="ebf74-106">有关如何处理路线的详细信息，请参阅[主要方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf74-106">For more information on how itineraries are processed, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>