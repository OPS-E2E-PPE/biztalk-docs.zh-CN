---
title: 有关 BAM 事件发布的性能注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c031f9a3325eda9cbcf865eaf72d1d9e100616c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997534"
---
# <a name="performance-considerations-for-bam-event-publishing"></a>有关 BAM 事件发布的性能注意事项
BAM 支持两种形式的业务事件发布：  
  
- 同步  
  
- 异步  
  
  下图演示了两个模型。  
  
  ![](../core/media/bam-topologies.gif "bam_topologies")  
  BAM 拓扑  
  
  同步方法是要简单得多的管理和使用在代码中，而异步方法可提高性能。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [同步业务事件跟踪](../core/synchronous-business-event-tracking.md)  
  
-   [异步业务事件跟踪](../core/asynchronous-business-event-tracking.md)