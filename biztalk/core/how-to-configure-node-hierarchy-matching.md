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
ms.openlocfilehash: 00de1b7431fd942451d99b958746d209fcdf427d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386246"
---
# <a name="how-to-configure-node-hierarchy-matching"></a><span data-ttu-id="dd249-102">如何配置节点层次级别匹配</span><span class="sxs-lookup"><span data-stu-id="dd249-102">How to Configure Node Hierarchy Matching</span></span>
<span data-ttu-id="dd249-103">当在映射中创建一个链接时，BizTalk 映射器将自动创建编译器链接以实现您绘制的链接。</span><span class="sxs-lookup"><span data-stu-id="dd249-103">When you create a link in a map, the BizTalk Mapper automatically creates compiler links to implement the link you have drawn.</span></span> <span data-ttu-id="dd249-104">**目标链接**链接的属性控制 BizTalk 映射器绘制编译器链接的方式。</span><span class="sxs-lookup"><span data-stu-id="dd249-104">The **Target Links** property of a link controls how the BizTalk Mapper draws the compiler links.</span></span> <span data-ttu-id="dd249-105">本主题提供有关如何设置目标链接的信息。</span><span class="sxs-lookup"><span data-stu-id="dd249-105">This topic provides information about how to set the target links.</span></span>  
  
 <span data-ttu-id="dd249-106">**源链接**属性指定如何从源节点检索值并将应用于目标节点。</span><span class="sxs-lookup"><span data-stu-id="dd249-106">The **Source Links** property specifies how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="dd249-107">有关如何设置源链接的信息，请参阅[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)。</span><span class="sxs-lookup"><span data-stu-id="dd249-107">For information about how to set source links, see [How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd249-108">此操作需要 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="dd249-108">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-set-the-target-links-property"></a><span data-ttu-id="dd249-109">若要设置目标链接属性</span><span class="sxs-lookup"><span data-stu-id="dd249-109">To set the Target Links property</span></span>  
  
1. <span data-ttu-id="dd249-110">在映射网格页上，单击你想要设置目标链接属性的链接。</span><span class="sxs-lookup"><span data-stu-id="dd249-110">On the map grid page, click a link to which you want to set the target links property.</span></span>  
  
2. <span data-ttu-id="dd249-111">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**属性**窗口中，设置**目标链接**属性设置为以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="dd249-111">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**Properties** window, set the **Target Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="dd249-112">**平展链接。**</span><span class="sxs-lookup"><span data-stu-id="dd249-112">**Flatten Links.**</span></span> <span data-ttu-id="dd249-113">源记录节点中的层次结构平展至目标架构中的链接到记录节点。</span><span class="sxs-lookup"><span data-stu-id="dd249-113">The hierarchy in the source record node is flattened to the linked-to-record node in the destination schema.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="dd249-114">默认情况下，BizTalk 映射器设置**目标链接**属性设置为**平展**。</span><span class="sxs-lookup"><span data-stu-id="dd249-114">By default, the BizTalk Mapper sets the **Target Links** property to **Flatten**.</span></span>  
  
   -   <span data-ttu-id="dd249-115">**匹配项的链接上而下。**</span><span class="sxs-lookup"><span data-stu-id="dd249-115">**Match Links Top Down.**</span></span> <span data-ttu-id="dd249-116">匹配节点已关闭-到-级别执行顶部。</span><span class="sxs-lookup"><span data-stu-id="dd249-116">Node matching is performed level-to-level from the top down.</span></span>  
  
   -   <span data-ttu-id="dd249-117">**下到上匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="dd249-117">**Match Links Bottom Up.**</span></span> <span data-ttu-id="dd249-118">匹配节点由到-级别执行从底部。</span><span class="sxs-lookup"><span data-stu-id="dd249-118">Node matching is performed level-to-level from the bottom up.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd249-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd249-119">See Also</span></span>  
 <span data-ttu-id="dd249-120">[节点层次级别匹配](../core/node-hierarchy-level-matching.md) </span><span class="sxs-lookup"><span data-stu-id="dd249-120">[Node-Hierarchy Level Matching](../core/node-hierarchy-level-matching.md) </span></span>  
 <span data-ttu-id="dd249-121">[编译器指令和链接](../core/compiler-directives-and-links.md) </span><span class="sxs-lookup"><span data-stu-id="dd249-121">[Compiler Directives and Links](../core/compiler-directives-and-links.md) </span></span>  
 [<span data-ttu-id="dd249-122">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="dd249-122">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)