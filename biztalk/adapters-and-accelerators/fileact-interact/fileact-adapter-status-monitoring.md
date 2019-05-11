---
title: FileAct 适配器状态监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1701e68b592e7f6eab012d14b1a14d6143c09da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367158"
---
# <a name="fileact-adapter-status-monitoring"></a>FileAct 适配器状态监视
下图显示了文件传输和这些状态之间的转换的可能状态。  
  
 ![FileAct 适配器文件传输状态](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")  
  
 文件传输状态如下：  
  
-   **启动**– 客户端已协商信息发送到服务器，但未收到响应。 服务器已收到协商请求，但不是发送响应。  
  
-   **接受**– 服务器已接受请求和响应消息中发送 TransferAnswer，传输是仍在进行中。  
  
-   **拒绝**– 服务器已拒绝的请求和响应消息中具有 TransferAnswer，已终止传输。  
  
-   **正在进行**– 传输正在进行中并且将继续执行 （与上面定期续订）。  
  
-   **完成**-文件传输已成功完成，就而言这方面的传输，包括的摘要值进行比较。  
  
-   **失败**-文件传输失败，因为数据访问处理、 通信或超时异常。 (注意：SWIFTNet 链接会强制实施超时和的值由 SWIFT）。  
  
-   **中止**-文件传输已中止 （任一端中止我的问题）。  
  
-   **未知和重复**– 只是由于计时，出现此状态。 对于发送程序，该文件应重新发送标记为可能是重复 (PDIndicator)。 对于接收方，当 PDIndicator 意味着，该文件可能已发送，FileAct 适配器将检查重复项，并且如果找到，则将返回 TransferAnswer 的重复，这将终止当前尝试。  
  
## <a name="see-also"></a>请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)