---
title: ESB 失败协调异常路由机制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa05f44b-7fb2-48fd-886d-c6d179904e6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afda61ea19587b327f0fe773b150eeb8f88a4f7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295077"
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a>ESB 失败协调异常路由机制
ESB 失败业务流程异常路由机制提供以下功能：  
  
-   **创建捕获环境属性的错误消息。** **CreateFaultMessage**方法将生成错误消息包含的业务流程服务名称和服务实例 ID，当前活动的业务流程形状，业务流程是应用程序的名称部署，处理业务流程，服务器的名称以及异常日期和时间 （UTC 格式）。 它还会隐式添加当前**System.Exception**在当前的业务流程形状的异常处理程序中生成的对象。  
  
-   **将现有的业务流程消息添加到的错误消息**。 **AddMessage**方法保留业务流程消息和错误消息中的所有消息上下文属性的 XLANG 设置。  
  
-   **现有异常对象显式添加到的错误消息**。 **SetFaultMsgException**方法序列化该对象作为**System.Exception**并保留在错误消息。  
  
-   **从订阅服务器收到的错误消息中检索的类型的消息的枚举的集合**。 **GetMessages**方法从作为 XLANG 消息失败的业务流程中检索持久化的所有消息。 它将每个 XLANG 消息中返回每个保留消息的所有原始上下文的属性。  
  
-   **从订阅服务器收到的错误消息中检索强类型化的 XLANG orchestration 消息**。 **GetMessage**方法从作为 XLANG 消息的错误消息中检索特定类型的持久的消息。 它将返回所有原始消息的上下文属性持久化 XLANG 消息中。 它还支持检索**System.Exception**对象生成的失败的业务流程和检索持久化**System.Exception**从错误消息的对象。