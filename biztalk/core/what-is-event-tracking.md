---
title: 什么是事件跟踪？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HAT tracking], events
- DTA_Services audit table [HAT]
- HAT, events
- events, tracking
- tracking, events
- Tracking database, DTA_Services audit table
- events, HAT
ms.assetid: dd211752-d1af-4287-967a-908b8d067ebb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e516121a27a1dda41019f99a0e5c2ba0c60c628b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379686"
---
# <a name="what-is-event-tracking"></a><span data-ttu-id="aedb8-103">什么是事件跟踪？</span><span class="sxs-lookup"><span data-stu-id="aedb8-103">What is Event Tracking?</span></span>
<span data-ttu-id="aedb8-104">跟踪的消息事件数据基于事件 （例如，当服务开始或结束，或发送或接收消息时）。</span><span class="sxs-lookup"><span data-stu-id="aedb8-104">Tracked message event data is based upon events (for example, when a service begins or ends, or when a message is sent or received).</span></span> <span data-ttu-id="aedb8-105">消息事件跟踪进程返回的事件的发生，这样您可以查看发生的所有基于设置的跟踪筛选器列表。</span><span class="sxs-lookup"><span data-stu-id="aedb8-105">The message event tracking process returns a list of the events that have occurred, enabling you to see everything that happened based on the tracking filters you have set.</span></span>  
  
 <span data-ttu-id="aedb8-106">你可以跟踪开始和结束的业务流程和端口，发送和接收消息时，以及在业务流程中每个形状的执行。</span><span class="sxs-lookup"><span data-stu-id="aedb8-106">You can track the start and end of orchestrations and ports, when messages are sent and received, as well as the execution of each shape in an orchestration.</span></span>  
  
 <span data-ttu-id="aedb8-107">BizTalk 跟踪 (BizTalkDTADb) 数据库包含 DTA_Services 审核表。</span><span class="sxs-lookup"><span data-stu-id="aedb8-107">The BizTalk Tracking (BizTalkDTADb) database contains a DTA_Services audit table.</span></span> <span data-ttu-id="aedb8-108">此表包含所有已部署服务的历史记录 — 管道、 传输和业务流程。</span><span class="sxs-lookup"><span data-stu-id="aedb8-108">This table contains history of all deployed services—pipelines, transports, and orchestrations.</span></span> <span data-ttu-id="aedb8-109">它不会不跟踪的取消部署的服务。</span><span class="sxs-lookup"><span data-stu-id="aedb8-109">It does not keep track of undeployments.</span></span>  
  
 <span data-ttu-id="aedb8-110">你可以跟踪消息的内容以及一条消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="aedb8-110">You can track the contents of a message as well as the promoted properties of a message.</span></span> <span data-ttu-id="aedb8-111">跟踪消息事件将作为这些操作定义**消息正文**跟踪并**消息属性**跟踪。</span><span class="sxs-lookup"><span data-stu-id="aedb8-111">Tracking message events defines these actions as **Message Body** tracking and **Message Property** tracking.</span></span> <span data-ttu-id="aedb8-112">尽管在消息事件跟踪输出中会出现信封，但不能通过它们跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="aedb8-112">Although envelopes appear in the message event tracking output, you cannot track message properties from them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedb8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="aedb8-113">See Also</span></span>  
 [<span data-ttu-id="aedb8-114">使用 BizTalk Server 管理控制台配置跟踪</span><span class="sxs-lookup"><span data-stu-id="aedb8-114">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)
