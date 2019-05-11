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
ms.openlocfilehash: d857d2505d90e3dbbdefd6233e9fa337a1d8fd8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389460"
---
# <a name="developing-a-custom-inline-functoid"></a>开发自定义内联 Functoid
自定义内联 functoid 通过将复制到映射中，直接实现代码而不是由引用程序集、 类和方法名称，如自定义引用的 functoid 提供的功能。  
  
## <a name="building-inline-script"></a>生成内联脚本  
 有两种方法提供脚本以包含在映射。 选择以下方法，根据是否自定义 functoid 支持个数可变的参数：  
  
- 重写**GetInlineScriptBuffer**时自定义 functoid 接受个数可变的输入参数，并且已将**HasVariableInputs**属性设置为`true`。 如果你想要连接个数可变的字符串或在一组值中找到的最大值，例如，使用此方法。  
  
- 使用**SetScriptBuffer**不需要支持个数可变的输入参数。 您仍可以使用可选参数，但固定参数的总数。  
  
  这两种方法需要不同的实现。  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a>使用 SetScriptBuffer 提供内联代码  
 若要配置自定义 functoid 以使用内联脚本：  
  
1. 调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)以启用内联代码并设置支持的脚本类型。  
  
2. 调用**SetScriptBuffer**来设置要用于自定义 functoid 的代码。 您将调用此函数三次，并在`functionNumber`自定义累计 functoid，一次用于自定义非累计 functoid 的参数。  
  
3. 使用**SetScriptGlobalBuffer**声明内联代码使用任何全局变量。  
  
4. 使用**RequiredGlobalHelperFunctions**以指示自定义内联 functoid 的帮助器函数。  
  
   可以通过使用 StringBuilder 或常数生成脚本。 编写脚本代码的一种方法是首先编写自定义引用的 functoid，然后时消除了所有 bug，将其转换为内联将函数复制到字符串常数。  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a>使用 GetInlineScriptBuffer 提供内联代码  
 如果您的自定义内联 functoid 支持个数可变的参数，则将重写**GetInlineScriptBuffer**。 若要配置自定义 functoid 以使用内联脚本：  
  
1. 在构造函数中声明自定义 functoid 通过设置具有变量输入**HasVariableInputs**到`true`。  
  
2. 在构造函数中，调用**AddScriptTypeSupport**与[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)以启用内联代码并设置支持的脚本类型。  
  
3. 重写**GetInlineScriptBuffer**构造并返回要为自定义 functoid 在映射中使用的代码。 使用参数来生成正确的代码通过检查`scriptType`和`numParams`。 最后一个参数， `functionNumber`，应为 0。 这是因为累计函数的输入个数固定，并且不使用此机制。  
  
4. 使用**SetScriptGlobalBuffer**声明内联代码使用的全局变量。  
  
5. 使用**RequiredGlobalHelperFunctions**以指示自定义内联 functoid 的帮助器函数。  
  
   下面的代码段生成 C# 函数中传递的参数数目与`numParams`但没有使用函数体。 若要使用此代码片段，复制到你的解决方案示例，并添加代码以使用参数执行某些操作并返回一个值。  
  
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
 测试是任何开发工作中的一个重要考虑因素。 自定义内联 functoid 可能很难测试。 若要简化过程，使用一个或两个以下技术：  
  
-   检查使用自定义内联 functoid 的映射的 XSLT。  
  
-   验证输入和输出使用自定义内联 functoid 的映射。  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a>检查使用自定义内联 Functoid 的映射的 XSLT  
 此方法通常能显示逻辑问题或细微的语法问题。 它还可帮助你了解映射中会发生什么情况。  
  
 若要查看 XSLT 的映射：  
  
1.  从 Visual Studio BizTalk 项目中，单击**解决方案资源管理器**选项卡上，右键单击使用自定义内联 functoid 的映射，然后单击**验证映射**。  
  
2.  滚动输出窗口以查找 XSLT 文件的 URL。 按 CTRL 并单击要查看该文件的 URL。  
  
> [!NOTE]
>  请记住 XSLT 文件所做的任何更改不会反映在自定义 functoid。  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a>测试使用自定义内联 Functoid 的映射  
 这会测试是否按预期方式工作的映射和自定义内联 functoid。  
  
 若要测试映射：  
  
1. 从 Visual Studio BizTalk 项目中，单击**解决方案资源管理器**选项卡上，右键单击使用自定义内联 functoid 的映射，然后单击**测试映射**。  
  
2. 滚动输出窗口以查找输出文件的 URL。 按 CTRL 并单击要查看该文件的 URL。  
  
   您可以检查输入和输出值，以验证映射按预期方式。  
  
## <a name="example"></a>示例  
 下面的示例说明了如何创建用于连接两个字符串的自定义内联 functoid。 它依赖于包含三个字符串资源和 16 x 16 像素位图资源的资源文件。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 BaseFunctoid](../core/using-basefunctoid.md)   
 [开发自定义引用的 Functoid](../core/developing-a-custom-referenced-functoid.md)   
 [自定义 Functoid（BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)