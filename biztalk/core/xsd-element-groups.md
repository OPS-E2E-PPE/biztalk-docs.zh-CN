---
title: "XSD 元素组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b850841819ce844a10e407827d02993ce3559bad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xsd-element-groups"></a><span data-ttu-id="92dfc-102">XSD 元素组</span><span class="sxs-lookup"><span data-stu-id="92dfc-102">XSD Element Groups</span></span>
<span data-ttu-id="92dfc-103">通过在架构中使用某些结构，可以在 BizTalk 映射器生成的可扩展样式表语言转换 (XSLT) 中创建变体。</span><span class="sxs-lookup"><span data-stu-id="92dfc-103">The use of certain structures in a schema may create variations in the Extensible Stylesheet Language Transformations (XSLT) that BizTalk Mapper generates.</span></span>  
  
 <span data-ttu-id="92dfc-104">当映射中包括定义序列、所选项或所有元素组的架构时，可能会出现上述情况。</span><span class="sxs-lookup"><span data-stu-id="92dfc-104">This can occur when you include a schema in your map that defines sequence, choice, or all element groups.</span></span> <span data-ttu-id="92dfc-105">例如，如果你使用包含的架构**选项组**节点，它是你可以创建一个映射，需要两个或多个的子级**选项组**节点显示在输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="92dfc-105">For example, if you use a schema that includes a **Choice Group** node, it is possible for you to create a map that requires two or more of the children of the **Choice Group** node to appear in an output instance message.</span></span> <span data-ttu-id="92dfc-106">在这种情况下，BizTalk 映射器将在编译映射时显示警告。</span><span class="sxs-lookup"><span data-stu-id="92dfc-106">In this case, BizTalk Mapper displays a warning when you compile the map.</span></span> <span data-ttu-id="92dfc-107">警告将提示您，所映射的必填字段中只有一个字段能在运行时通过父循环的同一个迭代填充。</span><span class="sxs-lookup"><span data-stu-id="92dfc-107">The warning tells you that only one of the required fields you have mapped may be populated in the same iteration of the parent loop at run time.</span></span> <span data-ttu-id="92dfc-108">BizTalk 映射器将不显示表明映射逻辑不正确的错误消息。</span><span class="sxs-lookup"><span data-stu-id="92dfc-108">BizTalk Mapper does not give you an error message stating that your mapping logic is incorrect.</span></span>  
  
 <span data-ttu-id="92dfc-109">另一种可以在 XSLT 中生成变体情况需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="92dfc-109">Another situation in which you might generate variations in the XSLT is when the following conditions are met:</span></span>  
  
-   <span data-ttu-id="92dfc-110">**记录一个**中有一个子**字段元素 B**。</span><span class="sxs-lookup"><span data-stu-id="92dfc-110">**Record A** has a child **Field Element B**.</span></span>  
  
-   <span data-ttu-id="92dfc-111">**记录一个**和子**字段元素 B**出现一次。</span><span class="sxs-lookup"><span data-stu-id="92dfc-111">**Record A** and child **Field Element B** occur once.</span></span>  
  
-   <span data-ttu-id="92dfc-112">**记录一个**属于**选项组**重复。</span><span class="sxs-lookup"><span data-stu-id="92dfc-112">**Record A** is part of a **Choice Group** that repeats.</span></span>  
  
 <span data-ttu-id="92dfc-113">在这种情况下，BizTalk 映射器将生成包含迭代逻辑的 XSLT，以处理可能会有许多源记录变体的情形。</span><span class="sxs-lookup"><span data-stu-id="92dfc-113">In this situation, BizTalk Mapper generates XSLT that contains iteration logic to handle the possibility of the many variations of the source records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92dfc-114">对于涉及组的映射，必须明确地加以指定。</span><span class="sxs-lookup"><span data-stu-id="92dfc-114">You must be explicit with respect to mappings involving groups.</span></span> <span data-ttu-id="92dfc-115">例如，如果目标架构包含**选项组**与 A 和 B 的子节点的节点，所以不能具有 A 和 B 同时对其父组的同一迭代。</span><span class="sxs-lookup"><span data-stu-id="92dfc-115">For example, if a destination schema contains a **Choice Group** node with child nodes A and B, it is not valid to have A and B simultaneously on the same iteration of their parent group.</span></span> <span data-ttu-id="92dfc-116">BizTalk 映射器不会阻止您创建无效的映射。</span><span class="sxs-lookup"><span data-stu-id="92dfc-116">BizTalk Mapper does not prevent you from creating mappings that are not valid.</span></span> <span data-ttu-id="92dfc-117">因此，必须使用判断 functoid 设置映射，以便 A 和 B 永远不会同时出现。</span><span class="sxs-lookup"><span data-stu-id="92dfc-117">Therefore, you must use logical functoids to set up mappings in which A and B can never occur at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dfc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92dfc-118">See Also</span></span>  
 <span data-ttu-id="92dfc-119">[地图](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="92dfc-119">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="92dfc-120">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="92dfc-120">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)