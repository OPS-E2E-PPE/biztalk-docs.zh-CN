---
title: "开发自定义的累积 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f69ae870269948358f117b07f37d481faced160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-custom-cumulative-functoid"></a><span data-ttu-id="0df38-102">开发自定义的累积 Functoid</span><span class="sxs-lookup"><span data-stu-id="0df38-102">Developing a Custom Cumulative Functoid</span></span>
<span data-ttu-id="0df38-103">使用自定义累计 functoid 可以对在一个实例消息中多次出现的值执行累计操作。</span><span class="sxs-lookup"><span data-stu-id="0df38-103">Use a custom cumulative functoid to perform accumulation operations for values that occur multiple times within an instance message.</span></span>  
  
 <span data-ttu-id="0df38-104">在开发累计 functoid 时，必须实现三个函数。</span><span class="sxs-lookup"><span data-stu-id="0df38-104">You must implement three functions when developing a cumulative functoid.</span></span> <span data-ttu-id="0df38-105">这三个函数对应于映射执行累计所需的初始化、累计和获取操作。</span><span class="sxs-lookup"><span data-stu-id="0df38-105">The three functions correspond to the initialize, cumulate, and get actions that the map needs to perform the accumulation.</span></span> <span data-ttu-id="0df38-106">在讨论这些函数之前，有必要讨论一下线程安全。</span><span class="sxs-lookup"><span data-stu-id="0df38-106">Before discussing these functions it is important to discuss thread safety.</span></span>  
  
## <a name="writing-a-thread-safe-functoid"></a><span data-ttu-id="0df38-107">编写线程安全 Functoid</span><span class="sxs-lookup"><span data-stu-id="0df38-107">Writing a Thread-Safe Functoid</span></span>  
 <span data-ttu-id="0df38-108">functoid 代码必须为线程安全代码，因为在任务繁忙时，可以同时运行多个映射实例。</span><span class="sxs-lookup"><span data-stu-id="0df38-108">The functoid code must be thread-safe because under stress conditions multiple instances of a map may be running concurrently.</span></span> <span data-ttu-id="0df38-109">应记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="0df38-109">Some of the points to remember include:</span></span>  
  
-   <span data-ttu-id="0df38-110">静态状态必须是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="0df38-110">Static state must be thread-safe.</span></span>  
  
-   <span data-ttu-id="0df38-111">实例状态并非始终需要是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="0df38-111">Instance state does not always need to be thread-safe.</span></span>  
  
-   <span data-ttu-id="0df38-112">在设计时应考虑在任务繁忙时的运行情况。</span><span class="sxs-lookup"><span data-stu-id="0df38-112">Design with consideration for running under high-stress conditions.</span></span> <span data-ttu-id="0df38-113">应尽可能避免进行锁定。</span><span class="sxs-lookup"><span data-stu-id="0df38-113">Avoid taking locks whenever possible.</span></span>  
  
-   <span data-ttu-id="0df38-114">应尽可能避免进行同步。</span><span class="sxs-lookup"><span data-stu-id="0df38-114">Avoid the need for synchronization if possible.</span></span>  
  
 <span data-ttu-id="0df38-115">BizTalk Server 提供了一种简单机制，可降低编写线程安全累计 functoid 的复杂度。</span><span class="sxs-lookup"><span data-stu-id="0df38-115">BizTalk Server provides a simple mechanism to reduce the complexity of writing a thread-safe cumulative functoid.</span></span> <span data-ttu-id="0df38-116">所有这三个函数的第一个参数都相同，均为整数索引值。</span><span class="sxs-lookup"><span data-stu-id="0df38-116">All three functions have the same first parameter, an integer index value.</span></span> <span data-ttu-id="0df38-117">BizTalk Server 在调用您的初始化函数时会为索引值分配一个唯一的编号。</span><span class="sxs-lookup"><span data-stu-id="0df38-117">BizTalk Server assigns a unique number to the index value when it calls your initialization function.</span></span> <span data-ttu-id="0df38-118">您可以使用此值作为存放累计值的数组的索引，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="0df38-118">You can use this value as an index into an array that holds accumulating values, as shown in the following code:</span></span>  
  
```  
private HashTable cumulativeArray = new HashTable();  
…  
// Initialization function  
public string InitCumulativeMultiply(int index)  
{  
    cumulativeArray[index] = 1.0;  
    return string.Empty;  
}  
```  
  
 <span data-ttu-id="0df38-119">此示例使用 HashTable 而不是 ArrayList。</span><span class="sxs-lookup"><span data-stu-id="0df38-119">This example uses a HashTable instead of an ArrayList.</span></span> <span data-ttu-id="0df38-120">这是因为初始化函数可能不是按索引值的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="0df38-120">This is because the initialization function might not be called with in-order index values.</span></span>  
  
## <a name="implementing-the-three-cumulative-functions"></a><span data-ttu-id="0df38-121">实现三个累计函数</span><span class="sxs-lookup"><span data-stu-id="0df38-121">Implementing the Three Cumulative Functions</span></span>  
 <span data-ttu-id="0df38-122">您需要为开发的每个自定义累计 functoid 实现三个函数。</span><span class="sxs-lookup"><span data-stu-id="0df38-122">You will need to implement three functions for each custom cumulative functoid you develop.</span></span> <span data-ttu-id="0df38-123">下表概括介绍了这些函数以及为设置这些函数必须在构造函数中调用方法。</span><span class="sxs-lookup"><span data-stu-id="0df38-123">The functions and the methods you must call in the constructor to set them are summarized in the following table.</span></span> <span data-ttu-id="0df38-124">所有函数都返回字符串值。</span><span class="sxs-lookup"><span data-stu-id="0df38-124">All of the functions return string values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0df38-125">由您确定每个函数的最佳名称，但每个函数必须具有所指定的参数数目和类型。</span><span class="sxs-lookup"><span data-stu-id="0df38-125">You determine the best name for each function, but each function must have the number and type of arguments specified.</span></span>  
  
|<span data-ttu-id="0df38-126">函数用途</span><span class="sxs-lookup"><span data-stu-id="0df38-126">Function Purpose</span></span>|<span data-ttu-id="0df38-127">参数</span><span class="sxs-lookup"><span data-stu-id="0df38-127">Arguments</span></span>|<span data-ttu-id="0df38-128">设置引用</span><span class="sxs-lookup"><span data-stu-id="0df38-128">To set a reference</span></span>|<span data-ttu-id="0df38-129">设置内联脚本</span><span class="sxs-lookup"><span data-stu-id="0df38-129">To set inline script</span></span>|  
|----------------------|---------------|------------------------|--------------------------|  
|<span data-ttu-id="0df38-130">初始化</span><span class="sxs-lookup"><span data-stu-id="0df38-130">Initialization</span></span>|<span data-ttu-id="0df38-131">**int 索引**</span><span class="sxs-lookup"><span data-stu-id="0df38-131">**int index**</span></span>|<span data-ttu-id="0df38-132">**SetExternalFunctionName**</span><span class="sxs-lookup"><span data-stu-id="0df38-132">**SetExternalFunctionName**</span></span>|<span data-ttu-id="0df38-133">**SetScriptBuffer**与`functionNumber`= 0</span><span class="sxs-lookup"><span data-stu-id="0df38-133">**SetScriptBuffer** with `functionNumber` = 0</span></span>|  
|<span data-ttu-id="0df38-134">累计</span><span class="sxs-lookup"><span data-stu-id="0df38-134">Cumulation</span></span>|<span data-ttu-id="0df38-135">**int index、 string val、 string scope**</span><span class="sxs-lookup"><span data-stu-id="0df38-135">**int index, string val, string scope**</span></span>|<span data-ttu-id="0df38-136">**SetExternalFunctionName2**</span><span class="sxs-lookup"><span data-stu-id="0df38-136">**SetExternalFunctionName2**</span></span>|<span data-ttu-id="0df38-137">**SetScriptBuffer**与`functionNumber`= 1</span><span class="sxs-lookup"><span data-stu-id="0df38-137">**SetScriptBuffer** with `functionNumber` = 1</span></span>|  
|<span data-ttu-id="0df38-138">获取</span><span class="sxs-lookup"><span data-stu-id="0df38-138">Get</span></span>|<span data-ttu-id="0df38-139">**int 索引**</span><span class="sxs-lookup"><span data-stu-id="0df38-139">**int index**</span></span>|<span data-ttu-id="0df38-140">**SetExternalFunctionName3**</span><span class="sxs-lookup"><span data-stu-id="0df38-140">**SetExternalFunctionName3**</span></span>|<span data-ttu-id="0df38-141">**SetScriptBuffer**与`functionNumber`= 2</span><span class="sxs-lookup"><span data-stu-id="0df38-141">**SetScriptBuffer** with `functionNumber` = 2</span></span>|  
  
### <a name="initialization"></a><span data-ttu-id="0df38-142">初始化</span><span class="sxs-lookup"><span data-stu-id="0df38-142">Initialization</span></span>  
 <span data-ttu-id="0df38-143">通过初始化，您可以准备用于执行累计的机制。</span><span class="sxs-lookup"><span data-stu-id="0df38-143">Initialization enables you to prepare the mechanisms you will use to perform accumulation.</span></span> <span data-ttu-id="0df38-144">您可以初始化数组，重置一个或多个值，或者根据需要加载其他资源。</span><span class="sxs-lookup"><span data-stu-id="0df38-144">You can initialize an array, reset one or more values, or load other resources as needed.</span></span> <span data-ttu-id="0df38-145">不使用字符串返回值。</span><span class="sxs-lookup"><span data-stu-id="0df38-145">The string return value is not used.</span></span>  
  
### <a name="cumulation"></a><span data-ttu-id="0df38-146">累计</span><span class="sxs-lookup"><span data-stu-id="0df38-146">Cumulation</span></span>  
 <span data-ttu-id="0df38-147">这是执行与您的 functoid 相应的累计操作的地方。</span><span class="sxs-lookup"><span data-stu-id="0df38-147">This is where you perform the accumulation operation appropriate for your functoid.</span></span> <span data-ttu-id="0df38-148">BizTalk Server 将传入以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="0df38-148">BizTalk Server passes in the following three parameters:</span></span>  
  
-   <span data-ttu-id="0df38-149">**索引。**</span><span class="sxs-lookup"><span data-stu-id="0df38-149">**Index.**</span></span> <span data-ttu-id="0df38-150">代表映射实例的整数值。</span><span class="sxs-lookup"><span data-stu-id="0df38-150">An integer value representing a map instance.</span></span> <span data-ttu-id="0df38-151">可以有多个映射实例在同时运行。</span><span class="sxs-lookup"><span data-stu-id="0df38-151">There may be multiple map instances running concurrently.</span></span>  
  
-   <span data-ttu-id="0df38-152">**Val。**</span><span class="sxs-lookup"><span data-stu-id="0df38-152">**Val.**</span></span> <span data-ttu-id="0df38-153">包含应累计的值的字符串。</span><span class="sxs-lookup"><span data-stu-id="0df38-153">A string containing the value that should be accumulated.</span></span> <span data-ttu-id="0df38-154">除非是在编写字符串累计 functoid，否则该参数为数字值。</span><span class="sxs-lookup"><span data-stu-id="0df38-154">Unless you are writing a string Cumulate functoid it is a numeric value.</span></span>  
  
-   <span data-ttu-id="0df38-155">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="0df38-155">**Scope.**</span></span> <span data-ttu-id="0df38-156">包含有数值的字符串，指示应对哪个元素或属性值进行累计。</span><span class="sxs-lookup"><span data-stu-id="0df38-156">A string containing a number indicating which element or attribute value should be accumulated.</span></span> <span data-ttu-id="0df38-157">实际值通过实现来确定。</span><span class="sxs-lookup"><span data-stu-id="0df38-157">Actual values are determined by an implementation.</span></span>  
  
 <span data-ttu-id="0df38-158">由您决定要累计哪些值以及要忽略哪些值。</span><span class="sxs-lookup"><span data-stu-id="0df38-158">You decide which values to accumulate and which values to ignore.</span></span> <span data-ttu-id="0df38-159">例如，您可以忽略不小于 0 的值，并在值不是数字时引发异常。</span><span class="sxs-lookup"><span data-stu-id="0df38-159">For example, you may ignore values that are not below 0 but throw an exception when a value is not numeric.</span></span> <span data-ttu-id="0df38-160">**BaseFunctoid**提供两个函数-**IsDate**和**IsNumeric**-有助于验证。</span><span class="sxs-lookup"><span data-stu-id="0df38-160">**BaseFunctoid** supplies two functions—**IsDate** and **IsNumeric**—to assist with validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0df38-161">如果你使用**IsDate**或**IsNumeric**在内联脚本中，请务必设置**RequiredGlobalHelperFunctions**以便函数都提供给你的脚本。</span><span class="sxs-lookup"><span data-stu-id="0df38-161">If you use **IsDate** or **IsNumeric** in an inline script, be sure to set **RequiredGlobalHelperFunctions** so that the functions are made available to your script.</span></span>  
  
 <span data-ttu-id="0df38-162">不使用字符串返回值。</span><span class="sxs-lookup"><span data-stu-id="0df38-162">The string return value is not used.</span></span>  
  
### <a name="get"></a><span data-ttu-id="0df38-163">获取</span><span class="sxs-lookup"><span data-stu-id="0df38-163">Get</span></span>  
 <span data-ttu-id="0df38-164">BizTalk Server 完成了映射中的 functoid 设置所确定的所有值的循环迭代之后，将请求累计值。</span><span class="sxs-lookup"><span data-stu-id="0df38-164">When BizTalk Server finishes iterating through all of the values determined by the functoid settings in the map, it requests the accumulated value.</span></span> <span data-ttu-id="0df38-165">获取函数具有一个参数，即 `Index`，该参数是代表映射实例的整数值。</span><span class="sxs-lookup"><span data-stu-id="0df38-165">The get function has one argument, `Index`, which is an integer value representing a map instance.</span></span> <span data-ttu-id="0df38-166">您的函数应使用索引值来查找累计值并将其作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="0df38-166">Your function should use the index value to find and return the accumulated value as a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0df38-167">示例</span><span class="sxs-lookup"><span data-stu-id="0df38-167">Example</span></span>  
 <span data-ttu-id="0df38-168">下面的示例阐释了如何创建执行累计乘法的自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="0df38-168">The following example illustrates how to create a custom functoid for performing cumulative multiplication.</span></span> <span data-ttu-id="0df38-169">该 functoid 依赖于一个包含三个字符串资源和一个 16x16 像素位图资源的资源文件。</span><span class="sxs-lookup"><span data-stu-id="0df38-169">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
using System.Collections;  
using System.Globalization;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    public class CumulativeMultiplyFunctoid : BaseFunctoid  
    {  
        private ArrayList myCumulativeArray = new ArrayList();  
  
        public CumulativeMultiplyFunctoid() : base()  
        {  
            //ID for this functoid  
            ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUMULATIVEMULTIPLYFUNCTOID_NAME");  
            SetTooltip("IDS_CUMULATIVEMULTIPLYFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUMULATIVEMULTIPLYFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUMULATIVEMULTIPLYFUNCTOID_BITMAP");  
  
            // Put this string handling function under the Cumulative  
            // Functoid tab in the Visual Studio toolbox for functoids  
            Category = FunctoidCategory.Cumulative;  
  
            // 2 required parameters, no optional parameters  
            SetMinParams(1);  
            SetMaxParams(2);  
  
            // Functoid accepts three inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType((~ConnectionType.FunctoidCount) & (~ConnectionType.FunctoidIndex) & (~ConnectionType.FunctoidIteration) & (~ConnectionType.FunctoidCumulative) & (~ConnectionType.FunctoidLooping) & (~ConnectionType.Record));  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the Initialize, Cumulative and Get functions  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CumulativeMultiplyFunctoid", "InitCumulativeMultiply");  
            SetExternalFunctionName2("AddToCumulativeMultiply");  
            SetExternalFunctionName3("GetCumulativeMultiply");  
        }  
  
        // Initialization function  
        public string InitCumulativeMultiply(int index)  
        {  
            if (index >= 0)  
            {  
                if (index >= myCumulativeArray.Count)  
                {  
                    myCumulativeArray.Add(1.0);  
                }  
                else  
                {  
                    myCumulativeArray[index] = 1.0;  
                }  
            }  
  
            return "";  
        }  
  
        // Cumulative function  
        public string AddToCumulativeMultiply(int index, string val, string reserved)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            if (IsNumeric(val))  
            {  
                double dval = Convert.ToDouble(val, CultureInfo.InvariantCulture);  
                myCumulativeArray[index] = (double)(myCumulativeArray[index]) * dval;  
            }  
            return myCumulativeArray[index].ToString();  
        }  
  
        // Get Function  
        public string GetCumulativeMultiply(int index)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            return myCumulativeArray[index].ToString();  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="0df38-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0df38-170">See Also</span></span>  
 <span data-ttu-id="0df38-171">[使用 BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="0df38-171">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="0df38-172">[开发自定义的内联 Functoid](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0df38-172">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 [<span data-ttu-id="0df38-173">自定义 Functoid （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="0df38-173">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)