---
title: Business Exchange 的 interAct 适配器消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea8e7d4f4ed8397c88a3cf21280352b446d629c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020149"
---
# <a name="interact-adapter-messages-for-business-exchange"></a>Business Exchange 的 interAct 适配器消息
InterAct 适配器端到端周期中有四个消息。 这些消息是 SWIFTNet 基元。 第一个和最后一个消息包含客户端基元、 SwInt:ExchangeRequest 和 SwInt:ExchangeResponse。 中间的两个消息组成的服务器端基元、 SwInt:HandleRequest 和 SwInt:HandleResponse。  
  
 在此级别的简化，有六个步骤中的端到端消息循环：  
  
1. 客户端应用程序准备请求消息。  
  
2. 客户端应用程序将请求消息传递给 SWIFTNet。  
  
3. SWIFTNet 处理请求消息，并将其发送到服务器应用程序。  
  
4. 服务器应用程序从 SWIFTNet 接收请求消息。  
  
5. 服务器应用程序准备的响应消息。  
  
6. 服务器应用程序将响应消息传递给 SWIFTNet。  
  
7. SWIFTNet 处理响应消息，并将其发送到客户端应用程序。  
  
8. 客户端应用程序从 SWIFTNet 接收响应消息。  
  
   下图显示了 InterAct 消息交换。  
  
   ![InterAct 消息交换](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)