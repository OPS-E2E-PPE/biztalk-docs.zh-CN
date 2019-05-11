---
title: 业务流程管理解决方案的消息引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, message reference
ms.assetid: 0595817e-da5d-426a-9ee1-0c5d04334de6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a96b1602aabfd7c56c576c545089ae53c1dc4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325044"
---
# <a name="message-reference-for-the-business-process-management-solution"></a>业务流程管理解决方案的消息引用
本部分列出的消息和使用的解决方案中每个业务流程的消息类型。  
  
 在表中， \<*前缀*\>将替代 Microsoft.Samples.BizTalk.SouthridgeVideo，以使表更易于读取。  
  
> [!NOTE]
>  消息类型的**System.Xml.XmlDocument**指示由.NET 类而不是架构定义的消息类型。  
  
 业务流程、 消息和类型如下所示。  
  
|业务流程|消息|消息类型|  
|-------------------|-------------|------------------|  
|Activate.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Activate.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|Analyze.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|Analyze.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|TerminatedMsg|\<SolutionPrefix\>.SchemaClasses.Terminated|  
|CableOrder1.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|CompletionMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|CableOrder1.odx|AckMsg|\<SolutionPrefix\>.SchemaClasses.OrderAck|  
|CableOrder1.odx|InterruptMsg|\<SolutionPrefix\>.SchemaClasses.Interrupt|  
|CableOrder2.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder2.odx|TerminatedMsg|\<SolutionPrefix\>.SchemaClasses.Terminated|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|CableOrder2.odx|CompleteOrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|CableOrder2.odx|AckMsg|\<SolutionPrefix\>.SchemaClasses.OrderAck|  
|CableOrder2.odx|CompletionMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Cancel.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Change.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|CheckInterrupt.odx|InterruptMsg|\<SolutionPrefix\>.SchemaClasses.Interrupt|  
|Complete.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|Complete.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|InterruptMsg|\<SolutionPrefix\>.SchemaClasses.Interrupt|  
|ErrorHandler.odx|OrderStatusMsg|\<SolutionPrefix\>.SchemaClasses.OrderStatus|  
|ErrorHandler.odx|ResponseMsg|\<SolutionPrefix\>.SchemaClasses.OrderStatus|  
|ErrorHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|ReturnedMsg|System.Xml.XmlDocument|  
|ExceptionHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|Interrupter.odx|InterruptMsg|\<SolutionPrefix\>.SchemaClasses.Interrupt|  
|OrderBroker.odx|CSRConfMsg|\<SolutionPrefix\>.OrderBrokerSchemas.CSR_OrderRequestSchema|  
|OrderBroker.odx|CSROrderMsg|\<SolutionPrefix\>.OrderBrokerSchemas.CSR_OrderRequestSchema|  
|OrderBroker.odx|HistoryInsertMsg|\<SolutionPrefix\>.OrderBrokerSchemas.SQLHistoryInsertSchema.HistoryInsert|  
|OrderBroker.odx|ServicingMsg|\<SolutionPrefix\>.OrderBrokerSchemas.Servicing_OrderRequestSchema|  
|OrderBroker.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
|OrderBroker.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderBroker.OrderMgrMPMsg|  
|OrderManager.odx|CompletionMsg|\<SolutionPrefix\>.SchemaClasses.OrderStatus|  
|OrderManager.odx|NewOrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderAck|\<SolutionPrefix\>.SchemaClasses.OrderAck|  
|OrderManager.odx|TerminatedMsg|\<SolutionPrefix\>.SchemaClasses.Terminated|  
|OrderManager.odx|ErrorMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|Validate.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|OrderMsg|\<SolutionPrefix\>.Schemas.OrderSchema|  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案参考](../core/business-process-management-solution-reference.md)   
 [主要消息和字段](../core/key-messages-and-fields.md)   
 [通过进程管理器的订单流](../core/order-flow-through-the-process-manager.md)