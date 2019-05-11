---
title: 创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27051cdb72d4cae58edaf5e78d091ea973caf988
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353731"
---
# <a name="creating-maps"></a><span data-ttu-id="184ed-102">创建映射</span><span class="sxs-lookup"><span data-stu-id="184ed-102">Creating Maps</span></span>
<span data-ttu-id="184ed-103">上一个选项卡中显示为 BizTalk 映射器的主用户界面[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="184ed-103">The primary user interface for BizTalk Mapper is displayed on a tab within the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="184ed-104">此显示分成三个窗格。</span><span class="sxs-lookup"><span data-stu-id="184ed-104">This display is divided into three panes.</span></span> <span data-ttu-id="184ed-105">左窗格中显示为树的源架构。</span><span class="sxs-lookup"><span data-stu-id="184ed-105">The left pane displays the source schema as a tree.</span></span> <span data-ttu-id="184ed-106">右窗格中显示为树的目标架构。</span><span class="sxs-lookup"><span data-stu-id="184ed-106">The right pane displays the destination schema as a tree.</span></span> <span data-ttu-id="184ed-107">中间窗格中显示为多个网页的网格。</span><span class="sxs-lookup"><span data-stu-id="184ed-107">The middle pane displays the grid as multiple pages.</span></span> <span data-ttu-id="184ed-108">若要指示你想要将映射到目标架构源架构中的数据，请记录你想要映射的字段之间绘制线条。</span><span class="sxs-lookup"><span data-stu-id="184ed-108">To indicate how you want to map data from the source schema to the destination schema, you draw lines between the records and fields you want to map.</span></span> <span data-ttu-id="184ed-109">这些线条称为*链接*，它们是最基本的方法指定的数据的映射。</span><span class="sxs-lookup"><span data-stu-id="184ed-109">These lines are called *links*, and they are the most basic way to specify the mapping of data.</span></span> <span data-ttu-id="184ed-110">有关链接记录和字段的详细信息，请参阅[映射中的链接](../core/links-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="184ed-110">For more information about linking records and fields, see [Links in Maps](../core/links-in-maps.md).</span></span>  
  
 <span data-ttu-id="184ed-111">如果你想要实现更高级的映射方法，可以使用 functoid。</span><span class="sxs-lookup"><span data-stu-id="184ed-111">If you want to implement more advanced mapping methods, you can use functoids.</span></span> <span data-ttu-id="184ed-112">Functoid 是 BizTalk 映射器中的选项卡上提供的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="184ed-112">Functoids are tools available on BizTalk Mapper tabs within the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="184ed-113">它们使您能够创建映射，以执行更复杂的操作，如：</span><span class="sxs-lookup"><span data-stu-id="184ed-113">They enable you to create maps to perform more complex operations, such as:</span></span>  
  
- <span data-ttu-id="184ed-114">源架构中的两个字段的值相加，并将结果放入目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="184ed-114">Adding the values in two fields in a source schema and putting the result in a field in the destination schema.</span></span>  
  
- <span data-ttu-id="184ed-115">计算循环记录并将结果放入目标架构中的字段中的字段的平均值。</span><span class="sxs-lookup"><span data-stu-id="184ed-115">Calculating the average value of a field in a looping record and putting the result in a field in the destination schema.</span></span>  
  
- <span data-ttu-id="184ed-116">编写自定义脚本操作根据你的业务需求的实例数据。</span><span class="sxs-lookup"><span data-stu-id="184ed-116">Writing a custom script to manipulate instance data as appropriate for your business needs.</span></span>  
  
  <span data-ttu-id="184ed-117">有关 functoid 的详细信息，请参阅[映射中的 Functoid](../core/functoids-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="184ed-117">For more information about functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span>  
  
  <span data-ttu-id="184ed-118">BizTalk 映射器可以支持到详细又复杂循环记录和层次结构的许多不同的映射方案从简单的父子关系。</span><span class="sxs-lookup"><span data-stu-id="184ed-118">BizTalk Mapper can support many different mapping scenarios from simple parent-child relationships to detailed, complex looping of records and hierarchies.</span></span> <span data-ttu-id="184ed-119">创建映射时，请考虑以下方法：</span><span class="sxs-lookup"><span data-stu-id="184ed-119">Consider the following when you create maps:</span></span>  
  
- <span data-ttu-id="184ed-120">BizTalk 映射器不支持合并和排序。</span><span class="sxs-lookup"><span data-stu-id="184ed-120">BizTalk Mapper does not support merge and sort.</span></span>  
  
- <span data-ttu-id="184ed-121">如果源和目标架构结构非常不同，就可以，不能在单个映射中完成转换。</span><span class="sxs-lookup"><span data-stu-id="184ed-121">If the source and target schema structures are extremely different, it is possible that the transformation cannot be done in a single map.</span></span> <span data-ttu-id="184ed-122">您可能需要双传递。</span><span class="sxs-lookup"><span data-stu-id="184ed-122">You may need a double pass.</span></span>  
  
- <span data-ttu-id="184ed-123">**循环**functoid 非常灵活而且功能强大，但您将无法再检测到源架构上的值的更改以开始目标循环的下一个迭代时中断迭代。</span><span class="sxs-lookup"><span data-stu-id="184ed-123">**Looping** functoids are flexible and powerful, yet you will not be able to break up the iteration when a change in value on the source schema is detected to start the next iteration of the target loop.</span></span>  
  
- <span data-ttu-id="184ed-124">你可以在方法外部变量声明**脚本**functoid，这会导致变量处于映射生存期的作用域。</span><span class="sxs-lookup"><span data-stu-id="184ed-124">You can declare a variable outside the method in a **Scripting** functoid, which results in the variable being in scope for the life of the map.</span></span> <span data-ttu-id="184ed-125">因此，可以使用**脚本**functoid 之间的转换作用域区域保留值。</span><span class="sxs-lookup"><span data-stu-id="184ed-125">Therefore, you can use the **Scripting** functoid for holding values between scope areas of the transformation.</span></span>  
  
  <span data-ttu-id="184ed-126">处理的所有数据[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时必须采用 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="184ed-126">All data processed by [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at run time must be in XML format.</span></span> <span data-ttu-id="184ed-127">所有非 XML 数据必须转换为等效之前映射的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="184ed-127">All non-XML data must be translated to an equivalent XML format before mapping.</span></span> <span data-ttu-id="184ed-128">同样，映射过程何时完成，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用映射操作的输出创建贸易合作伙伴或向其发送数据的应用程序识别的文件格式。</span><span class="sxs-lookup"><span data-stu-id="184ed-128">Similarly, when the mapping process is complete, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the output of a mapping operation to create a file format that is recognized by the trading partner or application to which the data is sent.</span></span>  
  
  <span data-ttu-id="184ed-129">BizTalk 映射器包括一个编译器。</span><span class="sxs-lookup"><span data-stu-id="184ed-129">BizTalk Mapper includes a compiler.</span></span> <span data-ttu-id="184ed-130">此工具级组件将生成可扩展样式表语言转换 (XSLT) 转换或转换为输出实例消息的输入的实例消息所需。</span><span class="sxs-lookup"><span data-stu-id="184ed-130">This tool-level component generates the Extensible Stylesheet Language Transformations (XSLT) needed to transform or translate input instance messages to output instance messages.</span></span>  
  
  <span data-ttu-id="184ed-131">本部分提供有关使用 BizTalk 映射器创建两个架构之间的映射的特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="184ed-131">This section provides task-specific information about using BizTalk Mapper to create the mapping between two schemas.</span></span> <span data-ttu-id="184ed-132">它假设已打开，并且已选择源和目标架构的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="184ed-132">It assumes that you already have BizTalk Mapper open, and have chosen your source and destination schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="184ed-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="184ed-133">In This Section</span></span>  
  
-   [<span data-ttu-id="184ed-134">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="184ed-134">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)  
  
-   [<span data-ttu-id="184ed-135">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="184ed-135">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [<span data-ttu-id="184ed-136">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="184ed-136">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [<span data-ttu-id="184ed-137">如何创建在无映射</span><span class="sxs-lookup"><span data-stu-id="184ed-137">How to Create a Map without Maps</span></span>](../core/how-to-create-a-map-without-maps.md)  
  
-   [<span data-ttu-id="184ed-138">管理默认映射器行为使用\<mapsource\></span><span class="sxs-lookup"><span data-stu-id="184ed-138">Managing Default Mapper Behavior Using \<mapsource\></span></span>](../core/managing-default-mapper-behavior-using-mapsource.md)