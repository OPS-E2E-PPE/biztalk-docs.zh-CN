---
title: "规划消息和跟踪的实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-message-and-instance-tracking"></a><span data-ttu-id="f279f-102">规划消息和实例跟踪</span><span class="sxs-lookup"><span data-stu-id="f279f-102">Planning for Message and Instance Tracking</span></span>
<span data-ttu-id="f279f-103">应当在计划阶段确定需要跟踪的信息，以便在部署项目后可以设置跟踪选项并限制跟踪的数据量，从而仅为您提供所需的信息。</span><span class="sxs-lookup"><span data-stu-id="f279f-103">You should decide during the planning stages which information you need to track, so that after you deploy the project you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
 <span data-ttu-id="f279f-104">建议您不要跟踪所有消息，因为每次访问消息时，BizTalk Server 消息与服务器实例跟踪都将生成另一个副本。</span><span class="sxs-lookup"><span data-stu-id="f279f-104">We recommend that you do not track all messages, because each time a message is touched, BizTalk Server message and server instance tracking makes another copy.</span></span> <span data-ttu-id="f279f-105">例如，可以通过仅跟踪特定的端口来缩小范围。</span><span class="sxs-lookup"><span data-stu-id="f279f-105">For example, you can narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="f279f-106">这样有助于最大限度地提高系统性能并保持数据库不乱。</span><span class="sxs-lookup"><span data-stu-id="f279f-106">This helps to maximize the performance of your system and keep the databases uncluttered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f279f-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f279f-107">See Also</span></span>  
 [<span data-ttu-id="f279f-108">管理和跟踪体系结构</span><span class="sxs-lookup"><span data-stu-id="f279f-108">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)