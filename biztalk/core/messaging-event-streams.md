---
title: 消息传送事件流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae51bce79ca06edc8874100648b1b3002f917f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324971"
---
# <a name="messaging-event-streams"></a><span data-ttu-id="29674-102">消息传送事件流</span><span class="sxs-lookup"><span data-stu-id="29674-102">Messaging Event Streams</span></span>
<span data-ttu-id="29674-103">在其安装 BizTalk Server，并且您的计算机上运行应用程序正在跟踪属于 BizTalk 管道事务的项时使用消息传送事件流 (MES)。</span><span class="sxs-lookup"><span data-stu-id="29674-103">You use Messaging Event Streams (MES) when your application runs on a computer on which BizTalk Server is installed and you are you are tracking items that are part of BizTalk pipeline transactions.</span></span> <span data-ttu-id="29674-104">使用 MES 可确保在 BAM 事件持久化保持与 BizTalk 管道事务同步。</span><span class="sxs-lookup"><span data-stu-id="29674-104">Using MES ensures that your BAM event persistence remains in sync with the BizTalk pipeline transactions.</span></span>  
  
 <span data-ttu-id="29674-105">消息传送事件流是由返回的 EventStream 对象的实例[Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="29674-105">Messaging Event Streams are instances of EventStream objects returned by the [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) method.</span></span>  
  
 <span data-ttu-id="29674-106">消息传送事件流是异步的首先在 BizTalk MessageBox 数据库中存储的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="29674-106">Messaging Event Streams are asynchronous and store tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="29674-107">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="29674-107">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="29674-108">在中找到 IPipelineContext [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)命名空间。</span><span class="sxs-lookup"><span data-stu-id="29674-108">IPipelineContext is found in the [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) namespace.</span></span> <span data-ttu-id="29674-109">若要使用 API 必须将 Microsoft.BizTalk.Pipeline （在 microsoft.biztalk.pipeline.dll 中） 添加添加到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="29674-109">To use the API you must add the Microsoft.BizTalk.Pipeline (in microsoft.biztalk.pipeline.dll) to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29674-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="29674-110">See Also</span></span>  
 <span data-ttu-id="29674-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span><span class="sxs-lookup"><span data-stu-id="29674-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span></span>  
 <span data-ttu-id="29674-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span><span class="sxs-lookup"><span data-stu-id="29674-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span></span>  
 [<span data-ttu-id="29674-113">Microsoft.BizTalk.Component.Interop</span><span class="sxs-lookup"><span data-stu-id="29674-113">Microsoft.BizTalk.Component.Interop</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)