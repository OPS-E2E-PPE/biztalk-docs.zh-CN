---
title: "有关使用 BAM Api 注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b00eb00013fefde42e1972b89a661d0a2ba0de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-for-working-with-bam-apis"></a>使用 BAM Api 的注意事项
在使用“Microsoft.BizTalk.Bam.EventObservation.EventStream”对象（如 DirectEventStream、BufferedEventStream、MessagingEventStream 或 OrchestrationEventStream）时，BAM 将会捕获里程碑，使这些里程碑自动以世界时 (UTC) 格式（也称为格林威治标准时间）进行记录。 当使用这些 API 向 BAM 发送日期/时间时，这些日期和时间将以发送格式接收，而不会转换为 UTC 格式。 在开发 BAM 解决方案时，应考虑以下情况：  
  
-   来自 BizTalk Server 的跟踪数据会以 UTC 格式接收。 这就造成与来自事件流的其他数据不一致。  
  
-   如果使用事件流 API 以本地时间格式提供日期和时间跟踪数据，则 BAM 门户中的数据将不正确，因为 BAM 数据中的所有时间必需是 UTC 格式。  
  
 如果现有的应用程序使用的是本地时间，并且现在想要升级并计划使用 BAM 门户，则必须修改数据，使其符合 UTC 格式。 还需要修改自定义应用程序，使其转换为 UTC 格式。  
  
## <a name="see-also"></a>另请参阅  
 [实现 BAM 解决方案](../core/implementing-bam-solutions.md)