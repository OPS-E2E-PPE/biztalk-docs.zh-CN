---
title: 衡量最大可持续引擎吞吐量 |Microsoft 文档
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
ms.openlocfilehash: a5507aca58669ed5c81034ba91e16d1183e07188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262325"
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a>测量的最大可持续引擎吞吐量
规划 BizTalk Server 系统时主要考虑因素之一应是确定系统的最大可承受吞吐量 (MST)。 BizTalk Server 系统的 MST 是 BizTalk 系统在生产中可无限制处理的最高消息通信负载。 这一点非常重要，因为当负载超过 MST 时，消息将积压在 MessageBox 数据库中，消息传送可能会延迟。 如果您计算 BizTalk Server 系统的 MST，将其作为正常测试的一部分，则您可以扩展系统以避免在生产中出现扩展过载情况。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [影响最大可持续性能因素](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [测试引擎性能的建议](../core/recommendations-when-testing-engine-performance.md)