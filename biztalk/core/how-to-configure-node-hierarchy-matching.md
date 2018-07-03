---
title: 如何配置节点层次级别匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb785793b865e36c5b37bd6b32199ab3e34f5d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009574"
---
# <a name="how-to-configure-node-hierarchy-matching"></a><span data-ttu-id="3720f-102">如何配置节点层次级别匹配</span><span class="sxs-lookup"><span data-stu-id="3720f-102">How to Configure Node Hierarchy Matching</span></span>
<span data-ttu-id="3720f-103">在映射中创建链接时，BizTalk 映射器会自动创建编译器链接以实现您绘制的链接。</span><span class="sxs-lookup"><span data-stu-id="3720f-103">When you create a link in a map, the BizTalk Mapper automatically creates compiler links to implement the link you have drawn.</span></span> <span data-ttu-id="3720f-104">**目标链接**链接的属性控制 BizTalk 映射器绘制编译器链接的方式。</span><span class="sxs-lookup"><span data-stu-id="3720f-104">The **Target Links** property of a link controls how the BizTalk Mapper draws the compiler links.</span></span> <span data-ttu-id="3720f-105">本主题提供有关如何设置目标链接的信息。</span><span class="sxs-lookup"><span data-stu-id="3720f-105">This topic provides information about how to set the target links.</span></span>  
  
 <span data-ttu-id="3720f-106">**源链接**属性指定如何从源节点检索值并将应用于目标节点。</span><span class="sxs-lookup"><span data-stu-id="3720f-106">The **Source Links** property specifies how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="3720f-107">有关如何设置源链接的信息，请参阅[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)。</span><span class="sxs-lookup"><span data-stu-id="3720f-107">For information about how to set source links, see [How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3720f-108">此操作要求 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="3720f-108">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-set-the-target-links-property"></a><span data-ttu-id="3720f-109">设置“目标链接”属性</span><span class="sxs-lookup"><span data-stu-id="3720f-109">To set the Target Links property</span></span>  
  
1. <span data-ttu-id="3720f-110">在映射网格页上，单击您要设置目标链接属性的链接。</span><span class="sxs-lookup"><span data-stu-id="3720f-110">On the map grid page, click a link to which you want to set the target links property.</span></span>  
  
2. <span data-ttu-id="3720f-111">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**属性**窗口中，设置**目标链接**属性设置为以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="3720f-111">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**Properties** window, set the **Target Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="3720f-112">**平展链接。**</span><span class="sxs-lookup"><span data-stu-id="3720f-112">**Flatten Links.**</span></span> <span data-ttu-id="3720f-113">源记录节点中的层次将平展至目标架构中所链接到的记录节点。</span><span class="sxs-lookup"><span data-stu-id="3720f-113">The hierarchy in the source record node is flattened to the linked-to-record node in the destination schema.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="3720f-114">默认情况下，BizTalk 映射器设置**目标链接**属性设置为**平展**。</span><span class="sxs-lookup"><span data-stu-id="3720f-114">By default, the BizTalk Mapper sets the **Target Links** property to **Flatten**.</span></span>  
  
   -   <span data-ttu-id="3720f-115">**匹配项的链接上而下。**</span><span class="sxs-lookup"><span data-stu-id="3720f-115">**Match Links Top Down.**</span></span> <span data-ttu-id="3720f-116">从上向下按级别执行节点匹配。</span><span class="sxs-lookup"><span data-stu-id="3720f-116">Node matching is performed level-to-level from the top down.</span></span>  
  
   -   <span data-ttu-id="3720f-117">**下到上匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="3720f-117">**Match Links Bottom Up.**</span></span> <span data-ttu-id="3720f-118">从下向上按级别执行节点匹配。</span><span class="sxs-lookup"><span data-stu-id="3720f-118">Node matching is performed level-to-level from the bottom up.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3720f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3720f-119">See Also</span></span>  
 <span data-ttu-id="3720f-120">[节点层次级别匹配](../core/node-hierarchy-level-matching.md) </span><span class="sxs-lookup"><span data-stu-id="3720f-120">[Node-Hierarchy Level Matching](../core/node-hierarchy-level-matching.md) </span></span>  
 <span data-ttu-id="3720f-121">[编译器指令和链接](../core/compiler-directives-and-links.md) </span><span class="sxs-lookup"><span data-stu-id="3720f-121">[Compiler Directives and Links](../core/compiler-directives-and-links.md) </span></span>  
 [<span data-ttu-id="3720f-122">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="3720f-122">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)