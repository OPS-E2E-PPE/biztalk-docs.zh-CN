---
title: "编译器指令和链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b598638072d59e635fd75c8e00836829d9459078
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="compiler-directives-and-links"></a><span data-ttu-id="84449-102">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="84449-102">Compiler Directives and Links</span></span>
<span data-ttu-id="84449-103">您可以按每个链接配置以下两条编译器指令：</span><span class="sxs-lookup"><span data-stu-id="84449-103">You can configure the following two compiler directives on a link-by-link basis:</span></span>  
  
-   <span data-ttu-id="84449-104">从输入实例消息中检索哪些数据并将其复制为输出实例消息中相关的元素或属性值。</span><span class="sxs-lookup"><span data-stu-id="84449-104">What data from the input instance message is retrieved and copied as the relevant element or attribute value in the output instance message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84449-105">此处的数据包括用于复制元素或属性的自身名称的选项，而不包括与元素或属性关联的任何值。</span><span class="sxs-lookup"><span data-stu-id="84449-105">Data here includes the option to copy the name of the element or attribute itself, rather than any value associated with the element or attribute.</span></span> <span data-ttu-id="84449-106">元素名称和属性名称并不像通常一样视为 XML 实例消息中所传递数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="84449-106">Element and attribute names are not normally thought of as part of the data carried in an XML instance message.</span></span>  
  
-   <span data-ttu-id="84449-107">如何在源架构和目标架构之间实现节点匹配。</span><span class="sxs-lookup"><span data-stu-id="84449-107">How node-matching is performed between the source and destination schemas.</span></span>  
  
 <span data-ttu-id="84449-108">本部分详细说明了可用于这些指令的选项。</span><span class="sxs-lookup"><span data-stu-id="84449-108">This section provides a detailed explanation of these options available for these directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84449-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="84449-109">In This Section</span></span>  
  
-   [<span data-ttu-id="84449-110">数据转换配置</span><span class="sxs-lookup"><span data-stu-id="84449-110">Data Transformation Configuration</span></span>](../core/data-transformation-configuration.md)  
  
-   [<span data-ttu-id="84449-111">节点层次结构级别匹配</span><span class="sxs-lookup"><span data-stu-id="84449-111">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)