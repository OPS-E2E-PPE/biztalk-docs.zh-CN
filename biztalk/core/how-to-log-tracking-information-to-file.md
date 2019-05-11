---
title: 如何跟踪信息记录到文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, tracking
- DebugTrackingInterceptor
- Business Rules Framework, code samples
ms.assetid: c832b763-aa08-4a0e-9086-776dccb0a6ef
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: facc8f6bf3e50e6aa267f1df8addc6ee1c2653a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384739"
---
# <a name="how-to-log-tracking-information-to-file"></a>如何跟踪信息记录到文件
业务规则引擎执行时，它将传递到侦听器跟踪信息的执行。 该引擎配置为使用跟踪消息事件和服务实例数据时使用的 BizTalk 侦听器。 如果你正在调用外部 BizTalk 业务流程引擎，可以传递所需执行策略时要使用的侦听器。 除了 BizTalk 侦听器，还可以使用**DebugTrackingInterceptor**输出跟踪信息写入文件。 下面的代码示例演示如何使用**DebugTrackingInterceptor**。  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```