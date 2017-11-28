---
title: "什么是事件跟踪？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa53881cf42ae2769621e10ce21e1160f9b7be0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-event-tracking"></a><span data-ttu-id="35fcb-103">什么是事件跟踪？</span><span class="sxs-lookup"><span data-stu-id="35fcb-103">What is Event Tracking?</span></span>
<span data-ttu-id="35fcb-104">跟踪消息事件数据是基于事件（例如，服务开始或结束时，或发送或接收消息时）进行的。</span><span class="sxs-lookup"><span data-stu-id="35fcb-104">Tracked message event data is based upon events (for example, when a service begins or ends, or when a message is sent or received).</span></span> <span data-ttu-id="35fcb-105">消息事件跟踪过程会返回一个已发生事件的列表，这样您就可以查看基于所设置的跟踪筛选器发生的所有事件。</span><span class="sxs-lookup"><span data-stu-id="35fcb-105">The message event tracking process returns a list of the events that have occurred, enabling you to see everything that happened based on the tracking filters you have set.</span></span>  
  
 <span data-ttu-id="35fcb-106">可以跟踪业务流程和端口的开始和结束、发送和接收消息的时间以及业务流程中每个形状的执行情况。</span><span class="sxs-lookup"><span data-stu-id="35fcb-106">You can track the start and end of orchestrations and ports, when messages are sent and received, as well as the execution of each shape in an orchestration.</span></span>  
  
 <span data-ttu-id="35fcb-107">BizTalk 跟踪 (BizTalkDTADb) 数据库包含 DTA_Services 审核表。</span><span class="sxs-lookup"><span data-stu-id="35fcb-107">The BizTalk Tracking (BizTalkDTADb) database contains a DTA_Services audit table.</span></span> <span data-ttu-id="35fcb-108">此表包含所有已部署服务（管道、传输和业务流程）的历史记录。</span><span class="sxs-lookup"><span data-stu-id="35fcb-108">This table contains history of all deployed services—pipelines, transports, and orchestrations.</span></span> <span data-ttu-id="35fcb-109">HAT 不跟踪取消部署的服务。</span><span class="sxs-lookup"><span data-stu-id="35fcb-109">It does not keep track of undeployments.</span></span>  
  
 <span data-ttu-id="35fcb-110">可以跟踪消息的内容以及消息的升级属性。</span><span class="sxs-lookup"><span data-stu-id="35fcb-110">You can track the contents of a message as well as the promoted properties of a message.</span></span> <span data-ttu-id="35fcb-111">跟踪消息事件定义这些操作，如**消息正文**跟踪和**消息属性**跟踪。</span><span class="sxs-lookup"><span data-stu-id="35fcb-111">Tracking message events defines these actions as **Message Body** tracking and **Message Property** tracking.</span></span> <span data-ttu-id="35fcb-112">尽管在消息事件跟踪输出中会显示信封，但无法通过这些信封跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="35fcb-112">Although envelopes appear in the message event tracking output, you cannot track message properties from them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35fcb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35fcb-113">See Also</span></span>  
 [<span data-ttu-id="35fcb-114">配置使用 BizTalk Server 管理控制台的跟踪</span><span class="sxs-lookup"><span data-stu-id="35fcb-114">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)