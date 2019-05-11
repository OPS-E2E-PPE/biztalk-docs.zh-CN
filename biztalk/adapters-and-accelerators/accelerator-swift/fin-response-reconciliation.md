---
title: FIN 响应对帐 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c2b74012c5f33967773234902a7475b8052f769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377853"
---
# <a name="fin-response-reconciliation"></a>FIN 响应对帐
FIN 响应对帐 (FRR) 功能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]协调与相应的原始消息的发送 FIN 响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这会建立原始消息的状态并启用[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]执行基于该状态的步骤。 而无需对帐，这不是可能。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 会知道，它已成功 （或未成功） 将原始消息发送到 SAA，和它必须从 SAA，指示状态的传输，它接收的响应，但它将不能两者之间建立连接。 FRR 建立该连接。  
  
 FIN 响应是确认 (Ack) 或否定确认 (NAKs) 发送到 SAA [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，或由 SWIFT 网络发送到 SAA，并转发到 SAA 按[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这些确认存在定义消息的业务状态。 你可以监视通过业务活动监视 (BAM) 报告此状态。  
  
 此外可以实现 FRR 周围的自定义应用程序行为。 自定义处理程序可以实现自己的逻辑来处理的 FIN 响应对帐的集。 处理的消息的 FRR 具有相关 MTS21_FIN_ACKNAK NAK 消息的自定义处理程序的示例，请参阅[FRR NAK 处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。  
  
 默认情况下安装 FRR 业务流程[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序。 您需要通过创建接收管道中，配置的 FRR 系统接收位置和发送端口。 此外需要配置 FRR 来指定它应等待多长延迟 NAKs 和响应一般情况下。 FRR 配置和管理有关的详细信息，请参阅[配置 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)并[管理 FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)。  
  
 本部分包含：  
  
-   [FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [FRR 处理](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [FRR 业务流程](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [从后端应用程序接收消息的 FRR 接收位置](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [向 SWIFT 发送消息的 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [从 SWIFT 接收消息的 FRR 接收位置](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [向自定义处理程序发送消息的 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [处理已对帐的消息集](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)