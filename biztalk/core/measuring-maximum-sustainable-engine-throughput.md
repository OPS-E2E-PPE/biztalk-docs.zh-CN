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
# <a name="measuring-maximum-sustainable-engine-throughput"></a><span data-ttu-id="20473-102">测量的最大可持续引擎吞吐量</span><span class="sxs-lookup"><span data-stu-id="20473-102">Measuring Maximum Sustainable Engine Throughput</span></span>
<span data-ttu-id="20473-103">规划 BizTalk Server 系统时主要考虑因素之一应是确定系统的最大可承受吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="20473-103">One of the primary considerations when planning a BizTalk Server system should be to determine the maximum sustainable throughput (MST) of the system.</span></span> <span data-ttu-id="20473-104">BizTalk Server 系统的 MST 是 BizTalk 系统在生产中可无限制处理的最高消息通信负载。</span><span class="sxs-lookup"><span data-stu-id="20473-104">The MST of a BizTalk Server system is measured as the highest load of message traffic that the BizTalk system can handle indefinitely in production.</span></span> <span data-ttu-id="20473-105">这一点非常重要，因为当负载超过 MST 时，消息将积压在 MessageBox 数据库中，消息传送可能会延迟。</span><span class="sxs-lookup"><span data-stu-id="20473-105">This is important because as load exceeds MST, messages are backlogged in the MessageBox database and message delivery may be delayed.</span></span> <span data-ttu-id="20473-106">如果您计算 BizTalk Server 系统的 MST，将其作为正常测试的一部分，则您可以扩展系统以避免在生产中出现扩展过载情况。</span><span class="sxs-lookup"><span data-stu-id="20473-106">If you calculate the MST of your BizTalk Server system as part of normal testing then you can scale your system to avoid extended overload scenarios in production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20473-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="20473-107">In This Section</span></span>  
  
-   [<span data-ttu-id="20473-108">影响最大可持续性能因素</span><span class="sxs-lookup"><span data-stu-id="20473-108">Factors that Affect Maximum Sustainable Performance</span></span>](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [<span data-ttu-id="20473-109">用于测量引擎 MST 测试方案</span><span class="sxs-lookup"><span data-stu-id="20473-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [<span data-ttu-id="20473-110">测试引擎性能的建议</span><span class="sxs-lookup"><span data-stu-id="20473-110">Recommendations When Testing Engine Performance</span></span>](../core/recommendations-when-testing-engine-performance.md)