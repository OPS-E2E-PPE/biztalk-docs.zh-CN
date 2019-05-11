---
title: FRR NAK 处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c39c564595852fa8c19d3d9f26b5ba5946f6c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377565"
---
# <a name="frr-nak-handler-sample"></a>FRR NAK 处理程序示例
FRR NAK 处理程序示例演示如何使用 SWIFT 响应创建 FIN 响应对帐 (FRR) 具有关联的处理消息的自定义处理。 此自定义处理程序处理 MTS21_FIN_ACKNAK 否定确认消息，指示的 SWIFT 没有成功收到消息 A4SWIFT FRR 具有相关的消息。 自定义处理程序将错误对象添加到该消息，使消息分为两部分消息，并将导致消息修复业务流程选取该消息的属性升级。 因此，repairer 可以解决该消息并重新发送到 SWIFT 联盟访问 (SAA)。  
  
 **示例组件**  
  
 FRR NAK 处理程序示例包括以下组件：  
  
- **RepairSWIFTRejectedMessage.odx.** 此业务流程是处理 SWIFT 无法成功接收，其路由到消息修复业务流程以便 repairer 进行修复，重新发送消息的消息的自定义处理程序。  
  
- **RepairSWIFTRejectedMessage.btproj.** 此项目包括 RepairSWIFTRejectedMessage.odx 和项目所需的引用来构建和部署。  
  
- **RepairSWIFTRejectedMessage.sln.** 此解决方案包括 RepairSWIFTRejectedMessage.btproj 项目。  
  
  本部分包含：  
  
- [实现 FRR NAK 处理程序示例](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [FRR NAK 处理程序示例工作原理](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  
