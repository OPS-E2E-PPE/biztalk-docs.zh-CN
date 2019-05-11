---
title: 调整限制阈值：何时以及为何 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afb26c8-e5f4-4b78-9a45-a1263e3cb6ab
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fa8ad1a9c8c9c94bc41bc4ca33b3fb8763d2b69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360112"
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a>调整限制阈值：时间和原因
谈到限制，一个大小根本不够。 有一系列因素，以确定最佳设置应该是什么。 默认情况下，BizTalk Server 提供的默认值，已通过测试，来有效保护系统的情况下被证实喜欢积压工作超额部分。 但是，对于某些情况下，这可能过高。 以下示例说明了这一点。  
  
## <a name="example-1-peak-loads-and-database-size"></a>示例 1：高峰负载和数据库大小  
 BizTalk Server 上构建每个解决方案都有最大可承受吞吐量 (MST)。 只要负载低于此级别，系统可以承受该负载无限期地，通过定义。 在实践中，但是，它是更常见的是与具有恒定的负载不会随着时间的推移而变化的相比有高峰和低谷负载配置文件中。  
  
 而不是生成一个系统能够承受的最高的峰值，无限期地加载，它是更具成本效益构建系统可以处理在峰值负载时，一些积压工作和低谷期间恢复。 但是，如果加载峰值期间预计的积压高于默认限制数据库大小值然后系统将通过阻止输入来阻止积压工作。 如果不需要这样做，例如，因为您需要的所有输入文件被作为快速，然后解决方案是提高数据库大小阈值，若要阻止之前接受预计的积压。  
  
## <a name="example-2-memory-usage-optimization"></a>示例 2：内存使用情况的优化  
 限制使用来衡量处理速度的另一个资源是内存量是可用于的主机进程。 如果与阈值相比，可用内存获取太小，限制将会减慢引擎检索从主机队列要处理的消息数。 给定的量和可用性如今的企业级服务器上的内存中的可变性，尤其是在使用 x64 支持在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，阈值很可能需要以引发或降低以优化内存使用情况。  
  
## <a name="recommendation"></a>建议  
 中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认提供良好的保护现成的系统配置。 默认设置应不是，但是，想当然当作最佳配置。 监视性能计数器限制状态，以查看是否限制的位置，然后自行衡量阻止行为的资源为基础 （例如，数据库大小或内存使用率） 的利用情况下或通过，然后调整限制阈值相应地增减。