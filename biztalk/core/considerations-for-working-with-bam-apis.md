---
title: 有关使用 BAM Api 注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b00eb00013fefde42e1972b89a661d0a2ba0de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237837"
---
# <a name="considerations-for-working-with-bam-apis"></a><span data-ttu-id="5ea97-102">使用 BAM Api 的注意事项</span><span class="sxs-lookup"><span data-stu-id="5ea97-102">Considerations for Working with BAM APIs</span></span>
<span data-ttu-id="5ea97-103">在使用“Microsoft.BizTalk.Bam.EventObservation.EventStream”对象（如 DirectEventStream、BufferedEventStream、MessagingEventStream 或 OrchestrationEventStream）时，BAM 将会捕获里程碑，使这些里程碑自动以世界时 (UTC) 格式（也称为格林威治标准时间）进行记录。</span><span class="sxs-lookup"><span data-stu-id="5ea97-103">When using an  "Microsoft.BizTalk.Bam.EventObservation.EventStream" object, such as DirectEventStream, BufferedEventStream, MessagingEventStream, or OrchestrationEventStream, BAM captures milestones such that they are automatically recorded in Coordinated Universal Time (UTC) format (this is also referred to as Greenwich Mean Time).</span></span> <span data-ttu-id="5ea97-104">当使用这些 API 向 BAM 发送日期/时间时，这些日期和时间将以发送格式接收，而不会转换为 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="5ea97-104">When you send date/times to BAM using the APIs they are received in the format sent with no conversion to UTC format.</span></span> <span data-ttu-id="5ea97-105">在开发 BAM 解决方案时，应考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="5ea97-105">You should take the following considerations into account when you are developing your BAM solutions:</span></span>  
  
-   <span data-ttu-id="5ea97-106">来自 BizTalk Server 的跟踪数据会以 UTC 格式接收。</span><span class="sxs-lookup"><span data-stu-id="5ea97-106">Data traced from BizTalk Server is received in UTC format.</span></span> <span data-ttu-id="5ea97-107">这就造成与来自事件流的其他数据不一致。</span><span class="sxs-lookup"><span data-stu-id="5ea97-107">This could be inconsistent with other data that comes from the event stream.</span></span>  
  
-   <span data-ttu-id="5ea97-108">如果使用事件流 API 以本地时间格式提供日期和时间跟踪数据，则 BAM 门户中的数据将不正确，因为 BAM 数据中的所有时间必需是 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="5ea97-108">If you use the event stream APIs to provide date and time tracking data in local time format, the data in the BAM portal will be incorrect as the expectation is that all times in BAM data are in UTC format.</span></span>  
  
 <span data-ttu-id="5ea97-109">如果现有的应用程序使用的是本地时间，并且现在想要升级并计划使用 BAM 门户，则必须修改数据，使其符合 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="5ea97-109">If you have existing applications that use local time, and you are now upgrading and planning to use the BAM portal, you must modify your data to make it conform to UTC format.</span></span> <span data-ttu-id="5ea97-110">还需要修改自定义应用程序，使其转换为 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="5ea97-110">You also need to modify your custom application to convert to UTC format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea97-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea97-111">See Also</span></span>  
 [<span data-ttu-id="5ea97-112">实现 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="5ea97-112">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)