---
title: Ops 适配器实现详细信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e890b7413726993dd28aa21dec0f13e92f90f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323430"
---
# <a name="ops-adapter-implementation-details"></a>Ops 适配器实现详细信息
你可能会发现可以修改适配器时了解 Ops 适配器的以下方面或以编程方式对其进行配置。  
  
> [!NOTE]
>  Ops 适配器是使用适配器框架生成的。 有关构建与框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="batch-processing"></a>批处理  
 适配器一次处理一条消息，以便分别处理每条消息和一次只有一个订单执行回滚操作。 尽管适配器一次处理一条消息，但它是通过使用批处理大小为一个批处理。 这使得更轻松地修改适配器处理批中的消息。  
  
## <a name="transaction-handling"></a>事务处理  
 适配器使用由 Microsoft 提供的交易设备[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**设施。 适配器创建一个新**CommittableTransaction**并将其与**TransactionScope**。 适配器调用**初始化**并**Execute**此事务的上下文中的方法。 被调用的程序集中的代码可以参与该事务通过**Transaction.Current**静态方法，用于获取事务上下文。 示例错误处理程序不会使此工具的使用。 有关详细信息**System.Transactions**，在.NET Framework 类库版本中看到"System.Transactions Namespace"。  
  
## <a name="handling-data-other-than-error-reports"></a>处理数据的非错误报告  
 在解决方案中，适配器处理错误报告消息从新的错误报告功能。 但是，由于**Execute**方法将获取作为其唯一参数的字节数组，则不执行任何专门限制什么可以传递给**Execute**方法。  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a>以编程方式创建端口时使用的适配器  
 从代码创建端口时，可以指定适配器。 下表显示了自定义属性名称并与它们对应的显示名称。  
  
|发送自定义属性名称|显示名称|  
|-------------------------------|------------------|  
|**DotNetAssemblyStrongName**|**DotNetAssemblyStrongName**|  
|**DotNetClassName**|**DotNetClassName**|  
|**InitializationData**|**InitializationData**|  
|**TransportLocationUri**|不适用。|  
  
 所有属性都是字符串值。 您构造从程序集名称和类名 TransportLocationUri 属性的值。 URI 具有值 OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\>其中占位符将替换为相应的自定义属性的值。  
  
 有关从代码创建端口的信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。  
  
## <a name="see-also"></a>请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)