---
title: 自定义异常 |Microsoft Docs
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
ms.openlocfilehash: 5118de4dc75d65f328838d9e7cecf4d51875db1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353398"
---
# <a name="custom-exceptions"></a>自定义异常
情况下业务流程管理解决方案对于不可恢复的错误情况，使用异常处理程序和自定义异常的组合。  
  
## <a name="handling-exceptions"></a>处理异常  
 而不是使用**Terminate**中调用的业务流程形状可以使用引发由根业务流程处理的异常的模式。 这允许上下文来决定如何处理异常的业务流程与尽可能最广泛的知识。 具有从属业务流程引发自定义异常，可更具体的信息传递给根业务流程。  
  
 业务流程管理解决方案采用这种模式。 有四个根，或在解决方案中的使用未调用，业务流程：**OrderBroker**， **OrderManager**， **CableOrder1**，并且**CableOrder2**。 三个根业务流程接收和处理自定义异常：**OrderManager**， **CableOrder1**，和**CableOrder2**。  
  
 请注意，某些根业务流程使用**Terminate**形状和该**终止**形状就显示业务流程的正常的终结点之前。 该业务流程仍使用**Terminate**形状发生错误时，以便该业务流程记录为已终止，而不是已完成但有一条错误消息。 这样，解决方案后，以跟踪轻松除了将错误记录的失败的实例。  
  
 有关详细信息**Terminate**形状中，请参阅[如何配置终止形状](../core/how-to-configure-the-terminate-shape.md)。 有关详细信息**ThrowException**形状中，请参阅[如何配置引发异常形状](../core/how-to-configure-the-throw-exception-shape.md)。  
  
## <a name="the-custom-exceptions"></a>自定义异常  
 以下三个自定义异常的每个遵循相同的模式。 具有不同类型允许区分不同的异常代码。  
  
|异常|引发者 （业务流程）|  
|---------------|---------------------------------|  
|**ActivateException**|**更改**|  
|**CableOrderException**|**Activate**, **CableOrder1**|  
|**InterruptException**|**CableOrder1**， **CheckInterrupt**， **ErrorHandlerOrch**|  
  
 中定义的所有自定义异常**实用程序**程序集。 自定义例外情况是所有.NET 类。 所有自定义异常类继承自.NET **ApplicationException**类，该类又继承自**System.Exception**类。 因为可能导致此异常可能被冻结 （序列化和存储在数据库中），因此异常必须实现反序列化构造函数。 反序列化构造函数是采用两个参数的构造函数： 一个 SerializationInfo 对象和一个 StreamingContext 对象。 在解除异常冻结期间，将使用反序列化构造函数。 因为**ApplicationException**类已经实现反序列化构造函数、 自定义异常的构造函数只是调用基本 (ApplicationException) 反序列化构造函数。 例如， **InterruptException**包括以下构造函数：  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 详细了解自定义序列化的详细信息，请参阅中的自定义序列化[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发人员指南。  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a>嵌套的异常处理程序和补偿模块  
 除了充当特殊异常，多个位置中的自定义异常还充当排序标志。 在中**更改**业务流程中，有两个位置的取消操作必须回滚。  
  
> [!NOTE]
>  你可能想要阅读此部分**更改**Visual Studio 中打开业务流程。  
  
 顶部的业务流程中，如果在调用**取消**业务流程失败**CancelCompensation**块执行和回滚**取消**事务。 如果一切正常，则该业务流程将调用**激活**业务流程。  
  
 如果**激活**操作将失败，**取消**事务必须还被回滚。 但是，在调用的异常处理程序**激活**的相关信息一无所知**取消**事务。 为了处理此问题，提供了整个业务流程的异常处理程序。 此处理程序，因为它包含**取消**范围，知道**取消**事务。 处理程序捕获引发的异常**激活**作用域 ( **ActivateException**)，将回滚**取消**事务，然后再次引发异常和以便业务流程调用的函数**更改**业务流程可以执行任何其他处理。  
  
 请注意，此设计只会补偿**取消**如果**激活**失败。 如果**取消**失败并引发异常，**取消**永远不会成功，不应进行补偿。  
  
 有关补偿模块详细信息和**Compensate**形状中，请参阅[如何配置补偿形状](../core/how-to-configure-the-compensate-shape.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)