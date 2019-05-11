---
title: FRR 接收的消息的位置从后端应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a865ced8a204bf571dde00c6f98869348934540f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377906"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>FRR 接收的消息的位置从后端应用程序
若要启用 FIN 响应对帐 (FRR)，必须设置 FRR 接收位置从后端应用程序接收消息并将他们路由到 BizTalk MessageBox 中以便消耗 FRR 业务流程。 接收位置路由通过自定义的 FRR 接收管道，则必须使用以下管道组件创建一条消息：  
  
- SWIFT 反汇编程序中的拆装阶段  
  
- 解码器阶段中的 SWIFT 的 FRR 解码器管道组件  
  
- SWIFT FRR CorrelationSet 冲突解决程序管道组件中的参与方解析阶段  
  
  接收端口处理的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True。 传输机制是后端应用程序决定了任何内容。  
  
  此接收端口的接收位置使用同一自定义接收管道，使用来自 SWIFT 的消息。 但是，管道执行不同的函数，为这两个接收位置。 在从后端应用程序的消息的接收位置，SWIFT FRR CorrelationSet 冲突解决程序管道组件初始化的相关标记。