---
title: ESB 故障业务流程异常路由机制 |Microsoft Docs
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
ms.openlocfilehash: 1da528a8af1b232f014a349afae292a7c0e319d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399818"
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a>ESB 故障业务流程异常路由机制
ESB 失败，业务流程异常路由机制提供了以下功能：  
  
-   **创建捕获环境属性的错误消息。** **CreateFaultMessage**方法将生成错误消息包含的业务流程服务名称和服务实例 ID，当前激活业务流程形状中，该业务流程将应用程序的名称部署，处理业务流程中，服务器的名称以及异常日期和时间 （UTC 格式）。 它还将隐式添加当前**System.Exception**在当前业务流程形状的异常处理程序中生成的对象。  
  
-   **将现有业务流程消息添加到的错误消息**。 **AddMessage**方法保留的业务流程消息和错误消息中的所有消息上下文属性的 XLANG 设置。  
  
-   **显式将一个现有的异常对象添加到的错误消息**。 **SetFaultMsgException**方法以将对象序列化为**System.Exception**并保留在错误消息中。  
  
-   **从订阅服务器收到的错误消息中检索枚举的集合的类型无消息**。 **GetMessages**方法从失败的业务流程作为 XLANG 消息中检索所有持久的消息。 它在每个 XLANG 消息中返回每个持久化消息的所有原始上下文的属性。  
  
-   **从订阅服务器收到的错误消息中检索强类型化的 XLANG 业务流程消息**。 **GetMessage**方法从错误消息作为 XLANG 消息中检索特定类型的持久的消息。 它返回原始上下文的所有属性持久化消息 XLANG 消息中。 它还支持检索**System.Exception**对象生成的失败的业务流程和检索的持久化**System.Exception**错误消息中的对象。