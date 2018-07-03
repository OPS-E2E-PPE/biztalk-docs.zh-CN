---
title: 迁移平面文件记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f055b6a572e357a520b9679796ad0288dda19f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994070"
---
# <a name="migrate-flat-file-records"></a><span data-ttu-id="69da6-102">迁移平面文件记录</span><span class="sxs-lookup"><span data-stu-id="69da6-102">Migrate Flat File Records</span></span>

## <a name="overview"></a><span data-ttu-id="69da6-103">概述</span><span class="sxs-lookup"><span data-stu-id="69da6-103">Overview</span></span>
<span data-ttu-id="69da6-104">Microsoft BizTalk Server 支持多字符分隔符，但它支持只有一个类型的分隔符-子分隔符。</span><span class="sxs-lookup"><span data-stu-id="69da6-104">Microsoft BizTalk Server supports multi-character delimiters, although it supports only one type of delimiter—child delimiter.</span></span> 
  
 <span data-ttu-id="69da6-105">三个架构批注来控制分隔符的 BizTalk Server 中的处理： 两个用于解析 (**skip_CR**， **skip_LF**)，一个用于序列化 (**append_newline**)。</span><span class="sxs-lookup"><span data-stu-id="69da6-105">Three schema annotations control delimiter handling in BizTalk Server: two for parsing (**skip_CR**, **skip_LF**), and one for serializing (**append_newline**).</span></span> <span data-ttu-id="69da6-106">BizTalk Server 将解释这些批注在迁移记录时，如下所示：</span><span class="sxs-lookup"><span data-stu-id="69da6-106">BizTalk Server interprets these annotations as follows when migrating records:</span></span>  
  
- <span data-ttu-id="69da6-107">如果**skip_CR**批注的值为**true**和当前分隔符不是回车符 (0x0D)，BizTalk Server 将向当前分隔符添加回车符。</span><span class="sxs-lookup"><span data-stu-id="69da6-107">If the **skip_CR** annotation has a value of **true** and the current delimiter is not carriage return (0x0D), BizTalk Server adds a carriage return to the current delimiter.</span></span> <span data-ttu-id="69da6-108">例如，如果当前分隔符为管道符号 (0x7C)，则最终分隔符将为管道符号后跟回车符 (0x7C 0x0D)。</span><span class="sxs-lookup"><span data-stu-id="69da6-108">For example, if the current delimiter were the pipe symbol (0x7C), the resulting delimiter is a pipe symbol followed by a carriage return (0x7C 0x0D).</span></span> <span data-ttu-id="69da6-109">如果当前分隔符为回车符，它保留为单个回车符而不考虑的值**skip_CR**。</span><span class="sxs-lookup"><span data-stu-id="69da6-109">If the current delimiter is carriage return, it remains as a single carriage return regardless of the value of **skip_CR**.</span></span>  
  
- <span data-ttu-id="69da6-110">如果**skip_LF**批注的值为**true**，BizTalk Server 将添加一个换行符 (0x0A) 字符向当前分隔符。</span><span class="sxs-lookup"><span data-stu-id="69da6-110">If the **skip_LF** annotation has a value of **true**, BizTalk Server adds a linefeed character (0x0A) to the current delimiter.</span></span> <span data-ttu-id="69da6-111">请注意，在上面的案例，其中当前分隔符为管道符号 (0x7C)，一个三字符分隔符会产生 (0x7C 0x0D 0x0A) 如果这两个**skip_CR**并**skip_LF**是**true**.</span><span class="sxs-lookup"><span data-stu-id="69da6-111">Notice that in the preceding case where the current delimiter is the pipe symbol (0x7C), a three character delimiter results (0x7C 0x0D 0x0A) if both **skip_CR** and **skip_LF** are **true**.</span></span>  
  
- <span data-ttu-id="69da6-112">BizTalk Server 会忽略的设置**append_newline**批注。</span><span class="sxs-lookup"><span data-stu-id="69da6-112">BizTalk Server ignores the setting of the **append_newline** annotation.</span></span>  
  
  <span data-ttu-id="69da6-113">虽然对批注的这些解释可确保在大部分情况下迁移都不会出现问题，但在某些情况下仍可能出现迁移失败的情况。</span><span class="sxs-lookup"><span data-stu-id="69da6-113">While these interpretations of the annotations ensure the majority of cases migrate without difficulty, there are some cases where migration fails.</span></span> <span data-ttu-id="69da6-114">例如，如果**skip_CR**并**skip_LF**都是**true**和当前分隔符为管道符号 (0x7C)，BizTalk Server 接受所有以下内容作为有效单个记录集中的分隔符： 0x7C 0x0D 0x0A 0x7C 0x0D、 0x7C 0x0A 和 0x7C。</span><span class="sxs-lookup"><span data-stu-id="69da6-114">For example, if **skip_CR** and **skip_LF** are both **true** and the current delimiter is the pipe symbol (0x7C), BizTalk Server accepts all of the following as valid delimiters within a single set of records: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A, and 0x7C.</span></span> <span data-ttu-id="69da6-115">使用这种分隔符集的记录不能迁移，需要在 BizTalk Server 中的自定义解析程序代码。</span><span class="sxs-lookup"><span data-stu-id="69da6-115">Records using such sets of delimiters cannot be migrated and require custom parser code in BizTalk Server.</span></span>  
  
  <span data-ttu-id="69da6-116">尽管 BizTalk Server 具有只有一个类型的分隔符，但它可解释旧的批注，以便可以轻松迁移记录。</span><span class="sxs-lookup"><span data-stu-id="69da6-116">Although BizTalk Server has only one type of delimiter, it interprets the old annotations so that records migrate easily.</span></span> <span data-ttu-id="69da6-117">如果 BizTalk Server 架构都具有值**def_record_delimdef_field_delim**， **def_subfield_delim**，并在引用这些**delimiter_type**作为**inherit_record**，依此类推，BizTalk Server 检索相应的值并将其存储在本地。</span><span class="sxs-lookup"><span data-stu-id="69da6-117">If a BizTalk Server schema has values for **def_record_delimdef_field_delim**, **def_subfield_delim**, and these are referenced in **delimiter_type** as **inherit_record**, and so on, BizTalk Server retrieves the corresponding value and stores it locally.</span></span>  
  
  <span data-ttu-id="69da6-118">此外，BizTalk Server 将添加无子级的标记位置记录的字段。</span><span class="sxs-lookup"><span data-stu-id="69da6-118">In addition, BizTalk Server adds fields for tagged positional records without children.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69da6-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="69da6-119">See Also</span></span>  
 [<span data-ttu-id="69da6-120">架构生成和验证的已知问题</span><span class="sxs-lookup"><span data-stu-id="69da6-120">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)