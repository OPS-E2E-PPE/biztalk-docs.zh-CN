---
title: "FIN 响应对帐 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation"></a>FIN 响应对帐
FIN 响应对帐 (FRR) 功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]与相应的原始消息发送的协调 FIN 响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这建立原始消息的状态，并使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行基于该状态的步骤。 而无需对帐，这将不是可能发生的情形。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]会知道，它 （无论成功) 发送原始消息到 SAA，并且它必须从 SAA，指示的状态的传输，收到的响应，但它将不能使这两者之间的连接。 FRR 建立该连接。  
  
 FIN 响应是否确认 (Ack) 或否定确认 (NAKs) 发送到 SAA [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，或由 SWIFT 网络发送给 SAA，然后转发到 SAA 由[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 传送这些确认存在定义消息的业务的状态。 你可以监视通过业务活动监视 (BAM) 报告此状态。  
  
 你也可以实现 FRR 周围的自定义应用程序行为。 自定义处理程序可以实现自己的逻辑来处理对帐的套 FIN 响应。 自定义处理程序处理的消息，具有相关的 FRR MTS21_FIN_ACKNAK 否认消息的示例，请参阅[FRR 否认处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。  
  
 默认情况下，通过安装 FRR 业务流程[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序。 你需要通过创建接收管道，配置 FRR 系统接收位置和发送端口。 你还需要配置 FRR 指定它应等待的时间延迟 NAKs 和响应一般情况下。 有关 FRR 配置和管理的详细信息，请参阅[配置 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)和[管理 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)。  
  
 本部分包含：  
  
-   [FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [FRR 处理](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [FRR 业务流程](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [FRR 从后端应用程序接收的消息的位置](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [消息到 SWIFT FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [FRR 从 SWIFT 接收的消息的位置](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [为到自定义处理程序的消息的 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [处理已协调消息集](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)