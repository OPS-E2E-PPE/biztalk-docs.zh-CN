---
title: 消息传送事件流 |Microsoft 文档
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
ms.openlocfilehash: 9d955dbc2b50d1d9c40b54736762fcbaa2bfe536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262781"
---
# <a name="messaging-event-streams"></a><span data-ttu-id="1ed1f-102">消息传送事件流</span><span class="sxs-lookup"><span data-stu-id="1ed1f-102">Messaging Event Streams</span></span>
<span data-ttu-id="1ed1f-103">当您的应用程序运行在安装有 BizTalk Server 的计算机上并且您正在跟踪属于 BizTalk 管道事务的项时，使用消息传送事件流 (MES)。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-103">You use Messaging Event Streams (MES) when your application runs on a computer on which BizTalk Server is installed and you are you are tracking items that are part of BizTalk pipeline transactions.</span></span> <span data-ttu-id="1ed1f-104">使用 MES 可确保您的 BAM 事件持久化保持与 BizTalk 管道事务同步。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-104">Using MES ensures that your BAM event persistence remains in sync with the BizTalk pipeline transactions.</span></span>  
  
 <span data-ttu-id="1ed1f-105">消息传递的事件流是 EventStream 返回的对象的实例[Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-105">Messaging Event Streams are instances of EventStream objects returned by the [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) method.</span></span>  
  
 <span data-ttu-id="1ed1f-106">消息传送事件流是异步的，并且将跟踪数据首先存储在 BizTalk MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-106">Messaging Event Streams are asynchronous and store tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="1ed1f-107">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-107">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="1ed1f-108">在中找到 IPipelineContext [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)命名空间。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-108">IPipelineContext is found in the [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) namespace.</span></span> <span data-ttu-id="1ed1f-109">若要使用该 API，您必须将 Microsoft.BizTalk.Pipeline（在 microsoft.biztalk.pipeline.dll 中）添加到您的项目。</span><span class="sxs-lookup"><span data-stu-id="1ed1f-109">To use the API you must add the Microsoft.BizTalk.Pipeline (in microsoft.biztalk.pipeline.dll) to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed1f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ed1f-110">See Also</span></span>  
 <span data-ttu-id="1ed1f-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span><span class="sxs-lookup"><span data-stu-id="1ed1f-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span></span>  
 <span data-ttu-id="1ed1f-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span><span class="sxs-lookup"><span data-stu-id="1ed1f-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span></span>  
 [<span data-ttu-id="1ed1f-113">Microsoft.BizTalk.Component.Interop</span><span class="sxs-lookup"><span data-stu-id="1ed1f-113">Microsoft.BizTalk.Component.Interop</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)