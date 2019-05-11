---
title: 如何替换架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d71c2c4231d3de506e3efc472281cac31f2b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334930"
---
# <a name="how-to-replace-schemas"></a><span data-ttu-id="a3b94-102">如何替换架构</span><span class="sxs-lookup"><span data-stu-id="a3b94-102">How to Replace Schemas</span></span>
<span data-ttu-id="a3b94-103">可能存在你想要替换现有映射，例如当您从贸易合作伙伴收到更新的架构中的源或目标架构。</span><span class="sxs-lookup"><span data-stu-id="a3b94-103">There may be times when you want to replace either the source or destination schema in an existing map, such as when you receive an updated schema from a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3b94-104">BizTalk 映射器尝试维护保留的架构与替换的架构之间的所有现有链接。</span><span class="sxs-lookup"><span data-stu-id="a3b94-104">The BizTalk Mapper attempts to maintain all existing links between the retained schema and the replaced schema.</span></span>  
  
## <a name="replace-a-source-or-destination-schema"></a><span data-ttu-id="a3b94-105">替换为源或目标架构</span><span class="sxs-lookup"><span data-stu-id="a3b94-105">Replace a source or destination schema</span></span>  
  
1. <span data-ttu-id="a3b94-106">右键单击源或目标架构树视图，然后选择**替换为架构**。</span><span class="sxs-lookup"><span data-stu-id="a3b94-106">Right-click either the source or destination schema tree view, and then select **Replace Schema**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a3b94-107">或者，您还可以按 CTRL + M、 CTRL + S 键盘。</span><span class="sxs-lookup"><span data-stu-id="a3b94-107">Alternatively, you can also press CTRL+M, CTRL+S from the keyboard.</span></span> <span data-ttu-id="a3b94-108">有关映射器键盘快捷方式的完整列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b94-108">For a complete list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
2. <span data-ttu-id="a3b94-109">在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，选择相应的架构，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="a3b94-109">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node in the tree, select the appropriate schema, and then select **OK**.</span></span>  
  
    <span data-ttu-id="a3b94-110">![选择架构](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span><span class="sxs-lookup"><span data-stu-id="a3b94-110">![Select the Schema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span></span>  

   > [!TIP]
   > <span data-ttu-id="a3b94-111">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整大小类型选取器窗口以查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="a3b94-111">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
      
    <span data-ttu-id="a3b94-112">如果仅替换架构中存在单个根或根节点已经为替换架构使用建立**根引用**的属性**架构**节点，会打开该替换架构在相关窗格中，您不需要执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="a3b94-112">If only a single root exists in the replacement schema, or a root node has been established for the replacement schema using the **Root Reference** property of the **Schema** node, the replacement schema opens in the relevant pane, and you will not need to perform step 3.</span></span>  
  
3. <span data-ttu-id="a3b94-113">如果目标架构中存在多个根节点，并且已使用目标架构建立任何根节点**根引用**的属性**架构**节点，请在**根节点\<*源/目标*\>架构**对话框中，选择相应的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="a3b94-113">If multiple root nodes exist in the destination schema, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for \<*Source/Target*\> Schema** dialog box, select the appropriate root node, and then select **OK**.</span></span>  
  
    <span data-ttu-id="a3b94-114">该替换架构将在相关窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="a3b94-114">The replacement schema opens in the relevant pane.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a3b94-115">替换架构时，如果未找到相关的记录字段，某些链接可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="a3b94-115">While replacing schema, if relevant records/fields are not found, some links may get lost.</span></span> <span data-ttu-id="a3b94-116">只能在选择时，才替换架构**是**上**确认**对话框。</span><span class="sxs-lookup"><span data-stu-id="a3b94-116">The schema is replaced only when you select **Yes** on the **Confirmation**  dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b94-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3b94-117">See Also</span></span>  
 [<span data-ttu-id="a3b94-118">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="a3b94-118">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)