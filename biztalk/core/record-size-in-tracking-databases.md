---
title: 跟踪数据库中记录大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e19e5861a061294806c428d300d475ac2e21c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398047"
---
# <a name="record-size-in-tracking-databases"></a>跟踪数据库中的记录大小
为了帮助你规划 BizTalk 的硬件要求下, 表显示在跟踪数据库中的各种事件记录的预期的记录大小。  
  
|操作类型|大小|说明|  
|-----------------|----------|-----------|  
|部署服务|1864 + 符号化信息大小|符号化信息取决于业务流程的大小。 例如，接收一条消息，并使用 2 个形状发出一条消息的业务流程占据大约 4000 字节。|  
|已启动并已成功完成服务实例|通常为 252 字节。<br /><br /> 在极端情况下，可能达到 735 字节。||  
|启动并失败/遇到异常的服务实例|通常为 252 字节 + 错误信息。<br /><br /> 在极端情况下可能达到 735 字节 + 错误信息。|错误信息是 BizTalk 或用户组件返回的文本数据。 范围的范围是从 100 个字节到 2 KB。|  
|在业务流程中形状的开始/结束|每个 120 字节。||  
|消息输入/输出事件|最小 162 字节。<br /><br /> 第一次查看消息时它为 202 字节 + 消息属性 （如果跟踪）<br /><br /> 在极端情况下可能达到 2930 字节。|您可以放心平均值为 182 字节，如果没有任何消息属性跟踪。|  
|消息属性大小|如果 DTA 识别此跟踪属性的 40 到 288 字节。<br /><br /> 添加总计为 268 字节用于跟踪该属性第一次。||  
  
## <a name="see-also"></a>请参阅  
 [什么是消息跟踪？](../core/what-is-message-tracking.md)   
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)