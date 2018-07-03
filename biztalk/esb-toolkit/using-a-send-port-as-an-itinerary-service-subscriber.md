---
title: 发送端口用作路线服务订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8cf33ab303127ba369a619637abf455c80ee539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018724"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a><span data-ttu-id="7227e-102">发送端口用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="7227e-102">Using a Send Port as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="7227e-103">为举例说明如何将发送端口用作路线服务订阅方，图 1 显示了满足以下条件的消息会选取一个动态单向发送端口的筛选器条件：</span><span class="sxs-lookup"><span data-stu-id="7227e-103">As an example of how to use a send port as an itinerary service subscriber, Figure 1 shows the filter conditions for a dynamic one-way sent port that picks up messages that meet the following conditions:</span></span>  
  
- <span data-ttu-id="7227e-104">**IsRequestResponse = False**</span><span class="sxs-lookup"><span data-stu-id="7227e-104">**IsRequestResponse = False**</span></span>  
  
- <span data-ttu-id="7227e-105">**ServiceName = DynamicTest**</span><span class="sxs-lookup"><span data-stu-id="7227e-105">**ServiceName = DynamicTest**</span></span>  
  
- <span data-ttu-id="7227e-106">**ServiceState = 挂起**</span><span class="sxs-lookup"><span data-stu-id="7227e-106">**ServiceState = Pending**</span></span>  
  
- <span data-ttu-id="7227e-107">**ServiceType = 消息传送**</span><span class="sxs-lookup"><span data-stu-id="7227e-107">**ServiceType = Messaging**</span></span>  
  
  <span data-ttu-id="7227e-108">![发送端口](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span><span class="sxs-lookup"><span data-stu-id="7227e-108">![Send Port](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span></span>  
  
  <span data-ttu-id="7227e-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="7227e-109">**Figure 1**</span></span>  
  
  <span data-ttu-id="7227e-110">**发送端口筛选器的示例**</span><span class="sxs-lookup"><span data-stu-id="7227e-110">**Example of send port filters**</span></span>  
  
  <span data-ttu-id="7227e-111">使用发送端口筛选器表达式来指定它将从 Messagebox 数据库路线接入点通过选取的消息的属性和值集。</span><span class="sxs-lookup"><span data-stu-id="7227e-111">Use send port filter expressions to specify the property and value sets of messages it will pick up from the Message Box database through the itinerary on-ramp.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7227e-112">务必要使用的是为特定且其焦点位于尽可能; 筛选条件否则，为存在风险的意外消息，可能会在大容量环境中引起问题的提取。</span><span class="sxs-lookup"><span data-stu-id="7227e-112">It is important to use filter conditions that are as specific and focused as possible; otherwise, there is a risk of picking up unintended messages, which could cause problems in a high-volume environment.</span></span> <span data-ttu-id="7227e-113">架构系统 Properties.xsd 定义订阅的筛选器属性。</span><span class="sxs-lookup"><span data-stu-id="7227e-113">The schema System-Properties.xsd defines the filter properties of subscriptions.</span></span>