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
ms.openlocfilehash: fc424533a859f33a139c081897164e9f5db25b2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019892"
---
# <a name="developing-custom-functoids"></a><span data-ttu-id="8b907-102">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b907-102">Developing Custom Functoids</span></span>
<span data-ttu-id="8b907-103">尽管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供许多 functoid 以支持一系列不同的操作，您可能仍会遇到需要其他方法的情况。</span><span class="sxs-lookup"><span data-stu-id="8b907-103">Although [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides many functoids to support a range of diverse operations, you will likely encounter a situation that requires a different approach.</span></span> <span data-ttu-id="8b907-104">自定义 functoid 提供的方法可扩展 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 映射环境中可用操作的范围。</span><span class="sxs-lookup"><span data-stu-id="8b907-104">Custom functoids provide a way for you to extend the range of operations available within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapping environment.</span></span> <span data-ttu-id="8b907-105">每个自定义 functoid 可部署.NET 程序集使用的类派生自**Microsoft.BizTalk.BaseFunctoids**。</span><span class="sxs-lookup"><span data-stu-id="8b907-105">Each custom functoid is deployed as a .NET assembly using classes derived from **Microsoft.BizTalk.BaseFunctoids**.</span></span> <span data-ttu-id="8b907-106">一个程序集可包含多个自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="8b907-106">An assembly can contain more than one custom functoid.</span></span>  
  
 <span data-ttu-id="8b907-107">在以下情况下可以考虑使用自定义 functoid：</span><span class="sxs-lookup"><span data-stu-id="8b907-107">You should consider using a custom functoid in the following scenarios:</span></span>  
  
- <span data-ttu-id="8b907-108">您对使用只能通过专用旧式 API 访问的数据的字符代码字段应用特殊的验证和转换规则。</span><span class="sxs-lookup"><span data-stu-id="8b907-108">You have special validation and conversion rules for a character code field using data that is only accessible through a proprietary legacy API.</span></span>  
  
- <span data-ttu-id="8b907-109">您需要使用自定义业务逻辑和密钥管理来加密或解密字段。</span><span class="sxs-lookup"><span data-stu-id="8b907-109">You need to encrypt or decrypt fields using custom business logic and key management.</span></span>  
  
- <span data-ttu-id="8b907-110">您需要从部分消息生成哈希代码以用于其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b907-110">You need to generate a hash code from part of the message for use in another application.</span></span>  
  
- <span data-ttu-id="8b907-111">财务要求传输到他们部门的消息包含有关每种产品类型销售总额的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="8b907-111">Accounting requests that messages transmitted to their department include summary information about total sales by each product type.</span></span>  
  
- <span data-ttu-id="8b907-112">您希望通过合并一些相关步骤、使用其他方法或使用新的类库来降低映射的复杂性。</span><span class="sxs-lookup"><span data-stu-id="8b907-112">You want to reduce the complexity of a map by combining several related steps, by using a different approach, or by using new class libraries.</span></span>  
  
- <span data-ttu-id="8b907-113">多个映射在脚本 functoid 中使用相同的脚本代码。</span><span class="sxs-lookup"><span data-stu-id="8b907-113">More than one map is using the same script code in a script functoid.</span></span>  
  
- <span data-ttu-id="8b907-114">您需要将操作失败写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="8b907-114">You need to write to the event log when an operation fails.</span></span>  
  
  <span data-ttu-id="8b907-115">使用内联代码可直接将自定义 functoid 集成到解决方案中，也可以通过引用部署在全局程序集缓存中的类库的方法来间接集成。</span><span class="sxs-lookup"><span data-stu-id="8b907-115">Custom functoids can be integrated into a solution directly by using inline code or indirectly by reference to a method in a class library deployed into the global assembly cache.</span></span> <span data-ttu-id="8b907-116">这两种类型的集成依赖于**BizTalk.BaseFunctoid**类并遵循相同的一组通用步骤：</span><span class="sxs-lookup"><span data-stu-id="8b907-116">Both types of integration rely on the **BizTalk.BaseFunctoid** class and follow the same set of general steps:</span></span>  
  
1. <span data-ttu-id="8b907-117">使用您选择的 .NET 语言创建新的类库项目。</span><span class="sxs-lookup"><span data-stu-id="8b907-117">Create a new class library project using the .NET language of your choice.</span></span>  
  
2. <span data-ttu-id="8b907-118">使用强名称实用程序 sn.exe 创建密钥文件并将其指定给项目。</span><span class="sxs-lookup"><span data-stu-id="8b907-118">Using the strong-naming utility sn.exe, create a keyfile and assign it to the project.</span></span>  
  
3. <span data-ttu-id="8b907-119">添加对 Microsoft.BizTalk.BaseFunctoids.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="8b907-119">Add a reference to Microsoft.BizTalk.BaseFunctoids.dll.</span></span> <span data-ttu-id="8b907-120">此程序集包含**BaseFunctoid**基类。</span><span class="sxs-lookup"><span data-stu-id="8b907-120">This assembly contains the **BaseFunctoid** base class.</span></span>  
  
4. <span data-ttu-id="8b907-121">创建资源文件并将其添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="8b907-121">Create a resource file and add it to the project.</span></span> <span data-ttu-id="8b907-122">为 functoid 名称、工具提示和说明添加字符串资源。</span><span class="sxs-lookup"><span data-stu-id="8b907-122">Add string resources for the functoid name, tooltip, and description.</span></span> <span data-ttu-id="8b907-123">添加一个 16x16 像素的图像资源，在映射设计器面板上代表该 functoid。</span><span class="sxs-lookup"><span data-stu-id="8b907-123">Add a 16x16-pixel image resource to represent the functoid on the map designer palette.</span></span>  
  
5. <span data-ttu-id="8b907-124">实现 functoid 类，通过派生自**BaseFunctoid**、 构造函数中，在建立基本参数，然后编写 functoid 方法和所有支持方法。</span><span class="sxs-lookup"><span data-stu-id="8b907-124">Implement the functoid class by deriving from **BaseFunctoid**, establishing basic parameters in the constructor, and then writing the functoid method and any supporting methods.</span></span> <span data-ttu-id="8b907-125">该程序集可包含多个自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="8b907-125">The assembly can contain multiple custom functoids.</span></span>  
  
6. <span data-ttu-id="8b907-126">部署该程序集并确保可从工具箱面板访问新 functoid。</span><span class="sxs-lookup"><span data-stu-id="8b907-126">Deploy the assembly and ensure the new functoid is available from the Toolbox palette.</span></span> <span data-ttu-id="8b907-127">请参阅[添加和删除自定义 Functoid 从 Visual Studio 工具箱](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8b907-127">See [Adding and Removing Custom Functoids from the Visual Studio Toolbox](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md).</span></span>  
  
   <span data-ttu-id="8b907-128">以下是 Floor functoid 的说明。</span><span class="sxs-lookup"><span data-stu-id="8b907-128">The following is an illustration for Floor functoid.</span></span>  
  
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
  
 <span data-ttu-id="8b907-129">将此示例代码用作 C# 项目的一部分时，“程序集名称”必须设置为“MultipleFunctoids”。</span><span class="sxs-lookup"><span data-stu-id="8b907-129">While using this sample code as part of your C# project, the “Assembly name” must be set to “MultipleFunctoids”.</span></span> <span data-ttu-id="8b907-130">C# 项目（包含此代码）应包含 Resource.resx 文件。</span><span class="sxs-lookup"><span data-stu-id="8b907-130">Your C# project (containing this code) should include a Resource.resx file.</span></span>  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 <span data-ttu-id="8b907-131">在上述代码中，值“NAME_FLOOR”、“DESCRIPTION_FLOOR”和“DESCRIPTION_FLOOR”是嵌入 Resource.resx 文件中的资源字符串的“键”。</span><span class="sxs-lookup"><span data-stu-id="8b907-131">In the above code, the values “NAME_FLOOR”, “DESCRIPTION_FLOOR”, and “DESCRIPTION_FLOOR” are the “keys” of resource strings embedded in Resource.resx file.</span></span> <span data-ttu-id="8b907-132">另外，“IMAGE_FLOOR”是嵌入 Resource.resx 文件中的图像名称。</span><span class="sxs-lookup"><span data-stu-id="8b907-132">And, “IMAGE_FLOOR” is the name of an image embedded in the Resource.resx file.</span></span> <span data-ttu-id="8b907-133">此图像用作 functoid 的图标。</span><span class="sxs-lookup"><span data-stu-id="8b907-133">This image will act as an icon for the functoid.</span></span>  
  
 <span data-ttu-id="8b907-134">如果您未指定正确的资源键或删除了 SetName 方法，那么将创建一个没有名称的自定义 functoid，这并不是一种好的做法。</span><span class="sxs-lookup"><span data-stu-id="8b907-134">If you do not specify proper resource keys, or if you delete the SetName method, then a nameless custom functoid is created, which is not a good practice.</span></span> <span data-ttu-id="8b907-135">同样适用于 SetDescription 和 SetTooltip 方法。</span><span class="sxs-lookup"><span data-stu-id="8b907-135">Same holds true for SetDescription and SetTooltip methods.</span></span> <span data-ttu-id="8b907-136">始终正确使用这些方法以避免任何不需要的垃圾回收行为。</span><span class="sxs-lookup"><span data-stu-id="8b907-136">Always use these methods properly to avoid any unwanted garbage behavior.</span></span> <span data-ttu-id="8b907-137">但是，如果你没有任何合适的映像以用作 functoid 的图标可以跳过 SetBitmap 方法。</span><span class="sxs-lookup"><span data-stu-id="8b907-137">However, you may skip the SetBitmap method if you do not have any suitable images to be used as functoid icons.</span></span> <span data-ttu-id="8b907-138">在这种情况下，默认图标使用通过自定义 functoid （除非有多个无图标的 functoid），这是无害的。</span><span class="sxs-lookup"><span data-stu-id="8b907-138">In such a case, a default icon is used by the custom functoid, which is harmless (unless there are multiple icon-less functoids).</span></span>  
  
 <span data-ttu-id="8b907-139">有关如何创建自定义 functoid 的详细信息，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="8b907-139">For more information about how to create a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b907-140">某些 functoid ID 已由标准/内置映射器 functoid 保留。</span><span class="sxs-lookup"><span data-stu-id="8b907-140">Certain functoid IDs are reserved by standard/inbuilt Mapper functoids.</span></span> <span data-ttu-id="8b907-141">通常情况下，标准的映射器 functoid 使用从 1 到 10000 的 Id。</span><span class="sxs-lookup"><span data-stu-id="8b907-141">Usually, the standard Mapper functoids use the IDs from 1 to 10000.</span></span> <span data-ttu-id="8b907-142">在创建自定义 functoid 时，不要使用 functoid Id 小于 10000。</span><span class="sxs-lookup"><span data-stu-id="8b907-142">While creating custom functoids, do not use the functoid IDs less than 10000.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b907-143">本节内容</span><span class="sxs-lookup"><span data-stu-id="8b907-143">In This Section</span></span>  
 <span data-ttu-id="8b907-144">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="8b907-144">This section contains:</span></span>  
  
-   [<span data-ttu-id="8b907-145">使用 BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="8b907-145">Using BaseFunctoid</span></span>](../core/using-basefunctoid.md)  
  
-   [<span data-ttu-id="8b907-146">开发自定义引用的 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b907-146">Developing a Custom Referenced Functoid</span></span>](../core/developing-a-custom-referenced-functoid.md)  
  
-   [<span data-ttu-id="8b907-147">开发自定义内联 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b907-147">Developing a Custom Inline Functoid</span></span>](../core/developing-a-custom-inline-functoid.md)  
  
-   [<span data-ttu-id="8b907-148">开发自定义累积 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b907-148">Developing a Custom Cumulative Functoid</span></span>](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [<span data-ttu-id="8b907-149">从 Visual Studio 工具箱添加和删除自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b907-149">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b907-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b907-150">See Also</span></span>  
 [<span data-ttu-id="8b907-151">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="8b907-151">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)