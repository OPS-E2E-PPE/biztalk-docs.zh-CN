---
title: "FRR 接收的消息的位置从 SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d609cfc8c5177581f32ee0957a6a7ae7c1fe9a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-receive-location-for-messages-from-swift"></a>FRR 从 SWIFT 接收的消息的位置
若要启用 FIN 响应对帐 (FRR)，必须设置 FRR 接收管道组件以从 SAA 收到一条消息并准备将其以供处理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 接收管道包含以下组件：  
  
-   拆装阶段中 SWIFT 反汇编程序  
  
-   解码器阶段中的 SWIFT FRR 解码器管道组件  
  
-   在参与方解析阶段 SWIFT FRR CorrelationSet 冲突解决程序管道组件  
  
 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收平移/NAN、 SWIFT FRR 解码器读取 MQ 反馈上下文属性，以确定响应是平移或为 NAN。 它将设置传输不可知[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck 布尔值平移或 nan 的 false 值为 true。  
  
 SWIFT FRR CorrelationSet 冲突解决程序管道组件将覆盖与响应消息的 FRRCorrelationToken 属性，用于使用 FRR 业务流程，MQMD 中的值。CorrelId 属性。