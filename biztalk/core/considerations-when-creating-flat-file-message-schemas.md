---
title: 考虑事项时创建平面文件消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52271b17-4f0b-4286-a462-cd5951ae49aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ea131abf4f506ad8f396d7da895b44d8c24536e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354692"
---
# <a name="considerations-when-creating-flat-file-message-schemas"></a><span data-ttu-id="b6f34-102">考虑事项时创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="b6f34-102">Considerations When Creating Flat File Message Schemas</span></span>
<span data-ttu-id="b6f34-103">使用平面文件消息架构时，有一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6f34-103">There are a number of considerations when working with flat file message schemas.</span></span> <span data-ttu-id="b6f34-104">这包括适用于所有的平面文件架构的注意事项，以及仅适用于位置记录、 分隔的记录、 位置字段或分隔的字段的注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6f34-104">This includes considerations that apply to all flat file schemas, as well as considerations that apply specifically to positional records, delimited records, positional fields, or delimited fields.</span></span> <span data-ttu-id="b6f34-105">此外，还有一些注意事项涉及如何解释否则特殊字符作为常规数据。</span><span class="sxs-lookup"><span data-stu-id="b6f34-105">There are also considerations about how to interpret otherwise special characters as regular data.</span></span> <span data-ttu-id="b6f34-106">本部分提供有关这些注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="b6f34-106">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6f34-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6f34-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b6f34-108">平面文件架构的代码页规范</span><span class="sxs-lookup"><span data-stu-id="b6f34-108">Code Page Specification for Flat File Schemas</span></span>](../core/code-page-specification-for-flat-file-schemas.md)  
  
-   [<span data-ttu-id="b6f34-109">平面文件架构中的用例处理</span><span class="sxs-lookup"><span data-stu-id="b6f34-109">Case Handling in Flat File Schemas</span></span>](../core/case-handling-in-flat-file-schemas.md)  
  
-   [<span data-ttu-id="b6f34-110">受限字符范围</span><span class="sxs-lookup"><span data-stu-id="b6f34-110">Restricted Character Ranges</span></span>](../core/restricted-character-ranges.md)  
  
-   [<span data-ttu-id="b6f34-111">嵌套位置和分隔记录</span><span class="sxs-lookup"><span data-stu-id="b6f34-111">Nested Positional and Delimited Records</span></span>](../core/nested-positional-and-delimited-records.md)  
  
-   [<span data-ttu-id="b6f34-112">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="b6f34-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)  
  
-   [<span data-ttu-id="b6f34-113">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="b6f34-113">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)  
  
-   [<span data-ttu-id="b6f34-114">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="b6f34-114">Field Considerations</span></span>](../core/field-considerations.md)  
  
-   [<span data-ttu-id="b6f34-115">将特殊字符作为字段值的一部分进行解释的方法</span><span class="sxs-lookup"><span data-stu-id="b6f34-115">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)