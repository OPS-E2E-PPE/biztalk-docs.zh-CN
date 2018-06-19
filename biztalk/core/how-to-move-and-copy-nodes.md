---
title: 如何移动和复制节点 |Microsoft 文档
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
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254765"
---
# <a name="how-to-move-and-copy-nodes"></a><span data-ttu-id="3ce66-102">如何移动和复制节点</span><span class="sxs-lookup"><span data-stu-id="3ce66-102">How to Move and Copy Nodes</span></span>
<span data-ttu-id="3ce66-103">您可能会遇到要将现有节点移动到架构树中的其他位置的情况。</span><span class="sxs-lookup"><span data-stu-id="3ce66-103">You will probably encounter situations where you want to move an existing node to a different location in the schema tree.</span></span> <span data-ttu-id="3ce66-104">还可以通过创建现有节点的副本，然后将其粘贴到架构树中的其他位置来节约时间。</span><span class="sxs-lookup"><span data-stu-id="3ce66-104">You might also be able to save time by making a copy of an existing node and then pasting it into a different location in the schema tree.</span></span> <span data-ttu-id="3ce66-105">本主题介绍了执行这些任务的逐步说明。</span><span class="sxs-lookup"><span data-stu-id="3ce66-105">This topic provides step-by-step instructions for performing these tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce66-106">BizTalk 编辑器仅支持在架构内复制和粘贴节点，而不支持在架构之间进行这些操作。</span><span class="sxs-lookup"><span data-stu-id="3ce66-106">BizTalk Editor supports copying and pasting nodes only within schemas, not between schemas.</span></span>  
  
### <a name="to-move-a-node-within-a-schema"></a><span data-ttu-id="3ce66-107">在架构内移动节点</span><span class="sxs-lookup"><span data-stu-id="3ce66-107">To move a node within a schema</span></span>  
  
1.  <span data-ttu-id="3ce66-108">如果需要，可以展开架构树以同时显示要移动的节点和要将该节点移动到的位置。</span><span class="sxs-lookup"><span data-stu-id="3ce66-108">If necessary, expand the schema tree to show both the node you are moving and the location to which you want to move it.</span></span> <span data-ttu-id="3ce66-109">有关展开和折叠架构树视图的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。</span><span class="sxs-lookup"><span data-stu-id="3ce66-109">For more information about expanding and collapsing the schema tree view, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
2.  <span data-ttu-id="3ce66-110">单击要移动的节点并按住鼠标按钮，将其拖至树中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="3ce66-110">Click and hold the node that you want to move and drag it to another location in the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce66-111">开始在架构树中向上或向下拖动节点时，鼠标指针将变为上箭头、下箭头或子箭头。</span><span class="sxs-lookup"><span data-stu-id="3ce66-111">When you begin to drag the node up and down the schema tree, the mouse pointer changes to an Up, Down, or child arrow.</span></span> <span data-ttu-id="3ce66-112">此箭头指示释放鼠标按钮时节点将放置到的位置：节点之前、节点之后或作为节点的子节点。</span><span class="sxs-lookup"><span data-stu-id="3ce66-112">This arrow indicates where the node will be placed when you release the mouse button, either before the node, after the node, or as a child of the node.</span></span>  
  
#### <a name="to-copy-a-node-within-a-schema"></a><span data-ttu-id="3ce66-113">在架构内复制节点</span><span class="sxs-lookup"><span data-stu-id="3ce66-113">To copy a node within a schema</span></span>  
  
1.  <span data-ttu-id="3ce66-114">右键单击你想要复制，，然后单击该节点**复制**。</span><span class="sxs-lookup"><span data-stu-id="3ce66-114">Right-click the node that you want to copy, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3ce66-115">右键单击**记录**要向其中插入复制节点，，然后单击的节点或组节点**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="3ce66-115">Right-click the **Record** node or group node into which you want to insert the copied node, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="3ce66-116">复制的节点的副本放在末尾的子节点**记录**节点或你在步骤 2 中所选的组节点。</span><span class="sxs-lookup"><span data-stu-id="3ce66-116">The copy of the copied node is placed at the end of the child nodes of the **Record** node or group node you selected in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce66-117">只能在单个架构中使用剪切/复制/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="3ce66-117">You may only use cut/copy/paste functionality within a single schema.</span></span> <span data-ttu-id="3ce66-118">换句话说，您不能将节点从一个架构复制到另一个架构中。</span><span class="sxs-lookup"><span data-stu-id="3ce66-118">In other words, you cannot copy nodes from one schema into another schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce66-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ce66-119">See Also</span></span>  
 [<span data-ttu-id="3ce66-120">使用现有节点</span><span class="sxs-lookup"><span data-stu-id="3ce66-120">Working with Existing Nodes</span></span>](../core/working-with-existing-nodes.md)