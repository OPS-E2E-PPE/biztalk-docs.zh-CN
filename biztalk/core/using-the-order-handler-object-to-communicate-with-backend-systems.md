---
title: 使用顺序处理程序对象与后端系统进行通信 |Microsoft 文档
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
ms.openlocfilehash: 8d7621c4e5737def0e9fc0682de709ae57f98790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288061"
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a>使用顺序处理程序对象与后端系统进行通信
业务流程管理解决方案可以采用多种方式与原有后端订单系统进行通信，该系统是接收最终订单的宽带提供系统。 该解决方案使用 Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 中提供的 .NET 远程处理功能与提供系统进行通信。  
  
 该解决方案采用一项常用技术，即使用接口来定义后端系统的访问对象。 通过将接口放置在单独的程序集中，客户端程序集可以具有访问远程对象的权限，而无需具有访问编译的程序集的权限。  
  
 **IOrderHandler**接口定义的方法与后端订单系统进行通信。 该接口包括用于分析、激活、取消和完成订单的方法。 它还提供用于标识服务类型，需要取消订单时的方法的方法。  
  
 **CableOrder1**， **CableOrder2**，附属业务流程并用**OrderHandlerWrapper**实现对象**IOrderHandler**. **OrderHandlerWrapper**对象，反过来，将调用的远程实例**OrderHandler**提供对象**CableProvisioningSystemServer**可执行文件。 通过使用包装对象，可以满足使用 .NET 远程处理与后端订单系统进行通信的业务需求，同时还允许使用异常处理组件的重试功能。  
  
 因为其中一个必须能序列化中业务流程，引用每个对象**OrderHandlerWrapper**也可序列化。 使用**OrderHandlerWrapper**隔离业务流程中的序列化代码。  
  
 如果你查看代码，你将 se， **OrderHandlerWrapper**对象显式实现**ISerializable**接口。 该对象必须处理其自身的序列化，因为它使用非默认的构造函数。  
  
 与使用消息传送相比，使用 .NET 远程处理可以更有效地与后端系统进行通信。 另一方面，与单纯的消息传送解决方案相比，使用 .NET 远程处理可以将业务流程更紧密地绑定到后端系统。 通过使用 .NET 远程处理，还可以防止该解决方案利用内置的 BizTalk Server 功能来重试请求。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [过程管理器逻辑](../core/process-manager-logic.md)