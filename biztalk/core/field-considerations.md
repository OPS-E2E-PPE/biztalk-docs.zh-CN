---
title: 字段注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7f1853-60ed-49c2-a592-61bde5445d36
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 861f8d8bacb7c0110c9ccbfdf55f8f0547c79bad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245781"
---
# <a name="field-considerations"></a><span data-ttu-id="c3bdb-102">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="c3bdb-102">Field Considerations</span></span>
<span data-ttu-id="c3bdb-103">有大量的使用时应牢记的注意事项**Field 元素**和**字段特性**在你的架构内的节点。</span><span class="sxs-lookup"><span data-stu-id="c3bdb-103">There are a number of considerations that you should keep in mind when working with **Field Element** and **Field Attribute** nodes within your schemas.</span></span> <span data-ttu-id="c3bdb-104">这包括有关何时使用各个节点类型的基本差别，以及与字段长度、字段对齐和字段填充规范有关的更具体的注意事项。</span><span class="sxs-lookup"><span data-stu-id="c3bdb-104">This includes the basic distinctions regarding when to use each of these nodes types, as well as more specific considerations related to the specification of field lengths, field justification, and field padding.</span></span> <span data-ttu-id="c3bdb-105">本部分提供了有关上述注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="c3bdb-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3bdb-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c3bdb-106">In This Section</span></span>  
  
-   [<span data-ttu-id="c3bdb-107">字段元素节点 vs。字段属性节点</span><span class="sxs-lookup"><span data-stu-id="c3bdb-107">Field Element Nodes vs. Field Attribute Nodes</span></span>](../core/field-element-nodes-vs-field-attribute-nodes.md)  
  
-   [<span data-ttu-id="c3bdb-108">自定义日期时间格式</span><span class="sxs-lookup"><span data-stu-id="c3bdb-108">Custom Date-Time Formats</span></span>](../core/custom-date-time-formats.md)  
  
-   [<span data-ttu-id="c3bdb-109">字段填充</span><span class="sxs-lookup"><span data-stu-id="c3bdb-109">Field Padding</span></span>](../core/field-padding.md)  
  
-   [<span data-ttu-id="c3bdb-110">字段理由</span><span class="sxs-lookup"><span data-stu-id="c3bdb-110">Field Justification</span></span>](../core/field-justification.md)  
  
-   [<span data-ttu-id="c3bdb-111">位置记录中的字段位置的规范</span><span class="sxs-lookup"><span data-stu-id="c3bdb-111">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  
  
-   [<span data-ttu-id="c3bdb-112">分隔记录中的最小的字段长度</span><span class="sxs-lookup"><span data-stu-id="c3bdb-112">Minimum Field Lengths Within Delimited Records</span></span>](../core/minimum-field-lengths-within-delimited-records.md)