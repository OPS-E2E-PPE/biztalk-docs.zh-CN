---
title: "开发自定义 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77419e1f-9f01-44ac-bf5b-a393f1d17f61
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5534f3209cb943fb3e2c2a63a18f9e29928be5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-functoids"></a>开发自定义 Functoid
尽管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供许多 functoid 以支持一系列不同的操作，您可能仍会遇到需要其他方法的情况。 自定义 functoid 提供的方法可扩展 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 映射环境中可用操作的范围。 每个自定义 functoid 部署因为.NET 程序集使用类派生自**Microsoft.BizTalk.BaseFunctoids**。 一个程序集可包含多个自定义 functoid。  
  
 在以下情况下可以考虑使用自定义 functoid：  
  
-   您对使用只能通过专用旧式 API 访问的数据的字符代码字段应用特殊的验证和转换规则。  
  
-   您需要使用自定义业务逻辑和密钥管理来加密或解密字段。  
  
-   您需要从部分消息生成哈希代码以用于其他应用程序。  
  
-   财务要求传输到他们部门的消息包含有关每种产品类型销售总额的摘要信息。  
  
-   您希望通过合并一些相关步骤、使用其他方法或使用新的类库来降低映射的复杂性。  
  
-   多个映射在脚本 functoid 中使用相同的脚本代码。  
  
-   您需要将操作失败写入事件日志。  
  
 使用内联代码可直接将自定义 functoid 集成到解决方案中，也可以通过引用部署在全局程序集缓存中的类库的方法来间接集成。 集成这两种类型依赖于**BizTalk.BaseFunctoid**类，并按照同一套的常规步骤：  
  
1.  使用您选择的 .NET 语言创建新的类库项目。  
  
2.  使用强名称实用程序 sn.exe 创建密钥文件并将其指定给项目。  
  
3.  添加对 Microsoft.BizTalk.BaseFunctoids.dll 的引用。 此程序集包含**BaseFunctoid**基类。  
  
4.  创建资源文件并将其添加到项目中。 为 functoid 名称、工具提示和说明添加字符串资源。 添加一个 16x16 像素的图像资源，在映射设计器面板上代表该 functoid。  
  
5.  由派生自实现 functoid 类**BaseFunctoid**、 构造函数中，在建立基本参数，然后编写 functoid 方法和任意支持的方法。 该程序集可包含多个自定义 functoid。  
  
6.  部署该程序集并确保可从工具箱面板访问新 functoid。 请参阅[添加和删除从 Visual Studio 工具箱的自定义 Functoid](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)。  
  
 以下是 Floor functoid 的说明。  
  
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
  
 将此示例代码用作 C# 项目的一部分时，“程序集名称”必须设置为“MultipleFunctoids”。 C# 项目（包含此代码）应包含 Resource.resx 文件。  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 在上述代码中，值“NAME_FLOOR”、“DESCRIPTION_FLOOR”和“DESCRIPTION_FLOOR”是嵌入 Resource.resx 文件中的资源字符串的“键”。 另外，“IMAGE_FLOOR”是嵌入 Resource.resx 文件中的图像名称。 此图像用作 functoid 的图标。  
  
 如果您未指定正确的资源键或删除了 SetName 方法，那么将创建一个没有名称的自定义 functoid，这并不是一种好的做法。 同样适用于 SetDescription 和 SetTooltip 方法。 始终正确使用这些方法来避免任何不需要的垃圾回收行为。 但是，如果你没有任何合适的映像以用作 functoid 图标可以跳过 SetBitmap 方法。 在这种情况下，使用默认图标是通过自定义 functoid，（除非有多个图标免 functoid），这是无害的。  
  
 有关如何创建自定义 functoid 的详细信息，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。  
  
> [!IMPORTANT]
>  某些 functoid ID 已由标准/内置映射器 functoid 保留。 通常情况下，标准的映射程序 functoid 使用从 1 到 10000 的 Id。 在创建自定义 functoid，不要使用 functoid Id 小于 10000。  
  
## <a name="in-this-section"></a>本节内容  
 本部分包含：  
  
-   [使用 BaseFunctoid](../core/using-basefunctoid.md)  
  
-   [开发自定义引用 Functoid](../core/developing-a-custom-referenced-functoid.md)  
  
-   [开发自定义的内联 Functoid](../core/developing-a-custom-inline-functoid.md)  
  
-   [开发自定义的累积 Functoid](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [添加和删除从 Visual Studio 工具箱的自定义 Functoid](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)