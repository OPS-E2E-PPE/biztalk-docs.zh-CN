---
title: InterAct 适配器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28effe3955d273e3164d34eb46f8ad947e798907
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366932"
---
# <a name="interact-adapter-components"></a>InterAct 适配器组件
InterAct 适配器具有客户端和服务器组件。 请注意，是否可能会有 A4SWIFT （最小） 安装在同一台计算机作为 SWIFT 联盟网关 （压降） 上的运行 Windows Server。 另请注意，SWIFTNet 链接 (SNL) 可能压降从一台计算机上。 远程应用程序编程接口 (API) 提供的 SWIFT 的主机适配器用于从 A4SWIFT 到压降，而不考虑组件的位置进行通信。  
  
 下图显示了包含整个适配器和通信链与 InterAct 适配器相关的组件所在的位置。  
  
 ![InterAct 组件](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")  
  
 在下图中，客户端应用程序使用 A4SWIFT 和 InterAct 适配器。 BizTalk Server 是通过 TCPIP 来与远程 API 主机适配器通信的中间件。  
  
 ![InterAct 客户端应用程序](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")  
  
 在下图中，服务器应用程序使用 A4SWIFT 和 InterAct 适配器。 BizTalk Server 是通过 TCPIP 来与远程 API 主机适配器通信的中间件。  
  
 ![InterAct 服务器应用程序](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)