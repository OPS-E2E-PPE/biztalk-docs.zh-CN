---
title: 在跟踪数据库中记录大小 |Microsoft 文档
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
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="record-size-in-tracking-databases"></a>跟踪数据库中的记录大小
为了帮助您计划 BizTalk 的硬件要求，下表显示了跟踪数据库中不同事件记录的预期记录大小：  
  
|操作类型|Size|说明|  
|-----------------|----------|-----------|  
|部署服务|1864 + 符号化信息大小|符号化信息取决于业务流程的大小。 例如，接收一个消息并发送出一个包含 2 个形状的消息的业务流程占据大约 4000 字节。|  
|已启动并已成功完成的服务实例|通常为 252 字节。<br /><br /> 在极端情况下，可能达到 735 字节。||  
|已启动但失败/遇到异常的服务实例|通常为 252 字节 + 错误信息。<br /><br /> 在极端情况下，可能达到 735 字节 + 错误信息。|错误信息是 BizTalk 或用户组件返回的文本数据。 大小从 100 字节到 2 KB 不等。|  
|业务流程中形状的开始/结束|每个 120 字节。||  
|消息输入/输出事件|最小 162 字节。<br /><br /> 首次查看消息时，此记录大小为 202 字节 + 消息属性（如果跟踪）<br /><br /> 在极端情况下，可能达到 2930 字节。|如果不存在任何消息属性跟踪，则可以安全地假定平均大小为 182 字节。|  
|消息属性大小|如果 DTA 识别此跟踪属性的 40 到 288 个字节。<br /><br /> 对于首次跟踪属性，则此记录大小总计为 268 字节。||  
  
## <a name="see-also"></a>另请参阅  
 [什么是邮件跟踪？](../core/what-is-message-tracking.md)   
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)