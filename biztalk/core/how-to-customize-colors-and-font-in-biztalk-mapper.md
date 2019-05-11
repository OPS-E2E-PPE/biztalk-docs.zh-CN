---
title: 如何自定义的颜色和字体在 BizTalk 映射器 |Microsoft Docs
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
ms.openlocfilehash: 25c4981e083352bbba24a6579083dc4023605cba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338899"
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a><span data-ttu-id="0216c-102">如何自定义的颜色和字体在 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="0216c-102">How to Customize Colors and Font in BizTalk Mapper</span></span>
<span data-ttu-id="0216c-103">您可以更改与不同类型的链接和网格视图中的所选对象的颜色相关联的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-103">You can change the colors associated with various types of links and the color of selected objects in the Grid view.</span></span> <span data-ttu-id="0216c-104">此外可以更改用于显示架构树节点的字体。</span><span class="sxs-lookup"><span data-stu-id="0216c-104">You can also change the font used to display the schema tree nodes.</span></span> <span data-ttu-id="0216c-105">本主题提供执行这些更改的分步说明。</span><span class="sxs-lookup"><span data-stu-id="0216c-105">This topic provides step-by-step instructions for making such changes.</span></span>  
  
 <span data-ttu-id="0216c-106">您还可以选择自定义 BizTalk 映射器的常规设置。</span><span class="sxs-lookup"><span data-stu-id="0216c-106">You can also choose to customize the general settings for BizTalk Mapper.</span></span> <span data-ttu-id="0216c-107">有关如何选择的设置的信息，请参阅[如何在 BizTalk 映射器中自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="0216c-107">For information on how to choose the settings, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0216c-108">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="0216c-108">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a><span data-ttu-id="0216c-109">若要更改颜色和 BizTalk 映射器中使用的字体</span><span class="sxs-lookup"><span data-stu-id="0216c-109">To change the colors and font used in BizTalk Mapper</span></span>  
  
1. <span data-ttu-id="0216c-110">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。</span><span class="sxs-lookup"><span data-stu-id="0216c-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2. <span data-ttu-id="0216c-111">在中**选项**对话框框中，展开**BizTalk 映射器**节点，，然后单击**颜色和字体**。</span><span class="sxs-lookup"><span data-stu-id="0216c-111">In the **Options** dialog box, expand the **BizTalk Mapper** node, and then click **Colors & Fonts**.</span></span>  
  
    <span data-ttu-id="0216c-112">![选择颜色和字体](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span><span class="sxs-lookup"><span data-stu-id="0216c-112">![Select colors and fonts](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span></span>  
  
3. <span data-ttu-id="0216c-113">通过使用与每个颜色属性相关联的下拉颜色选取器更改为各种类型的链接、 编译器警告、 网格前景和网格背景的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-113">Change the colors for the various types of links, compiler warnings, grid foreground, and grid background by using the drop-down color picker associated with each color property.</span></span>  
  
    <span data-ttu-id="0216c-114">可用以下颜色选项如下：</span><span class="sxs-lookup"><span data-stu-id="0216c-114">The following color choices are available:</span></span>  
  
   -   <span data-ttu-id="0216c-115">**子节点链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-115">**Child Node Links.**</span></span> <span data-ttu-id="0216c-116">用于绘制折叠的父级的子项的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-116">The color used for drawing links of collapsed parent’s children.</span></span>  
  
   -   <span data-ttu-id="0216c-117">**编译器错误。**</span><span class="sxs-lookup"><span data-stu-id="0216c-117">**Compiler Errors.**</span></span> <span data-ttu-id="0216c-118">用于绘制编译器错误的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-118">The color used for drawing the compiler error.</span></span>  
  
   -   <span data-ttu-id="0216c-119">**编译器链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-119">**Compiler Links.**</span></span> <span data-ttu-id="0216c-120">编译器链接的颜色，是指编译器指令链接。</span><span class="sxs-lookup"><span data-stu-id="0216c-120">The color of compiler links, which are the compiler directive links.</span></span> <span data-ttu-id="0216c-121">它们是将链接从源架构树中的某个字段从设置到目标架构树中的字段时自动创建的链接。</span><span class="sxs-lookup"><span data-stu-id="0216c-121">They are links that are automatically created when a link is set from a field in the source schema tree to a field in the destination schema tree.</span></span>  
  
   -   <span data-ttu-id="0216c-122">**灰显的链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-122">**Dimmed Links.**</span></span> <span data-ttu-id="0216c-123">用于绘制未选中或未突出显示的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-123">The color used to draw links that are not selected or highlighted.</span></span>  
  
   -   <span data-ttu-id="0216c-124">**弹性链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-124">**Elastic Links.**</span></span> <span data-ttu-id="0216c-125">弹性链接是从源架构树拖到目标架构树的简单的值复制链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-125">The color of elastic links, which are simple value-copy links that are dragged from the source schema tree to the destination schema tree.</span></span> <span data-ttu-id="0216c-126">链接之后进行，链接更改为固定链接的颜色的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-126">After the link is made, the color of the link changes to the color for fixed links.</span></span>  
  
   -   <span data-ttu-id="0216c-127">**常规链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-127">**General Links.**</span></span> <span data-ttu-id="0216c-128">用于绘制两端在视图中，当未选择任何内容的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-128">The color used to draw links that have both the ends in the view, when nothing is selected.</span></span>  
  
   -   <span data-ttu-id="0216c-129">**网格背景。**</span><span class="sxs-lookup"><span data-stu-id="0216c-129">**Grid Background.**</span></span> <span data-ttu-id="0216c-130">网格页中背景的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-130">The color of the background in grid pages.</span></span>  
  
   -   <span data-ttu-id="0216c-131">**网格线。**</span><span class="sxs-lookup"><span data-stu-id="0216c-131">**Grid Lines.**</span></span> <span data-ttu-id="0216c-132">用于绘制网格线的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-132">The color used for drawing the grid lines.</span></span>  
  
   -   <span data-ttu-id="0216c-133">**突出显示的链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-133">**Highlighted Links.**</span></span> <span data-ttu-id="0216c-134">用于突出显示链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-134">The color used for highlighting links.</span></span>  
  
   -   <span data-ttu-id="0216c-135">**指示匹配的链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-135">**Indicative Match Links.**</span></span> <span data-ttu-id="0216c-136">用于绘制指示匹配的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-136">The color used to draw indicative matches.</span></span>  
  
   -   <span data-ttu-id="0216c-137">**部分所有作用域链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-137">**Partially Out of Scope Links.**</span></span> <span data-ttu-id="0216c-138">用于绘制具有只有一端在视图中的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-138">The color used to draw links that have only one end in view.</span></span>  
  
   -   <span data-ttu-id="0216c-139">**架构节点字体颜色。**</span><span class="sxs-lookup"><span data-stu-id="0216c-139">**Schema Node Font Color.**</span></span> <span data-ttu-id="0216c-140">使用架构树节点的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-140">The color used for schema tree nodes.</span></span>  
  
   -   <span data-ttu-id="0216c-141">**搜索结果。**</span><span class="sxs-lookup"><span data-stu-id="0216c-141">**Search Results.**</span></span> <span data-ttu-id="0216c-142">用于绘制架构树上的搜索匹配项的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-142">The color used for drawing search matches on the schema tree.</span></span>  
  
   -   <span data-ttu-id="0216c-143">**选定的网格对象。**</span><span class="sxs-lookup"><span data-stu-id="0216c-143">**Selected Grid Objects.**</span></span> <span data-ttu-id="0216c-144">用于绘制网格图面中的所选内容的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-144">The color used for drawing the selection in the grid surface.</span></span>  
  
   -   <span data-ttu-id="0216c-145">**完全超出作用域的链接。**</span><span class="sxs-lookup"><span data-stu-id="0216c-145">**Totally Out of Scope Links.**</span></span> <span data-ttu-id="0216c-146">用于绘制两端不在视图的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="0216c-146">The color used to draw links that have both ends out of the view.</span></span>  
  
4. <span data-ttu-id="0216c-147">单击省略号 (**...**) 按钮位于右侧**架构节点字体**属性值框。</span><span class="sxs-lookup"><span data-stu-id="0216c-147">Click the ellipsis (**…**) button located at the right end of the **Schema node font** property value box.</span></span>  
  
5. <span data-ttu-id="0216c-148">在中**字体**对话框中，更改主编辑窗口中的视图中使用的字体。</span><span class="sxs-lookup"><span data-stu-id="0216c-148">In the **Font** dialog box, change the font used in the views in the main editing window.</span></span>  
  
6. <span data-ttu-id="0216c-149">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0216c-149">Click **OK**.</span></span> <span data-ttu-id="0216c-150">选择应用的设置。</span><span class="sxs-lookup"><span data-stu-id="0216c-150">The settings are applied as chosen.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="0216c-151">如果不想使用自定义的设置，请单击**还原为默认值**中**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="0216c-151">If you do not want to use the customized settings, click **Restore Defaults** in the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0216c-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="0216c-152">See Also</span></span>  
 [<span data-ttu-id="0216c-153">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="0216c-153">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)