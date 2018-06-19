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
# <a name="how-to-log-tracking-information-to-file"></a><span data-ttu-id="e485d-102">如何登录到文件中跟踪信息</span><span class="sxs-lookup"><span data-stu-id="e485d-102">How to Log Tracking Information to File</span></span>
<span data-ttu-id="e485d-103">在执行业务规则引擎时，该引擎将向侦听器传递执行跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="e485d-103">When the Business Rule Engine executes, it passes execution tracking information to an interceptor.</span></span> <span data-ttu-id="e485d-104">该引擎配置为使用在跟踪消息事件和服务实例数据时使用的 BizTalk 侦听器。</span><span class="sxs-lookup"><span data-stu-id="e485d-104">The engine is configured to use the BizTalk interceptor which is used when tracking message events and service instance data.</span></span> <span data-ttu-id="e485d-105">如果是在 BizTalk 业务流程之外调用该引擎，可以在执行策略时传递要使用的侦听器。</span><span class="sxs-lookup"><span data-stu-id="e485d-105">If you are calling the engine outside of BizTalk orchestration, you can pass the interceptor you want to use when you execute the policy.</span></span> <span data-ttu-id="e485d-106">除了 BizTalk 侦听器，还可以使用**DebugTrackingInterceptor**输出跟踪信息写入文件。</span><span class="sxs-lookup"><span data-stu-id="e485d-106">In addition to the BizTalk interceptor, you can also use the **DebugTrackingInterceptor** to output the tracking information to file.</span></span> <span data-ttu-id="e485d-107">下面的代码示例演示如何使用**DebugTrackingInterceptor**。</span><span class="sxs-lookup"><span data-stu-id="e485d-107">The following code example demonstrates how to use **DebugTrackingInterceptor**.</span></span>  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```