---
title: "创建映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8831e0d76c2bb4483bc1012ed7345c760b87bdf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-maps"></a><span data-ttu-id="52c1b-102">创建映射</span><span class="sxs-lookup"><span data-stu-id="52c1b-102">Creating Maps</span></span>
<span data-ttu-id="52c1b-103">在选项卡上显示 BizTalk 映射程序的主要用户界面[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="52c1b-103">The primary user interface for BizTalk Mapper is displayed on a tab within the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="52c1b-104">此显示分成三个窗格。</span><span class="sxs-lookup"><span data-stu-id="52c1b-104">This display is divided into three panes.</span></span> <span data-ttu-id="52c1b-105">左窗格以树视图的形式显示源架构。</span><span class="sxs-lookup"><span data-stu-id="52c1b-105">The left pane displays the source schema as a tree.</span></span> <span data-ttu-id="52c1b-106">右窗格以树视图的形式显示目标架构。</span><span class="sxs-lookup"><span data-stu-id="52c1b-106">The right pane displays the destination schema as a tree.</span></span> <span data-ttu-id="52c1b-107">中间窗格以多个页面的形式显示网格。</span><span class="sxs-lookup"><span data-stu-id="52c1b-107">The middle pane displays the grid as multiple pages.</span></span> <span data-ttu-id="52c1b-108">为了指示要如何将数据从源架构映射到目标架构，需在要映射的记录和字段之间绘制线条。</span><span class="sxs-lookup"><span data-stu-id="52c1b-108">To indicate how you want to map data from the source schema to the destination schema, you draw lines between the records and fields you want to map.</span></span> <span data-ttu-id="52c1b-109">这些行被称为*链接*，并且它们是指定的数据的映射的最基本方法。</span><span class="sxs-lookup"><span data-stu-id="52c1b-109">These lines are called *links*, and they are the most basic way to specify the mapping of data.</span></span> <span data-ttu-id="52c1b-110">有关链接记录和字段的详细信息，请参阅[Maps 中的链接](../core/links-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="52c1b-110">For more information about linking records and fields, see [Links in Maps](../core/links-in-maps.md).</span></span>  
  
 <span data-ttu-id="52c1b-111">如果要实现更高级的映射方法，可以使用 functoid。</span><span class="sxs-lookup"><span data-stu-id="52c1b-111">If you want to implement more advanced mapping methods, you can use functoids.</span></span> <span data-ttu-id="52c1b-112">Functoid 均可在 BizTalk 映射程序中的选项卡上的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="52c1b-112">Functoids are tools available on BizTalk Mapper tabs within the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="52c1b-113">您可以使用它们来创建映射，以执行更复杂的操作，如：</span><span class="sxs-lookup"><span data-stu-id="52c1b-113">They enable you to create maps to perform more complex operations, such as:</span></span>  
  
-   <span data-ttu-id="52c1b-114">将源架构中的两个字段的值相加，然后将结果放到目标架构的字段中。</span><span class="sxs-lookup"><span data-stu-id="52c1b-114">Adding the values in two fields in a source schema and putting the result in a field in the destination schema.</span></span>  
  
-   <span data-ttu-id="52c1b-115">计算循环记录中某个字段的平均值，然后将结果放到目标架构的字段中。</span><span class="sxs-lookup"><span data-stu-id="52c1b-115">Calculating the average value of a field in a looping record and putting the result in a field in the destination schema.</span></span>  
  
-   <span data-ttu-id="52c1b-116">根据业务需求，编写自定义脚本以处理实例数据。</span><span class="sxs-lookup"><span data-stu-id="52c1b-116">Writing a custom script to manipulate instance data as appropriate for your business needs.</span></span>  
  
 <span data-ttu-id="52c1b-117">有关 functoid 的详细信息，请参阅[Maps 中的 Functoid](../core/functoids-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="52c1b-117">For more information about functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span>  
  
 <span data-ttu-id="52c1b-118">BizTalk 映射器可以支持从简单父子关系到繁琐复杂的记录和层次循环的多种不同的映射方案。</span><span class="sxs-lookup"><span data-stu-id="52c1b-118">BizTalk Mapper can support many different mapping scenarios from simple parent-child relationships to detailed, complex looping of records and hierarchies.</span></span> <span data-ttu-id="52c1b-119">创建映射时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="52c1b-119">Consider the following when you create maps:</span></span>  
  
-   <span data-ttu-id="52c1b-120">BizTalk 映射器不支持合并和排序。</span><span class="sxs-lookup"><span data-stu-id="52c1b-120">BizTalk Mapper does not support merge and sort.</span></span>  
  
-   <span data-ttu-id="52c1b-121">如果源架构结构和目标架构结构非常不同，有可能无法在单个映射中完成转换。</span><span class="sxs-lookup"><span data-stu-id="52c1b-121">If the source and target schema structures are extremely different, it is possible that the transformation cannot be done in a single map.</span></span> <span data-ttu-id="52c1b-122">您可能需要双传递。</span><span class="sxs-lookup"><span data-stu-id="52c1b-122">You may need a double pass.</span></span>  
  
-   <span data-ttu-id="52c1b-123">**循环**functoid 均灵活且功能强大，但你将无法分解迭代时将源架构上的值中检测到更改时启动目标循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="52c1b-123">**Looping** functoids are flexible and powerful, yet you will not be able to break up the iteration when a change in value on the source schema is detected to start the next iteration of the target loop.</span></span>  
  
-   <span data-ttu-id="52c1b-124">你可以声明中的方法之外的变量**脚本**functoid，这会导致变量正在的地图的整个生命周期的作用域中。</span><span class="sxs-lookup"><span data-stu-id="52c1b-124">You can declare a variable outside the method in a **Scripting** functoid, which results in the variable being in scope for the life of the map.</span></span> <span data-ttu-id="52c1b-125">因此，你可以使用**脚本**functoid 用于保存转换的范围区域之间的值。</span><span class="sxs-lookup"><span data-stu-id="52c1b-125">Therefore, you can use the **Scripting** functoid for holding values between scope areas of the transformation.</span></span>  
  
 <span data-ttu-id="52c1b-126">处理的所有数据[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时必须采用 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="52c1b-126">All data processed by [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at run time must be in XML format.</span></span> <span data-ttu-id="52c1b-127">在映射之前，所有非 XML 数据必须转换成等效的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="52c1b-127">All non-XML data must be translated to an equivalent XML format before mapping.</span></span> <span data-ttu-id="52c1b-128">同样，映射过程何时完成，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射操作的输出用于创建以识别的贸易合作伙伴或应用程序数据发送到的文件格式。</span><span class="sxs-lookup"><span data-stu-id="52c1b-128">Similarly, when the mapping process is complete, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the output of a mapping operation to create a file format that is recognized by the trading partner or application to which the data is sent.</span></span>  
  
 <span data-ttu-id="52c1b-129">BizTalk 映射器包含编译器。</span><span class="sxs-lookup"><span data-stu-id="52c1b-129">BizTalk Mapper includes a compiler.</span></span> <span data-ttu-id="52c1b-130">这一工具级组件可生成将输入实例消息转换或翻译成输出实例消息所需的可扩展样式表语言转换 (XSLT)。</span><span class="sxs-lookup"><span data-stu-id="52c1b-130">This tool-level component generates the Extensible Stylesheet Language Transformations (XSLT) needed to transform or translate input instance messages to output instance messages.</span></span>  
  
 <span data-ttu-id="52c1b-131">本部分提供有关使用 BizTalk 映射器在两个架构之间创建映射的特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="52c1b-131">This section provides task-specific information about using BizTalk Mapper to create the mapping between two schemas.</span></span> <span data-ttu-id="52c1b-132">假定您已打开 BizTalk 映射器，并已选择源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="52c1b-132">It assumes that you already have BizTalk Mapper open, and have chosen your source and destination schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52c1b-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="52c1b-133">In This Section</span></span>  
  
-   [<span data-ttu-id="52c1b-134">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="52c1b-134">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)  
  
-   [<span data-ttu-id="52c1b-135">使用链接以指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="52c1b-135">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [<span data-ttu-id="52c1b-136">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="52c1b-136">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [<span data-ttu-id="52c1b-137">如何创建没有映射图</span><span class="sxs-lookup"><span data-stu-id="52c1b-137">How to Create a Map without Maps</span></span>](../core/how-to-create-a-map-without-maps.md)  
  
-   [<span data-ttu-id="52c1b-138">管理默认映射器行为使用\<mapsource ></span><span class="sxs-lookup"><span data-stu-id="52c1b-138">Managing Default Mapper Behavior Using \<mapsource></span></span>](../core/managing-default-mapper-behavior-using-mapsource.md)