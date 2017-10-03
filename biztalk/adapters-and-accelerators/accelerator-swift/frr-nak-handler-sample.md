---
title: "FRR 否认处理程序示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-nak-handler-sample"></a>FRR 否认处理程序示例
FRR 否认处理程序示例演示如何使用 SWIFT 响应创建 FIN 响应对帐 (FRR) 具有关联的处理消息的自定义处理程序。 此自定义处理程序处理提供 MTS21_FIN_ACKNAK 负确认消息，指示，SWIFT 未成功收到消息 A4SWIFT FRR 具有相关的消息。 自定义处理程序添加到该消息，使两个部分构成消息的消息的对象时出错，而且有助于提升会导致消息修复业务流程来选取消息的属性。 因此，repairer 可以修复消息并重新发送到 SWIFT 联盟访问 (SAA)。  
  
 **示例组件**  
  
 FRR 否认处理程序示例包括以下组件：  
  
-   **RepairSWIFTRejectedMessage.odx。** 此业务流程是处理 SWIFT 无法成功接收，将它路由到消息修复业务流程，以便 repairer 可以修复并重新发送消息的消息的自定义处理程序。  
  
-   **RepairSWIFTRejectedMessage.btproj。** 此项目包括 RepairSWIFTRejectedMessage.odx 和所需项目的引用，生成和部署。  
  
-   **RepairSWIFTRejectedMessage.sln。** 此解决方案包括 RepairSWIFTRejectedMessage.btproj 项目。  
  
 本部分包含：  
  
-   [实现 FRR 否认处理程序示例](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [FRR 否认处理程序示例的工作原理](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
