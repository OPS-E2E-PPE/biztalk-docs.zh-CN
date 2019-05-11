---
title: SWIFT 发送适配器动态发送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 105972fe-9dc0-480a-a4d1-2ec682fa7ad9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5161c47011a5239435739d08783e3da6f2547aaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364196"
---
# <a name="swift-send-adapter-dynamic-send"></a>SWIFT 发送适配器动态发送
发送适配器动态发送模式拉取来自队列的消息。 动态发送的 URI 为：  
  
```  
SWIFT://<queue name>/<Force Acquire>/<Session Mode>/<Order By>/<Recovery mode>  
```  
  
 可以使用业务流程或管道来构造 URI。  
  
## <a name="see-also"></a>请参阅  
 [SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 发送适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)   
 [SWIFT 发送适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)   
 [SWIFT 发送适配器同步模式](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)   
 [SWIFT 发送适配器终止](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)