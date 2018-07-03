---
title: 开发自定义内联 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4533f09f-b62d-4b09-b7de-44541c6cf053
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6e208cd894c2b307bd2c601b7d8bd774e204ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976694"
---
# <a name="developing-a-custom-inline-functoid"></a><span data-ttu-id="e1237-102">开发自定义内联 Functoid</span><span class="sxs-lookup"><span data-stu-id="e1237-102">Developing a Custom Inline Functoid</span></span>
<span data-ttu-id="e1237-103">自定义内联 functoid 通过将实现代码直接复制到映射中提供功能，而不像自定义引用的 functoid 通过引用程序集、类和方法名称来提供功能。</span><span class="sxs-lookup"><span data-stu-id="e1237-103">Custom inline functoids provide functionality by copying implementation code directly into a map and not by referencing an assembly, class, and method name like a custom referenced functoid.</span></span>  
  
## <a name="building-inline-script"></a><span data-ttu-id="e1237-104">生成内联脚本</span><span class="sxs-lookup"><span data-stu-id="e1237-104">Building Inline Script</span></span>  
 <span data-ttu-id="e1237-105">有两种方法提供脚本以包含在映射中。</span><span class="sxs-lookup"><span data-stu-id="e1237-105">There are two ways to provide script for inclusion into the map.</span></span> <span data-ttu-id="e1237-106">根据自定义 functoid 是否支持参数个数可变，从以下方法进行选择：</span><span class="sxs-lookup"><span data-stu-id="e1237-106">Choose from the following methods, based on whether your custom functoid supports a variable number of parameters:</span></span>  
  
- <span data-ttu-id="e1237-107">重写**GetInlineScriptBuffer**时自定义 functoid 接受个数可变的输入参数，并且已将**HasVariableInputs**属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="e1237-107">Override **GetInlineScriptBuffer** when your custom functoid accepts a variable number of input parameters and you have set the **HasVariableInputs** property to `true`.</span></span> <span data-ttu-id="e1237-108">例如，如果要连接个数可变的字符串或在一组值中查找最大值时，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e1237-108">For example, use this method if you want to concatenate a variable number of strings or find the largest value in a set of values.</span></span>  
  
- <span data-ttu-id="e1237-109">使用**SetScriptBuffer**不需要支持个数可变的输入参数。</span><span class="sxs-lookup"><span data-stu-id="e1237-109">Use **SetScriptBuffer** when you do not need to support a variable number of input parameters.</span></span> <span data-ttu-id="e1237-110">仍可以使用可选参数，但参数的总数是固定的。</span><span class="sxs-lookup"><span data-stu-id="e1237-110">You can still use optional parameters, but the total number of parameters is fixed.</span></span>  
  
  <span data-ttu-id="e1237-111">这两种方法需要不同的实现。</span><span class="sxs-lookup"><span data-stu-id="e1237-111">These two methods require different implementations.</span></span>  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a><span data-ttu-id="e1237-112">使用 SetScriptBuffer 提供内联代码</span><span class="sxs-lookup"><span data-stu-id="e1237-112">Providing Inline Code with SetScriptBuffer</span></span>  
 <span data-ttu-id="e1237-113">若要配置自定义 functoid 以使用内联脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1237-113">To configure your custom functoid to use inline script:</span></span>  
  
1. <span data-ttu-id="e1237-114">调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)以启用内联代码并设置支持的脚本类型。</span><span class="sxs-lookup"><span data-stu-id="e1237-114">Call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
2. <span data-ttu-id="e1237-115">调用**SetScriptBuffer**来设置要用于自定义 functoid 的代码。</span><span class="sxs-lookup"><span data-stu-id="e1237-115">Invoke **SetScriptBuffer** to set the code to use for the custom functoid.</span></span> <span data-ttu-id="e1237-116">将使用 `functionNumber` 参数为自定义累计 functoid 调用此函数三次，为自定义非累计 functoid 调用此函数一次。</span><span class="sxs-lookup"><span data-stu-id="e1237-116">You will call this function three times with the `functionNumber` parameter for custom cumulative functoids and once for custom noncumulative functoids.</span></span>  
  
3. <span data-ttu-id="e1237-117">使用**SetScriptGlobalBuffer**声明内联代码使用任何全局变量。</span><span class="sxs-lookup"><span data-stu-id="e1237-117">Use **SetScriptGlobalBuffer** to declare any global variables that your inline code uses.</span></span>  
  
4. <span data-ttu-id="e1237-118">使用**RequiredGlobalHelperFunctions**以指示自定义内联 functoid 的帮助器函数。</span><span class="sxs-lookup"><span data-stu-id="e1237-118">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
   <span data-ttu-id="e1237-119">可以使用 StringBuilder 或常数生成脚本。</span><span class="sxs-lookup"><span data-stu-id="e1237-119">You can build your script by using StringBuilder or constants.</span></span> <span data-ttu-id="e1237-120">编写脚本代码的一种方法是：首先编写自定义引用的 functoid，消除了所有错误之后，通过将函数复制到字符串常数中将其转换成内联。</span><span class="sxs-lookup"><span data-stu-id="e1237-120">One approach to writing script code is to write a custom referenced functoid first and, when all bugs are eliminated, convert it to inline by copying your functions into string constants.</span></span>  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a><span data-ttu-id="e1237-121">使用 GetInlineScriptBuffer 提供内联代码</span><span class="sxs-lookup"><span data-stu-id="e1237-121">Providing Inline Code with GetInlineScriptBuffer</span></span>  
 <span data-ttu-id="e1237-122">如果您的自定义内联 functoid 支持个数可变的参数，则将重写**GetInlineScriptBuffer**。</span><span class="sxs-lookup"><span data-stu-id="e1237-122">If your custom inline functoid supports a variable number of parameters, you will override **GetInlineScriptBuffer**.</span></span> <span data-ttu-id="e1237-123">若要配置自定义 functoid 以使用内联脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1237-123">To configure your custom functoid to use inline script:</span></span>  
  
1. <span data-ttu-id="e1237-124">在构造函数中声明自定义 functoid 通过设置具有变量输入**HasVariableInputs**到`true`。</span><span class="sxs-lookup"><span data-stu-id="e1237-124">In the constructor, declare that your custom functoid has variable inputs by setting **HasVariableInputs** to `true`.</span></span>  
  
2. <span data-ttu-id="e1237-125">在构造函数中，调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)以启用内联代码并设置支持的脚本类型。</span><span class="sxs-lookup"><span data-stu-id="e1237-125">In the constructor, call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
3. <span data-ttu-id="e1237-126">重写**GetInlineScriptBuffer**构造并返回要为自定义 functoid 在映射中使用的代码。</span><span class="sxs-lookup"><span data-stu-id="e1237-126">Override **GetInlineScriptBuffer** to construct and return the code to use in the map for your custom functoid.</span></span> <span data-ttu-id="e1237-127">检查 `scriptType` 和 `numParams`，使用参数生成正确的代码。</span><span class="sxs-lookup"><span data-stu-id="e1237-127">Use the parameters to build the correct code by checking the `scriptType` and `numParams`.</span></span> <span data-ttu-id="e1237-128">最后一个参数， `functionNumber`，应为 0。</span><span class="sxs-lookup"><span data-stu-id="e1237-128">The final parameter, `functionNumber`, should be 0.</span></span> <span data-ttu-id="e1237-129">这是因为累计函数的输入个数固定，并且不使用此机制。</span><span class="sxs-lookup"><span data-stu-id="e1237-129">This is because cumulative functions have a fixed number of inputs and do not use this mechanism.</span></span>  
  
4. <span data-ttu-id="e1237-130">使用**SetScriptGlobalBuffer**声明内联代码使用的全局变量。</span><span class="sxs-lookup"><span data-stu-id="e1237-130">Use **SetScriptGlobalBuffer** to declare global variables that your inline code uses.</span></span>  
  
5. <span data-ttu-id="e1237-131">使用**RequiredGlobalHelperFunctions**以指示自定义内联 functoid 的帮助器函数。</span><span class="sxs-lookup"><span data-stu-id="e1237-131">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
   <span data-ttu-id="e1237-132">以下代码段使用传入 `numParams` 的参数个数生成 C# 函数，但没有使用函数体。</span><span class="sxs-lookup"><span data-stu-id="e1237-132">The following code fragment builds a C# function with the number of parameters passed in `numParams` but with no function body.</span></span> <span data-ttu-id="e1237-133">若要使用此代码段，请将该示例复制到您的解决方案中，然后添加代码使用参数以执行任务并返回值。</span><span class="sxs-lookup"><span data-stu-id="e1237-133">To use this code fragment, copy the example to your solution and add code to do something with the parameters and return a value.</span></span>  
  
```  
// Override GetInlineScriptBuffer  
protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
{  
    // Is this one of the supported script types?  
    if(ScriptType.CSharp == scriptType)  
    {  
        // Assume functionNumber == 0  
        StringBuilder builder = new StringBuilder();  
        // Function declaration   
        builder.Append("public string MyFunction("  
        // Declare parameters using numParams  
        for(int i=0; i<numParams; i++)  
        {  
            // Separate params with a comma  
            if(i > 0)  
                builder.Append(", ");  
            // Declare parameters, param0 to paramNUMPARAM  
            builder.Append("string param" + i.ToString());  
        }  
        builder.Append(")\n");  
        // Function body; process params as needed  
        builder.Append("{\n");  
        builder.Append("}\n");  
        // Return script  
        return builder.ToString();  
    }  
    // scriptType is unsupported  
    return string.Empty;  
}  
```  
  
## <a name="testing-an-inline-script"></a><span data-ttu-id="e1237-134">测试内联脚本</span><span class="sxs-lookup"><span data-stu-id="e1237-134">Testing an Inline Script</span></span>  
 <span data-ttu-id="e1237-135">测试在任何开发工作中都是重点。</span><span class="sxs-lookup"><span data-stu-id="e1237-135">Testing is an important consideration in any development effort.</span></span> <span data-ttu-id="e1237-136">自定义内联 functoid 的测试工作可能非常困难。</span><span class="sxs-lookup"><span data-stu-id="e1237-136">Custom inline functoids can be challenging to test.</span></span> <span data-ttu-id="e1237-137">若要简化该过程，请使用以下方法之一或两种方法都使用：</span><span class="sxs-lookup"><span data-stu-id="e1237-137">To simplify the process, use one or both of the following techniques:</span></span>  
  
-   <span data-ttu-id="e1237-138">检查使用自定义内联 functoid 的映射的 XSLT。</span><span class="sxs-lookup"><span data-stu-id="e1237-138">Examine the XSLT of a map that uses the custom inline functoid.</span></span>  
  
-   <span data-ttu-id="e1237-139">验证使用自定义内联 functoid 的映射的输入和输出。</span><span class="sxs-lookup"><span data-stu-id="e1237-139">Verify the input and output of a map that uses the custom inline functoid.</span></span>  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="e1237-140">检查使用自定义内联 functoid 的映射的 XSLT</span><span class="sxs-lookup"><span data-stu-id="e1237-140">Examine the XSLT of a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="e1237-141">此方法通常能显示逻辑问题或细微的语法问题。</span><span class="sxs-lookup"><span data-stu-id="e1237-141">This technique often reveals problems with logic or subtle syntax issues.</span></span> <span data-ttu-id="e1237-142">还有助于了解映射中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="e1237-142">It also helps you to understand what happens in the map.</span></span>  
  
 <span data-ttu-id="e1237-143">若要查看映射的 XSLT，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1237-143">To view the XSLT for a map:</span></span>  
  
1.  <span data-ttu-id="e1237-144">从 Visual Studio BizTalk 项目中，单击**解决方案资源管理器**选项卡上，右键单击使用自定义内联 functoid 的映射，然后单击**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="e1237-144">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="e1237-145">滚动“输出”窗口以查找 XSLT 文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1237-145">Scroll the Output window to find the URL for the XSLT file.</span></span> <span data-ttu-id="e1237-146">按住 Ctrl 单击 URL 以查看文件。</span><span class="sxs-lookup"><span data-stu-id="e1237-146">Press CTRL and click the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1237-147">请注意，对 XSLT 文件所做的任何更改都不会反映在自定义 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="e1237-147">Remember that any changes made to the XSLT file will not be reflected in your custom functoid.</span></span>  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="e1237-148">测试使用自定义内联 Functoid 的映射</span><span class="sxs-lookup"><span data-stu-id="e1237-148">Test a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="e1237-149">此方法可以测试映射和自定义内联 functoid 是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="e1237-149">This tests whether the map and custom inline functoid work as expected.</span></span>  
  
 <span data-ttu-id="e1237-150">若要测试映射，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1237-150">To test a map:</span></span>  
  
1. <span data-ttu-id="e1237-151">从 Visual Studio BizTalk 项目中，单击**解决方案资源管理器**选项卡上，右键单击使用自定义内联 functoid 的映射，然后单击**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="e1237-151">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Test Map**.</span></span>  
  
2. <span data-ttu-id="e1237-152">滚动“输出”窗口以查找输出文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1237-152">Scroll the Output window to find the URL for the output file.</span></span> <span data-ttu-id="e1237-153">按住 Ctrl 单击 URL 以查看文件。</span><span class="sxs-lookup"><span data-stu-id="e1237-153">Press CTRL and click the URL to view the file.</span></span>  
  
   <span data-ttu-id="e1237-154">可以检查输入和输出值，以验证映射是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="e1237-154">You can check input and output values to verify that the map behaved as expected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1237-155">示例</span><span class="sxs-lookup"><span data-stu-id="e1237-155">Example</span></span>  
 <span data-ttu-id="e1237-156">下面的示例说明了如何创建用于连接两个字符串的自定义内联 functoid。</span><span class="sxs-lookup"><span data-stu-id="e1237-156">The following example illustrates how to create a custom inline functoid for concatenating two strings.</span></span> <span data-ttu-id="e1237-157">该 functoid 依赖于一个包含三个字符串资源和一个 16x16 像素位图资源的资源文件。</span><span class="sxs-lookup"><span data-stu-id="e1237-157">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation using inline code.  
    /// </summary>  
    public class CustomStringConcatFunctoid : BaseFunctoid  
    {  
        public CustomStringConcatFunctoid()  
            : base()  
        {  
            //ID for this functoid  
            this.ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUSTOMSTRINGCONCATFUNCTOID_NAME");  
            SetTooltip("IDS_CUSTOMSTRINGCONCATFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUSTOMSTRINGCONCATFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUSTOMSTRINGCONCATFUNCTOID_BITMAP");  
  
            // Put this string handling function under the String   
            // Functoid tab in the Visual Studio toolbox for functoids  
            this.Category = FunctoidCategory.String;  
  
            // 2 required parameters, no optional parameters  
            this.SetMinParams(2);  
            this.SetMaxParams(2);  
  
            // Functoid accepts two inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            this.OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Declare support for CSharp inline function and  
            // pass the method implementation to the buffer  
            AddScriptTypeSupport(ScriptType.CSharp);  
            SetScriptBuffer(ScriptType.CSharp, GetCSharpBuffer());  
        }  
  
        private string GetCSharpBuffer()  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string ConCatStrings(string val1, string val2)\n");  
            builder.Append("{\n");  
            builder.Append("    return val2+val1;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1237-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1237-158">See Also</span></span>  
 <span data-ttu-id="e1237-159">[使用 BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="e1237-159">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="e1237-160">[开发自定义引用的 Functoid](../core/developing-a-custom-referenced-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="e1237-160">[Developing a Custom Referenced Functoid](../core/developing-a-custom-referenced-functoid.md) </span></span>  
 [<span data-ttu-id="e1237-161">自定义 Functoid（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e1237-161">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)