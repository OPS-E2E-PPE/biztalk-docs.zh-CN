---
title: 交互适配器组件 |Microsoft 文档
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
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224685"
---
# <a name="interact-adapter-components"></a>交互适配器组件
交互适配器具有客户端和服务器组件。 请注意，可能会出现在同一台计算机作为 SWIFT 联盟网关 （压降） 上的 A4SWIFT （最小） 安装是否它正在运行 Windows Server。 另请注意，SWIFTNet 链接 (SNL) 可能压降从一台计算机上。 远程的应用程序编程接口 (API) 主机适配器 SWIFT 提供用于从 A4SWIFT 到压降，而不考虑组件位置的通信。  
  
 下图显示构成整个适配器和通信链的交互适配器相关的组件的驻留位置。  
  
 ![交互组件](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")  
  
 在下图中，客户端应用程序使用 A4SWIFT 和交互适配器。 BizTalk Server 是中间，其中通过 TCPIP 到远程 API 主机适配器进行通信。  
  
 ![客户端应用程序进行交互](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")  
  
 在下图中，服务器应用程序使用 A4SWIFT 和交互适配器。 BizTalk Server 是中间，其中通过 TCPIP 到远程 API 主机适配器进行通信。  
  
 ![服务器应用程序进行交互](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)