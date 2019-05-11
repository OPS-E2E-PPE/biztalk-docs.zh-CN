---
title: ESB 异常 API 成员 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a095549-7e5d-4a7c-96d2-8fc6ca3efd63
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab2e1863ddbafe96a0ea053fe2075e92c361f65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399826"
---
# <a name="the-esb-exception-api-members"></a>ESB 异常 API 成员
**ESB。ExceptionHandling**下表中所述的程序集公开公共方法，可以创建错误消息还可以管理并进行处理，检索它们。  
  
|成员和用例|Description|  
|-------------------------|-----------------|  
|**CreateFaultMessage** [异常处理程序作用域]|**公共静态 XLANGMessage CreateFaultMessage()** 不带任何参数。 返回作为 ESB 错误消息的实例**XLANGMessage**使用当前的业务流程名称，业务流程实例 ID (GUID) 填充实例**System.Exception**实例，以及其他环境属性。 **注意：** 此应用程序编程接口 (API) 需要调用只能从 XLANG 中的异常块。|  
|**AddMessage** [异常处理程序作用域]|**（faultMessage，existingMessage） 的公共静态 void AddMessage**采用两个参数作为**XLANGMessage**实例; 第一种是新建的 ESB 错误消息，第二项是中的任何现有消息实例业务流程。 该方法将现有的消息实例和其消息上下文属性保留在错误消息并使其可用于检索使用**GetMessage**方法。 没有返回值。|  
|**SetException** [异常处理程序作用域]|**（faultMessage，异常） 的公共静态 void SetException**将作为参数作为到 ESB 的错误消息**XLANGMessage**实例和**异常**作为**对象**实例。 该方法仍然存在到现有的错误消息的异常，并使其可用于检索使用**GetException**方法。 没有返回值。|  
|**GetMessage** [Subscriber/processor]|**公共静态 XLANGMessage GetMessage(faultMessage, messageName)** 将作为参数 ESB 错误从作为订阅接收消息**XLANGMessage**实例和 (**字符串**) 前面添加到错误消息 （在原始业务流程形状的异常处理程序） 的消息的名称。 返回**XLANGMessage**实例消息名称相匹配，并包含所有原始的上下文属性，包括任何自定义升级的属性。|  
|**GetMessages** [Subscriber/processor]|**公共静态 MessageCollection GetMessages(faultMessage)** 作为从作为订阅接收到 ESB 的错误消息的单个参数采用**XLANGMessage**实例。 返回**MessageCollection**填充所有实例**XLANGMessage**实例之前添加到错误消息 （在原始业务流程形状的异常处理程序）。 每个**XLANGMessage**实例包含所有原始的上下文属性，包括任何自定义升级的属性。|  
|**GetException** [Subscriber/processor]|**公共静态 System.Exception GetException(faultMessage)** 将作为单个参数的错误消息来自与订阅**XLANGMessage**实例。 返回**System.Exception**之前添加到错误消息 （在原始业务流程形状的异常处理程序） 的对象。|  
|**FaultSeverity** [异常处理程序作用域和订阅服务器/处理器]|ESB 错误消息的公共读/写属性**XLANGMessage**类，该类公开错误消息的严重性。 中的值**FaultCodes**枚举：**信息**(0)，**警告**(1)，**错误**(2)**严重**(3) 或**关键**(4)。|  
|**MessageCollection** [Subscriber/processor]|返回的消息的集合**GetMessages**方法。 此类派生自**ArrayList**并实现要允许使用迭代的枚举数**MoveNext**方法。|