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
ms.openlocfilehash: cb6d3a08cf1cc4f22ea339d74a1b7ca2de081a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334220"
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="4abf5-102">如何设置源链接编译器值</span><span class="sxs-lookup"><span data-stu-id="4abf5-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="4abf5-103">可以使用**源链接**属性用于指定如何从源节点检索值并将应用于目标节点的链接。</span><span class="sxs-lookup"><span data-stu-id="4abf5-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="4abf5-104">本主题介绍可用选项以及如何从中进行选择。</span><span class="sxs-lookup"><span data-stu-id="4abf5-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="4abf5-105">若要设置源链接链接属性</span><span class="sxs-lookup"><span data-stu-id="4abf5-105">To set the Source Links link property</span></span>  
  
1. <span data-ttu-id="4abf5-106">在 BizTalk 映射器网格页上，单击链接以选择它。</span><span class="sxs-lookup"><span data-stu-id="4abf5-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="4abf5-107">突出显示的网格页中所选链接的终结点。</span><span class="sxs-lookup"><span data-stu-id="4abf5-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="4abf5-108">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，设置**源链接**属性设置为以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="4abf5-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="4abf5-109">**复制名称。**</span><span class="sxs-lookup"><span data-stu-id="4abf5-109">**Copy Name.**</span></span> <span data-ttu-id="4abf5-110">源架构中节点的名称用作目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="4abf5-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
   -   <span data-ttu-id="4abf5-111">**复制文本值。**</span><span class="sxs-lookup"><span data-stu-id="4abf5-111">**Copy Text Value.**</span></span> <span data-ttu-id="4abf5-112">与源架构 （元素数据或属性值） 中的节点对应的值用作目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="4abf5-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="4abf5-113">选择此选项默认值。</span><span class="sxs-lookup"><span data-stu-id="4abf5-113">This choice is the default.</span></span> <span data-ttu-id="4abf5-114">例如，`<Node>Hello<Name>Chris</Name>Barry</Node>`会导致"Hello"。</span><span class="sxs-lookup"><span data-stu-id="4abf5-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
   -   <span data-ttu-id="4abf5-115">**复制文本和子内容值。**</span><span class="sxs-lookup"><span data-stu-id="4abf5-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="4abf5-116">对应于记录节点和所有子节点和及其子节点的值的值，在源架构 （元素数据和属性值） 组合作为目标架构中链接节点的值。</span><span class="sxs-lookup"><span data-stu-id="4abf5-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="4abf5-117">例如，`<Node>Hello<Name>Chris</Name>Barry</Node>`会导致"Hello Chris Barry"。</span><span class="sxs-lookup"><span data-stu-id="4abf5-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4abf5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4abf5-118">See Also</span></span>  
 <span data-ttu-id="4abf5-119">[使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="4abf5-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="4abf5-120">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="4abf5-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)