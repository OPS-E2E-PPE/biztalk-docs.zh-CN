---
title: "使用基于路线的路由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc0a0eb3a212efccd4ddbe4e275042ecb850095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-itinerary-based-routing"></a><span data-ttu-id="e5699-102">使用基于路线的路由</span><span class="sxs-lookup"><span data-stu-id="e5699-102">Using Itinerary-Based Routing</span></span>
<span data-ttu-id="e5699-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供基于路线的邮件路由通过实现要启用方案时的处理序列步骤的某个特定消息的路由滑动模式不知道在设计时和每个消息都可能不同。</span><span class="sxs-lookup"><span data-stu-id="e5699-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides itinerary-based message routing by implementing the Routing Slip pattern to enable scenarios when the sequence of processing steps for a particular message is not known at design time and may vary for each message.</span></span> <span data-ttu-id="e5699-104">此模式的实现使用路由滑动来表示这些步骤以 XML 格式的集合，并确定需要在运行时期间可能出现哪些步骤。</span><span class="sxs-lookup"><span data-stu-id="e5699-104">The implementation of this pattern uses a routing slip to represent a collection of these steps in XML format and determines which steps need to occur during at run time.</span></span> <span data-ttu-id="e5699-105">路由滑动，通常称为"ESB 日程表"，状态是一组有序的定义必须执行的消息，因为它正在处理的步骤的声明性说明[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件和 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5699-105">A state of the routing slip, frequently referred to as an "ESB itinerary," is an ordered set of declarative instructions that define the steps that must be executed for a message as it is being processed by [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components and the BizTalk Server runtime.</span></span> <span data-ttu-id="e5699-106">在 ESB 路线中指定特定的处理指令与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件，也称为"ESB 路线本服务。"</span><span class="sxs-lookup"><span data-stu-id="e5699-106">A particular processing instruction specified in ESB itinerary is associated with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] component, which is also referred to as the "ESB itinerary service."</span></span> <span data-ttu-id="e5699-107">ESB 路线服务的目的是滑动的要执行的处理说明进行操作并更新路由，以指示挂起指令下的一步的状态。</span><span class="sxs-lookup"><span data-stu-id="e5699-107">The purpose of the ESB itinerary service is to execute the processing instructions and to update the state of the routing slip to indicate the next pending instruction.</span></span>  
  
 <span data-ttu-id="e5699-108">本部分介绍的基于路线的处理功能[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5699-108">This section describes the itinerary-based processing features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="e5699-109">本节包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="e5699-109">It contains the following topics:</span></span>  
  
-   [<span data-ttu-id="e5699-110">ESB 路线管理</span><span class="sxs-lookup"><span data-stu-id="e5699-110">ESB Itinerary Management</span></span>](../esb-toolkit/esb-itinerary-management.md)  
  
-   [<span data-ttu-id="e5699-111">上渐变和关闭渐变</span><span class="sxs-lookup"><span data-stu-id="e5699-111">On-Ramps and Off-Ramps</span></span>](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [<span data-ttu-id="e5699-112">选择消息传送和业务流程路线服务</span><span class="sxs-lookup"><span data-stu-id="e5699-112">Choosing Between Messaging and Orchestration Itinerary Services</span></span>](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [<span data-ttu-id="e5699-113">使用管道组件来选择现有路线</span><span class="sxs-lookup"><span data-stu-id="e5699-113">Using a Pipeline Component to Select an Existing Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [<span data-ttu-id="e5699-114">使用管道组件读取一条路线</span><span class="sxs-lookup"><span data-stu-id="e5699-114">Using a Pipeline Component to Read an Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [<span data-ttu-id="e5699-115">使用管道组件来缓存请求作出响应一条路线</span><span class="sxs-lookup"><span data-stu-id="e5699-115">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [<span data-ttu-id="e5699-116">创建路线订阅服务器</span><span class="sxs-lookup"><span data-stu-id="e5699-116">Creating Itinerary Subscribers</span></span>](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [<span data-ttu-id="e5699-117">执行路线服务</span><span class="sxs-lookup"><span data-stu-id="e5699-117">Executing an Itinerary Service</span></span>](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   <span data-ttu-id="e5699-118">超链接"http://msdn.microsoft.com/en-us/library/ee236752 (BTS.10).aspx"[路线基于路由的项目](../esb-toolkit/itinerary-based-routing-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="e5699-118">HYPERLINK "http://msdn.microsoft.com/en-us/library/ee236752(BTS.10).aspx" [Itinerary-Based Routing Artifacts](../esb-toolkit/itinerary-based-routing-artifacts.md)</span></span>