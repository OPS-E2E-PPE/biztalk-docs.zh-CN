---
title: Recaller 对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ad2868892f0190cb9ebf8c63dfd6e3df200505
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394065"
---
# <a name="the-recaller-object"></a>Recaller 对象
业务流程管理解决方案提供的重试，在泛型方法，一些失败的对象方法调用。 该解决方案的作用通过这**Recaller**对象中**ExceptionHandler**业务流程。 **ExceptionHandler**业务流程使用的对象来重试对象方法调用。 有关详细信息，请参阅[ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)。  
  
## <a name="the-invoke-method"></a>调用方法  
 **Recaller**对象具有单个静态方法， **Invoke**。 因为它是静态的永远不需要创建的实例**Recaller**对象。 可以使用**Invoke**三种方式的方法： 若要构造一个对象，若要为对象，调用静态方法，或若要为对象调用非静态方法。  
  
> [!NOTE]
>  **Invoke**方法用作的包装**Type.InvokeMember**中的方法[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。  
  
### <a name="arguments-for-the-invoke-method"></a>自变量调用方法  
 下表描述了参数**Invoke**方法：  
  
|参数|类型|Description|  
|---------------|----------|-----------------|  
|*t*|**类型**|要对其调用该方法的对象的类型。|  
|obj|**Object**|要使用的对象的实例。|  
|*methodName*|**string**|要调用的方法的名称。|  
|*args*|**Array**|类型的数组**对象**包含方法的参数。|  
  
 若要为对象调用构造函数，请使用空字符串 ("") 或**null**有关*methodName*。  
  
 若要调用静态方法，请使用**null**有关*obj*。  
  
 若要调用非静态方法，提供的所有参数。  
  
> [!NOTE]
>  使用**null**作为类型参数的值*t*，导致**Invoke**引发**ArgumentNullException**异常。 自变量*t*不应为 null 因为**Invoke**方法使用**Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]方法。  
  
## <a name="calling-invoke"></a>调用 Invoke  
 在解决方案中，仅**ExceptionHandler**业务流程将使用**Recaller**对象。 **ExceptionHandler** ，反过来，由其他业务流程。 传递给的值**Invoke**方法来自其他业务流程。 例如，下面的代码中将出现**激活**中的业务流程**InitialException**表达式形状：  
  
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
  
 请注意，该代码如何创建数组使用**System.Array.CreateInstance** ，并使用**SetValue**方法来存储中使用的值。  
  
 表达式形状后，将调用 Activate 业务流程**ExceptionHandler**业务流程。 下面的代码演示如何在业务流程设计器转换调用形状：  
  
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
  
 在中**ExceptionHandler**业务流程中，以下代码显示在**调用原始代码**表达式形状：  
  
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
  
 请注意，尽管参数名称与 Activate 业务流程的调用中的匹配，参数匹配的顺序并不是按名称调用业务流程时。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)