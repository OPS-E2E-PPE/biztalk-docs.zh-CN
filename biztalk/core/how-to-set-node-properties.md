---
title: 如何设置节点属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c79eac-d9ba-45e2-a6e9-770b2bcb2067
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dc0f13814808a69c4c4b9c3976e9047acde5b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255445"
---
# <a name="how-to-set-node-properties"></a><span data-ttu-id="3f790-102">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="3f790-102">How to Set Node Properties</span></span>
<span data-ttu-id="3f790-103">在将节点插入 BizTalk 架构后，通常需要对该节点属性的默认值进行更改。</span><span class="sxs-lookup"><span data-stu-id="3f790-103">After inserting a node into a BizTalk schema, you will often need to change the properties of that node from their default values.</span></span> <span data-ttu-id="3f790-104">每种类型的节点都具有不同的属性集，在这些属性集中，对一种属性的设置将会影响其他属性的可用性。</span><span class="sxs-lookup"><span data-stu-id="3f790-104">Each type of node has a distinct set of properties, and within one of those sets, the settings of one property can affect the availability of other properties.</span></span> <span data-ttu-id="3f790-105">例如，在设置之前**默认换行字符**属性**架构**节点，必须设置**默认换行字符类型**属性设置为任一**字符**或**十六进制**，从而建立你打算在其中表示以前的属性的格式。</span><span class="sxs-lookup"><span data-stu-id="3f790-105">For example, before setting the **Default Wrap Character** property of the **Schema** node, you must set the **Default Wrap Character Type** property to either **Character** or **Hexadecimal**, thereby establishing the format in which you intend to represent the former property.</span></span> <span data-ttu-id="3f790-106">此外，既不这些属性不可用，也不是整个**分析**属性它们所属的类别，除非**平面文件扩展名**通过使用**架构编辑器扩展**属性。</span><span class="sxs-lookup"><span data-stu-id="3f790-106">Further, neither of these properties is available, nor is the entire **Parse** property category to which they belong, unless **Flat File Extension** is enabled by using the **Schema Editor Extensions** property.</span></span>  

 <span data-ttu-id="3f790-107">与其支持的 XML 架构定义 (XSD) 语言一样，节点属性数量较多而且可能十分复杂。</span><span class="sxs-lookup"><span data-stu-id="3f790-107">Node properties are extensive and can be complex, as is the XML Schema definition (XSD) language that they support.</span></span> <span data-ttu-id="3f790-108">本主题只对检查和设置节点属性所涉及的通用步骤进行了简要说明。</span><span class="sxs-lookup"><span data-stu-id="3f790-108">This topic only briefly describes the general steps involved in examining and setting node properties.</span></span> <span data-ttu-id="3f790-109">有关这些属性的详细信息，包括，例如，其默认值有关的信息和允许的值，请参阅**架构属性引用**。</span><span class="sxs-lookup"><span data-stu-id="3f790-109">For detailed information about these properties, including, for example, information about their default and allowed values, see the **Schema Property Reference**.</span></span> <span data-ttu-id="3f790-110">有关更多有关详细信息的 XSD 概念和之下大部分这些节点属性的元素，请直接与信息有关[在 Web 上找到的 XSD](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="3f790-110">For even more detailed information about the XSD concepts and elements that underlie most of these node properties, refer directly to information about [XSD on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

<span data-ttu-id="3f790-111">这些属性和架构属性引用的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f790-111">More info on these properties, and the schema property reference [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

  
## <a name="examine-a-node-property-value"></a><span data-ttu-id="3f790-112">检查节点属性值</span><span class="sxs-lookup"><span data-stu-id="3f790-112">Examine a node property value</span></span>  
  
1.  <span data-ttu-id="3f790-113">在 BizTalk 编辑器中，打开包含要检查的属性的架构，然后选择包含该属性的节点。</span><span class="sxs-lookup"><span data-stu-id="3f790-113">In BizTalk Editor, open the schema that contains the property you want to examine, and then select the node that contains that property.</span></span>  
  
2.  <span data-ttu-id="3f790-114">如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="3f790-114">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3.  <span data-ttu-id="3f790-115">如有必要，可滚动“属性”窗口以查找目标属性，并记下其值。</span><span class="sxs-lookup"><span data-stu-id="3f790-115">If necessary, scroll the Properties window to find the property of interest, and note its value.</span></span>  
  
     <span data-ttu-id="3f790-116">您可以使用位于“属性”窗口顶部的按钮更改属性的排序方式，可以在其类别内按字母顺序排列，或按字母顺序排列但不考虑（或不显示）其类别。</span><span class="sxs-lookup"><span data-stu-id="3f790-116">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
## <a name="set-a-node-property-value"></a><span data-ttu-id="3f790-117">设置节点属性值</span><span class="sxs-lookup"><span data-stu-id="3f790-117">Set a node property value</span></span>  
  
1.  <span data-ttu-id="3f790-118">在 BizTalk 编辑器中，打开包含要设置的属性的架构，然后选择包含该属性的节点。</span><span class="sxs-lookup"><span data-stu-id="3f790-118">In BizTalk Editor, open the schema that contains the property you want to set, and then select the node that contains that property.</span></span>  
  
2.  <span data-ttu-id="3f790-119">如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="3f790-119">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
3.  <span data-ttu-id="3f790-120">如有必要，可滚动“属性”窗口以查找目标属性。</span><span class="sxs-lookup"><span data-stu-id="3f790-120">If necessary, scroll the Properties window to find the property of interest.</span></span>  
  
     <span data-ttu-id="3f790-121">您可以使用位于“属性”窗口顶部的按钮更改属性的排序方式，可以在其类别内按字母顺序排列，或按字母顺序排列但不考虑（或不显示）其类别。</span><span class="sxs-lookup"><span data-stu-id="3f790-121">You can use buttons at the top of the Properties window to change the way that the properties are sorted, either alphabetically within their categories, or alphabetically without regard for (or display of) their categories.</span></span>  
  
4.  <span data-ttu-id="3f790-122">在值字段中设置属性的值，该字段将位于属性名称的右侧。</span><span class="sxs-lookup"><span data-stu-id="3f790-122">Set the value of the property in the value field, which is to the right of the property name.</span></span> <span data-ttu-id="3f790-123">根据属性的类型，可以键入值或从下拉列表中选择值，而此下拉列表会在选择值字段时显示。</span><span class="sxs-lookup"><span data-stu-id="3f790-123">Depending on the type of the property, you might type a value or choose a value from the drop-down list that is displayed when the value field is selected.</span></span> <span data-ttu-id="3f790-124">对于某些属性，这两种操作均可用。</span><span class="sxs-lookup"><span data-stu-id="3f790-124">Some properties allow either operation.</span></span> <span data-ttu-id="3f790-125">某些属性显示一个省略号 (**...**) 按钮，可以设置在其中一个对话框更复杂值，例如集合、 被单击的打开。</span><span class="sxs-lookup"><span data-stu-id="3f790-125">Some properties display an ellipsis (**...**) button that when clicked opens a dialog box in which more complicated values, such as collections, can be set.</span></span>  
  
5.  <span data-ttu-id="3f790-126">如果已为该属性键入新值，请按 Enter 结束。</span><span class="sxs-lookup"><span data-stu-id="3f790-126">If you have typed a new value for the property, finish by pressing ENTER.</span></span>  
  
##  <a name="clear-a-node-property-value"></a><span data-ttu-id="3f790-127">清除的节点属性值</span><span class="sxs-lookup"><span data-stu-id="3f790-127">Clear a node property value</span></span>  
  
1.  <span data-ttu-id="3f790-128">选择包含目标属性的节点。</span><span class="sxs-lookup"><span data-stu-id="3f790-128">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="3f790-129">在属性窗口中，双击你想要清除，右键单击属性值，，然后单击属性值**删除**。</span><span class="sxs-lookup"><span data-stu-id="3f790-129">In the Properties window, double-click the property value that you want to clear, right-click the property value, and then click **Delete**.</span></span>  
  
## <a name="restore-a-node-property-to-its-default-value"></a><span data-ttu-id="3f790-130">将节点属性还原为其默认值</span><span class="sxs-lookup"><span data-stu-id="3f790-130">Restore a node property to its default value</span></span>  
  
1.  <span data-ttu-id="3f790-131">选择包含目标属性的节点。</span><span class="sxs-lookup"><span data-stu-id="3f790-131">Select the node that contains the property of interest.</span></span>  
  
2.  <span data-ttu-id="3f790-132">在属性窗口中，右键单击你想要重置为其默认值，然后单击属性名称**重置**。</span><span class="sxs-lookup"><span data-stu-id="3f790-132">In the Properties window, right-click the property name that you want to reset to its default value, and then click **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f790-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f790-133">See Also</span></span>  
 [<span data-ttu-id="3f790-134">使用现有节点</span><span class="sxs-lookup"><span data-stu-id="3f790-134">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)