---
title: 如何向映射添加基本 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94787a629fcdea0c061a73e04de127acb1deea96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343401"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a><span data-ttu-id="4b364-102">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="4b364-102">How to Add Basic Functoids to a Map</span></span>
<span data-ttu-id="4b364-103">许多 functoid 都十分易于使用。</span><span class="sxs-lookup"><span data-stu-id="4b364-103">Many functoids are very simple to use.</span></span> <span data-ttu-id="4b364-104">这些内容称为到此处以将它们与中的 functoid 区分开来的基本 functoid**高级**类别。</span><span class="sxs-lookup"><span data-stu-id="4b364-104">These are referred to here as basic functoids to distinguish them from the functoids in the **Advanced** category.</span></span> <span data-ttu-id="4b364-105">基本 functoid 组成的其余类别的 functoid 如转换、 累计、 数据库、 日期和时间、 判断、 数学、 科学记数，以及字符串。</span><span class="sxs-lookup"><span data-stu-id="4b364-105">Basic functoids comprise the remaining categories of functoids such as Conversion, Cumulative, Database, Date and Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
 <span data-ttu-id="4b364-106">基本 functoid，一般情况下，具有简单类型，如数字和字符串，作为其输入和输出链接。</span><span class="sxs-lookup"><span data-stu-id="4b364-106">Basic functoids, in general, have simple types, such as numbers and strings, as their input and output links.</span></span>  
  
 <span data-ttu-id="4b364-107">基本 functoid 的使用涉及到将其添加到网格页上，创建来自左侧，并从离开至右侧的 functoid 创建输出链接的 functoid 的输入的链接。</span><span class="sxs-lookup"><span data-stu-id="4b364-107">Using a basic functoid involves adding it to a grid page, creating input links to the functoid, coming from the left, and creating output link from the functoid, leaving to the right.</span></span> <span data-ttu-id="4b364-108">本主题提供有关这些操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="4b364-108">This topic provides step-by-step instructions for these operations.</span></span>  
  
## <a name="add-a-basic-functoid-to-a-map"></a><span data-ttu-id="4b364-109">向映射添加基本 functoid</span><span class="sxs-lookup"><span data-stu-id="4b364-109">Add a basic functoid to a map</span></span>  
  
1. <span data-ttu-id="4b364-110">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，请单击相应的选项卡，选择你想要使用的 functoid 的类别。</span><span class="sxs-lookup"><span data-stu-id="4b364-110">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the appropriate tab to select the category of the functoid you want to use.</span></span>  
  
    <span data-ttu-id="4b364-111">显示所选类别中的可用 functoid 的列表。</span><span class="sxs-lookup"><span data-stu-id="4b364-111">The list of available functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="4b364-112">你想要从工具箱拖到网格页上的相应位置使用的 functoid 拖。</span><span class="sxs-lookup"><span data-stu-id="4b364-112">Drag the functoid you want to use from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4b364-113">该 functoid 将放置上显示的网格页。</span><span class="sxs-lookup"><span data-stu-id="4b364-113">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="4b364-114">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="4b364-114">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4b364-115">如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="4b364-115">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="4b364-116">从左向右执行 Functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-116">Functoids are executed from left to right.</span></span> <span data-ttu-id="4b364-117">Functoid 的输出只能输入到其右侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-117">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
## <a name="create-input-links-to-a-basic-functoid"></a><span data-ttu-id="4b364-118">创建指向基本 functoid 的输入的链接</span><span class="sxs-lookup"><span data-stu-id="4b364-118">Create input links to a basic functoid</span></span>  
  
1. <span data-ttu-id="4b364-119">将记录或字段节点从源架构拖到显示的网格页中的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-119">Drag a record or field node from the source schema to the basic functoid in the displayed grid page.</span></span>  
  
    <span data-ttu-id="4b364-120">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-120">**- Or -**</span></span>  
  
    <span data-ttu-id="4b364-121">在显示的网格页中，将位于左侧，另一个 functoid 拖到你想要创建输入的链接的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-121">In the displayed grid page, drag another functoid, which is located farther to the left, to the basic functoid to which you want to create an input link.</span></span>  
  
    <span data-ttu-id="4b364-122">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-122">**- Or -**</span></span>  
  
    <span data-ttu-id="4b364-123">将在显示的网格页中的基本 functoid 拖至源架构中的记录或字段节点。</span><span class="sxs-lookup"><span data-stu-id="4b364-123">Drag the basic functoid in the displayed grid page to a record or field node in the source schema.</span></span>  
  
    <span data-ttu-id="4b364-124">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-124">**- Or -**</span></span>  
  
    <span data-ttu-id="4b364-125">在显示的网格页中，将你想要创建输入的链接指向所在的另一个 functoid 左侧的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-125">In the displayed grid page, drag the basic functoid to which you want to create an input link to another functoid that is located farther to the left.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4b364-126">拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。</span><span class="sxs-lookup"><span data-stu-id="4b364-126">While dragging, the moving endpoint of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="4b364-127">如果鼠标悬停在一个对象，该链接相应的第二个终结点，如可能发生数据类型不匹配时的链接的移动终结点，十字线图标更改为显示带有贯穿斜线的圆形图标。</span><span class="sxs-lookup"><span data-stu-id="4b364-127">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
2. <span data-ttu-id="4b364-128">根据需要来建立指向基本 functoid 的输入链接的完整集合 （尽管可能不是全部输入参数的集合） 重复步骤 1。</span><span class="sxs-lookup"><span data-stu-id="4b364-128">Repeat step 1 as necessary to establish the complete set of input links (though perhaps not the entire set of input parameters) to the basic functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4b364-129">有几个不需要任何输入的链接的 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-129">There are a few functoids that do not require any input links.</span></span> <span data-ttu-id="4b364-130">例如，**日期**，**时间**，并**日期和时间**中的 functoid**日期和时间**functoid 类别提供当前日期时间或日期和时间，分别在其处理实例消息。</span><span class="sxs-lookup"><span data-stu-id="4b364-130">For example, the **Date**, **Time**, and **Date and Time** functoids in the **Date and Time** functoid category provide the current date, time, or date and time, respectively, at which an instance message is being processed.</span></span> <span data-ttu-id="4b364-131">因此，它们不需要将源架构中的任何输入的参数。</span><span class="sxs-lookup"><span data-stu-id="4b364-131">Thus, they do not require any input parameters from the source schema.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="4b364-132">许多 functoid 的输入参数的顺序非常重要，如相应的 functoid 参考主题中所述 (请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。</span><span class="sxs-lookup"><span data-stu-id="4b364-132">The order of input parameters to many functoids is significant, as indicated in the corresponding functoid reference topic (see **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]).</span></span> <span data-ttu-id="4b364-133">创建链接的顺序设置为提取 functoid 的输入参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="4b364-133">The order in which you create links sets the order of input parameters to the functoid.</span></span> <span data-ttu-id="4b364-134">有关 functoid 属性和指定 functoid 输入参数的顺序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4b364-134">For more information about functoid properties and specifying the order of functoid input parameters, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="4b364-135">有关如何配置 functoid 的输入的参数的信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4b364-135">For information about how to configure the input parameters of a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="4b364-136">确保你想要链接的 functoid 或源架构节点可见在显示的网格页或源架构窗口中开始进行链接之前。</span><span class="sxs-lookup"><span data-stu-id="4b364-136">Ensure the functoids or source schema node you want to link are visible in the displayed grid page or source schema window before you begin linking.</span></span>  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a><span data-ttu-id="4b364-137">从基本 functoid 创建输出链接</span><span class="sxs-lookup"><span data-stu-id="4b364-137">Create the output link from a basic functoid</span></span>  
  
1.  <span data-ttu-id="4b364-138">将将目标架构中的记录或字段节点拖到显示的网格页中的基本 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="4b364-138">Drag a record or field node from the destination schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="4b364-139">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-139">**- Or -**</span></span>  
  
     <span data-ttu-id="4b364-140">在显示的网格页中，将位于的权限，你想要创建输出链接的基本 functoid 的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-140">In the displayed grid page, drag another functoid, which is located farther to the right, to the basic functoid to which you want to create the output link.</span></span>  
  
     <span data-ttu-id="4b364-141">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-141">**- Or -**</span></span>  
  
     <span data-ttu-id="4b364-142">将在显示的网格页中的基本 functoid 拖至目标架构中的记录或字段节点。</span><span class="sxs-lookup"><span data-stu-id="4b364-142">Drag the basic functoid in the displayed grid page to a record or field node in the destination schema.</span></span>  
  
     <span data-ttu-id="4b364-143">**- Or -**</span><span class="sxs-lookup"><span data-stu-id="4b364-143">**- Or -**</span></span>  
  
2.  <span data-ttu-id="4b364-144">在显示的网格页中，将你想要创建的输出链接指向另一个 functoid，它位于其右侧的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="4b364-144">In the displayed grid page, drag the basic functoid to which you want to create the output link to another functoid that is located farther to the right.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b364-145">确保你想要链接的 functoid 和源架构节点已经可见在显示的网格页中和源架构窗口中，分别在开始链接操作之前。</span><span class="sxs-lookup"><span data-stu-id="4b364-145">Ensure the functoids and source schema node that you want to link are already visible in the displayed grid page and source schema window, respectively, before you begin the linking operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b364-146">Functoid 链接始终尝试禁止不适当的链接，如链接源和目标数据类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="4b364-146">Functoid linking always attempts to disallow inappropriate linking, such as links where source and target data types do not match.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b364-147">拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。</span><span class="sxs-lookup"><span data-stu-id="4b364-147">While dragging, the moving end point of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="4b364-148">如果鼠标悬停在一个对象，该链接相应的第二个终结点，如可能发生数据类型不匹配时的链接的移动终结点，十字线图标更改为显示带有贯穿斜线的圆形图标。</span><span class="sxs-lookup"><span data-stu-id="4b364-148">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b364-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b364-149">See Also</span></span>  
<span data-ttu-id="4b364-150">**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4b364-150">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>