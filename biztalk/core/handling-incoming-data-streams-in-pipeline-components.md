---
title: "处理管道组件中的传入数据流 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a>处理管道组件中的传入数据流
编写管道中的组件的自定义反汇编程序代码时，应进行以下注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a>不要在自定义拆装器代码中关闭传入数据流  
 当你编写自定义反汇编程序代码中的管道组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确保不要关闭反汇编程序代码中的对传入数据流。 来自输入消息的传入流是共享资源。 跟踪中的组件消息正文也使用传入流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。  
  
 如果隐式或显式关闭传入流，则跟踪数据可能会丢失，并且将无法使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的消息事件和服务实例跟踪检查流数据。  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a>使用 Stream 类的 Seek 方法将数据流指针设置到流的开始位置  
 确保读取传入数据流时达到流的末尾。 例如，如果自定义代码做出 300 KB 数据的读取请求，并且代码仅收到 34 KB 数据，此时不要认为已达到流的末尾。 自定义代码始终应该从传入流中进行读取，直到返回 0 字节。  
  
 在自定义组件逻辑中返回数据流前，请将数据流指针设置回流的开始位置。 例如，下面的代码说明了在返回流前使用 Seek 方法指向流的开始位置的逻辑：  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 如果不这样做，并在当前组件中读取到了流的末尾，由于未将数据流指针设置到流的开始位置，下一个组件收到的将是一个空流。 这可能会在随后的管道组件中导致意外的解析错误和验证错误。