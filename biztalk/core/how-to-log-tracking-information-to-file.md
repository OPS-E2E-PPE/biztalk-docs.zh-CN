---
title: 如何登录到文件中跟踪信息 |Microsoft 文档
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
ms.openlocfilehash: 6cdaae8e727cedc784ecaade83178cf50f863f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254709"
---
# <a name="how-to-log-tracking-information-to-file"></a>如何登录到文件中跟踪信息
在执行业务规则引擎时，该引擎将向侦听器传递执行跟踪信息。 该引擎配置为使用在跟踪消息事件和服务实例数据时使用的 BizTalk 侦听器。 如果是在 BizTalk 业务流程之外调用该引擎，可以在执行策略时传递要使用的侦听器。 除了 BizTalk 侦听器，还可以使用**DebugTrackingInterceptor**输出跟踪信息写入文件。 下面的代码示例演示如何使用**DebugTrackingInterceptor**。  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```