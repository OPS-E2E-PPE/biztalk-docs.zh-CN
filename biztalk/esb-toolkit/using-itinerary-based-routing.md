---
title: 使用基于路线的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adcb32367a42403e769111f7b3d3d343c604671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978686"
---
# <a name="using-itinerary-based-routing"></a><span data-ttu-id="df789-102">使用基于路线的路由</span><span class="sxs-lookup"><span data-stu-id="df789-102">Using Itinerary-Based Routing</span></span>
<span data-ttu-id="df789-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供基于路线的消息路由通过实现以启用方案时的一系列处理步骤的特定消息的传送名单模式不知道在设计时和每个消息都可能不同。</span><span class="sxs-lookup"><span data-stu-id="df789-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides itinerary-based message routing by implementing the Routing Slip pattern to enable scenarios when the sequence of processing steps for a particular message is not known at design time and may vary for each message.</span></span> <span data-ttu-id="df789-104">此模式的实现使用传送名单来表示这些步骤以 XML 格式的集合，并确定需要在运行时期间执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="df789-104">The implementation of this pattern uses a routing slip to represent a collection of these steps in XML format and determines which steps need to occur during at run time.</span></span> <span data-ttu-id="df789-105">传送名单，通常称为"ESB 路线"，状态是一个有序的声明性定义在通过处理，则在一条消息时必须执行的步骤的说明[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件和 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="df789-105">A state of the routing slip, frequently referred to as an "ESB itinerary," is an ordered set of declarative instructions that define the steps that must be executed for a message as it is being processed by [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components and the BizTalk Server runtime.</span></span> <span data-ttu-id="df789-106">ESB 路线中指定的特定处理指令与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件，也称为"ESB 路线服务。"</span><span class="sxs-lookup"><span data-stu-id="df789-106">A particular processing instruction specified in ESB itinerary is associated with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] component, which is also referred to as the "ESB itinerary service."</span></span> <span data-ttu-id="df789-107">ESB 路线服务的目的是要执行的处理指令并更新以指示下一个挂起的指令的传送名单的状态。</span><span class="sxs-lookup"><span data-stu-id="df789-107">The purpose of the ESB itinerary service is to execute the processing instructions and to update the state of the routing slip to indicate the next pending instruction.</span></span>  

 <span data-ttu-id="df789-108">本部分介绍的基于路线的处理功能[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="df789-108">This section describes the itinerary-based processing features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="df789-109">本节包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="df789-109">It contains the following topics:</span></span>  

- [<span data-ttu-id="df789-110">ESB 路线管理</span><span class="sxs-lookup"><span data-stu-id="df789-110">ESB Itinerary Management</span></span>](../esb-toolkit/esb-itinerary-management.md)  

- [<span data-ttu-id="df789-111">接入点和接出点</span><span class="sxs-lookup"><span data-stu-id="df789-111">On-Ramps and Off-Ramps</span></span>](../esb-toolkit/on-ramps-and-off-ramps.md)  

- [<span data-ttu-id="df789-112">在消息传递和业务流程路线服务之间进行选择</span><span class="sxs-lookup"><span data-stu-id="df789-112">Choosing Between Messaging and Orchestration Itinerary Services</span></span>](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  

- [<span data-ttu-id="df789-113">使用管道组件选择现有路线</span><span class="sxs-lookup"><span data-stu-id="df789-113">Using a Pipeline Component to Select an Existing Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  

- [<span data-ttu-id="df789-114">使用管道组件读取路线</span><span class="sxs-lookup"><span data-stu-id="df789-114">Using a Pipeline Component to Read an Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  

- [<span data-ttu-id="df789-115">使用管道组件缓存“要求-响应”路线</span><span class="sxs-lookup"><span data-stu-id="df789-115">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  

- [<span data-ttu-id="df789-116">创建路线订阅方</span><span class="sxs-lookup"><span data-stu-id="df789-116">Creating Itinerary Subscribers</span></span>](../esb-toolkit/creating-itinerary-subscribers.md)  

- [<span data-ttu-id="df789-117">执行路线服务</span><span class="sxs-lookup"><span data-stu-id="df789-117">Executing an Itinerary Service</span></span>](../esb-toolkit/executing-an-itinerary-service.md)  

- <span data-ttu-id="df789-118">超链接"<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>"[基于路线的路由项目](../esb-toolkit/itinerary-based-routing-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="df789-118">HYPERLINK "<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>" [Itinerary-Based Routing Artifacts](../esb-toolkit/itinerary-based-routing-artifacts.md)</span></span>
