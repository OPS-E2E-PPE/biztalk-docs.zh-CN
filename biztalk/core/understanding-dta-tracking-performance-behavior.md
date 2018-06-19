---
title: 了解 DTA 跟踪性能行为 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 278d1e3c4b52c14c68d692ce3d3a3179d15bb10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287021"
---
# <a name="understanding-dta-tracking-performance-behavior"></a>了解 DTA 跟踪性能行为
有关跟踪的 DTA 确定最大可持续吞吐量 (MST) 的主要因素是：  
  
-   所需的消息吞吐量，即每时间单位，系统收到的消息。  
  
-   正在为每个消息跟踪数据量。  
  
-   数据在被清除前在 BizTalkDTADb 数据库中存活多长时间，即数据保留时段。  
  
-   是否存档和清除 BizTalkDTADb 数据。 存档是可选的，但清除必须定期执行。  
  
 有一点，所有这些因素具有共同点： DTA 可以接受并处理的速度 （存档和清除） 的数据。  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a>BizTalkDTADb 插入和处理速度如何影响您的系统  
 现在，让我们逐步完成跟踪程序中所述的数据通道[测量最大的可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)，并对系统的各个组件的 BizTalkDTADb insert 和处理速度的影响进行评估。  
  
 从 trackingdata 表和 spool 表开始，我们可以假设，如果在将数据从这些表移到 BizTalkDTADb 数据库的进程中，将数据插入 BizTalkDTADb 数据库的速度无法与运行时将数据插入 trackingdata 表和 spool 表的速度至少相当，则 trackingdata 表和 spool 表将开始积压。 只要您知道将降低消息吞吐量以便最终消除积压，短期内上述情况不见得就是坏事。 但是，只要数据仍处于 spool 或 trackingdata 表中，就无法在 BizTalkDTADb 数据库中使用“组中心”页中的跟踪查询或任何其他工具对这些数据进行查询。  因此，它对解决问题没有作用。 因此，任何预期的积压期间都必须足够短，以便只要发生需要使用 BizTalkDTADb 数据进行调查的问题，仍可以及时地利用跟踪的信息予以解决。  
  
 从测试，我们知道它并不将跟踪数据移动到如果积压建立，是决定因素 BizTalkDTADb 数据库 （即，TDDS 和 TrackedMessages_Copy_BizTalkMsgBoxDb） 但 BizTalkDTADb 数据库中的速度的进程接受输入。 通常，这是受到 I/O 限制的 BizTalkDTADb 数据库的数据文件。 即，决定因素是 BizTalkDTADb 数据库数据文件所驻留的驱动器的速度，该速度将确定 DTA 的整体速度。  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a>BizTalkDTADb 中的数据量如何影响 I/O 速度  
 与 I/O 速度相关的另一个关键因素是 BizTalkDTADb 数据库中的数据量： 为跟踪中的数据量 BizTalkDTADb 数据库增加，BizTalkDTADb 数据库的输入和处理速度降低由于没有只需更多的数据若要插入新数据，以及这会影响的每个插入所需的 I/O 数量，对通过进行排序。  
  
 这就是为什么要考虑存档和清除操作，因为就是这些进程使得 BizTalkDTADb 数据库增长得过大，以致难以维护。 因此，基本思路就是：确保 BizTalkDTADb 数据库大小保持在较低的级别，其级别要低于不得不开始在 spool 表和 trackingdata 表中进行备份的级别。 但是，在 DTA 清除和存档 (BizTalkDTADb) SQL 作业中实现的清除和存档进程也要求来自 BizTalkDTADb 数据库服务器的资源（CPU、内存，尤其是 I/O），在度量与跟踪有关的 MST 时必须将此考虑在内。  
  
## <a name="see-also"></a>另请参阅  
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [用于测量 MST DTA 跟踪测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [查找的跟踪的 DTA MST 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)