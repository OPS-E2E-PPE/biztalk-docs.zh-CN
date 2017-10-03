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
ms.openlocfilehash: 81e9790c36d1af9d48942c5de7ccc8eab6d87a5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="58efd-102">创建路线订阅服务器</span><span class="sxs-lookup"><span data-stu-id="58efd-102">Creating Itinerary Subscribers</span></span>
[!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="58efd-103">自动将发布到消息框数据库中; 通过接收管道到达的消息这使得消息供提取相关的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="58efd-103"> automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="58efd-104">此种去耦的方法是首选的方法，以开发 BizTalk 解决方案，因为它提供了最大的灵活性、 缩放，并使用发布-订阅机制。</span><span class="sxs-lookup"><span data-stu-id="58efd-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="58efd-105">有两种方法来创建路线服务订阅服务器：</span><span class="sxs-lookup"><span data-stu-id="58efd-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="58efd-106">为路线服务的订阅服务器使用发送端口</span><span class="sxs-lookup"><span data-stu-id="58efd-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="58efd-107">为路线服务的订阅服务器使用一个业务流程</span><span class="sxs-lookup"><span data-stu-id="58efd-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)