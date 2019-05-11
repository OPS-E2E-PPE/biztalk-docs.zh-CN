---
title: 字段注意事项 |Microsoft Docs
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
ms.openlocfilehash: 2dfcc57be3e28a2882f1430cb87c672031dbc496
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388084"
---
# <a name="field-considerations"></a><span data-ttu-id="2d7da-102">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="2d7da-102">Field Considerations</span></span>
<span data-ttu-id="2d7da-103">有多种使用时应牢记的注意事项**Field 元素**并**字段属性**节点在架构中的。</span><span class="sxs-lookup"><span data-stu-id="2d7da-103">There are a number of considerations that you should keep in mind when working with **Field Element** and **Field Attribute** nodes within your schemas.</span></span> <span data-ttu-id="2d7da-104">这包括有关何时使用每个这些节点类型，以及更具体的注意事项与的字段长度、 字段对齐和字段填充本规范相关的基本区别。</span><span class="sxs-lookup"><span data-stu-id="2d7da-104">This includes the basic distinctions regarding when to use each of these nodes types, as well as more specific considerations related to the specification of field lengths, field justification, and field padding.</span></span> <span data-ttu-id="2d7da-105">本部分提供有关这些注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="2d7da-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d7da-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2d7da-106">In This Section</span></span>  
  
-   [<span data-ttu-id="2d7da-107">“字段元素”节点与“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="2d7da-107">Field Element Nodes vs. Field Attribute Nodes</span></span>](../core/field-element-nodes-vs-field-attribute-nodes.md)  
  
-   [<span data-ttu-id="2d7da-108">自定义日期-时间格式</span><span class="sxs-lookup"><span data-stu-id="2d7da-108">Custom Date-Time Formats</span></span>](../core/custom-date-time-formats.md)  
  
-   [<span data-ttu-id="2d7da-109">字段填充</span><span class="sxs-lookup"><span data-stu-id="2d7da-109">Field Padding</span></span>](../core/field-padding.md)  
  
-   [<span data-ttu-id="2d7da-110">字段对齐</span><span class="sxs-lookup"><span data-stu-id="2d7da-110">Field Justification</span></span>](../core/field-justification.md)  
  
-   [<span data-ttu-id="2d7da-111">位置记录中的字段位置规范</span><span class="sxs-lookup"><span data-stu-id="2d7da-111">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  
  
-   [<span data-ttu-id="2d7da-112">分隔记录中的最小字段长度</span><span class="sxs-lookup"><span data-stu-id="2d7da-112">Minimum Field Lengths Within Delimited Records</span></span>](../core/minimum-field-lengths-within-delimited-records.md)