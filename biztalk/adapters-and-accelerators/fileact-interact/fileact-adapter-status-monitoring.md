---
title: "FileAct 适配器状态监视 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5b717a02631d47b864cc9180cba2fba673c5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-status-monitoring"></a>FileAct 适配器状态监视
在下图说明了这些状态之间的转换的文件传输以及可能的状态。  
  
 ![FileAct 适配器文件传输状态](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")  
  
 文件传输状态包括：  
  
-   **启动**– 客户端已协商信息发送到服务器，但未收到响应。 服务器收到协商请求中，但不是发送响应。  
  
-   **接受**– 服务器已接受请求，并且已在响应消息中，发送 TransferAnswer 以及传输是仍在进行。  
  
-   **拒绝**– 服务器已拒绝请求，并且在响应消息中，有 TransferAnswer 和已终止传输。  
  
-   **正在进行**– 传输正在进行，并且将继续执行 （按上面所述的定期续订）。  
  
-   **完成**-文件传输已成功完成，就而言传输该端，包括的摘要值进行比较。  
  
-   **失败**-文件传输失败的数据访问，由于处理时，通信或超时异常。 (注意： 超时会强制执行由 SWIFTNet 链接，并且值由 SWIFT)。  
  
-   **中止**-文件传输已中止 （或者端中止我的问题）。  
  
-   **未知和重复**– 仅由于计时会出现此状态。 对于发送程序，该文件应为重新发送标记为可能重复 (PDIndicator)。 对于接收方，当 PDIndicator 意味着，该文件可能已发送，FileAct 适配器将检查重复，并且如果找到，则将返回 TransferAnswer 的重复，这将终止当前的尝试。  
  
## <a name="see-also"></a>另请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)