---
title: 如何自定义颜色和字体在 BizTalk 映射程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.options.colors
ms.assetid: 494e4d70-8159-4721-9378-85bfc3c3d6f2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d9e3c118afc4ef0ca369be17b36f439c5885e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250389"
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a><span data-ttu-id="31afe-102">如何自定义 BizTalk 映射器中的颜色和字体</span><span class="sxs-lookup"><span data-stu-id="31afe-102">How to Customize Colors and Font in BizTalk Mapper</span></span>
<span data-ttu-id="31afe-103">您可以更改与不同类型的链接关联的颜色，以及网格视图中选定对象的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-103">You can change the colors associated with various types of links and the color of selected objects in the Grid view.</span></span> <span data-ttu-id="31afe-104">还可以更改用于显示架构树节点的字体。</span><span class="sxs-lookup"><span data-stu-id="31afe-104">You can also change the font used to display the schema tree nodes.</span></span> <span data-ttu-id="31afe-105">本主题提供了执行这些更改的分步说明。</span><span class="sxs-lookup"><span data-stu-id="31afe-105">This topic provides step-by-step instructions for making such changes.</span></span>  
  
 <span data-ttu-id="31afe-106">还可以选择为 BizTalk 映射器自定义常规设置。</span><span class="sxs-lookup"><span data-stu-id="31afe-106">You can also choose to customize the general settings for BizTalk Mapper.</span></span> <span data-ttu-id="31afe-107">有关如何选择的设置的信息，请参阅[如何在 BizTalk 映射程序自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="31afe-107">For information on how to choose the settings, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31afe-108">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="31afe-108">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a><span data-ttu-id="31afe-109">更改 BizTalk 映射器中使用的颜色和字体</span><span class="sxs-lookup"><span data-stu-id="31afe-109">To change the colors and font used in BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="31afe-110">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。</span><span class="sxs-lookup"><span data-stu-id="31afe-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="31afe-111">在**选项**对话框框中，展开**BizTalk 映射程序**节点，，然后单击**颜色和字体**。</span><span class="sxs-lookup"><span data-stu-id="31afe-111">In the **Options** dialog box, expand the **BizTalk Mapper** node, and then click **Colors & Fonts**.</span></span>  
  
     <span data-ttu-id="31afe-112">![选择颜色和字体](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span><span class="sxs-lookup"><span data-stu-id="31afe-112">![Select colors and fonts](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span></span>  
  
3.  <span data-ttu-id="31afe-113">通过使用与各个颜色属性关联的下拉颜色选取器，更改不同类型的链接、编译器警告、网格前景和网格背景的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-113">Change the colors for the various types of links, compiler warnings, grid foreground, and grid background by using the drop-down color picker associated with each color property.</span></span>  
  
     <span data-ttu-id="31afe-114">有以下颜色选项：</span><span class="sxs-lookup"><span data-stu-id="31afe-114">The following color choices are available:</span></span>  
  
    -   <span data-ttu-id="31afe-115">**子节点链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-115">**Child Node Links.**</span></span> <span data-ttu-id="31afe-116">。用于绘制折叠父级的子项的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-116">The color used for drawing links of collapsed parent’s children.</span></span>  
  
    -   <span data-ttu-id="31afe-117">**编译器错误。**</span><span class="sxs-lookup"><span data-stu-id="31afe-117">**Compiler Errors.**</span></span> <span data-ttu-id="31afe-118">。用于绘制编译器错误的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-118">The color used for drawing the compiler error.</span></span>  
  
    -   <span data-ttu-id="31afe-119">**编译器提供的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-119">**Compiler Links.**</span></span> <span data-ttu-id="31afe-120">。编译器链接的颜色，编译器链接是编译器指令链接。</span><span class="sxs-lookup"><span data-stu-id="31afe-120">The color of compiler links, which are the compiler directive links.</span></span> <span data-ttu-id="31afe-121">如果设置了从源架构树中的字段指向目标架构树中的字段的链接，则会自动创建编译器指令链接。</span><span class="sxs-lookup"><span data-stu-id="31afe-121">They are links that are automatically created when a link is set from a field in the source schema tree to a field in the destination schema tree.</span></span>  
  
    -   <span data-ttu-id="31afe-122">**为灰色的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-122">**Dimmed Links.**</span></span> <span data-ttu-id="31afe-123">用于绘制未选中或未突出显示的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-123">The color used to draw links that are not selected or highlighted.</span></span>  
  
    -   <span data-ttu-id="31afe-124">**弹性的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-124">**Elastic Links.**</span></span> <span data-ttu-id="31afe-125">。弹性链接的颜色，弹性链接是指从源架构树拖至目标架构树的简单的值复制链接。</span><span class="sxs-lookup"><span data-stu-id="31afe-125">The color of elastic links, which are simple value-copy links that are dragged from the source schema tree to the destination schema tree.</span></span> <span data-ttu-id="31afe-126">在建立链接后，该链接的颜色将改为固定链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-126">After the link is made, the color of the link changes to the color for fixed links.</span></span>  
  
    -   <span data-ttu-id="31afe-127">**常规链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-127">**General Links.**</span></span> <span data-ttu-id="31afe-128">用于绘制在视图中，有两个 ends 时未选择任何内容的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-128">The color used to draw links that have both the ends in the view, when nothing is selected.</span></span>  
  
    -   <span data-ttu-id="31afe-129">**网格的背景。**</span><span class="sxs-lookup"><span data-stu-id="31afe-129">**Grid Background.**</span></span> <span data-ttu-id="31afe-130">。网格页中背景的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-130">The color of the background in grid pages.</span></span>  
  
    -   <span data-ttu-id="31afe-131">**网格线。**</span><span class="sxs-lookup"><span data-stu-id="31afe-131">**Grid Lines.**</span></span> <span data-ttu-id="31afe-132">。用于绘制网格线的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-132">The color used for drawing the grid lines.</span></span>  
  
    -   <span data-ttu-id="31afe-133">**突出显示的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-133">**Highlighted Links.**</span></span> <span data-ttu-id="31afe-134">。用于突出显示链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-134">The color used for highlighting links.</span></span>  
  
    -   <span data-ttu-id="31afe-135">**指示匹配的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-135">**Indicative Match Links.**</span></span> <span data-ttu-id="31afe-136">用于绘制指示匹配的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-136">The color used to draw indicative matches.</span></span>  
  
    -   <span data-ttu-id="31afe-137">**部分超出作用域的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-137">**Partially Out of Scope Links.**</span></span> <span data-ttu-id="31afe-138">用于绘制只有一端在视图中的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-138">The color used to draw links that have only one end in view.</span></span>  
  
    -   <span data-ttu-id="31afe-139">**架构节点字体颜色。**</span><span class="sxs-lookup"><span data-stu-id="31afe-139">**Schema Node Font Color.**</span></span> <span data-ttu-id="31afe-140">用于架构树节点的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-140">The color used for schema tree nodes.</span></span>  
  
    -   <span data-ttu-id="31afe-141">**搜索结果。**</span><span class="sxs-lookup"><span data-stu-id="31afe-141">**Search Results.**</span></span> <span data-ttu-id="31afe-142">。用于绘制架构树中的搜索匹配项的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-142">The color used for drawing search matches on the schema tree.</span></span>  
  
    -   <span data-ttu-id="31afe-143">**所选网格对象。**</span><span class="sxs-lookup"><span data-stu-id="31afe-143">**Selected Grid Objects.**</span></span> <span data-ttu-id="31afe-144">。用于绘制网格图面中的所选内容的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-144">The color used for drawing the selection in the grid surface.</span></span>  
  
    -   <span data-ttu-id="31afe-145">**完全超出作用域的链接。**</span><span class="sxs-lookup"><span data-stu-id="31afe-145">**Totally Out of Scope Links.**</span></span> <span data-ttu-id="31afe-146">用于绘制两端都不在视图中的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="31afe-146">The color used to draw links that have both ends out of the view.</span></span>  
  
4.  <span data-ttu-id="31afe-147">单击省略号 (**...**) 按钮位于右侧**架构节点字体**属性值框。</span><span class="sxs-lookup"><span data-stu-id="31afe-147">Click the ellipsis (**…**) button located at the right end of the **Schema node font** property value box.</span></span>  
  
5.  <span data-ttu-id="31afe-148">在**字体**在主编辑窗口中的视图对话框中，更改使用的字体。</span><span class="sxs-lookup"><span data-stu-id="31afe-148">In the **Font** dialog box, change the font used in the views in the main editing window.</span></span>  
  
6.  <span data-ttu-id="31afe-149">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="31afe-149">Click **OK**.</span></span> <span data-ttu-id="31afe-150">根据所作选择应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="31afe-150">The settings are applied as chosen.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="31afe-151">如果不想使用自定义的设置，请单击**还原默认值**中**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="31afe-151">If you do not want to use the customized settings, click **Restore Defaults** in the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31afe-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31afe-152">See Also</span></span>  
 [<span data-ttu-id="31afe-153">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="31afe-153">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)