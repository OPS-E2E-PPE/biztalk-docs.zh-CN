---
title: "FRR 从后端应用程序接收的消息的位置 |Microsoft 文档"
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
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d50f83feceac0238742cd474f70ecc1449f906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>FRR 从后端应用程序接收的消息的位置
若要启用 FIN 响应对帐 (FRR)，必须设置 FRR 接收从后端应用程序接收消息并将它们路由至消耗 BizTalk MessageBox 通过 FRR 业务流程的位置。 接收位置将通过自定义 FRR 接收管道，必须使用以下的管道组件创建的消息：  
  
-   拆装阶段中 SWIFT 反汇编程序  
  
-   解码器阶段中的 SWIFT FRR 解码器管道组件  
  
-   在参与方解析阶段 SWIFT FRR CorrelationSet 冲突解决程序管道组件  
  
 接收端口处理的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True。 此传输机制是后端应用程序所指示的任何内容。  
  
 此接收端口由接收位置使用相同的自定义接收管道使用来自 SWIFT 的消息。 但是，管道执行不同的函数，为这两个接收位置。 在来自后端应用程序的消息接收位置中，SWIFT FRR CorrelationSet 冲突解决程序管道组件初始化相关标记。