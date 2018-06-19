---
title: 如何管理现有链接 |Microsoft 文档
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
ms.openlocfilehash: 7cdc505f98f61dd7259c8893b526ff094128df42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970139"
---
# <a name="how-to-manage-existing-links"></a><span data-ttu-id="64132-102">如何管理现有链接</span><span class="sxs-lookup"><span data-stu-id="64132-102">How to Manage Existing Links</span></span>
<span data-ttu-id="64132-103">有时候您可能需要更改链接的源或目标，命名或重命名链接，或删除链接。</span><span class="sxs-lookup"><span data-stu-id="64132-103">Sometimes you may need to change the source or destination of a link, name or rename a link, or delete a link.</span></span> <span data-ttu-id="64132-104">本主题为执行以上类型的链接操作提供了分步说明。</span><span class="sxs-lookup"><span data-stu-id="64132-104">This topic provides step-by-step instructions for performing these types of link operations.</span></span>  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a><span data-ttu-id="64132-105">更改链接的源或目标</span><span class="sxs-lookup"><span data-stu-id="64132-105">To change the source or destination of a link</span></span>  
  
1.  <span data-ttu-id="64132-106">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="64132-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="64132-107">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="64132-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="64132-108">将该链接的终结点拖至要连接的新 schema 节点或 functoid。</span><span class="sxs-lookup"><span data-stu-id="64132-108">Drag either endpoint of the link to the new schema node or functoid to which you want it to connect it.</span></span>  
  
     <span data-ttu-id="64132-109">拖动终结点时，光标将变为十字线。</span><span class="sxs-lookup"><span data-stu-id="64132-109">As you drag an endpoint, the cursor becomes a crosshair.</span></span> <span data-ttu-id="64132-110">如果指向无法接受链接的 schema 节点或 functoid（或其他对象），光标将变为带有贯穿线的圆形。</span><span class="sxs-lookup"><span data-stu-id="64132-110">If you point to a schema node or functoid (or other object) which cannot accept the link, the cursor becomes a circle with a line through it.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64132-111">如果具有两个或多个连接到某个 functoid 的输入链接，并将这些输入链接中的一个或多个重定向到源架构中的其他节点或其他 functoid，则可能不会保留原始 functoid 的输入参数顺序。　</span><span class="sxs-lookup"><span data-stu-id="64132-111">If you have two or more input links connected to a functoid and you redirect one or more of those input links to other nodes in the source schema or to other functoids, the order of the input parameters to the original functoid may not be preserved.</span></span> <span data-ttu-id="64132-112">使用**配置\<Functoid\> Functoid**对话框查看生成的输入参数的顺序并对其重新排序，如有必要。</span><span class="sxs-lookup"><span data-stu-id="64132-112">Use the **Configure \<Functoid\> Functoid** dialog box to review the resulting order of the input parameters and to reorder them if necessary.</span></span> <span data-ttu-id="64132-113">有关重新排序 functoid 的输入的参数的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="64132-113">For more information about reordering the input parameters of a functoid, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span>  
  
### <a name="to-setedit-the-label-of-a-link"></a><span data-ttu-id="64132-114">设置/编辑链接的标签的步骤</span><span class="sxs-lookup"><span data-stu-id="64132-114">To set/edit the label of a link</span></span>  
  
1.  <span data-ttu-id="64132-115">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="64132-115">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="64132-116">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="64132-116">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="64132-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供链接时使用的 （新） 名称**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="64132-117">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a (new) name for the link using the **Label** property.</span></span>  
  
### <a name="to-delete-a-link"></a><span data-ttu-id="64132-118">删除链接</span><span class="sxs-lookup"><span data-stu-id="64132-118">To delete a link</span></span>  
  
1.  <span data-ttu-id="64132-119">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="64132-119">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="64132-120">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="64132-120">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="64132-121">上**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="64132-121">On the **Edit** menu, click **Delete**.</span></span>  
  
     <span data-ttu-id="64132-122">此外可以按 DELETE 键或右键单击该链接并单击**删除**快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="64132-122">You can also press the DELETE key or right-click the link and click **Delete** on the shortcut menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64132-123">您可以批量选择多个链接和/或 functoid，然后一次性将其删除。</span><span class="sxs-lookup"><span data-stu-id="64132-123">You can bulk-select multiple link(s) and/or functoid(s) and then delete them in one operation.</span></span> <span data-ttu-id="64132-124">可以撤消或重做链接和/或 functoid 的批量删除。</span><span class="sxs-lookup"><span data-stu-id="64132-124">You can undo or redo the bulk deletion of link(s) and/or functoid(s).</span></span> <span data-ttu-id="64132-125">有关撤消和重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="64132-125">For more information about undo and redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64132-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64132-126">See Also</span></span>  
 [<span data-ttu-id="64132-127">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="64132-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)