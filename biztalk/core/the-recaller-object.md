---
title: Recaller 对象 |Microsoft 文档
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
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279885"
---
# <a name="the-recaller-object"></a><span data-ttu-id="a319a-102">Recaller 对象</span><span class="sxs-lookup"><span data-stu-id="a319a-102">The Recaller Object</span></span>
<span data-ttu-id="a319a-103">业务流程管理解决方案支持以常规方式重试某些失败的对象方法调用。</span><span class="sxs-lookup"><span data-stu-id="a319a-103">The business process management solution provides for retrying, in a generic way, some failed object method calls.</span></span> <span data-ttu-id="a319a-104">解决方案执行此通过**Recaller**对象在**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="a319a-104">The solution does this through the **Recaller** object in the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="a319a-105">**ExceptionHandler**业务流程使用对象来重试对象方法调用。</span><span class="sxs-lookup"><span data-stu-id="a319a-105">The **ExceptionHandler** orchestration uses the object to retry object method calls.</span></span> <span data-ttu-id="a319a-106">有关详细信息，请参阅[ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="a319a-106">For more information, see [The ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md).</span></span>  
  
## <a name="the-invoke-method"></a><span data-ttu-id="a319a-107">Invoke 方法</span><span class="sxs-lookup"><span data-stu-id="a319a-107">The Invoke Method</span></span>  
 <span data-ttu-id="a319a-108">**Recaller**对象具有单一的静态方法**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="a319a-108">The **Recaller** object has a single, static method, **Invoke**.</span></span> <span data-ttu-id="a319a-109">由于它是静态的永远不会需要创建的实例**Recaller**对象。</span><span class="sxs-lookup"><span data-stu-id="a319a-109">Because it is static, you never need to create an instance of the **Recaller** object.</span></span> <span data-ttu-id="a319a-110">你可以使用**Invoke**三种方式的方法： 若要构造一个对象，若要为对象，调用静态方法，或若要为对象调用非静态方法。</span><span class="sxs-lookup"><span data-stu-id="a319a-110">You can use the **Invoke** method in three ways: to construct an object, to call a static method for an object, or to call a non-static method for an object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a319a-111">**Invoke**方法用作包装器**为**中的方法[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。</span><span class="sxs-lookup"><span data-stu-id="a319a-111">The **Invoke** method serves as a wrapper for the **Type.InvokeMember** method in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
### <a name="arguments-for-the-invoke-method"></a><span data-ttu-id="a319a-112">Invoke 方法的参数</span><span class="sxs-lookup"><span data-stu-id="a319a-112">Arguments for the Invoke Method</span></span>  
 <span data-ttu-id="a319a-113">下表介绍参数**Invoke**方法：</span><span class="sxs-lookup"><span data-stu-id="a319a-113">The following table describes arguments for the **Invoke** method:</span></span>  
  
|<span data-ttu-id="a319a-114">参数</span><span class="sxs-lookup"><span data-stu-id="a319a-114">Parameter</span></span>|<span data-ttu-id="a319a-115">类型</span><span class="sxs-lookup"><span data-stu-id="a319a-115">Type</span></span>|<span data-ttu-id="a319a-116">Description</span><span class="sxs-lookup"><span data-stu-id="a319a-116">Description</span></span>|  
|---------------|----------|-----------------|  
|<span data-ttu-id="a319a-117">*t*</span><span class="sxs-lookup"><span data-stu-id="a319a-117">*t*</span></span>|<span data-ttu-id="a319a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a319a-118">**Type**</span></span>|<span data-ttu-id="a319a-119">对其调用该方法的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="a319a-119">The type of the object on which to call the method.</span></span>|  
|<span data-ttu-id="a319a-120">*obj*</span><span class="sxs-lookup"><span data-stu-id="a319a-120">*obj*</span></span>|<span data-ttu-id="a319a-121">**对象**</span><span class="sxs-lookup"><span data-stu-id="a319a-121">**Object**</span></span>|<span data-ttu-id="a319a-122">要使用的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="a319a-122">The instance of the object to use.</span></span>|  
|<span data-ttu-id="a319a-123">*方法名称*</span><span class="sxs-lookup"><span data-stu-id="a319a-123">*methodName*</span></span>|<span data-ttu-id="a319a-124">**string**</span><span class="sxs-lookup"><span data-stu-id="a319a-124">**string**</span></span>|<span data-ttu-id="a319a-125">要调用的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="a319a-125">The name of the method to invoke.</span></span>|  
|<span data-ttu-id="a319a-126">*参数*</span><span class="sxs-lookup"><span data-stu-id="a319a-126">*args*</span></span>|<span data-ttu-id="a319a-127">**数组**</span><span class="sxs-lookup"><span data-stu-id="a319a-127">**Array**</span></span>|<span data-ttu-id="a319a-128">类型的数组**对象**包含方法的自变量。</span><span class="sxs-lookup"><span data-stu-id="a319a-128">An array of type **Object** containing the method's arguments.</span></span>|  
  
 <span data-ttu-id="a319a-129">若要为对象调用构造函数，使用空字符串 ("") 或**null**为*methodName*。</span><span class="sxs-lookup"><span data-stu-id="a319a-129">To call the constructor for an object, use an empty string ("") or **null** for *methodName*.</span></span>  
  
 <span data-ttu-id="a319a-130">若要调用的静态方法，使用**null**为*obj*。</span><span class="sxs-lookup"><span data-stu-id="a319a-130">To call a static method, use **null** for *obj*.</span></span>  
  
 <span data-ttu-id="a319a-131">若要调用非静态方法，请提供所有参数。</span><span class="sxs-lookup"><span data-stu-id="a319a-131">To call a non-static method, supply all of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a319a-132">使用**null**作为类型参数的值*t*，导致**Invoke**引发**ArgumentNullException**异常。</span><span class="sxs-lookup"><span data-stu-id="a319a-132">Using **null** as the value of the Type argument, *t*, causes **Invoke** to throw an **ArgumentNullException** exception.</span></span> <span data-ttu-id="a319a-133">自变量*t*不应为 null 因为**Invoke**方法使用**为**[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]方法。</span><span class="sxs-lookup"><span data-stu-id="a319a-133">The argument *t* should not be null because the **Invoke** method uses the **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] method.</span></span>  
  
## <a name="calling-invoke"></a><span data-ttu-id="a319a-134">调用 Invoke</span><span class="sxs-lookup"><span data-stu-id="a319a-134">Calling Invoke</span></span>  
 <span data-ttu-id="a319a-135">在解决方案中，仅**ExceptionHandler**业务流程使用**Recaller**对象。</span><span class="sxs-lookup"><span data-stu-id="a319a-135">In the solution, only the **ExceptionHandler** orchestration uses the **Recaller** object.</span></span> <span data-ttu-id="a319a-136">**ExceptionHandler** ，反过来，可供其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="a319a-136">The **ExceptionHandler** is, in turn, used by other orchestrations.</span></span> <span data-ttu-id="a319a-137">值传递给**Invoke**方法来自这些其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="a319a-137">The values passed to the **Invoke** method come from these other orchestrations.</span></span> <span data-ttu-id="a319a-138">例如，下面的代码将出现在**激活**中的业务流程**InitialException**表达式形状：</span><span class="sxs-lookup"><span data-stu-id="a319a-138">For example, the following code appears in the **Activate** orchestration in the **InitialException** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="a319a-139">请注意该代码如何创建数组使用**System.Array.CreateInstance**并使用**SetValue**方法来存储用于它的值。</span><span class="sxs-lookup"><span data-stu-id="a319a-139">Notice how the code creates an array using **System.Array.CreateInstance** and uses the **SetValue** method to store the values used in it.</span></span>  
  
 <span data-ttu-id="a319a-140">表达式形状后激活业务流程调用**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="a319a-140">After the Expression shape, the Activate orchestration calls the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="a319a-141">以下代码显示了业务流程设计器是如何转换调用形状的：</span><span class="sxs-lookup"><span data-stu-id="a319a-141">The following code shows how the orchestration designer translates the Call shape:</span></span>  
  
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
  
 <span data-ttu-id="a319a-142">在**ExceptionHandler**业务流程，下面的代码将出现在**调用原始代码**表达式形状：</span><span class="sxs-lookup"><span data-stu-id="a319a-142">In the **ExceptionHandler** orchestration, the following code appears in the **Call Original Code** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="a319a-143">请注意，尽管参数名称与 Activate 业务流程的调用中的名称相匹配，但在调用业务流程时，是按顺序匹配参数，而不是按名称匹配参数。</span><span class="sxs-lookup"><span data-stu-id="a319a-143">Notice that, although the argument names match those in the Activate orchestration's call, arguments are matched by order and not by name when calling orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a319a-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a319a-144">See Also</span></span>  
 <span data-ttu-id="a319a-145">[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="a319a-145">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="a319a-146">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="a319a-146">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)