---
title: "为到自定义处理程序的消息的 FRR 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6babc312ddad7d77a96e29bc9e59ec9298aa6ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>为到自定义处理程序的消息的 FRR 发送端口
若要为 FRR 启用自定义处理程序，必须创建一系列 FRR 发送端口，每个将特定类型的原始消息的副本路由到的自定义处理程序。 这些发送端口都必须具有以下管道组件：  
  
-   组装阶段中 SWIFT 汇编程序  
  
-   编码阶段中的 SWIFTSendFrrComponent 管道组件  
  
 对于除类别 0 到 9 SWIFT FIN 消息不成功发送的所有消息，发送端口必须具有以下筛选器：  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS。操作将设置为所需的每种消息类型的值。 有关 BTS 的可能值。操作属性，请参阅中的表[为发送到的自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。  
  
 对于类别 0 到 9 SWIFT FIN 未成功发送的消息，发送端口必须具有以下筛选器：  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed = = true  
  
-   BTS。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason 设置为所需的每种消息类型的值。 有关 BTS 的可能值。操作属性，请参阅中的表[为发送到的自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。