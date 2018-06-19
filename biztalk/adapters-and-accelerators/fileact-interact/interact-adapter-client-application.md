---
title: 交互适配器客户端应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdab4624-0fc2-42a3-9867-8f77e144b40c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dac8f459799f59b63976c29f4a87dfe22b56e7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223093"
---
# <a name="interact-adapter-client-application"></a>交互适配器客户端应用程序
交互适配器客户端应用程序请求消息是从客户端应用程序到客户端 SWIFTNet 链接 (SNL) 传递的 XML 文档。 此类型的消息发生作为客户端上执行过的 SWIFTNet 请求/响应基元的第一部分。  
  
 本主题介绍 SwInt:ExchangeRequest 消息。 它用于对 SWIFTNet 的"同步，"客户端调用。 在此上下文中，"同步"意味着，函数调用将会阻止客户端应用程序，并强制对它等待，直到从服务器端应用程序收到的响应。 （或者，或者，出现错误条件，该错误报告回客户端。）  
  
 加密块 (SwSec:Crypto)，如果它们存在，包含消息签名和/或验证处理的结果。 此外，在某些处理阶段，它们可能包含直接通过 SNL 要执行的加密处理的说明。  
  
## <a name="interact-adapter-payload-format"></a>交互适配器负载格式  
 请求负载包含业务消息的实质。 负载的结构必须符合格式正确的 XML （这只是意味着负载不会中断 XML 分析，但在这种情况下，不需要使用 XML 文档结构） 的要求。 如果应用 SWIFTNet 消息验证，则负载必须符合其他结构化要求。 除此之外，由业务应用程序确定的负载结构和内容。  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)