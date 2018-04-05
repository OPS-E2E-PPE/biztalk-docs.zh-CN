---
title: 如何在向地图添加脚本 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e66e6ed25fd44b1e89fe5500346a7ad01d5d7ff0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a><span data-ttu-id="8543b-102">如何向映射添加“脚本”Functoid</span><span class="sxs-lookup"><span data-stu-id="8543b-102">How to Add Scripting Functoids to a Map</span></span>
<span data-ttu-id="8543b-103">**脚本**functoid，可使用自定义脚本或代码在运行时执行功能不可用。</span><span class="sxs-lookup"><span data-stu-id="8543b-103">The **Scripting** functoid enables you to use custom script or code at run time to perform functions otherwise not available.</span></span> <span data-ttu-id="8543b-104">例如，通过使用，在运行时调用的 COM 对象**脚本**functoid 和编写您自己的自定义脚本。</span><span class="sxs-lookup"><span data-stu-id="8543b-104">For example, you can call a COM object at run time by using the **Scripting** functoid and writing your own custom script.</span></span>  
  
 <span data-ttu-id="8543b-105">有关概念性信息**脚本**functoid，请参阅[脚本 Functoid](../core/scripting-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="8543b-105">For conceptual information about the **Scripting** functoid, see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="8543b-106">向映射添加“脚本”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="8543b-106">To add the Scripting functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="8543b-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="8543b-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="8543b-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="8543b-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="8543b-109">拖动**脚本**functoid![](../core/media/bts-tls-scripting.gif "bts_tls_scripting")从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="8543b-109">Drag the **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting") from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="8543b-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="8543b-111">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="8543b-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-112">如果你在构造结合使用多个 functoid 的映射，你需要考虑它们相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="8543b-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="8543b-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="8543b-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="8543b-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="8543b-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="8543b-115">选择**脚本**functoid 刚才添加到显示的网格页。</span><span class="sxs-lookup"><span data-stu-id="8543b-115">Select the **Scripting** functoid that you just added to the displayed grid page.</span></span>  
  
4.  <span data-ttu-id="8543b-116">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，单击省略号 (**...**) 与关联的按钮**脚本**属性。</span><span class="sxs-lookup"><span data-stu-id="8543b-116">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, click the ellipsis (**...**) button associated with the **Script** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-117">或者，你可以右键单击提取 functoid，，然后单击**配置 Functoid 脚本**上下文菜单中。</span><span class="sxs-lookup"><span data-stu-id="8543b-117">Alternatively, you can right-click the functoid, and then click **Configure Functoid Script** in the context menu.</span></span> <span data-ttu-id="8543b-118">**配置脚本 Functoid**对话框中将显示**脚本 Functoid 配置**选定选项卡。</span><span class="sxs-lookup"><span data-stu-id="8543b-118">The **Configure Scripting Functoid** dialog box appears with the **Script Functoid Configuration** tab selected.</span></span>  
  
5.  <span data-ttu-id="8543b-119">在**配置脚本 Functoid**对话框中，在**选择脚本类型**下拉列表中，选择你的脚本的类型。</span><span class="sxs-lookup"><span data-stu-id="8543b-119">In the **Configure Scripting Functoid** dialog box, in the **Select script type** drop-down list, select the type of your script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-120">根据所选择的脚本类型，将启用和禁用剩余对话框字段的不同子集。</span><span class="sxs-lookup"><span data-stu-id="8543b-120">Depending on your selection of script type, different subsets of the remaining dialog box fields will be enabled and disabled.</span></span>  
  
6.  <span data-ttu-id="8543b-121">如果你选择**外部程序集**作为脚本类型，使用**脚本程序集**，**脚本类**，和**脚本方法**下拉列表表，请在该顺序，以选择程序集、 类和方法，分别与此关联**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="8543b-121">If you selected **External Assembly** as the script type, use the **Script assembly**, **Script class**, and **Script method** drop-down lists, in that order, to select the assembly, class, and method, respectively, to associate with this **Scripting** functoid.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="8543b-122">外部程序集中的代码必须为线程安全代码。</span><span class="sxs-lookup"><span data-stu-id="8543b-122">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="8543b-123">在任务繁忙时，可以同时运行多个映射实例。</span><span class="sxs-lookup"><span data-stu-id="8543b-123">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-124">选择一个程序集后,**脚本类**下拉列表中会填入中该程序集的类。</span><span class="sxs-lookup"><span data-stu-id="8543b-124">After you have selected an assembly, the **Script class** drop-down list will be populated with the classes in that assembly.</span></span> <span data-ttu-id="8543b-125">同样，之后你已选择一个类，**脚本方法**下拉列表将使用该类中的方法进行填充。</span><span class="sxs-lookup"><span data-stu-id="8543b-125">Likewise, after you have selected a class, the **Script method** drop-down list will be populated with the methods in that class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-126">**内联脚本**文本框被禁用，当你选择**外部程序集**作为脚本类型。</span><span class="sxs-lookup"><span data-stu-id="8543b-126">The **Inline script** text box is disabled when you select **External Assembly** as the script type.</span></span>  
  
     <span data-ttu-id="8543b-127">如果选择了命令以外**外部程序集**作为脚本类型 （其中一个内联选项），使用**内联脚本**文本框中，在你所选的语言中输入你的脚本。</span><span class="sxs-lookup"><span data-stu-id="8543b-127">If you selected something other than **External Assembly** as the script type (one of the inline choices), use the **Inline script** text box to enter your script in the language you selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-128">为内联语言选择**脚本**functoid 包括 C#.NET、 JScript.NET、 Visual Basic.NET、 XSLT 和 XSLT 调用模板。</span><span class="sxs-lookup"><span data-stu-id="8543b-128">The inline language choices for the **Scripting** functoid include C# .NET, JScript.NET, Visual Basic .NET, XSLT, and XSLT Call Template.</span></span>  
  
     <span data-ttu-id="8543b-129">使用 C# 编写脚本时不允许使用“using”语句。</span><span class="sxs-lookup"><span data-stu-id="8543b-129">Scripting using C# does not allow "using" statements.</span></span> <span data-ttu-id="8543b-130">如果脚本需要使用任何特殊的 .Net 类，则应将相应的程序集及其依存程序集添加到 BizTalk 项目的“参考”中，并且脚本代码应该使用完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="8543b-130">If the script needs to use any special .Net classes, then the corresponding assemblies and their dependent assemblies should be added to "References" in the BizTalk project, and the script code should use fully qualified names.</span></span> <span data-ttu-id="8543b-131">如果您编写一个执行区分区域性的小写转换脚本，应按如下所示编写相应的代码段。</span><span class="sxs-lookup"><span data-stu-id="8543b-131">If you write a script to perform culture-sensitive lowercase conversion, the corresponding code fragment should be written as below.</span></span> <span data-ttu-id="8543b-132">类似限制适用于所有受支持的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="8543b-132">Similar limitations apply to all supported scripting languages.</span></span>  
  
    ```  
    string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
    ```  
  
     <span data-ttu-id="8543b-133">在脚本中，若要使用任何程序集中的类，请确保将相应程序集及其依存程序集添加到包含映射的 BizTalk 项目的“参考”中。</span><span class="sxs-lookup"><span data-stu-id="8543b-133">In the script, to use classes from any assembly, ensure you add the corresponding assembly and its dependent assemblies to “References” in the BizTalk project containing your map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-134">你可以创建自定义脚本中直接在**内联脚本**文本框中，或者你可以创建你的脚本在其他位置，并将其粘贴到**内联脚本**文本框。</span><span class="sxs-lookup"><span data-stu-id="8543b-134">You can create your custom script directly in the **Inline script** text box, or you can create your script elsewhere, and paste it into the **Inline script** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8543b-135">**脚本程序集**，**脚本类**，和**脚本方法**当你选择的内联选项之一时，会禁用的下拉列表 (内容以外**外部程序集**) 作为脚本类型。</span><span class="sxs-lookup"><span data-stu-id="8543b-135">The **Script assembly**, **Script class**, and **Script method** drop-down lists are disabled when you select one of the inline choices (something other than **External Assembly**) as the script type.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8543b-136">如果创建包含多个函数的脚本，则第一个函数将被视为主函数，其余函数只在执行主函数时进行调用。</span><span class="sxs-lookup"><span data-stu-id="8543b-136">If you create a script containing multiple functions, the first function will be treated as the main or primary function; other functions are only called if they are called in the execution of the primary function.</span></span>  
  
     <span data-ttu-id="8543b-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8543b-137">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8543b-138">如果外部程序集中的脚本或相关方法需要输入参数，请创建相应数量和类型的输入链接（就像使用基本 functoid 一样）。</span><span class="sxs-lookup"><span data-stu-id="8543b-138">If your script or the associated method in an external assembly requires input parameters, create the appropriate number and type of input links as you would for a basic functoid.</span></span>  
  
8.  <span data-ttu-id="8543b-139">在大多数情况下，你**脚本**functoid 将产生输出值用于填充目标架构中的字段或作为另一个 functoid 的输入，在很多相同方式该基本 functoid 执行。</span><span class="sxs-lookup"><span data-stu-id="8543b-139">In most circumstances, your **Scripting** functoid will produce an output value used to populate a field in the destination schema, or as input to another functoid, in much the same way that basic functoids do.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8543b-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8543b-140">See Also</span></span>  
 [<span data-ttu-id="8543b-141">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="8543b-141">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)