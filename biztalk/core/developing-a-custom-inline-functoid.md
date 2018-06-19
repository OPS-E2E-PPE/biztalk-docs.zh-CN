---
title: 开发自定义的内联 Functoid |Microsoft 文档
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
ms.openlocfilehash: 1a742e6a53b5fb81d92922ff94e7754239f723ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242013"
---
# <a name="developing-a-custom-inline-functoid"></a>开发自定义的内联 Functoid
自定义内联 functoid 通过将实现代码直接复制到映射中提供功能，而不像自定义引用的 functoid 通过引用程序集、类和方法名称来提供功能。  
  
## <a name="building-inline-script"></a>生成内联脚本  
 有两种方法提供脚本以包含在映射中。 根据自定义 functoid 是否支持参数个数可变，从以下方法进行选择：  
  
-   重写**GetInlineScriptBuffer**时自定义 functoid 接受数目可变的输入参数，并且已设置**HasVariableInputs**属性`true`。 例如，如果要连接个数可变的字符串或在一组值中查找最大值时，请使用此方法。  
  
-   使用**SetScriptBuffer**不需要支持可变数目的输入参数。 仍可以使用可选参数，但参数的总数是固定的。  
  
 这两种方法需要不同的实现。  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a>使用 SetScriptBuffer 提供内联代码  
 若要配置自定义 functoid 以使用内联脚本，请执行以下操作：  
  
1.  调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)启用内联代码和设置的受支持的脚本类型。  
  
2.  调用**SetScriptBuffer**来设置要用于自定义 functoid 的代码。 将使用 `functionNumber` 参数为自定义累计 functoid 调用此函数三次，为自定义非累计 functoid 调用此函数一次。  
  
3.  使用**SetScriptGlobalBuffer**将声明为内联代码使用任何全局变量。  
  
4.  使用**RequiredGlobalHelperFunctions**以指示自定义的内联 functoid 需要的帮助器函数。  
  
 可以使用 StringBuilder 或常数生成脚本。 编写脚本代码的一种方法是：首先编写自定义引用的 functoid，消除了所有错误之后，通过将函数复制到字符串常数中将其转换成内联。  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a>使用 GetInlineScriptBuffer 提供内联代码  
 如果你自定义的内联 functoid 支持可变数目的参数，则将重写**GetInlineScriptBuffer**。 若要配置自定义 functoid 以使用内联脚本，请执行以下操作：  
  
1.  在构造函数中，声明自定义 functoid 通过设置具有变量输入**HasVariableInputs**到`true`。  
  
2.  在构造函数中，调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)启用内联代码和设置的受支持的脚本类型。  
  
3.  重写**GetInlineScriptBuffer**构造并返回代码以在映射中使用自定义 functoid。 检查 `scriptType` 和 `numParams`，使用参数生成正确的代码。 最后一个参数， `functionNumber`，应为 0。 这是因为累积函数具有固定的数量的输入和不使用此机制。  
  
4.  使用**SetScriptGlobalBuffer**将声明为内联代码使用的全局变量。  
  
5.  使用**RequiredGlobalHelperFunctions**以指示自定义的内联 functoid 需要的帮助器函数。  
  
 以下代码段使用传入 `numParams` 的参数个数生成 C# 函数，但没有使用函数体。 若要使用此代码段，请将该示例复制到您的解决方案中，然后添加代码使用参数以执行任务并返回值。  
  
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
  
## <a name="testing-an-inline-script"></a>测试内联脚本  
 测试在任何开发工作中都是重点。 自定义内联 functoid 的测试工作可能非常困难。 若要简化该过程，请使用以下方法之一或两种方法都使用：  
  
-   检查使用自定义内联 functoid 的映射的 XSLT。  
  
-   验证使用自定义内联 functoid 的映射的输入和输出。  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a>检查使用自定义内联 functoid 的映射的 XSLT  
 此方法通常能显示逻辑问题或细微的语法问题。 还有助于了解映射中发生的情况。  
  
 若要查看映射的 XSLT，请执行以下操作：  
  
1.  从 Visual Studio BizTalk 项目，单击**解决方案资源管理器**选项卡上，请右键单击使用您自定义的内联 functoid，映射，然后单击**验证映射**。  
  
2.  滚动“输出”窗口以查找 XSLT 文件的 URL。 按住 Ctrl 单击 URL 以查看文件。  
  
> [!NOTE]
>  请注意，对 XSLT 文件所做的任何更改都不会反映在自定义 functoid 中。  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a>测试使用自定义内联 Functoid 的映射  
 此方法可以测试映射和自定义内联 functoid 是否按预期方式工作。  
  
 若要测试映射，请执行以下操作：  
  
1.  从 Visual Studio BizTalk 项目，单击**解决方案资源管理器**选项卡上，请右键单击使用您自定义的内联 functoid，映射，然后单击**测试映射**。  
  
2.  滚动“输出”窗口以查找输出文件的 URL。 按住 Ctrl 单击 URL 以查看文件。  
  
 可以检查输入和输出值，以验证映射是否按预期方式工作。  
  
## <a name="example"></a>示例  
 下面的示例说明了如何创建用于连接两个字符串的自定义内联 functoid。 该 functoid 依赖于一个包含三个字符串资源和一个 16x16 像素位图资源的资源文件。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用 BaseFunctoid](../core/using-basefunctoid.md)   
 [开发自定义引用 Functoid](../core/developing-a-custom-referenced-functoid.md)   
 [自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)