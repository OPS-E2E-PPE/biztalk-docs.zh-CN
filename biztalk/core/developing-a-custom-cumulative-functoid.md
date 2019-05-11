---
title: 开发自定义累计 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05152065b93fabe103125718334a61da878fd309
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389472"
---
# <a name="developing-a-custom-cumulative-functoid"></a><span data-ttu-id="09a35-102">开发自定义的累计 Functoid</span><span class="sxs-lookup"><span data-stu-id="09a35-102">Developing a Custom Cumulative Functoid</span></span>
<span data-ttu-id="09a35-103">自定义累计 functoid 用于执行累计操作在实例消息中多次出现的值。</span><span class="sxs-lookup"><span data-stu-id="09a35-103">Use a custom cumulative functoid to perform accumulation operations for values that occur multiple times within an instance message.</span></span>  
  
 <span data-ttu-id="09a35-104">在开发累计 functoid 时，必须实现三个函数。</span><span class="sxs-lookup"><span data-stu-id="09a35-104">You must implement three functions when developing a cumulative functoid.</span></span> <span data-ttu-id="09a35-105">三个函数对应于初始化、 累计和获取地图需要对其执行累计操作。</span><span class="sxs-lookup"><span data-stu-id="09a35-105">The three functions correspond to the initialize, cumulate, and get actions that the map needs to perform the accumulation.</span></span> <span data-ttu-id="09a35-106">在讨论这些函数之前务必讨论一下线程安全。</span><span class="sxs-lookup"><span data-stu-id="09a35-106">Before discussing these functions it is important to discuss thread safety.</span></span>  
  
## <a name="writing-a-thread-safe-functoid"></a><span data-ttu-id="09a35-107">编写线程安全 Functoid</span><span class="sxs-lookup"><span data-stu-id="09a35-107">Writing a Thread-Safe Functoid</span></span>  
 <span data-ttu-id="09a35-108">Functoid 代码必须是映射的线程安全，因为在任务繁忙多个实例可以同时运行。</span><span class="sxs-lookup"><span data-stu-id="09a35-108">The functoid code must be thread-safe because under stress conditions multiple instances of a map may be running concurrently.</span></span> <span data-ttu-id="09a35-109">一些要记住的要点包括：</span><span class="sxs-lookup"><span data-stu-id="09a35-109">Some of the points to remember include:</span></span>  
  
- <span data-ttu-id="09a35-110">静态状态必须是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="09a35-110">Static state must be thread-safe.</span></span>  
  
- <span data-ttu-id="09a35-111">实例状态不始终需要是线程安全。</span><span class="sxs-lookup"><span data-stu-id="09a35-111">Instance state does not always need to be thread-safe.</span></span>  
  
- <span data-ttu-id="09a35-112">设计时应考虑高高负荷环境下运行。</span><span class="sxs-lookup"><span data-stu-id="09a35-112">Design with consideration for running under high-stress conditions.</span></span> <span data-ttu-id="09a35-113">避免进行锁定，只要有可能。</span><span class="sxs-lookup"><span data-stu-id="09a35-113">Avoid taking locks whenever possible.</span></span>  
  
- <span data-ttu-id="09a35-114">如果可能，避免同步需求。</span><span class="sxs-lookup"><span data-stu-id="09a35-114">Avoid the need for synchronization if possible.</span></span>  
  
  <span data-ttu-id="09a35-115">BizTalk Server 提供了一个简单的机制来降低编写线程安全累计 functoid 的复杂性。</span><span class="sxs-lookup"><span data-stu-id="09a35-115">BizTalk Server provides a simple mechanism to reduce the complexity of writing a thread-safe cumulative functoid.</span></span> <span data-ttu-id="09a35-116">所有三个函数都具有相同的第一个参数为整数索引值。</span><span class="sxs-lookup"><span data-stu-id="09a35-116">All three functions have the same first parameter, an integer index value.</span></span> <span data-ttu-id="09a35-117">调用初始化函数时，BizTalk Server 分配到的索引值的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="09a35-117">BizTalk Server assigns a unique number to the index value when it calls your initialization function.</span></span> <span data-ttu-id="09a35-118">可以使用此值作为索引到一个数组，其中存放累计值，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="09a35-118">You can use this value as an index into an array that holds accumulating values, as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="09a35-119">此示例使用哈希表，而不是 ArrayList。</span><span class="sxs-lookup"><span data-stu-id="09a35-119">This example uses a HashTable instead of an ArrayList.</span></span> <span data-ttu-id="09a35-120">这是因为初始化函数可能不会调用的顺序索引值。</span><span class="sxs-lookup"><span data-stu-id="09a35-120">This is because the initialization function might not be called with in-order index values.</span></span>  
  
## <a name="implementing-the-three-cumulative-functions"></a><span data-ttu-id="09a35-121">实现三个累计函数</span><span class="sxs-lookup"><span data-stu-id="09a35-121">Implementing the Three Cumulative Functions</span></span>  
 <span data-ttu-id="09a35-122">您需要实现的每个开发的自定义累计 functoid 的三个函数。</span><span class="sxs-lookup"><span data-stu-id="09a35-122">You will need to implement three functions for each custom cumulative functoid you develop.</span></span> <span data-ttu-id="09a35-123">下表总结了函数和必须在构造函数中设置这些调用的方法。</span><span class="sxs-lookup"><span data-stu-id="09a35-123">The functions and the methods you must call in the constructor to set them are summarized in the following table.</span></span> <span data-ttu-id="09a35-124">所有函数返回字符串值。</span><span class="sxs-lookup"><span data-stu-id="09a35-124">All of the functions return string values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09a35-125">您确定最佳名称对于每个函数，但每个函数必须具有的数量和类型指定的参数。</span><span class="sxs-lookup"><span data-stu-id="09a35-125">You determine the best name for each function, but each function must have the number and type of arguments specified.</span></span>  
  
|<span data-ttu-id="09a35-126">函数用途</span><span class="sxs-lookup"><span data-stu-id="09a35-126">Function Purpose</span></span>|<span data-ttu-id="09a35-127">参数</span><span class="sxs-lookup"><span data-stu-id="09a35-127">Arguments</span></span>|<span data-ttu-id="09a35-128">若要设置的引用</span><span class="sxs-lookup"><span data-stu-id="09a35-128">To set a reference</span></span>|<span data-ttu-id="09a35-129">若要设置内联脚本</span><span class="sxs-lookup"><span data-stu-id="09a35-129">To set inline script</span></span>|  
|----------------------|---------------|------------------------|--------------------------|  
|<span data-ttu-id="09a35-130">初始化</span><span class="sxs-lookup"><span data-stu-id="09a35-130">Initialization</span></span>|<span data-ttu-id="09a35-131">**int index**</span><span class="sxs-lookup"><span data-stu-id="09a35-131">**int index**</span></span>|<span data-ttu-id="09a35-132">**SetExternalFunctionName**</span><span class="sxs-lookup"><span data-stu-id="09a35-132">**SetExternalFunctionName**</span></span>|<span data-ttu-id="09a35-133">**SetScriptBuffer**与`functionNumber`= 0</span><span class="sxs-lookup"><span data-stu-id="09a35-133">**SetScriptBuffer** with `functionNumber` = 0</span></span>|  
|<span data-ttu-id="09a35-134">累计</span><span class="sxs-lookup"><span data-stu-id="09a35-134">Cumulation</span></span>|<span data-ttu-id="09a35-135">**int index、 string val、 string scope**</span><span class="sxs-lookup"><span data-stu-id="09a35-135">**int index, string val, string scope**</span></span>|<span data-ttu-id="09a35-136">**SetExternalFunctionName2**</span><span class="sxs-lookup"><span data-stu-id="09a35-136">**SetExternalFunctionName2**</span></span>|<span data-ttu-id="09a35-137">**SetScriptBuffer**与`functionNumber`= 1</span><span class="sxs-lookup"><span data-stu-id="09a35-137">**SetScriptBuffer** with `functionNumber` = 1</span></span>|  
|<span data-ttu-id="09a35-138">获取</span><span class="sxs-lookup"><span data-stu-id="09a35-138">Get</span></span>|<span data-ttu-id="09a35-139">**int index**</span><span class="sxs-lookup"><span data-stu-id="09a35-139">**int index**</span></span>|<span data-ttu-id="09a35-140">**SetExternalFunctionName3**</span><span class="sxs-lookup"><span data-stu-id="09a35-140">**SetExternalFunctionName3**</span></span>|<span data-ttu-id="09a35-141">**SetScriptBuffer**与`functionNumber`= 2</span><span class="sxs-lookup"><span data-stu-id="09a35-141">**SetScriptBuffer** with `functionNumber` = 2</span></span>|  
  
### <a name="initialization"></a><span data-ttu-id="09a35-142">初始化</span><span class="sxs-lookup"><span data-stu-id="09a35-142">Initialization</span></span>  
 <span data-ttu-id="09a35-143">初始化可准备将用于执行累计的机制。</span><span class="sxs-lookup"><span data-stu-id="09a35-143">Initialization enables you to prepare the mechanisms you will use to perform accumulation.</span></span> <span data-ttu-id="09a35-144">可以初始化数组、 重置一个或多个值，或根据需要加载其他资源。</span><span class="sxs-lookup"><span data-stu-id="09a35-144">You can initialize an array, reset one or more values, or load other resources as needed.</span></span> <span data-ttu-id="09a35-145">字符串返回不使用值。</span><span class="sxs-lookup"><span data-stu-id="09a35-145">The string return value is not used.</span></span>  
  
### <a name="cumulation"></a><span data-ttu-id="09a35-146">累计</span><span class="sxs-lookup"><span data-stu-id="09a35-146">Cumulation</span></span>  
 <span data-ttu-id="09a35-147">这是在其中执行相应的 functoid 累计操作。</span><span class="sxs-lookup"><span data-stu-id="09a35-147">This is where you perform the accumulation operation appropriate for your functoid.</span></span> <span data-ttu-id="09a35-148">BizTalk Server 将传入以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="09a35-148">BizTalk Server passes in the following three parameters:</span></span>  
  
- <span data-ttu-id="09a35-149">**索引。**</span><span class="sxs-lookup"><span data-stu-id="09a35-149">**Index.**</span></span> <span data-ttu-id="09a35-150">代表映射实例的整数值。</span><span class="sxs-lookup"><span data-stu-id="09a35-150">An integer value representing a map instance.</span></span> <span data-ttu-id="09a35-151">可能有多个映射实例在同时运行。</span><span class="sxs-lookup"><span data-stu-id="09a35-151">There may be multiple map instances running concurrently.</span></span>  
  
- <span data-ttu-id="09a35-152">**Val。**</span><span class="sxs-lookup"><span data-stu-id="09a35-152">**Val.**</span></span> <span data-ttu-id="09a35-153">包含应累计的值的字符串。</span><span class="sxs-lookup"><span data-stu-id="09a35-153">A string containing the value that should be accumulated.</span></span> <span data-ttu-id="09a35-154">除非你正在编写字符串累计 functoid，它数字值。</span><span class="sxs-lookup"><span data-stu-id="09a35-154">Unless you are writing a string Cumulate functoid it is a numeric value.</span></span>  
  
- <span data-ttu-id="09a35-155">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="09a35-155">**Scope.**</span></span> <span data-ttu-id="09a35-156">包含一个数字，指示应累计的元素或属性值的字符串。</span><span class="sxs-lookup"><span data-stu-id="09a35-156">A string containing a number indicating which element or attribute value should be accumulated.</span></span> <span data-ttu-id="09a35-157">实际值由实现决定。</span><span class="sxs-lookup"><span data-stu-id="09a35-157">Actual values are determined by an implementation.</span></span>  
  
  <span data-ttu-id="09a35-158">您决定要累计哪些值以及要忽略哪些值。</span><span class="sxs-lookup"><span data-stu-id="09a35-158">You decide which values to accumulate and which values to ignore.</span></span> <span data-ttu-id="09a35-159">例如，可能会忽略不小于 0 的值，但值不是数字时引发异常。</span><span class="sxs-lookup"><span data-stu-id="09a35-159">For example, you may ignore values that are not below 0 but throw an exception when a value is not numeric.</span></span> <span data-ttu-id="09a35-160">**BaseFunctoid**提供了两个函数 —**IsDate**并**IsNumeric**— 以协助您进行验证。</span><span class="sxs-lookup"><span data-stu-id="09a35-160">**BaseFunctoid** supplies two functions—**IsDate** and **IsNumeric**—to assist with validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09a35-161">如果您使用**IsDate**或**IsNumeric**中的内联脚本，请务必设置**RequiredGlobalHelperFunctions**以便函数都提供给您的脚本。</span><span class="sxs-lookup"><span data-stu-id="09a35-161">If you use **IsDate** or **IsNumeric** in an inline script, be sure to set **RequiredGlobalHelperFunctions** so that the functions are made available to your script.</span></span>  
  
 <span data-ttu-id="09a35-162">字符串返回不使用值。</span><span class="sxs-lookup"><span data-stu-id="09a35-162">The string return value is not used.</span></span>  
  
### <a name="get"></a><span data-ttu-id="09a35-163">获取</span><span class="sxs-lookup"><span data-stu-id="09a35-163">Get</span></span>  
 <span data-ttu-id="09a35-164">BizTalk Server 完成循环访问所有由映射中 functoid 设置的值，它请求的累计的值。</span><span class="sxs-lookup"><span data-stu-id="09a35-164">When BizTalk Server finishes iterating through all of the values determined by the functoid settings in the map, it requests the accumulated value.</span></span> <span data-ttu-id="09a35-165">获取函数具有一个自变量， `Index`，这是代表映射实例的整数值。</span><span class="sxs-lookup"><span data-stu-id="09a35-165">The get function has one argument, `Index`, which is an integer value representing a map instance.</span></span> <span data-ttu-id="09a35-166">你的函数应使用的索引值来查找并返回字符串形式的累计的值。</span><span class="sxs-lookup"><span data-stu-id="09a35-166">Your function should use the index value to find and return the accumulated value as a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09a35-167">示例</span><span class="sxs-lookup"><span data-stu-id="09a35-167">Example</span></span>  
 <span data-ttu-id="09a35-168">下面的示例说明了如何创建执行累计乘法的自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="09a35-168">The following example illustrates how to create a custom functoid for performing cumulative multiplication.</span></span> <span data-ttu-id="09a35-169">它依赖于包含三个字符串资源和 16 x 16 像素位图资源的资源文件。</span><span class="sxs-lookup"><span data-stu-id="09a35-169">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="09a35-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="09a35-170">See Also</span></span>  
 <span data-ttu-id="09a35-171">[使用 BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="09a35-171">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="09a35-172">[开发自定义内联 Functoid](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="09a35-172">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 [<span data-ttu-id="09a35-173">自定义 Functoid（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="09a35-173">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)