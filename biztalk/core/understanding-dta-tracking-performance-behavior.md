---
title: 了解 DTA 跟踪性能行为 |Microsoft Docs
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
ms.openlocfilehash: 409138a38b75aebdd4e2df63d23e301dae483738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292677"
---
# <a name="understanding-dta-tracking-performance-behavior"></a>了解 DTA 跟踪性能行为
确定 DTA 跟踪的最大可承受吞吐量 (MST) 的主要因素是：  
  
- 所需的消息吞吐量，即，每时间单位，系统收到的消息。  
  
- 正在为每个消息跟踪数据量。  
  
- 多长时间，数据将被清除前，即，数据保留时段 live BizTalkDTADb 数据库中。  
  
- 该值指示是否将 BizTalkDTADb 数据是存档，以及清除。 存档是可选的但必须定期执行清除。  
  
  还有一件事，所有这些因素具有共同点： DTA 可以接受和处理的速度 （存档和清除） 数据。  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a>BizTalkDTADb 插入和处理速度如何影响您的系统  
 现在，让我们逐步跟踪程序中所述的数据通道[测量的最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)，并评估系统的各个组件的 BizTalkDTADb 插入和处理速度的影响。  
  
 从 trackingdata 和后台处理表开始，我们可以想象，如果将数据从这些表移至 BizTalkDTADb 数据库的进程不能将数据插入 BizTalkDTADb 数据库至少尽可能快地运行时将插入到trackingdata 和后台处理表，然后在后台处理和 trackingdata 表将开始积压。 这不一定是坏事在短期内，只要您知道将降低消息吞吐量以便积压工作以最终耗尽。 但是，只要数据仍处于 spool 或 trackingdata 表，它将不能用于查询中的任何其他工具或组中心页上跟踪查询 BizTalkDTADb 数据库中。  因此它不会解决问题的方法很有用。 因此任何预期的积压期间必须足够短，被跟踪的信息是及时中仍然可用但应出现问题时需要使用 BizTalkDTADb 数据进行调查。  
  
 从测试中，我们知道，这并不将跟踪数据移到 BizTalkDTADb 数据库 （即，TDDS 和 TrackedMessages_Copy_BizTalkMsgBoxDb） 的决定因素如果积压累积了，但在 BizTalkDTADb 数据库的速度的进程接受输入。 通常情况下，它是受到 I/O 限制的 BizTalkDTADb 数据库数据文件。 也就是说，它是驱动器的 BizTalkDTADb 数据库数据文件所驻留的速度将确定 DTA 的整体速度。  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a>BizTalkDTADb 中的数据量如何影响 I/O 速度  
 与 I/O 速度相关的另一个关键因素是 BizTalkDTADb 数据库中的数据量： 为跟踪中的数据量 BizTalkDTADb 数据库增加而增加，BizTalkDTADb 数据库的输入和处理速度将下降，因为只需更多的数据若要插入新数据，以及这会影响每个插入所需的 I/O 量，对通过进行排序。  
  
 这是在其中存档和清除输入图片由于它是这些进程使得 BizTalkDTADb 数据库增长得太大，无法跟上。 基本理念是确保 BizTalkDTADb 数据库大小保留内容开始备份中的后台处理和 trackingdata 表级别之下。 但是，在 DTA 清除和存档 (BizTalkDTADb) SQL 作业中实现的清除和存档进程也需要资源 （CPU、 内存和尤其是 I/O） 从度量 MST 时必须考虑到 BizTalkDTADb 数据库服务器跟踪。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [测量 DTA 跟踪的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [DTA 跟踪的 Mst 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)