---
title: 适用于业务 Exchange 交互适配器消息 |Microsoft 文档
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
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224597"
---
# <a name="interact-adapter-messages-for-business-exchange"></a>适用于业务 Exchange 交互适配器消息
在交互适配器端到端周期中有四条消息。 这些消息将 SWIFTNet 基元。 客户端基元、 SwInt:ExchangeRequest 和 SwInt:ExchangeResponse，前者构成的第一个和最后一个消息。 服务器端基元、 SwInt:HandleRequest 和 SwInt:HandleResponse，前者构成中间两条消息。  
  
 在此级别的简化，有六个步骤在端到端消息周期中：  
  
1.  客户端应用程序准备请求消息。  
  
2.  客户端应用程序将请求消息传递给 SWIFTNet。  
  
3.  SWIFTNet 处理请求消息，并将其发送到服务器应用程序。  
  
4.  服务器应用程序从 SWIFTNet 接收请求消息。  
  
5.  服务器应用程序准备响应消息。  
  
6.  服务器应用程序将响应消息传递给 SWIFTNet。  
  
7.  SWIFTNet 处理响应消息，并将其发送到客户端应用程序。  
  
8.  客户端应用程序从 SWIFTNet 接收响应消息。  
  
 下图显示交互消息交换。  
  
 ![交互消息交换](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)