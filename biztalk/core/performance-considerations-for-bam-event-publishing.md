---
title: 有关 BAM 事件发布的性能注意事项 |Microsoft 文档
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
ms.openlocfilehash: ebab873c94c0ae17abf9938883662ca8777cef36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264421"
---
# <a name="performance-considerations-for-bam-event-publishing"></a>有关 BAM 事件发布的性能注意事项
BAM 支持两种形式的业务事件发布：  
  
-   同步  
  
-   异步  
  
 下图说明了两个模型。  
  
 ![](../core/media/bam-topologies.gif "bam_topologies")  
BAM 拓扑  
  
 同步的方法是用于管理和使用从代码中，异步方法可以更好的性能时要简单得多。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [同步业务事件跟踪](../core/synchronous-business-event-tracking.md)  
  
-   [异步业务事件跟踪](../core/asynchronous-business-event-tracking.md)