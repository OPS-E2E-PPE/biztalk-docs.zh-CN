---
title: SWIFTNet 客户端和服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18055bfae40f5a2369f153faa811639c1cc51bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364100"
---
# <a name="swiftnet-client-and-server"></a>SWIFTNet 客户端和服务器
SWIFT 使用条款客户端和服务器来描述发送和接收。 SWIFT 的客户端是一个过程，调用 SWIFTNet 链接 (SNL) 来通过 SWIFTNet 启动的通信。 在 BizTalk Server 中，这称为发送适配器。 SWIFT 服务器是在流量经过 SWIFTNet SNL 时调用的程序。 在 BizTalk Server 中，这称为接收适配器。  
  
 不要混淆 SWIFT 的客户端和业务客户端和服务器的服务器。 例如，客户端 （组织） 依赖于服务器 （组织） 提供的服务。 如果服务器 （组织） 想要启动与客户端 （组织） 通信，它必须使用 SNL 客户端应用程序来执行此操作，并且客户端 （组织） 必须具有 SNL 服务器应用程序用于接收传入流量。 下图对此进行了描述。  
  
 ![客户端和服务器之间的 SWIFTNet 关系](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")  
  
 SNL 假定客户端和服务器应用程序是在命令提示符下启动的可执行文件。 它们都链接到 SNL API DLL，这与实际 SNL 实例进程进行通信。  
  
## <a name="snl-client-applications"></a>SNL 客户端应用程序  
 SNL 客户端应用程序依赖于 SwCall API 如下所述。 从技术上讲，一个典型的客户端应用程序可以描述，如下所示：  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 SNL 客户端应用程序必须在专用进程中运行，因为 SNL 引用客户端上下文的进程 id。 SNL 同步使用的资源添加到 SwCall 炫的调用。 因此，只有一次的单个客户端线程可以有效地执行 SwCall。  
  
 客户端支持的同步通信模式。 这意味着 SWCall 回报出现当响应返回从服务器。 在此返回后才可进行下一步 SwCall。  
  
## <a name="snl-server-applications"></a>SNL 服务器应用程序  
 SNL 服务器应用程序是客户端应用程序比稍微复杂。 服务器应用程序在执行到 SNL DLL 是阻塞调用之前注册回调函数。 从技术上讲，一个典型的服务器应用程序可以描述，如下所示：  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 服务器应用程序可以调用 SwCall API 中的回调函数。 在某些情况下，它必须调用 SwCall 能够以生成所需的结果或响应。 但是，服务器应用程序永远不会可以通过网络启动通信。 服务器应用程序绝不能客户端应用程序。  
  
 在下图中，在调用标记的含义**初始化**是 SNL API 初始化过程中，需要多个调用的抽象概念。 标记为在调用**SwCallback()** 将重复几次，并在调用标**SwCall()** 是可选的。  
  
 ![SNL 服务器功能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")  
  
 在服务器和 SNL API DLL 之间的所有调用都是标准 C 调用约定在同步函数调用。  
  
## <a name="see-also"></a>请参阅  
 [了解 FileAct 和 InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)   
 [SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)