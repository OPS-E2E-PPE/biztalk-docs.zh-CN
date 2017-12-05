---
title: "Ops 适配器实现详细信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3172759541f46ec6c3c8c2b3e684086747036f37
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="ops-adapter-implementation-details"></a>Ops 适配器实现详细信息
你可能会发现有助于了解 Ops 适配器的以下方面，修改适配器时或以编程方式配置。  
  
> [!NOTE]
>  Ops 适配器使用适配器框架进行构建。 有关生成的框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="batch-processing"></a>批处理  
 适配器一次处理一条消息，以便分别处理每条消息，并一次只能有一个按顺序完成回滚操作。 尽管适配器一次处理一条消息，它都使用批处理的一个批次大小。 这样会更容易，若要修改的适配器来处理批中的消息。  
  
## <a name="transaction-handling"></a>事务处理  
 适配器使用由 Microsoft 提供的事务功能[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**设施。 适配器创建一个新**CommittableTransaction**并使用它与**TransactionScope**。 适配器调用**初始化**和**执行**此事务的上下文中的方法。 调用程序集中的代码可以参与事务使用**Transaction.Current**静态方法，用于获取事务上下文。 示例错误处理程序不会进行此工具的使用。 有关详细信息**System.Transactions**，请参阅.NET Framework 类库版本中的"System.Transactions Namespace"。  
  
## <a name="handling-data-other-than-error-reports"></a>处理错误报告之外的数据  
 在解决方案中，适配器处理从新的错误报告功能的错误报告消息。 但是，因为**执行**方法采用一个字节数组作为其唯一的自变量，无需进行任何专门限制可传递给内容**执行**方法。  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a>当以编程方式创建端口使用适配器  
 从代码中创建端口时，你可以指定适配器。 下表显示了自定义属性名称和它们对应的显示名称。  
  
|发送自定义属性名称|显示名称|  
|-------------------------------|------------------|  
|**DotNetAssemblyStrongName**|**DotNetAssemblyStrongName**|  
|**DotNetClassName**|**DotNetClassName**|  
|**InitializationData**|**InitializationData**|  
|**TransportLocationUri**|不适用。|  
  
 所有属性都是字符串值。 构造从程序集名称和类名称 TransportLocationUri 属性的值。 URI 包含值 OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\>其中将占位符替换为相应的自定义属性的值。  
  
 有关创建端口在代码中的信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)