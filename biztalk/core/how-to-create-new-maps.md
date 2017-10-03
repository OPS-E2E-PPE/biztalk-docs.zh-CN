---
title: "如何创建新映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 910d79782f4332ae1d706e12a8c5dda8c399a41b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-new-maps"></a><span data-ttu-id="e4847-102">如何创建新的映射</span><span class="sxs-lookup"><span data-stu-id="e4847-102">How to Create New Maps</span></span>

## <a name="overview"></a><span data-ttu-id="e4847-103">概述</span><span class="sxs-lookup"><span data-stu-id="e4847-103">Overview</span></span>
<span data-ttu-id="e4847-104">若要生成新的 BizTalk 映射，有三个主要步骤执行：</span><span class="sxs-lookup"><span data-stu-id="e4847-104">To build a new BizTalk map, there are three high-level steps to perform:</span></span>  
  
1.  <span data-ttu-id="e4847-105">创建 BizTalk 项目中的新映射。</span><span class="sxs-lookup"><span data-stu-id="e4847-105">Create the new map within a BizTalk project.</span></span>  
  
2.  <span data-ttu-id="e4847-106">向地图添加源和目标架构。</span><span class="sxs-lookup"><span data-stu-id="e4847-106">Add the source and destination schemas to the map.</span></span>  
  
3.  <span data-ttu-id="e4847-107">生成的链接集，并可能中间 functoid 指定如何将源架构映射到目标架构。</span><span class="sxs-lookup"><span data-stu-id="e4847-107">Build the set of links and, perhaps, intermediate functoids specifying how the source schema maps to the destination schema.</span></span>  
  
 <span data-ttu-id="e4847-108">在当前上下文中，以上三个步骤中的前两个步骤被视为“创建”映射。</span><span class="sxs-lookup"><span data-stu-id="e4847-108">In the current context, the first two of these three steps is considered "creating" the map.</span></span> <span data-ttu-id="e4847-109">第三个步骤被视为“构建”映射。</span><span class="sxs-lookup"><span data-stu-id="e4847-109">The third step is considered "building" the map.</span></span> <span data-ttu-id="e4847-110">许多生成图的过程与相关的任务的分步说明，请参阅[创建更复杂的映射到使用 Functoid](../core/using-functoids-to-create-more-complex-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="e4847-110">For step-by-step instructions on many of the tasks related to the process of building the map, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
## <a name="create-a-new-map"></a><span data-ttu-id="e4847-111">创建一个新图</span><span class="sxs-lookup"><span data-stu-id="e4847-111">Create a new map</span></span> 
  
1.  <span data-ttu-id="e4847-112">右键单击 BizTalk 项目在解决方案资源管理器，选择**添加**，然后选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="e4847-112">Right-click a BizTalk project in Solution Explorer, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="e4847-113">在**添加新项**对话框中，在**模板**区域中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="e4847-113">In the **Add New Item** dialog box, in the **Templates** area, select **Map**.</span></span>  
  
3.  <span data-ttu-id="e4847-114">选择中的文本**名称**框中，键入的地图的名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="e4847-114">Select the text in the **Name** box, type a name for the map, and then select **Add**.</span></span>  
  
     <span data-ttu-id="e4847-115">BizTalk 映射程序将在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口中，显示三个不同的窗格，并排显示。</span><span class="sxs-lookup"><span data-stu-id="e4847-115">BizTalk Mapper opens in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window, showing three distinct panes, side-by-side.</span></span> <span data-ttu-id="e4847-116">从左到右，这些窗格显示的源架构，网格中 （它们可能具有多个页），和目标架构。</span><span class="sxs-lookup"><span data-stu-id="e4847-116">From left to right, these panes show the source schema, the grid (which may have multiple pages), and the destination schema.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e4847-117">不能使用适用于映射以下名称:"XmlContent"、"SourceSchemas"、"TargetSchemas"或"XsltArgumentListContent"。</span><span class="sxs-lookup"><span data-stu-id="e4847-117">You cannot use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent".</span></span> <span data-ttu-id="e4847-118">因为.NET 程序集编译为生成的 C# 代码的结果会产生命名限制，不能使用这些名称。</span><span class="sxs-lookup"><span data-stu-id="e4847-118">These names cannot be used because compilation into a .NET assembly produces naming restrictions as the result of generated C# code.</span></span>  
  
4.  <span data-ttu-id="e4847-119">在 BizTalk 映射程序中，在左窗格中，选择**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="e4847-119">In BizTalk Mapper, in the left pane, select **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="e4847-120">在**BizTalk 类型选取器**对话框框中，展开**架构**节点，选择合适的源架构中，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4847-120">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the appropriate source schema, and then select **OK**.</span></span>  

    > [!TIP] 
    > <span data-ttu-id="e4847-121">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以调整大小类型选取器窗口以查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="e4847-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
  
     <span data-ttu-id="e4847-122">如果只有单个根源架构中存在或已建立了根节点进行架构使用**根引用**属性**架构**节点，在左窗格中，并且你打开的源架构可以继续执行步骤 7。</span><span class="sxs-lookup"><span data-stu-id="e4847-122">If only a single root exists in the source schema, or a root node has been established for the schema using the **Root Reference** property of the **Schema** node, the source schema opens in the left pane, and you can proceed to step 7.</span></span>  
  
6.  <span data-ttu-id="e4847-123">如果源架构具有多个根节点，并且没有根节点建立源架构使用**架构**节点的**根引用**属性，请在**源的根节点架构**对话框中，选择适当的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4847-123">If the source schema has multiple root nodes, and no root node has been established for the source schema using the **Schema** node's **Root Reference** property, in the **Root Node for Source Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e4847-124">如果您在 BizTalk 映射程序中选择架构的根节点，然后更高版本更改**根引用**属性在架构中，下次在 BizTalk 映射程序中打开架构的根节点不会更新到新的根引用配置在 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="e4847-124">If you choose a root node for a schema in BizTalk Mapper and then later change the **Root Reference** property in the schema, the next time you open the schema in BizTalk Mapper, the root node will not update to the new root reference configured in BizTalk Editor.</span></span>  
  
7.  <span data-ttu-id="e4847-125">在 BizTalk 映射程序中，在右窗格中，选择**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="e4847-125">In BizTalk Mapper, in the right pane, select **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="e4847-126">在**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，如果有必要，请选择适当的目标架构，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4847-126">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the tree, if necessary, select the appropriate destination schema, and then select **OK**.</span></span>  
  
     <span data-ttu-id="e4847-127">如果只有单个根目标架构中存在或已建立了根节点进行目标架构使用**根引用**属性**架构**节点，目标架构打开在右窗格中，并且你将不需要执行步骤 9。</span><span class="sxs-lookup"><span data-stu-id="e4847-127">If only a single root exists in the destination schema, or a root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, the destination schema opens in the right pane, and you will not need to perform step 9.</span></span>  
  
9. <span data-ttu-id="e4847-128">如果目标架构具有多个根节点，并且没有根节点建立目标架构使用**根引用**属性**架构**节点，请在**根节点对于目标架构**对话框中，选择适当的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4847-128">If the destination schema has multiple root nodes, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for Target Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
     <span data-ttu-id="e4847-129">在右窗格中打开目标架构。</span><span class="sxs-lookup"><span data-stu-id="e4847-129">The destination schema opens in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4847-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4847-130">See Also</span></span>  
 [<span data-ttu-id="e4847-131">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="e4847-131">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)