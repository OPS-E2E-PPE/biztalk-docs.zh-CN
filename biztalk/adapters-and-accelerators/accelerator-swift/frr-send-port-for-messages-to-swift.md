---
title: 用于发送到 SWIFT 消息的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1732e5e41cd60f6c98f435197e2e9c6284e4dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991734"
---
# <a name="frr-send-port-for-messages-to-swift"></a>用于发送到 SWIFT 消息的 FRR 发送端口
若要启用 FIN 响应对帐 (FRR)，必须设置为 MQSeries 向 SAA 通过 BizTalk 适配器发送一条消息的 FRR 发送端口。 此发送端口路由任何消息通过自定义的 FRR 发送管道组件，则必须使用以下管道组件创建：  
  
- SWIFT 汇编程序的组装阶段中  
  
- SWIFTAsmFrrMQSeriesHelper 管道组件中的编码阶段  
  
  SWIFTAsmFrrMQSeriesHelper 管道组件将传出消息的 MQMD_MsgID 属性设置为 FRRCorrelationToken 属性的值。 它还分配并升级开头"MQ"的值在管道设计时设置的任何其他所需的上下文属性。 发送管道包括用于 MQSeries 作为可配置属性定义每个属性。 每个值默认为"未使用"。  
  
  发送端口处理的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True。 传输机制是用于 MQSeries 的 BizTalk 适配器。 有关传输属性，例如碎片大小，请参阅 MQSeries 文档。