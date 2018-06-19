---
title: 调整限制阈值： 何时和为何 |Microsoft 文档
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
ms.openlocfilehash: 3b49ae78d4b2d0cf2dabfc69af9023b1e8676dea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229925"
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a>调整限制阈值： 何时和为何
对于阻止操作而言，一个大小根本不够。 将由一系列因素确定应采用的最佳设置。 BizTalk Server 本身提供了默认值，这些默认值经测试证明可有效地防止系统发生积压过多等现象。 然而，在某些情况下，这些默认值可能过于严格。 下面的示例阐释了这一点。  
  
## <a name="example-1-peak-loads-and-database-size"></a>示例 1： 高峰负载和数据库大小  
 在 BizTalk Server 上构建的每个解决方案都有最大可承受吞吐量 (MST)。 根据定义，只要负载低于此级别，系统就能够无限制地承受该负载。 在实践中，但是，它是更常见的是具有高峰和低谷中的负载配置文件与具有恒定的负载，不会随时间而有所不同。  
  
 从经济角度而言，与其构建一个可无限制地承受最高峰值负载的数据库，还不如构建一个适当的系统，此系统在峰值负载下可以处理一些积压，但在低谷期可以恢复正常。 然而，如果峰值负载期间预计的积压高于数据库大小的默认阻止值，则系统将通过阻止输入来阻止积压。 如果这一点不可行（例如，您需要尽快使用所有输入文件），此解决方案将提高数据库大小阈值，以便在阻止之前接受预计的积压。  
  
## <a name="example-2-memory-usage-optimization"></a>示例 2： 内存使用情况的优化  
 阻止过程用来衡量处理速度的另一个资源是主机进程可以使用多少内存。 如果与阈值相比，可用内存过小，则阻止过程将减少引擎从要处理的主机队列中检索的消息数。 鉴于现今的企业级服务器能够容纳大量内存并且内存不难获得（尤其是由于在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供了 64 位支持），因此有充分的理由需要提高和降低阈值，以优化内存使用率。  
  
## <a name="recommendation"></a>建议  
 默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的阻止行为被配置为随时向系统提供良好的保护。 然而，不应将默认设置当作最佳配置。 应监视性能计数器以了解阻止状态，从而确定是否发生了阻止行为，接着自行衡量阻止行为所依据的资源（例如，数据库大小或内存使用率）是处于欠利用状态还是处于过利用状态，然后相应地调整阻止阈值的大小。