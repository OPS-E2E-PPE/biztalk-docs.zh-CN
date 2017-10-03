---
title: "SWIFTNet 客户端和服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swiftnet-client-and-server"></a>SWIFTNet 客户端和服务器
SWIFT 使用条款客户端和服务器来描述发送和接收。 SWIFT 客户端是一个过程，调用 SWIFTNet 链接 (SNL) 以通过 SWIFTNet 启动的通信。 在 BizTalk Server 中，这被称为发送适配器。 SWIFT 服务器是时流量经过 SWIFTNet SNL 由调用程序。 在 BizTalk Server 中，这被称为接收适配器。  
  
 不要混淆 SWIFT 客户端和业务客户端和服务器的服务器。 例如，客户端 （组织） 依赖于由服务器 （组织） 提供的服务。 如果服务器 （组织） 想要启动与客户端 （组织） 的通信，它必须使用 SNL 客户端应用程序进行管理，以及客户端 （组织） 必须具有用于接收传入流量的 SNL 服务器应用程序。 下图对此进行了描述。  
  
 ![客户端和服务器之间的 SWIFTNet 关系](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")  
  
 SNL 假定客户端和服务器应用程序是在命令提示符下启动的可执行文件。 它们都链接到 SNL API DLL，而与实际 SNL 实例进程通信。  
  
## <a name="snl-client-applications"></a>SNL 客户端应用程序  
 SNL 客户端应用程序依赖于如下所述 SwCall API。 从技术角度讲，典型的客户端应用程序可以描述，如下所示：  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 SNL 客户端应用程序必须在专用的过程中，运行，因为 SNL 引用客户端上下文的进程 id。 SNL 同步使用 SwCall 炫资源的调用。 因此，只有一次单个客户端线程可以有效地执行 SwCall。  
  
 客户端支持的同步通信模式。 这意味着响应再次从服务器时发生 SWCall 回报。 在此返回后才可以执行下一步 SwCall。  
  
## <a name="snl-server-applications"></a>SNL 服务器应用程序  
 SNL 服务器应用程序是客户端应用程序比稍微复杂。 服务器应用程序在执行到 SNL DLL 的阻止调用之前注册回调函数。 从技术角度讲，典型的服务器应用程序可以描述，如下所示：  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 服务器应用程序可以调用的回调函数中 SwCall API。 在某些情况下，则必须调用 SwCall 能够以生成所需的结果或响应。 但是，服务器应用程序永远不会可以通过网络启动的通信。 服务器应用程序绝不会客户端应用程序。  
  
 下图中，在调用标记为**初始化**是用于 SNL API 初始化过程中，需要多个调用的抽象。 标记为调用**SwCallback()**将重复几次，并调用标记为**SwCall()**是可选的。  
  
 ![SNL 服务器功能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")  
  
 在服务器和 SNL API DLL 之间的所有调用都是标准 C 调用约定同步函数调用。  
  
## <a name="see-also"></a>另请参阅  
 [了解 FileAct 和交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)   
 [SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)