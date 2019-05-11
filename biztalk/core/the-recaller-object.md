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
# <a name="the-recaller-object"></a><span data-ttu-id="de966-102">Recaller 对象</span><span class="sxs-lookup"><span data-stu-id="de966-102">The Recaller Object</span></span>
<span data-ttu-id="de966-103">业务流程管理解决方案提供的重试，在泛型方法，一些失败的对象方法调用。</span><span class="sxs-lookup"><span data-stu-id="de966-103">The business process management solution provides for retrying, in a generic way, some failed object method calls.</span></span> <span data-ttu-id="de966-104">该解决方案的作用通过这**Recaller**对象中**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="de966-104">The solution does this through the **Recaller** object in the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="de966-105">**ExceptionHandler**业务流程使用的对象来重试对象方法调用。</span><span class="sxs-lookup"><span data-stu-id="de966-105">The **ExceptionHandler** orchestration uses the object to retry object method calls.</span></span> <span data-ttu-id="de966-106">有关详细信息，请参阅[ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="de966-106">For more information, see [The ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md).</span></span>  
  
## <a name="the-invoke-method"></a><span data-ttu-id="de966-107">调用方法</span><span class="sxs-lookup"><span data-stu-id="de966-107">The Invoke Method</span></span>  
 <span data-ttu-id="de966-108">**Recaller**对象具有单个静态方法， **Invoke**。</span><span class="sxs-lookup"><span data-stu-id="de966-108">The **Recaller** object has a single, static method, **Invoke**.</span></span> <span data-ttu-id="de966-109">因为它是静态的永远不需要创建的实例**Recaller**对象。</span><span class="sxs-lookup"><span data-stu-id="de966-109">Because it is static, you never need to create an instance of the **Recaller** object.</span></span> <span data-ttu-id="de966-110">可以使用**Invoke**三种方式的方法： 若要构造一个对象，若要为对象，调用静态方法，或若要为对象调用非静态方法。</span><span class="sxs-lookup"><span data-stu-id="de966-110">You can use the **Invoke** method in three ways: to construct an object, to call a static method for an object, or to call a non-static method for an object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de966-111">**Invoke**方法用作的包装**Type.InvokeMember**中的方法[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。</span><span class="sxs-lookup"><span data-stu-id="de966-111">The **Invoke** method serves as a wrapper for the **Type.InvokeMember** method in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
### <a name="arguments-for-the-invoke-method"></a><span data-ttu-id="de966-112">自变量调用方法</span><span class="sxs-lookup"><span data-stu-id="de966-112">Arguments for the Invoke Method</span></span>  
 <span data-ttu-id="de966-113">下表描述了参数**Invoke**方法：</span><span class="sxs-lookup"><span data-stu-id="de966-113">The following table describes arguments for the **Invoke** method:</span></span>  
  
|<span data-ttu-id="de966-114">参数</span><span class="sxs-lookup"><span data-stu-id="de966-114">Parameter</span></span>|<span data-ttu-id="de966-115">类型</span><span class="sxs-lookup"><span data-stu-id="de966-115">Type</span></span>|<span data-ttu-id="de966-116">Description</span><span class="sxs-lookup"><span data-stu-id="de966-116">Description</span></span>|  
|---------------|----------|-----------------|  
|<span data-ttu-id="de966-117">*t*</span><span class="sxs-lookup"><span data-stu-id="de966-117">*t*</span></span>|<span data-ttu-id="de966-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="de966-118">**Type**</span></span>|<span data-ttu-id="de966-119">要对其调用该方法的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="de966-119">The type of the object on which to call the method.</span></span>|  
|<span data-ttu-id="de966-120">obj</span><span class="sxs-lookup"><span data-stu-id="de966-120">*obj*</span></span>|<span data-ttu-id="de966-121">**Object**</span><span class="sxs-lookup"><span data-stu-id="de966-121">**Object**</span></span>|<span data-ttu-id="de966-122">要使用的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="de966-122">The instance of the object to use.</span></span>|  
|<span data-ttu-id="de966-123">*methodName*</span><span class="sxs-lookup"><span data-stu-id="de966-123">*methodName*</span></span>|<span data-ttu-id="de966-124">**string**</span><span class="sxs-lookup"><span data-stu-id="de966-124">**string**</span></span>|<span data-ttu-id="de966-125">要调用的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="de966-125">The name of the method to invoke.</span></span>|  
|<span data-ttu-id="de966-126">*args*</span><span class="sxs-lookup"><span data-stu-id="de966-126">*args*</span></span>|<span data-ttu-id="de966-127">**Array**</span><span class="sxs-lookup"><span data-stu-id="de966-127">**Array**</span></span>|<span data-ttu-id="de966-128">类型的数组**对象**包含方法的参数。</span><span class="sxs-lookup"><span data-stu-id="de966-128">An array of type **Object** containing the method's arguments.</span></span>|  
  
 <span data-ttu-id="de966-129">若要为对象调用构造函数，请使用空字符串 ("") 或**null**有关*methodName*。</span><span class="sxs-lookup"><span data-stu-id="de966-129">To call the constructor for an object, use an empty string ("") or **null** for *methodName*.</span></span>  
  
 <span data-ttu-id="de966-130">若要调用静态方法，请使用**null**有关*obj*。</span><span class="sxs-lookup"><span data-stu-id="de966-130">To call a static method, use **null** for *obj*.</span></span>  
  
 <span data-ttu-id="de966-131">若要调用非静态方法，提供的所有参数。</span><span class="sxs-lookup"><span data-stu-id="de966-131">To call a non-static method, supply all of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de966-132">使用**null**作为类型参数的值*t*，导致**Invoke**引发**ArgumentNullException**异常。</span><span class="sxs-lookup"><span data-stu-id="de966-132">Using **null** as the value of the Type argument, *t*, causes **Invoke** to throw an **ArgumentNullException** exception.</span></span> <span data-ttu-id="de966-133">自变量*t*不应为 null 因为**Invoke**方法使用**Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]方法。</span><span class="sxs-lookup"><span data-stu-id="de966-133">The argument *t* should not be null because the **Invoke** method uses the **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] method.</span></span>  
  
## <a name="calling-invoke"></a><span data-ttu-id="de966-134">调用 Invoke</span><span class="sxs-lookup"><span data-stu-id="de966-134">Calling Invoke</span></span>  
 <span data-ttu-id="de966-135">在解决方案中，仅**ExceptionHandler**业务流程将使用**Recaller**对象。</span><span class="sxs-lookup"><span data-stu-id="de966-135">In the solution, only the **ExceptionHandler** orchestration uses the **Recaller** object.</span></span> <span data-ttu-id="de966-136">**ExceptionHandler** ，反过来，由其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="de966-136">The **ExceptionHandler** is, in turn, used by other orchestrations.</span></span> <span data-ttu-id="de966-137">传递给的值**Invoke**方法来自其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="de966-137">The values passed to the **Invoke** method come from these other orchestrations.</span></span> <span data-ttu-id="de966-138">例如，下面的代码中将出现**激活**中的业务流程**InitialException**表达式形状：</span><span class="sxs-lookup"><span data-stu-id="de966-138">For example, the following code appears in the **Activate** orchestration in the **InitialException** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="de966-139">请注意，该代码如何创建数组使用**System.Array.CreateInstance** ，并使用**SetValue**方法来存储中使用的值。</span><span class="sxs-lookup"><span data-stu-id="de966-139">Notice how the code creates an array using **System.Array.CreateInstance** and uses the **SetValue** method to store the values used in it.</span></span>  
  
 <span data-ttu-id="de966-140">表达式形状后，将调用 Activate 业务流程**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="de966-140">After the Expression shape, the Activate orchestration calls the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="de966-141">下面的代码演示如何在业务流程设计器转换调用形状：</span><span class="sxs-lookup"><span data-stu-id="de966-141">The following code shows how the orchestration designer translates the Call shape:</span></span>  
  
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
  
 <span data-ttu-id="de966-142">在中**ExceptionHandler**业务流程中，以下代码显示在**调用原始代码**表达式形状：</span><span class="sxs-lookup"><span data-stu-id="de966-142">In the **ExceptionHandler** orchestration, the following code appears in the **Call Original Code** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="de966-143">请注意，尽管参数名称与 Activate 业务流程的调用中的匹配，参数匹配的顺序并不是按名称调用业务流程时。</span><span class="sxs-lookup"><span data-stu-id="de966-143">Notice that, although the argument names match those in the Activate orchestration's call, arguments are matched by order and not by name when calling orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de966-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="de966-144">See Also</span></span>  
 <span data-ttu-id="de966-145">[业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="de966-145">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="de966-146">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="de966-146">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)