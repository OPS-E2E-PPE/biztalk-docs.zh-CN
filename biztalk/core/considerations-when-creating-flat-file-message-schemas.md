---
title: "注意事项时创建平面文件消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52271b17-4f0b-4286-a462-cd5951ae49aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d0cbe19b85fc65c492f1e0ae377da94dad75baf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-creating-flat-file-message-schemas"></a><span data-ttu-id="36e11-102">注意事项时创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="36e11-102">Considerations When Creating Flat File Message Schemas</span></span>
<span data-ttu-id="36e11-103">在处理平面文件消息架构时，存在一些需要注意的事项。</span><span class="sxs-lookup"><span data-stu-id="36e11-103">There are a number of considerations when working with flat file message schemas.</span></span> <span data-ttu-id="36e11-104">这包括适用于所有平面文件架构的注意事项，以及专门适用于位置记录、分隔记录、位置字段或分隔字段的注意事项。</span><span class="sxs-lookup"><span data-stu-id="36e11-104">This includes considerations that apply to all flat file schemas, as well as considerations that apply specifically to positional records, delimited records, positional fields, or delimited fields.</span></span> <span data-ttu-id="36e11-105">还有一些注意事项涉及如何将其他特殊字符解释为常规数据。</span><span class="sxs-lookup"><span data-stu-id="36e11-105">There are also considerations about how to interpret otherwise special characters as regular data.</span></span> <span data-ttu-id="36e11-106">本部分提供了有关上述注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="36e11-106">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36e11-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="36e11-107">In This Section</span></span>  
  
-   [<span data-ttu-id="36e11-108">平面文件架构的代码页规范</span><span class="sxs-lookup"><span data-stu-id="36e11-108">Code Page Specification for Flat File Schemas</span></span>](../core/code-page-specification-for-flat-file-schemas.md)  
  
-   [<span data-ttu-id="36e11-109">在平面文件架构中处理的用例</span><span class="sxs-lookup"><span data-stu-id="36e11-109">Case Handling in Flat File Schemas</span></span>](../core/case-handling-in-flat-file-schemas.md)  
  
-   [<span data-ttu-id="36e11-110">有限的字符范围内</span><span class="sxs-lookup"><span data-stu-id="36e11-110">Restricted Character Ranges</span></span>](../core/restricted-character-ranges.md)  
  
-   [<span data-ttu-id="36e11-111">嵌套的位置和分隔记录</span><span class="sxs-lookup"><span data-stu-id="36e11-111">Nested Positional and Delimited Records</span></span>](../core/nested-positional-and-delimited-records.md)  
  
-   [<span data-ttu-id="36e11-112">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="36e11-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)  
  
-   [<span data-ttu-id="36e11-113">分隔记录的注意事项</span><span class="sxs-lookup"><span data-stu-id="36e11-113">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)  
  
-   [<span data-ttu-id="36e11-114">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="36e11-114">Field Considerations</span></span>](../core/field-considerations.md)  
  
-   [<span data-ttu-id="36e11-115">如何解释的特殊字符作为字段值的一部分</span><span class="sxs-lookup"><span data-stu-id="36e11-115">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)