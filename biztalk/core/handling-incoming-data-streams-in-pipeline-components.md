---
title: 处理管道组件中的传入数据流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691e0e28b8c3ab6cea273979a69d2eeba0135aa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344667"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a>处理管道组件中的传入数据流
编写自定义拆装器管道组件中的代码时应考虑以下注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a>不要关闭自定义拆装器代码中的传入数据流  
 当你编写自定义拆装器管道组件中的代码[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保在不关闭传入数据流中的拆装器代码。 从输入消息的传入流是共享的资源。 消息正文跟踪组件中的也使用传入流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。  
  
 如果隐式或显式关闭传入流，跟踪数据可能会丢失，你将不能检查消息事件和服务实例跟踪中的使用的流数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a>Stream 类的 Seek 方法用于将数据流指针设置为在流开头  
 确保直到到达流的末尾读取传入数据流。 例如，如果自定义代码做出 300 kb 数据的读取的请求和代码仅收到 34 KB 的数据，不要假定已到达流的末尾。 直到返回 0 字节的自定义代码应始终从传入流中读取。  
  
 自定义组件中返回数据流前逻辑，将数据流指针设置回流的开始。 例如，以下代码说明了使用 seek 方法指向流的开头之前返回流的逻辑：  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 如果您不这样做，到当前组件中端读取的流的下一个组件收到的将是一个空流，因为未数据流指针设置为在流开头。 这会在随后的管道组件中导致意外的分析和验证错误。