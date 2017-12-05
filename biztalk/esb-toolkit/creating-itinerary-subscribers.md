---
title: "创建路线订阅服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f470ed5268c445ab3b7175f1cba07ff1de52a27
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="88364-102">创建路线订阅服务器</span><span class="sxs-lookup"><span data-stu-id="88364-102">Creating Itinerary Subscribers</span></span>
<span data-ttu-id="88364-103">BizTalk Server 会自动将发布到消息框数据库中; 通过接收管道到达的消息这使得消息供提取相关的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="88364-103">BizTalk Server automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="88364-104">此种去耦的方法是首选的方法，以开发 BizTalk 解决方案，因为它提供了最大的灵活性、 缩放，并使用发布-订阅机制。</span><span class="sxs-lookup"><span data-stu-id="88364-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="88364-105">有两种方法来创建路线服务订阅服务器：</span><span class="sxs-lookup"><span data-stu-id="88364-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="88364-106">将发送端口用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="88364-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="88364-107">将业务流程用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="88364-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)