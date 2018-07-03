---
title: 如何管理现有链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacb316d9783692dd55cbdbbbda92b6f55d98a3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982886"
---
# <a name="how-to-manage-existing-links"></a><span data-ttu-id="8c013-102">如何管理现有链接</span><span class="sxs-lookup"><span data-stu-id="8c013-102">How to Manage Existing Links</span></span>
<span data-ttu-id="8c013-103">有时候您可能需要更改链接的源或目标，命名或重命名链接，或删除链接。</span><span class="sxs-lookup"><span data-stu-id="8c013-103">Sometimes you may need to change the source or destination of a link, name or rename a link, or delete a link.</span></span> <span data-ttu-id="8c013-104">本主题为执行以上类型的链接操作提供了分步说明。</span><span class="sxs-lookup"><span data-stu-id="8c013-104">This topic provides step-by-step instructions for performing these types of link operations.</span></span>  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a><span data-ttu-id="8c013-105">更改链接的源或目标</span><span class="sxs-lookup"><span data-stu-id="8c013-105">To change the source or destination of a link</span></span>  
  
1.  <span data-ttu-id="8c013-106">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="8c013-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="8c013-107">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="8c013-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="8c013-108">将该链接的终结点拖至要连接的新 schema 节点或 functoid。</span><span class="sxs-lookup"><span data-stu-id="8c013-108">Drag either endpoint of the link to the new schema node or functoid to which you want it to connect it.</span></span>  
  
     <span data-ttu-id="8c013-109">拖动终结点时，光标将变为十字线。</span><span class="sxs-lookup"><span data-stu-id="8c013-109">As you drag an endpoint, the cursor becomes a crosshair.</span></span> <span data-ttu-id="8c013-110">如果指向无法接受链接的 schema 节点或 functoid（或其他对象），光标将变为带有贯穿线的圆形。</span><span class="sxs-lookup"><span data-stu-id="8c013-110">If you point to a schema node or functoid (or other object) which cannot accept the link, the cursor becomes a circle with a line through it.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8c013-111">如果具有两个或多个连接到某个 functoid 的输入链接，并将这些输入链接中的一个或多个重定向到源架构中的其他节点或其他 functoid，则可能不会保留原始 functoid 的输入参数顺序。　</span><span class="sxs-lookup"><span data-stu-id="8c013-111">If you have two or more input links connected to a functoid and you redirect one or more of those input links to other nodes in the source schema or to other functoids, the order of the input parameters to the original functoid may not be preserved.</span></span> <span data-ttu-id="8c013-112">使用**配置\<Functoid\> Functoid**对话框以查看输入参数的生成顺序以及其重新排序，如有必要。</span><span class="sxs-lookup"><span data-stu-id="8c013-112">Use the **Configure \<Functoid\> Functoid** dialog box to review the resulting order of the input parameters and to reorder them if necessary.</span></span> <span data-ttu-id="8c013-113">有关对 functoid 的输入的参数重新排序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="8c013-113">For more information about reordering the input parameters of a functoid, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span>  
  
### <a name="to-setedit-the-label-of-a-link"></a><span data-ttu-id="8c013-114">设置/编辑链接的标签的步骤</span><span class="sxs-lookup"><span data-stu-id="8c013-114">To set/edit the label of a link</span></span>  
  
1. <span data-ttu-id="8c013-115">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="8c013-115">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="8c013-116">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="8c013-116">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="8c013-117">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供链接时使用的 （新） 名称**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="8c013-117">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a (new) name for the link using the **Label** property.</span></span>  
  
### <a name="to-delete-a-link"></a><span data-ttu-id="8c013-118">删除链接</span><span class="sxs-lookup"><span data-stu-id="8c013-118">To delete a link</span></span>  
  
1.  <span data-ttu-id="8c013-119">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="8c013-119">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="8c013-120">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="8c013-120">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="8c013-121">上**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="8c013-121">On the **Edit** menu, click **Delete**.</span></span>  
  
     <span data-ttu-id="8c013-122">此外可以按 DELETE 键或右键单击该链接，单击**删除**快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="8c013-122">You can also press the DELETE key or right-click the link and click **Delete** on the shortcut menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8c013-123">您可以批量选择多个链接和/或 functoid，然后一次性将其删除。</span><span class="sxs-lookup"><span data-stu-id="8c013-123">You can bulk-select multiple link(s) and/or functoid(s) and then delete them in one operation.</span></span> <span data-ttu-id="8c013-124">可以撤消或重做链接和/或 functoid 的批量删除。</span><span class="sxs-lookup"><span data-stu-id="8c013-124">You can undo or redo the bulk deletion of link(s) and/or functoid(s).</span></span> <span data-ttu-id="8c013-125">有关撤消和重做操作有关的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="8c013-125">For more information about undo and redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c013-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c013-126">See Also</span></span>  
 [<span data-ttu-id="8c013-127">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="8c013-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)