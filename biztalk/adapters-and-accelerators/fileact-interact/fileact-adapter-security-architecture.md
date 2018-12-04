---
title: FileAct 适配器安全体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be9997dca0a4b7a5c619848e4ed38cf9099bbc16
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826373"
---
# <a name="fileact-adapter-security-architecture"></a>FileAct 适配器安全体系结构
使用 SNL 和压降中固有的证书和加密功能实现的文件发送和接收的安全性。  管理的证书，等等，完全是 FileAct 适配器范围之外。 只要关联的 SNL/压降实例注册为使用 SWIFT FileAct 服务并使 SNL/压降，该适配器上正确安装该软件的使用情况通过 SNL Api 的功能。 FileAct 适配器将始终设置为"高级"（最佳做法） FACryptoMode。  
  
> [!NOTE]
>  对于适配器，可以创建每个发送端口的单独的安全上下文。  
  
## <a name="see-also"></a>请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
