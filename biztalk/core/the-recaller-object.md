---
title: "Recaller 对象 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-recaller-object"></a>Recaller 对象
业务流程管理解决方案支持以常规方式重试某些失败的对象方法调用。 解决方案执行此通过**Recaller**对象在**ExceptionHandler**业务流程。 **ExceptionHandler**业务流程使用对象来重试对象方法调用。 有关详细信息，请参阅[ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)。  
  
## <a name="the-invoke-method"></a>Invoke 方法  
 **Recaller**对象具有单一的静态方法**Invoke**。 由于它是静态的永远不会需要创建的实例**Recaller**对象。 你可以使用**Invoke**三种方式的方法： 若要构造一个对象，若要为对象，调用静态方法，或若要为对象调用非静态方法。  
  
> [!NOTE]
>  **Invoke**方法用作包装器**为**中的方法[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。  
  
### <a name="arguments-for-the-invoke-method"></a>Invoke 方法的参数  
 下表介绍参数**Invoke**方法：  
  
|参数|类型|Description|  
|---------------|----------|-----------------|  
|*t*|**类型**|对其调用该方法的对象的类型。|  
|*obj*|**对象**|要使用的对象的实例。|  
|*方法名称*|**string**|要调用的方法的名称。|  
|*参数*|**数组**|类型的数组**对象**包含方法的自变量。|  
  
 若要为对象调用构造函数，使用空字符串 ("") 或**null**为*methodName*。  
  
 若要调用的静态方法，使用**null**为*obj*。  
  
 若要调用非静态方法，请提供所有参数。  
  
> [!NOTE]
>  使用**null**作为类型参数的值*t*，导致**Invoke**引发**ArgumentNullException**异常。 自变量*t*不应为 null 因为**Invoke**方法使用**为**[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]方法。  
  
## <a name="calling-invoke"></a>调用 Invoke  
 在解决方案中，仅**ExceptionHandler**业务流程使用**Recaller**对象。 **ExceptionHandler** ，反过来，可供其他业务流程。 值传递给**Invoke**方法来自这些其他业务流程。 例如，下面的代码将出现在**激活**中的业务流程**InitialException**表达式形状：  
  
```  
Ex = CodeEx;  
ObjectType = orderHandler.GetType();  
CalledObject = orderHandler;  
Reason = "Standard Activate Failed";  
MethodName = "Activate";  
ParameterArray = System.Array.CreateInstance(typeof(System.Object),  
                                              3 );  
ParameterArray.SetValue(ServiceType, 0);  
ParameterArray.SetValue(OrderMsg.CustNum, 1);  
ParameterArray.SetValue(OrderMsg.OrderNum, 2);  
ReturnValue = null; // no return value expected  
  
```  
  
 请注意该代码如何创建数组使用**System.Array.CreateInstance**并使用**SetValue**方法来存储用于它的值。  
  
 表达式形状后激活业务流程调用**ExceptionHandler**业务流程。 以下代码显示了业务流程设计器是如何转换调用形状的：  
  
```  
call Microsoft.Samples.  
    BizTalk.SouthridgeVideo.  
        OrderManager.ExceptionHandlerOrch  
            (  
                Reason,  
                Ex,  
                CalledObject,  
                MethodName,   
                ParameterArray,   
                OrderCorrelation,   
                OrderMsg,   
                out ReturnValue,   
                ObjectType  
            );  
  
```  
  
 在**ExceptionHandler**业务流程，下面的代码将出现在**调用原始代码**表达式形状：  
  
```  
ReturnValue =   
    Microsoft.Samples.  
        BizTalk.SouthridgeVideo.  
            Utilities.Recaller.  
                Invoke(  
                    ObjectType,  
                    CalledObject,  
                    MethodName,  
                    ParameterArray  
                );  
```  
  
 请注意，尽管参数名称与 Activate 业务流程的调用中的名称相匹配，但在调用业务流程时，是按顺序匹配参数，而不是按名称匹配参数。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)