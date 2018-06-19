---
title: 提高性能的存档和清除进程 |Microsoft 文档
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
ms.openlocfilehash: 3876021fec4d604960d672671cab8bf4be1dc0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257837"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a>提高存档和清除进程的性能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中存储的数据量有可能增长得非常迅速，这与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 方案的设计方式、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 方案所处理的消息数量和消息大小以及跟踪的配置方式都有关。 使数据库大小维持在合理的水平，可提高处理效率并使系统中的数据量在任何给定时间都保持正常。 这样能够发挥出高效而稳定的性能。 此过程的自动化，可免去您手动维护数据库的工作。  
  
## <a name="configuring-a-healthy-environment"></a>配置运行状况良好的环境  
 维护运行状况良好的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的策略主要取决于您的特定方案和运行该方案的硬件。 关键是监视 BizTalk 跟踪 (BizTalkDTADb) 数据库的增长速率和大小。 跟踪数据库的一些表占据大量数据库空间，因此在运行时会影响性能。  
  
 配置同一个方案，却可以产生数量大不相同的跟踪数据，这取决于跟踪点的数量、用到的不同消息的数量、这些消息的大小以及所使用的消息正文跟踪的级别。 下面是有关的一些重要因素：  
  
-   跟踪点（如管道、业务流程和端口）的数量  
  
-   跟踪的消息属性数  
  
-   每个传入消息的消息数  
  
-   消息大小  
  
-   通信速率（平均值和峰值）  
  
-   消息正文跟踪配置  
  
 在涉及自动存档和清除数据时，请考虑需要保存在跟踪数据库中的实时数据量。 您需要根据您的环境调整 DTA 清除和存档作业参数，以便在清除性能不会下降的前提下支持目标实时数据量。  
  
 DTA 清除和存档作业可在给定时间间隔内清除特定数量的数据。 该作业的处理能力取决于运行的方案、当前数据库大小和硬件。 为了获得稳定的环境，必须在传入跟踪数据的生成和清除之间取得平衡。 在测试环境中，可通过改变数据的生存时段和清除作业的频率来找到平衡。 在平衡状态下，系统将具有持续稳定的吞吐量。 您的目标是在 BizTalk 跟踪数据库表大小导致持续显著的性能问题之前，具有足够的缓冲区。  
  
## <a name="performance-limitations"></a>性能限制  
 清除时的性能对所有方案都是不可调整的。 对于任何方案，跟踪数据量都可能不断增加。 当以持续较低速率清除跟踪数据时，跟踪数据库的大小就会增大，这会使清除性能进一步恶化。  
  
 在负载不可承受的条件下，复制消息正文的速度也会降低，这可能在 MessageBox 数据库中形成积压。 在极端条件下，日常消息正文复制和跟踪会产生消息正文不可用的存档，即使该消息包含相关的实例信息。 通常，高负载阶段和低负载阶段交替进行，使落后的作业在低负载阶段得以弥补。  
  
 由于不断清除数据库并对存储的跟踪数据进行压缩，存档和清除 BizTalk 跟踪数据库能够大大降低发生负载不可承受情况的可能性。 这些进程极大地减少了手动干预的需要。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)