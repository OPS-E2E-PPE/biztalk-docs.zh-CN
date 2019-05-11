---
title: 测量最大可承受引擎吞吐量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST)
- maximum sustainable throughput (MST), about maximum sustainable throughput (MST)
- performance, maximum sustainable thoughput (MST)
ms.assetid: d83f734f-1a44-4da0-a755-45ba204cadaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffbdbb3955a4b595f4a3a0486174f0f3a7005a4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325583"
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a>测量最大可承受引擎吞吐量
规划 BizTalk Server 系统时主要的考虑因素之一应是确定系统的最大可承受吞吐量 (MST)。 BizTalk Server 系统的 MST 的衡量标准 BizTalk 系统可在生产环境中无限制处理的消息流量的最高负载。 这非常重要，因为当负载超过 MST，消息将积压在 MessageBox 数据库和消息传送可能会延迟。 如果您计算 BizTalk Server 系统作为正常测试的一部分的 MST，则您可以扩展系统，以避免在生产环境中的扩展的过载情况。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [影响最大可承受性能的因素](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [测试引擎性能时的建议](../core/recommendations-when-testing-engine-performance.md)