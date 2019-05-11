---
title: 创建路线订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2998b47ec136414af896cadb40b8336fe41ef2ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394667"
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="dad17-102">创建路线订阅方</span><span class="sxs-lookup"><span data-stu-id="dad17-102">Creating Itinerary Subscribers</span></span>
<span data-ttu-id="dad17-103">BizTalk Server 会自动将发布到 Messagebox 数据库中; 通过接收管道到达的消息这会使消息准备好进行提取相关的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="dad17-103">BizTalk Server automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="dad17-104">此种去耦的方法是首选的方法来开发 BizTalk 解决方案，因为它提供了最大的灵活性、 扩展性好，并使用发布-订阅机制。</span><span class="sxs-lookup"><span data-stu-id="dad17-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="dad17-105">有两种方法来创建路线服务订阅方：</span><span class="sxs-lookup"><span data-stu-id="dad17-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="dad17-106">将发送端口用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="dad17-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="dad17-107">将业务流程用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="dad17-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)