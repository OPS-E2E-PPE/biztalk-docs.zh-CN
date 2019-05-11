---
title: 开发自定义 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77419e1f-9f01-44ac-bf5b-a393f1d17f61
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e751036edf8fc74c33c492dee310df232134dec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351155"
---
# <a name="developing-custom-functoids"></a>开发自定义 Functoid
尽管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供许多 functoid 以支持一系列不同的操作，可能仍会遇到需要不同的方法的情况。 自定义 functoid 提供的方法，以便扩展中可用操作的范围[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射环境。 每个自定义 functoid 可部署.NET 程序集使用的类派生自**Microsoft.BizTalk.BaseFunctoids**。 程序集可以包含多个自定义 functoid。  
  
 您应考虑以下方案中使用自定义 functoid:  
  
- 你有特殊的验证和使用仅可通过专用旧式 API 访问的数据的字符代码字段的转换规则。  
  
- 需要加密或解密字段使用自定义业务逻辑和密钥管理。  
  
- 您需要从另一个应用程序中使用的消息的一部分生成的哈希代码。  
  
- 财务要求传输到其院系的消息包括有关每个产品类型销售总额的摘要信息。  
  
- 你想要减少映射的复杂性，合并一些相关的步骤、 使用不同的方法，或使用新的类库。  
  
- 多个映射在脚本 functoid 中使用相同的脚本代码。  
  
- 需要写入事件日志，操作失败时。  
  
  自定义 functoid 可以集成到一个解决方案，使用内联代码由直接或间接通过对一个类库，部署到全局程序集缓存中的方法的引用。 这两种类型的集成依赖于**BizTalk.BaseFunctoid**类并遵循相同的一组通用步骤：  
  
1. 创建一个新类库项目使用所选的.NET 语言。  
  
2. 使用强命名实用程序 sn.exe 创建密钥文件并将其分配给项目。  
  
3. 添加对 Microsoft.BizTalk.BaseFunctoids.dll 的引用。 此程序集包含**BaseFunctoid**基类。  
  
4. 创建一个资源文件并将其添加到项目。 添加字符串资源的 functoid 名称、 工具提示和说明。 添加一个 16 x 16 像素图像资源，以映射设计器面板上代表该 functoid。  
  
5. 实现 functoid 类，通过派生自**BaseFunctoid**、 构造函数中，在建立基本参数，然后编写 functoid 方法和所有支持方法。 程序集可以包含多个自定义 functoid。  
  
6. 部署程序集并确保新的 functoid 从工具箱面板可用。 请参阅[添加和删除自定义 Functoid 从 Visual Studio 工具箱](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)。  
  
   以下是 Floor functoid 的一个示例。  
  
```  
/// <summary>  
/// Floor Functoid - finds the floor of input  
/// </summary>  
public class FloorFunctoid : BaseFunctoid  
{  
    public FloorFunctoid()  
        : base()  
    {  
        this.ID = 11001;  
        SetupResourceAssembly("MultipleFunctoids.Resource", Assembly.GetExecutingAssembly());  
  
        SetName("NAME_FLOOR");  
        SetDescription("DESCRIPTION_FLOOR");  
        SetTooltip("DESCRIPTION_FLOOR");  
        SetBitmap("IMAGE_FLOOR");  
  
        SetExternalFunctionName(GetType().Assembly.FullName, " MultipleFunctoids.FloorFunctoid", "MathFloor");  
        this.RequiredGlobalHelperFunctions = InlineGlobalHelperFunction.IsNumeric;  
  
        AddScriptTypeSupport(ScriptType.CSharp);  
        SetMinParams(1);  
        SetMaxParams(1);  
  
        this.Category = FunctoidCategory.Math;  
        this.OutputConnectionType = ConnectionType.AllExceptRecord;  
        AddInputConnectionType(ConnectionType.AllExceptRecord);  
        this.HasSideEffects = false;  
    }  
  
    /// <summary>  
    /// To create the C# function  
    /// </summary>  
    /// <param name="scriptType">Script type</param>  
    /// <param name="numParams">Number of parameters</param>  
    /// <param name="functionNumber">Functoid number</param>  
    /// <returns>C# script</returns>  
    protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
    {  
        if (ScriptType.CSharp == scriptType)  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string MathFloor(string input)\n");  
            builder.Append("{\n");  
            builder.Append("  if(string.IsNullOrEmpty(input))\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("double d = 0.0;\n");  
            builder.Append("if (IsNumeric(input, ref d))\n");  
            builder.Append("    return Math.Floor(d).ToString(System.Globalization.CultureInfo.InvariantCulture);\n");  
            builder.Append("else\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
        else  
        {  
            return string.Empty;  
        }  
    }  
}  
  
```  
  
 此示例代码使用作为的一部分时在C#项目中，"程序集名称"必须设置为"MultipleFunctoids"。 在C#项目 （包含此代码） 应包含 Resource.resx 文件。  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 在上述代码中，值"NAME_FLOOR"、"DESCRIPTION_FLOOR"和"DESCRIPTION_FLOOR"是"密钥"的资源字符串嵌入 Resource.resx 文件中。 和"IMAGE_FLOOR"是嵌入 Resource.resx 文件中的图像的名称。 此映像将充当该 functoid 的图标。  
  
 如果未指定正确的资源键，或如果删除了 SetName 方法，则会创建没有名称的自定义 functoid，这不是较好的做法。 同样适用于 SetDescription 和 SetTooltip 方法。 始终正确使用这些方法以避免任何不需要的垃圾回收行为。 但是，如果你没有任何合适的映像以用作 functoid 的图标可以跳过 SetBitmap 方法。 在这种情况下，默认图标使用通过自定义 functoid （除非有多个无图标的 functoid），这是无害的。  
  
 有关如何创建自定义 functoid 的详细信息，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。  
  
> [!IMPORTANT]
>  某些 functoid Id 由标准/内置映射器 functoid 保留。 通常情况下，标准的映射器 functoid 使用从 1 到 10000 的 Id。 在创建自定义 functoid 时，不要使用 functoid Id 小于 10000。  
  
## <a name="in-this-section"></a>本节内容  
 本部分包含：  
  
-   [使用 BaseFunctoid](../core/using-basefunctoid.md)  
  
-   [开发自定义引用的 Functoid](../core/developing-a-custom-referenced-functoid.md)  
  
-   [开发自定义内联 Functoid](../core/developing-a-custom-inline-functoid.md)  
  
-   [开发自定义累积 Functoid](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [从 Visual Studio 工具箱添加和删除自定义 Functoid](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)