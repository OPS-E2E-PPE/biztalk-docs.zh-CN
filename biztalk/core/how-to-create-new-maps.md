---
title: 如何创建新映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9eff8e4776ea1ead46f28572e4c950b3d72d970f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385502"
---
# <a name="how-to-create-new-maps"></a><span data-ttu-id="5d835-102">如何创建新映射</span><span class="sxs-lookup"><span data-stu-id="5d835-102">How to Create New Maps</span></span>

## <a name="overview"></a><span data-ttu-id="5d835-103">概述</span><span class="sxs-lookup"><span data-stu-id="5d835-103">Overview</span></span>
<span data-ttu-id="5d835-104">若要生成新的 BizTalk 映射，有三个主要步骤执行：</span><span class="sxs-lookup"><span data-stu-id="5d835-104">To build a new BizTalk map, there are three high-level steps to perform:</span></span>  
  
1. <span data-ttu-id="5d835-105">创建新 BizTalk 项目中的映射。</span><span class="sxs-lookup"><span data-stu-id="5d835-105">Create the new map within a BizTalk project.</span></span>  
  
2. <span data-ttu-id="5d835-106">向映射添加源和目标架构。</span><span class="sxs-lookup"><span data-stu-id="5d835-106">Add the source and destination schemas to the map.</span></span>  
  
3. <span data-ttu-id="5d835-107">生成的链接集，这样一来，中间 functoid 指定如何将源架构映射到目标架构。</span><span class="sxs-lookup"><span data-stu-id="5d835-107">Build the set of links and, perhaps, intermediate functoids specifying how the source schema maps to the destination schema.</span></span>  
  
   <span data-ttu-id="5d835-108">在当前上下文中，这三个步骤的前两个被视为"创建"映射。</span><span class="sxs-lookup"><span data-stu-id="5d835-108">In the current context, the first two of these three steps is considered "creating" the map.</span></span> <span data-ttu-id="5d835-109">第三个步骤将被视为"构建"映射。</span><span class="sxs-lookup"><span data-stu-id="5d835-109">The third step is considered "building" the map.</span></span> <span data-ttu-id="5d835-110">许多与构建映射过程相关的任务的分步说明，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="5d835-110">For step-by-step instructions on many of the tasks related to the process of building the map, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
## <a name="create-a-new-map"></a><span data-ttu-id="5d835-111">创建新的映射</span><span class="sxs-lookup"><span data-stu-id="5d835-111">Create a new map</span></span> 
  
1. <span data-ttu-id="5d835-112">右键单击 BizTalk 项目在解决方案资源管理器，选择**外**，然后选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="5d835-112">Right-click a BizTalk project in Solution Explorer, select **Add**, and then select **New Item**.</span></span>  
  
2. <span data-ttu-id="5d835-113">在中**添加新项**对话框中**模板**区域中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="5d835-113">In the **Add New Item** dialog box, in the **Templates** area, select **Map**.</span></span>  
  
3. <span data-ttu-id="5d835-114">选择中的文本**名称**框中，键入映射的名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="5d835-114">Select the text in the **Name** box, type a name for the map, and then select **Add**.</span></span>  
  
    <span data-ttu-id="5d835-115">BizTalk 映射器将在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口，显示三个不同的窗格，通过并行。</span><span class="sxs-lookup"><span data-stu-id="5d835-115">BizTalk Mapper opens in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window, showing three distinct panes, side-by-side.</span></span> <span data-ttu-id="5d835-116">从左到右，两个窗格显示源架构，网格 （它们可能具有多个页面） 和目标架构。</span><span class="sxs-lookup"><span data-stu-id="5d835-116">From left to right, these panes show the source schema, the grid (which may have multiple pages), and the destination schema.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5d835-117">不能使用以下名称用于映射："XmlContent"、"SourceSchemas"、"TargetSchemas"或者"XsltArgumentListContent"。</span><span class="sxs-lookup"><span data-stu-id="5d835-117">You cannot use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent".</span></span> <span data-ttu-id="5d835-118">由于编译到.NET 程序集作为结果生成的 C# 代码所生成的命名限制，不能使用这些名称。</span><span class="sxs-lookup"><span data-stu-id="5d835-118">These names cannot be used because compilation into a .NET assembly produces naming restrictions as the result of generated C# code.</span></span>  
  
4. <span data-ttu-id="5d835-119">在 BizTalk 映射器中，在左窗格中，选择**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="5d835-119">In BizTalk Mapper, in the left pane, select **Open Source Schema**.</span></span>  
  
5. <span data-ttu-id="5d835-120">在中**BizTalk 类型选取器**对话框框中，展开**架构**节点，选择相应的源架构，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d835-120">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the appropriate source schema, and then select **OK**.</span></span>  

   > [!TIP]
   > <span data-ttu-id="5d835-121">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整大小类型选取器窗口以查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="5d835-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
  
    <span data-ttu-id="5d835-122">如果只有在源架构中，存在单个根或根节点的架构使用已建立**根引用**的属性**架构**节点，在左窗格中，并且您打开源架构可以转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="5d835-122">If only a single root exists in the source schema, or a root node has been established for the schema using the **Root Reference** property of the **Schema** node, the source schema opens in the left pane, and you can proceed to step 7.</span></span>  
  
6. <span data-ttu-id="5d835-123">如果源架构包含多个根节点，并已使用源架构建立任何根节点**架构**节点的**根引用**属性，请在**源的根节点架构**对话框中，选择相应的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d835-123">If the source schema has multiple root nodes, and no root node has been established for the source schema using the **Schema** node's **Root Reference** property, in the **Root Node for Source Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5d835-124">如果您在 BizTalk 映射器中选择架构的根节点，并随后更改**根引用**属性在架构中，下次在 BizTalk 映射器中打开该架构的根节点不会更新到新的根引用配置在 BizTalk 编辑器中。</span><span class="sxs-lookup"><span data-stu-id="5d835-124">If you choose a root node for a schema in BizTalk Mapper and then later change the **Root Reference** property in the schema, the next time you open the schema in BizTalk Mapper, the root node will not update to the new root reference configured in BizTalk Editor.</span></span>  
  
7. <span data-ttu-id="5d835-125">在 BizTalk 映射器中，在右窗格中，选择**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="5d835-125">In BizTalk Mapper, in the right pane, select **Open Destination Schema**.</span></span>  
  
8. <span data-ttu-id="5d835-126">在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，如有必要，选择相应的目标架构中，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d835-126">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the tree, if necessary, select the appropriate destination schema, and then select **OK**.</span></span>  
  
    <span data-ttu-id="5d835-127">如果只有一个根目标架构中存在或已使用目标架构建立了根节点**根引用**的属性**架构**节点，将打开目标架构在右窗格中，您不需要执行步骤 9。</span><span class="sxs-lookup"><span data-stu-id="5d835-127">If only a single root exists in the destination schema, or a root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, the destination schema opens in the right pane, and you will not need to perform step 9.</span></span>  
  
9. <span data-ttu-id="5d835-128">如果目标架构具有多个根节点，并且已使用目标架构建立任何根节点**根引用**的属性**架构**节点，请在**根节点为目标架构**对话框中，选择相应的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d835-128">If the destination schema has multiple root nodes, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for Target Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
     <span data-ttu-id="5d835-129">在右窗格中打开目标架构。</span><span class="sxs-lookup"><span data-stu-id="5d835-129">The destination schema opens in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d835-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d835-130">See Also</span></span>  
 [<span data-ttu-id="5d835-131">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="5d835-131">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)