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
ms.openlocfilehash: c033ce9dff8b5d9a07dca574d089f575b4eaa5e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008934"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a><span data-ttu-id="a2fa5-102">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="a2fa5-102">How to Add Basic Functoids to a Map</span></span>
<span data-ttu-id="a2fa5-103">许多 functoid 都十分易于使用。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-103">Many functoids are very simple to use.</span></span> <span data-ttu-id="a2fa5-104">这些内容称为到此处以将它们与中的 functoid 区分开来的基本 functoid**高级**类别。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-104">These are referred to here as basic functoids to distinguish them from the functoids in the **Advanced** category.</span></span> <span data-ttu-id="a2fa5-105">基本 functoid 由除“高级”之外的其余类别的 functoid 组成，例如“转换”、“累计”、“数据库”、“日期和时间”、“判断”、“数学”、“科学计数法”和“字符串”。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-105">Basic functoids comprise the remaining categories of functoids such as Conversion, Cumulative, Database, Date and Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
 <span data-ttu-id="a2fa5-106">通常，基本 functoid 会使用简单类型（例如数字和字符串）作为其输入链接和输出链接。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-106">Basic functoids, in general, have simple types, such as numbers and strings, as their input and output links.</span></span>  
  
 <span data-ttu-id="a2fa5-107">基本 functoid 的使用包含将其添加到网格页、创建来自左侧并指向该 functoid 的输入链接、创建来自该 functoid 并离开至右侧的输出链接。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-107">Using a basic functoid involves adding it to a grid page, creating input links to the functoid, coming from the left, and creating output link from the functoid, leaving to the right.</span></span> <span data-ttu-id="a2fa5-108">本主题提供有关这些操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-108">This topic provides step-by-step instructions for these operations.</span></span>  
  
## <a name="add-a-basic-functoid-to-a-map"></a><span data-ttu-id="a2fa5-109">向映射添加基本 functoid</span><span class="sxs-lookup"><span data-stu-id="a2fa5-109">Add a basic functoid to a map</span></span>  
  
1. <span data-ttu-id="a2fa5-110">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，请单击相应的选项卡，选择你想要使用的 functoid 的类别。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-110">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the appropriate tab to select the category of the functoid you want to use.</span></span>  
  
    <span data-ttu-id="a2fa5-111">此时，将显示所选类别的可用 functoid 的列表。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-111">The list of available functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="a2fa5-112">将要使用的 functoid 从工具箱中拖至网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-112">Drag the functoid you want to use from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-113">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-113">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="a2fa5-114">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-114">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-115">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-115">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="a2fa5-116">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-116">Functoids are executed from left to right.</span></span> <span data-ttu-id="a2fa5-117">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-117">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
## <a name="create-input-links-to-a-basic-functoid"></a><span data-ttu-id="a2fa5-118">创建指向基本 functoid 的输入的链接</span><span class="sxs-lookup"><span data-stu-id="a2fa5-118">Create input links to a basic functoid</span></span>  
  
1. <span data-ttu-id="a2fa5-119">将源架构中的记录或字段节点拖至所显示的网格页中的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-119">Drag a record or field node from the source schema to the basic functoid in the displayed grid page.</span></span>  
  
    <span data-ttu-id="a2fa5-120">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-120">**- Or -**</span></span>  
  
    <span data-ttu-id="a2fa5-121">在所显示的网格页中，将位于左侧的另一个 functoid 拖至要创建的输入链接指向的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-121">In the displayed grid page, drag another functoid, which is located farther to the left, to the basic functoid to which you want to create an input link.</span></span>  
  
    <span data-ttu-id="a2fa5-122">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-122">**- Or -**</span></span>  
  
    <span data-ttu-id="a2fa5-123">将所显示的网格页中的基本 functoid 拖至源架构中的记录或字段节点。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-123">Drag the basic functoid in the displayed grid page to a record or field node in the source schema.</span></span>  
  
    <span data-ttu-id="a2fa5-124">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-124">**- Or -**</span></span>  
  
    <span data-ttu-id="a2fa5-125">在所显示的网格页中，将要创建的输入链接指向的基本 functoid 拖至位于其左侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-125">In the displayed grid page, drag the basic functoid to which you want to create an input link to another functoid that is located farther to the left.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-126">拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-126">While dragging, the moving endpoint of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="a2fa5-127">如果将链接的移动终结点悬停在某个对象上，而该对象不适合作为该链接的第二个终结点（例如，如果存在数据类型不匹配，则可能出现此情况），则十字线图标将更改为显示带有贯穿斜线的圆形的图标。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-127">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
2. <span data-ttu-id="a2fa5-128">根据需要重复步骤 1 以建立指向基本 functoid 的输入链接的完整集（尽管可能不是全部输入参数的集合）。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-128">Repeat step 1 as necessary to establish the complete set of input links (though perhaps not the entire set of input parameters) to the basic functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-129">少数 functoid 不需要任何输入链接。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-129">There are a few functoids that do not require any input links.</span></span> <span data-ttu-id="a2fa5-130">例如，**日期**，**时间**，并**日期和时间**中的 functoid**日期和时间**functoid 类别提供当前日期时间或日期和时间，分别在其处理实例消息。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-130">For example, the **Date**, **Time**, and **Date and Time** functoids in the **Date and Time** functoid category provide the current date, time, or date and time, respectively, at which an instance message is being processed.</span></span> <span data-ttu-id="a2fa5-131">因此，这些 functoid 不需要来自源架构的任何输入参数。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-131">Thus, they do not require any input parameters from the source schema.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-132">许多 functoid 的输入参数的顺序非常重要，如相应的 functoid 参考主题中所述 (请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-132">The order of input parameters to many functoids is significant, as indicated in the corresponding functoid reference topic (see **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]).</span></span> <span data-ttu-id="a2fa5-133">创建链接的顺序规定了该 functoid 的输入参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-133">The order in which you create links sets the order of input parameters to the functoid.</span></span> <span data-ttu-id="a2fa5-134">有关 functoid 属性和指定 functoid 输入参数的顺序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-134">For more information about functoid properties and specifying the order of functoid input parameters, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="a2fa5-135">有关如何配置 functoid 的输入的参数的信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-135">For information about how to configure the input parameters of a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="a2fa5-136">确保在开始进行链接之前，要链接的 functoid 或源架构的节点在所显示的网格页或源架构窗口中可见。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-136">Ensure the functoids or source schema node you want to link are visible in the displayed grid page or source schema window before you begin linking.</span></span>  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a><span data-ttu-id="a2fa5-137">从基本 functoid 创建输出链接</span><span class="sxs-lookup"><span data-stu-id="a2fa5-137">Create the output link from a basic functoid</span></span>  
  
1.  <span data-ttu-id="a2fa5-138">将目标架构中的记录或字段节点拖至所显示的网格页中的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-138">Drag a record or field node from the destination schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="a2fa5-139">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-139">**- Or -**</span></span>  
  
     <span data-ttu-id="a2fa5-140">在所显示的网格页中，将位于右侧的另一个 functoid 拖至要创建的输出链接指向的基本 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-140">In the displayed grid page, drag another functoid, which is located farther to the right, to the basic functoid to which you want to create the output link.</span></span>  
  
     <span data-ttu-id="a2fa5-141">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-141">**- Or -**</span></span>  
  
     <span data-ttu-id="a2fa5-142">将所显示的网格页中的基本 functoid 拖至目标架构中的记录或字段节点。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-142">Drag the basic functoid in the displayed grid page to a record or field node in the destination schema.</span></span>  
  
     <span data-ttu-id="a2fa5-143">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="a2fa5-143">**- Or -**</span></span>  
  
2.  <span data-ttu-id="a2fa5-144">在所显示的网格页中，将要创建的输出链接指向的基本 functoid 拖至位于其右侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-144">In the displayed grid page, drag the basic functoid to which you want to create the output link to another functoid that is located farther to the right.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2fa5-145">确保在开始进行链接操作之前，要链接的 functoid 和源架构的节点已分别在所显示的网格页中和源架构窗口中可见。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-145">Ensure the functoids and source schema node that you want to link are already visible in the displayed grid page and source schema window, respectively, before you begin the linking operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2fa5-146">Functoid 链接会始终尝试禁止使用不适当的链接，例如其中的源数据类型与目标数据类型不匹配的链接。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-146">Functoid linking always attempts to disallow inappropriate linking, such as links where source and target data types do not match.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2fa5-147">在拖动过程中，链接的移动终结点（与该链接的锚定终结点相对应）将更改为十字线图标，以便可以更准确地对准第二个终结点。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-147">While dragging, the moving end point of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="a2fa5-148">如果将链接的移动终结点悬停在某个对象上，而该对象不适合作为该链接的第二个终结点（例如，如果存在数据类型不匹配，则可能出现此情况），则十字线图标将更改为显示带有贯穿斜线的圆形的图标。</span><span class="sxs-lookup"><span data-stu-id="a2fa5-148">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fa5-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fa5-149">See Also</span></span>  
<span data-ttu-id="a2fa5-150">**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a2fa5-150">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>