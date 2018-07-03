---
title: 如何设置源链接编译器值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ad777bc5b4df2717d20fd95aa60fdf5d59d1f6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975166"
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="e8100-102">如何设置源链接编译器值</span><span class="sxs-lookup"><span data-stu-id="e8100-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="e8100-103">可以使用**源链接**属性用于指定如何从源节点检索值并将应用于目标节点的链接。</span><span class="sxs-lookup"><span data-stu-id="e8100-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="e8100-104">本主题介绍了可用的选项，并介绍如何进行选择。</span><span class="sxs-lookup"><span data-stu-id="e8100-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="e8100-105">设置“源链接”链接属性</span><span class="sxs-lookup"><span data-stu-id="e8100-105">To set the Source Links link property</span></span>  
  
1. <span data-ttu-id="e8100-106">在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。</span><span class="sxs-lookup"><span data-stu-id="e8100-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="e8100-107">网格页中所选链接的终结点将突出显示。</span><span class="sxs-lookup"><span data-stu-id="e8100-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="e8100-108">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，设置**源链接**属性设置为以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e8100-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="e8100-109">**复制名称。**</span><span class="sxs-lookup"><span data-stu-id="e8100-109">**Copy Name.**</span></span> <span data-ttu-id="e8100-110">源架构中的节点名称用作目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="e8100-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
   -   <span data-ttu-id="e8100-111">**复制文本值。**</span><span class="sxs-lookup"><span data-stu-id="e8100-111">**Copy Text Value.**</span></span> <span data-ttu-id="e8100-112">与源架构中的节点相应的值（元素数据或属性值）用作目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="e8100-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="e8100-113">此选项为默认选项。</span><span class="sxs-lookup"><span data-stu-id="e8100-113">This choice is the default.</span></span> <span data-ttu-id="e8100-114">例如，`<Node>Hello<Name>Chris</Name>Barry</Node>` 的结果为“Hello”。</span><span class="sxs-lookup"><span data-stu-id="e8100-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
   -   <span data-ttu-id="e8100-115">**复制文本和子内容值。**</span><span class="sxs-lookup"><span data-stu-id="e8100-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="e8100-116">与源架构中的记录节点相应的值、该节点所有子节点的值以及这些子节点的子节点的值（元素数据和属性值）合并为目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="e8100-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="e8100-117">例如，`<Node>Hello<Name>Chris</Name>Barry</Node>` 的结果为“Hello Chris Barry”。</span><span class="sxs-lookup"><span data-stu-id="e8100-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8100-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8100-118">See Also</span></span>  
 <span data-ttu-id="e8100-119">[使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="e8100-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="e8100-120">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="e8100-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)