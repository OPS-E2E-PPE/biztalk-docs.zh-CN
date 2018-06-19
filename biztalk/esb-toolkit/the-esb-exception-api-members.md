---
title: ESB 异常 API 成员 |Microsoft 文档
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
ms.openlocfilehash: 5e267f8533948fc46c4604ebfffb6d22367a321e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295581"
---
# <a name="the-esb-exception-api-members"></a>ESB 异常 API 成员
**ESB。ExceptionHandling**程序集公开公共方法，可以创建错误消息还可以管理并检索它们以进行处理下, 表中所述。  
  
|成员和使用情况|Description|  
|-------------------------|-----------------|  
|**CreateFaultMessage** [异常处理程序作用域]|**公共静态 XLANGMessage CreateFaultMessage()** 不带任何参数。 返回作为 ESB 错误消息的一个实例**XLANGMessage**实例的当前的业务流程名称，业务流程实例 ID (GUID) 填充**System.Exception**实例，以及其他环境属性。 **注意：** 需要只能从 XLANG 内的异常块调用此应用程序编程接口 (API)。|  
|**AddMessage** [异常处理程序作用域]|**（faultMessage，existingMessage） 的公共静态 void AddMessage**使用作为参数两个**XLANGMessage**实例; 第一种是新创建 ESB 错误消息，且第二个中的任何现有消息实例业务流程。 方法仍然在现有的消息实例和其消息上下文属性存在到错误消息并使其可用于检索使用**GetMessage**方法。 不返回值。|  
|**SetException** [异常处理程序作用域]|**（faultMessage，异常） 的公共静态 void SetException**使用作为参数作为 ESB 错误消息**XLANGMessage**实例和**异常**作为**对象**实例。 方法仍然存在到现有的错误消息的异常，并使其可用于检索使用**GetException**方法。 不返回值。|  
|**GetMessage** [订阅服务器/处理器]|**公共静态 XLANGMessage GetMessage(faultMessage, messageName)** 将作为参数 ESB 错误从作为订阅接收消息**XLANGMessage**实例和 (**字符串**) 之前添加到 （原始的业务流程形状的异常处理程序） 中的错误消息的消息的名称。 返回**XLANGMessage**实例的消息名称相匹配，并且包含所有原始的上下文属性，包括任何自定义的提升的属性。|  
|**GetMessages** [订阅服务器/处理器]|**公共静态 MessageCollection GetMessages(faultMessage)** 采用单个参数从作为订阅接收 ESB 错误消息作为**XLANGMessage**实例。 返回**MessageCollection**实例填充所有**XLANGMessage**之前添加到 （原始的业务流程形状的异常处理程序） 中的错误消息的实例。 每个**XLANGMessage**实例都包含所有原始的上下文属性，包括任何自定义的提升的属性。|  
|**GetException** [订阅服务器/处理器]|**公共静态 System.Exception GetException(faultMessage)** 采用单个参数从订阅视为接收错误消息作为**XLANGMessage**实例。 返回**System.Exception**之前添加到的错误消息 （源的业务流程形状的异常处理程序） 中的对象。|  
|**FaultSeverity** [异常处理程序作用域和订阅服务器/处理器]|ESB 错误消息的公共读/写属性**XLANGMessage**公开错误消息的严重性的类。 取值范围为**FaultCodes**枚举：**信息**(0)，**警告**(1)，**错误**(2)**严重**(3)、 或**关键**(4)。|  
|**MessageCollection** [订阅服务器/处理器]|返回的消息的集合**GetMessages**方法。 此类派生自**ArrayList**和实现枚举器以允许迭代使用**MoveNext**方法。|