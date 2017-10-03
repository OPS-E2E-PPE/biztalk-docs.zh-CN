---
title: "交互适配器状态监视 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32cf2f197508c0cd703a05780804c6bc880b5f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-status-monitoring"></a>交互适配器状态监视
SWIFTNet 链接 (SNL C) 将保留一个有关 SWIFTNet 存储和该 SNL 上获取的转发 (SnF) 会话的本地状态。 要获取有关会话的信息，请使用带有以下基元 SwCall():  
  
 ![获取会话信息](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")  
  
 请注意不需要提供 AuthorizationContext。 返回归本地 SNL 的信息，如下图中所示。  
  
 ![会话状态信息](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)