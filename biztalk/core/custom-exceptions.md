---
title: 自定义异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfead2aadc237d27e0fb8ed28a776dd1e4f5c6f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240133"
---
# <a name="custom-exceptions"></a>自定义异常
对于存在不可恢复的错误的情况，业务流程管理解决方案将组合使用异常处理程序和自定义异常。  
  
## <a name="handling-exceptions"></a>处理异常  
 而不是使用**终止**在调用业务流程中的形状可以使用引发由根业务流程处理的异常的模式。 这样，就可以由对上下文了解最全面的业务流程来决定如何处理异常。 通过让从属业务流程引发自定义异常，使您能够将更具体的信息传递给根业务流程。  
  
 业务流程管理解决方案将使用此模式。 有四个根，或在解决方案中的使用未调用，业务流程： **OrderBroker**， **OrderManager**， **CableOrder1**，和**CableOrder2**. 三个根业务流程接收和处理自定义异常： **OrderManager**， **CableOrder1**，和**CableOrder2**。  
  
 请注意，某些根业务流程使用**终止**形状，**终止**形状显示的业务流程正常的终结点之前。 业务流程仍使用**终止**调整发生错误时，以便业务流程被记录为终止，而不是为已完成，但并显示错误消息。 这样，解决方案除了可以记录错误之外，还可以轻松跟踪失败的实例。  
  
 有关详细信息**终止**形状，请参阅[如何配置终止形状](../core/how-to-configure-the-terminate-shape.md)。 有关详细信息**ThrowException**形状，请参阅[如何配置引发异常形状](../core/how-to-configure-the-throw-exception-shape.md)。  
  
## <a name="the-custom-exceptions"></a>自定义异常  
 以下三个自定义异常都使用相同的模式。 使用不同类型是为了便于代码区分不同的异常。  
  
|异常|引发者（业务流程）|  
|---------------|---------------------------------|  
|**ActivateException**|**更改**|  
|**CableOrderException**|**激活**， **CableOrder1**|  
|**InterruptException**|**CableOrder1**， **CheckInterrupt**， **ErrorHandlerOrch**|  
  
 在中定义的所有异常的自定义**实用工具**程序集。 自定义异常全部都是 .NET 类。 从.NET 中的所有自定义异常类继承**ApplicationException**类又继承自**System.Exception**类。 由于异常有可能被冻结（序列化并存储在数据库中），因此异常必须实现反序列化构造函数。 反序列化构造函数是采用两个参数的构造函数： 一个 SerializationInfo 和 StreamingContext 对象。 在解除异常冻结过程中，将使用反序列化构造函数。 因为**ApplicationException**类已经实现反序列化构造函数，自定义异常的构造函数只是调用基 (ApplicationException) 反序列化构造函数。 例如， **InterruptException**包括以下构造函数：  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 有关自定义序列化的详细信息，请参阅 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 开发人员指南中的“自定义序列化”。  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a>嵌套异常处理程序和补偿模块  
 除了充当特殊异常之外，一些位置的自定义异常还充当排序标志。 在**更改**业务流程，取消操作必须回滚的两个地方。  
  
> [!NOTE]
>  你可能想要读取此节**更改**业务流程在 Visual Studio 中打开。  
  
 顶部的业务流程，如果调用**取消**业务流程失败， **CancelCompensation**块执行，并回滚**取消**事务。 如果一切运行正常，然后，业务流程将调用**激活**业务流程。  
  
 如果**激活**操作失败，**取消**事务必须也被回滚。 但是，异常处理程序调用**激活**不知道有关**取消**事务。 为了处理这种情况，提供了一个针对整个业务流程的异常处理程序。 此处理程序，因为它包含**取消**范围，就会了解有关**取消**事务。 处理程序捕获异常从引发**激活**作用域 ( **ActivateException**)，回滚**取消**事务，然后再次引发异常和以便调用的业务流程的**更改**业务流程可以执行任何其他处理。  
  
 请注意，此设计仅补偿**取消**如果**激活**失败。 如果**取消**失败并引发异常，**取消**永远不会发生的时间和不应进行补偿。  
  
 有关补偿基块的详细信息和**Compensate**形状，请参阅[如何配置补偿形状](../core/how-to-configure-the-compensate-shape.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)