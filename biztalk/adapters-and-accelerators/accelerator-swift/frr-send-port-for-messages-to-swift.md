---
title: "消息到 SWIFT FRR 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a442b45f57009b839b4e184ef9662b253ba32b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-port-for-messages-to-swift"></a>消息到 SWIFT FRR 发送端口
若要启用 FIN 响应对帐 (FRR)，你必须设置为 MQSeries 向通过 BizTalk 适配器 SAA 发送一条消息 FRR 发送端口。 此发送端口路由任何消息通过自定义 FRR 发送必须创建具有以下管道组件的管道组件：  
  
-   组装阶段中 SWIFT 汇编程序  
  
-   编码阶段中的 SWIFTAsmFrrMQSeriesHelper 管道组件  
  
 SWIFTAsmFrrMQSeriesHelper 管道组件将传出消息的 MQMD_MsgID 属性设置为 FRRCorrelationToken 属性的值。 它还将分配，而且有助于提升在管道设计时设置的值与"MQ"开头的任何其他所需的上下文属性。 发送管道包括为 MQSeries 作为可配置属性定义每个属性。 每个值默认为"未使用"。  
  
 发送端口处理的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True。 此传输机制是 MQSeries BizTalk 适配器。 有关传输属性，例如碎片大小，请参阅 MQSeries 文档。