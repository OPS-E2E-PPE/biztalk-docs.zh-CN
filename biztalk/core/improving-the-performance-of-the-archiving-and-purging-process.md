---
title: 提高性能的存档和清除进程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d7cb6adf314bd5575d354c52c2682138bad784
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382200"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a>提高存档和清除进程的性能
存储中的数据量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库可根据设计方式非常快速地增长你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]方案中，根据的数量和处理的消息的大小在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]方案中，并取决于如何具有配置跟踪。 通过维护你的数据库大小正常级别，处理效率更高，并且在任何给定时间规范化你的系统中的数据量。 这提供了高效的一致性能。 通过自动执行此过程，解放自我您手动维护数据库的负担。  
  
## <a name="configuring-a-healthy-environment"></a>配置正常运行的环境  
 策略维护正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境是很大程度上取决于特定方案和硬件运行。 若要监视的重要事项是 BizTalk 跟踪 (BizTalkDTADb) 数据库的大小和增长的速率。 跟踪数据库的一些表占据大量数据库大小，因此将运行时对性能的影响。  
  
 相同的方案可以配置为生成都得到了显著不同数量的跟踪数据基于跟踪点的数量都存在，如何使用许多不同的消息，使用的消息大小和消息正文跟踪的级别。 以下是一些重要因素：  
  
- 跟踪点-例如管道、 业务流程和端口号  
  
- 跟踪消息属性的数目  
  
- 每个传入消息的消息数  
  
- 消息大小  
  
- 通信速率 （平均值和峰值）  
  
- 消息正文跟踪配置  
  
  自动存档和清除数据，请考虑需要保留在跟踪数据库中的实时数据量。 您需要调整 DTA 清除和存档作业参数，以根据你的环境，以便清除而不会降低性能可以支持目标实时数据量。  
  
  DTA 清除和存档作业可以在给定的时间间隔内清除一定数量的数据。 作业的容量取决于运行的方案、 当前数据库大小和硬件。 为了获得稳定的环境，必须具有传入的跟踪数据的生成和清除之间的平衡。 在测试环境中，可以通过不同的数据生存时段和清除作业的频率来找到平衡。 在平衡状态下，系统将提供可承受吞吐量。 你的目标是缓冲区的具有足够，然后 BizTalk 跟踪数据库表大小导致持续显著的性能问题。  
  
## <a name="performance-limitations"></a>性能限制  
 所有情况下将不能清除时的性能。 对于任何方案，就可以生成数量不断增长的跟踪数据。 当以持续较低速率清除跟踪数据时，会跟踪的数据库大小，清除性能进一步恶化。  
  
 在负载不可承受情况下复制消息正文可能也会降低，并且那里可能会积压在 MessageBox 数据库中。 在极端条件下每日消息正文复制和跟踪可能会导致存档消息正文并不可用的即使它包含相关的实例信息。 通常情况下，高负载的时间段与低负载的高峰期的备用和启用作业，以便在低负载时段保持同步。  
  
 存档和清除 BizTalk 跟踪数据库能够大大降低负载不可承受情况可能会由于数据库的连续修剪和存储的跟踪数据压缩。 这些进程极大地减少需手动干预。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)