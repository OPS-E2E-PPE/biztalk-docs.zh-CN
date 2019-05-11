---
title: BizTalk 框架组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 139d4bedbe8f42e9e7c97b2647b27d712697e8f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358073"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a>BizTalk 框架组装器管道组件
BizTalk 框架是一种方法进行完全的一次性传送即可使用线上传输协议，例如 HTTP 或 SMTP 送达。 此框架自 1998 年起，已存在，并且可以为 Web 服务，特别是 WSReliable 基础的视为挂起标准计划的前提。 通常情况下，这一问题完全保证的传递的数据后的技术，如消息队列 (也称为 MSMQ) 的域。 但是，此类技术通常需要在数据流中，两个终结点的常见软件，并且还不到地址使用的开放传输协议执行基于公共网络，例如，通过使用在企业边界之间流动的数据Internet。  
  
 毫无疑问，BizTalk 框架将实施某些在早期尝试解决这一问题中的相同机制保证的一次性传送即可送达数据。 其他解决方案的问题的一个典型示例是电子数据交换 (EDI)，其中 ANSI X12 控制编号和标准 997 功能确认文档形成保证的基础数据只接收一次，而且发件人是收到通知的接收端上的任何问题。  
  
 BizTalk 框架假定，但是不同贸易数据的系统，它们都了解 BizTalk 框架协议的以下要求：  
  
- 换行传输使用的可预测信封格式。  
  
- 标记具有全局唯一标识符的每个出站传输。  
  
- 始终返回到发件人的收据，其中包含的全局唯一标识符，即使对于数据已确认接收、 已确认和处理。  
  
- 一些方法，依据发件人可以重复的传输直到接收来自接收方，或持续的时间段超过该传输将不再有效。  
  
  BizTalk 框架组装器管道组件负责在传输和重新发送的情况中分配的时间段内回执未送达之前序列化 BizTalk 框架信封和消息内容。 它是还负责接收和处理回执并删除消息实例。 （已发送消息的消息实例的副本保留在 MessageBox 数据库中直到 BizTalk 收到来自目标的确认回执。 收到的确认回执后，消息实例会删除由消息引擎。）  
  
## <a name="see-also"></a>请参阅  
 [如何配置 BizTalk 框架组装器管道组件](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)   
 [管道组件](../core/pipeline-components.md)