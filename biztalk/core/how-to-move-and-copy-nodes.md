---
title: 如何移动和复制节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe123de8a55635aa06fc5f08ccc525690d945ec9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384531"
---
# <a name="how-to-move-and-copy-nodes"></a><span data-ttu-id="1b052-102">如何移动和复制节点</span><span class="sxs-lookup"><span data-stu-id="1b052-102">How to Move and Copy Nodes</span></span>
<span data-ttu-id="1b052-103">您可能会遇到你想要将现有节点移动到架构树中的不同位置的情况。</span><span class="sxs-lookup"><span data-stu-id="1b052-103">You will probably encounter situations where you want to move an existing node to a different location in the schema tree.</span></span> <span data-ttu-id="1b052-104">您还可以通过复制现有节点，然后将其粘贴到架构树中的其他位置来节省时间。</span><span class="sxs-lookup"><span data-stu-id="1b052-104">You might also be able to save time by making a copy of an existing node and then pasting it into a different location in the schema tree.</span></span> <span data-ttu-id="1b052-105">本主题提供执行这些任务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="1b052-105">This topic provides step-by-step instructions for performing these tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b052-106">BizTalk 编辑器支持复制和粘贴节点仅在架构，架构不之间。</span><span class="sxs-lookup"><span data-stu-id="1b052-106">BizTalk Editor supports copying and pasting nodes only within schemas, not between schemas.</span></span>  
  
### <a name="to-move-a-node-within-a-schema"></a><span data-ttu-id="1b052-107">若要将节点在架构内移动</span><span class="sxs-lookup"><span data-stu-id="1b052-107">To move a node within a schema</span></span>  
  
1.  <span data-ttu-id="1b052-108">如有必要，展开架构树以显示要移动的节点和想要将其移动到的位置。</span><span class="sxs-lookup"><span data-stu-id="1b052-108">If necessary, expand the schema tree to show both the node you are moving and the location to which you want to move it.</span></span> <span data-ttu-id="1b052-109">有关展开和折叠架构树视图的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。</span><span class="sxs-lookup"><span data-stu-id="1b052-109">For more information about expanding and collapsing the schema tree view, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
2.  <span data-ttu-id="1b052-110">单击并按住你想要移动并将其拖到树中的另一个位置的节点。</span><span class="sxs-lookup"><span data-stu-id="1b052-110">Click and hold the node that you want to move and drag it to another location in the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b052-111">当开始向下拖动向上和向下架构树中，鼠标指针将变为箭头、 节点或子箭头。</span><span class="sxs-lookup"><span data-stu-id="1b052-111">When you begin to drag the node up and down the schema tree, the mouse pointer changes to an Up, Down, or child arrow.</span></span> <span data-ttu-id="1b052-112">此箭头指示释放鼠标按钮，或者节点之前、 节点之后或作为节点的子时节点将放置的位置。</span><span class="sxs-lookup"><span data-stu-id="1b052-112">This arrow indicates where the node will be placed when you release the mouse button, either before the node, after the node, or as a child of the node.</span></span>  
  
#### <a name="to-copy-a-node-within-a-schema"></a><span data-ttu-id="1b052-113">复制架构中节点</span><span class="sxs-lookup"><span data-stu-id="1b052-113">To copy a node within a schema</span></span>  
  
1.  <span data-ttu-id="1b052-114">右键单击你想要复制，，然后单击的节点**复制**。</span><span class="sxs-lookup"><span data-stu-id="1b052-114">Right-click the node that you want to copy, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="1b052-115">右键单击**记录**要在其中插入所复制的节点，然后单击的节点或组节点**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="1b052-115">Right-click the **Record** node or group node into which you want to insert the copied node, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="1b052-116">复制节点的副本放在末尾的子节点**记录**节点或在步骤 2 中选择的组节点。</span><span class="sxs-lookup"><span data-stu-id="1b052-116">The copy of the copied node is placed at the end of the child nodes of the **Record** node or group node you selected in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b052-117">您只能使用在单个架构中的剪切/复制/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="1b052-117">You may only use cut/copy/paste functionality within a single schema.</span></span> <span data-ttu-id="1b052-118">换而言之，你不能将节点从一个架构复制到另一个架构。</span><span class="sxs-lookup"><span data-stu-id="1b052-118">In other words, you cannot copy nodes from one schema into another schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b052-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b052-119">See Also</span></span>  
 [<span data-ttu-id="1b052-120">使用现有节点</span><span class="sxs-lookup"><span data-stu-id="1b052-120">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)