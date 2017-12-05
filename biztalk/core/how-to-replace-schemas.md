---
title: "如何替换架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df444b8169d75408fe6e412135029ae2b051a6d2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-replace-schemas"></a><span data-ttu-id="584e1-102">如何替换架构</span><span class="sxs-lookup"><span data-stu-id="584e1-102">How to Replace Schemas</span></span>
<span data-ttu-id="584e1-103">有时候您可能希望替换现有映射中的源架构或目标架构，例如从贸易合作伙伴接收到更新后的架构时。</span><span class="sxs-lookup"><span data-stu-id="584e1-103">There may be times when you want to replace either the source or destination schema in an existing map, such as when you receive an updated schema from a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="584e1-104">BizTalk 映射器尝试维护被保留架构和被替换架构之间的所有现有链接。</span><span class="sxs-lookup"><span data-stu-id="584e1-104">The BizTalk Mapper attempts to maintain all existing links between the retained schema and the replaced schema.</span></span>  
  
## <a name="replace-a-source-or-destination-schema"></a><span data-ttu-id="584e1-105">将源或目标架构</span><span class="sxs-lookup"><span data-stu-id="584e1-105">Replace a source or destination schema</span></span>  
  
1.  <span data-ttu-id="584e1-106">右键单击源或目标架构树视图，然后选择**替换架构**。</span><span class="sxs-lookup"><span data-stu-id="584e1-106">Right-click either the source or destination schema tree view, and then select **Replace Schema**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="584e1-107">此外，还可以在键盘上按 Ctrl+M、Ctrl+S。</span><span class="sxs-lookup"><span data-stu-id="584e1-107">Alternatively, you can also press CTRL+M, CTRL+S from the keyboard.</span></span> <span data-ttu-id="584e1-108">映射器键盘快捷键的完整列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="584e1-108">For a complete list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
2.  <span data-ttu-id="584e1-109">在**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，选择适当的架构，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="584e1-109">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node in the tree, select the appropriate schema, and then select **OK**.</span></span>  
  
     <span data-ttu-id="584e1-110">![选择架构](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span><span class="sxs-lookup"><span data-stu-id="584e1-110">![Select the Schema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span></span>  

    > [!TIP] 
    > <span data-ttu-id="584e1-111">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以调整大小类型选取器窗口以查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="584e1-111">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
      
     <span data-ttu-id="584e1-112">如果只有单个根存在在替换模式中，或已建立了根节点进行替换架构使用**根引用**属性**架构**节点，替换架构打开在相关的窗格中，并且你将不需要执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="584e1-112">If only a single root exists in the replacement schema, or a root node has been established for the replacement schema using the **Root Reference** property of the **Schema** node, the replacement schema opens in the relevant pane, and you will not need to perform step 3.</span></span>  
  
3.  <span data-ttu-id="584e1-113">如果在目标架构中，存在多个根节点，并且没有根节点建立目标架构使用**根引用**属性**架构**节点，请在**的根节点\<*源/目标*\>架构 * * 对话框中，选择适当的根节点，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="584e1-113">If multiple root nodes exist in the destination schema, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for \<*Source/Target*\> Schema** dialog box, select the appropriate root node, and then select **OK**.</span></span>  
  
     <span data-ttu-id="584e1-114">此时，该替换架构将在相关窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="584e1-114">The replacement schema opens in the relevant pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="584e1-115">替换架构时，如果未找到相关的记录/字段，则可能会丢失某些链接。</span><span class="sxs-lookup"><span data-stu-id="584e1-115">While replacing schema, if relevant records/fields are not found, some links may get lost.</span></span> <span data-ttu-id="584e1-116">仅当你选择替换架构**是**上**确认**对话框。</span><span class="sxs-lookup"><span data-stu-id="584e1-116">The schema is replaced only when you select **Yes** on the **Confirmation**  dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584e1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="584e1-117">See Also</span></span>  
 [<span data-ttu-id="584e1-118">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="584e1-118">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)