---
title: 使用订单处理程序对象与后端系统进行通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 919013bbae989d588033437be54ce705179a44f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302995"
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a>使用订单处理程序对象与后端系统进行通信
有许多方法中的业务流程管理解决方案可以与旧的后端订单系统的宽带提供系统接收最终订单的系统通信。 该解决方案使用提供的.NET 远程处理功能在 Microsoft[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]与预配系统进行通信。  
  
 该解决方案使用使用接口来定义后端系统访问对象的常用的技术。 通过将接口置于单独的程序集在客户端程序集可以有权访问远程对象，而无需有权访问编译的程序集。  
  
 **IOrderHandler**接口定义与后端订单系统进行通信的方法。 该接口包括用于分析、 激活、 取消和完成订单的方法。 它还提供用于标识服务类型，需要取消订单时的方法。  
  
 **CableOrder1**， **CableOrder2**，并使用附属业务流程**OrderHandlerWrapper**对象，它实现**IOrderHandler**. **OrderHandlerWrapper**对象，进而调用的远程实例**OrderHandler**所提供对象**CableProvisioningSystemServer**可执行文件。 使用包装器对象满足业务要求使用.NET 远程处理进行通信的与后端订单系统时，同时，允许使用异常处理组件的重试功能。  
  
 因为其中一个必须能够在业务流程中引用每个对象进行序列化**OrderHandlerWrapper**还可序列化。 使用**OrderHandlerWrapper**隔离从业务流程的序列化代码。  
  
 如果您看一下代码，您将会**OrderHandlerWrapper**对象显式实现**ISerializable**接口。 该对象必须处理其自己的序列化，因为它使用非默认构造函数。  
  
 使用.NET 远程处理与后端系统进行通信是使用消息传送相比更高效。 另一方面，它将绑定业务流程更紧密地到后端系统不是纯消息传递解决方案可能。 使用.NET 远程处理还可防止该解决方案利用内置的 BizTalk Server 功能来重试请求。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [进程管理器逻辑](../core/process-manager-logic.md)