---
title: 迁移平面文件记录 |Microsoft 文档
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
ms.openlocfilehash: ddd43c231077f4e23efca374edbda5bf152f1415
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710816"
---
# <a name="migrate-flat-file-records"></a><span data-ttu-id="615cf-102">迁移平面文件记录</span><span class="sxs-lookup"><span data-stu-id="615cf-102">Migrate Flat File Records</span></span>

## <a name="overview"></a><span data-ttu-id="615cf-103">概述</span><span class="sxs-lookup"><span data-stu-id="615cf-103">Overview</span></span>
<span data-ttu-id="615cf-104">Microsoft BizTalk Server 支持多字符分隔符，但它支持的分隔符的一种类型-子分隔符。</span><span class="sxs-lookup"><span data-stu-id="615cf-104">Microsoft BizTalk Server supports multi-character delimiters, although it supports only one type of delimiter—child delimiter.</span></span> 
  
 <span data-ttu-id="615cf-105">三种架构批注控制处理 BizTalk Server 中的分隔符： 两个用于分析 (**skip_CR**， **skip_LF**)，和一个用于序列化 (**append_newline**)。</span><span class="sxs-lookup"><span data-stu-id="615cf-105">Three schema annotations control delimiter handling in BizTalk Server: two for parsing (**skip_CR**, **skip_LF**), and one for serializing (**append_newline**).</span></span> <span data-ttu-id="615cf-106">BizTalk Server 解释，如下所示时迁移记录这些批注：</span><span class="sxs-lookup"><span data-stu-id="615cf-106">BizTalk Server interprets these annotations as follows when migrating records:</span></span>  
  
-   <span data-ttu-id="615cf-107">如果**skip_CR**批注包含的值**true**和当前的分隔符不回车符 (0x0D)，BizTalk Server 将返回一个回车符添加到当前的分隔符。</span><span class="sxs-lookup"><span data-stu-id="615cf-107">If the **skip_CR** annotation has a value of **true** and the current delimiter is not carriage return (0x0D), BizTalk Server adds a carriage return to the current delimiter.</span></span> <span data-ttu-id="615cf-108">例如，如果当前分隔符为管道符号 (0x7C)，则最终分隔符将为管道符号后跟回车符 (0x7C 0x0D)。</span><span class="sxs-lookup"><span data-stu-id="615cf-108">For example, if the current delimiter were the pipe symbol (0x7C), the resulting delimiter is a pipe symbol followed by a carriage return (0x7C 0x0D).</span></span> <span data-ttu-id="615cf-109">如果当前分隔符为回车符，它将保持作为单个回车符无论的值如何 **skip_CR**。</span><span class="sxs-lookup"><span data-stu-id="615cf-109">If the current delimiter is carriage return, it remains as a single carriage return regardless of the value of **skip_CR**.</span></span>  
  
-   <span data-ttu-id="615cf-110">如果**skip_LF**批注包含的值**true**，BizTalk Server 将换行添加到当前的分隔符字符 (0x0A)。</span><span class="sxs-lookup"><span data-stu-id="615cf-110">If the **skip_LF** annotation has a value of **true**, BizTalk Server adds a linefeed character (0x0A) to the current delimiter.</span></span> <span data-ttu-id="615cf-111">请注意，在前面的示例，其中当前分隔符是管道符号 (0x7C)，三个字符分隔符结果 (0x7C 0x0D 0x0A) 如果这两个 **skip_CR** 和 **skip_LF** 是 **true**。</span><span class="sxs-lookup"><span data-stu-id="615cf-111">Notice that in the preceding case where the current delimiter is the pipe symbol (0x7C), a three character delimiter results (0x7C 0x0D 0x0A) if both **skip_CR** and **skip_LF** are **true**.</span></span>  
  
-   <span data-ttu-id="615cf-112">BizTalk Server 忽略该设置的**append_newline**批注。</span><span class="sxs-lookup"><span data-stu-id="615cf-112">BizTalk Server ignores the setting of the **append_newline** annotation.</span></span>  
  
 <span data-ttu-id="615cf-113">虽然对批注的这些解释可确保在大部分情况下迁移都不会出现问题，但在某些情况下仍可能出现迁移失败的情况。</span><span class="sxs-lookup"><span data-stu-id="615cf-113">While these interpretations of the annotations ensure the majority of cases migrate without difficulty, there are some cases where migration fails.</span></span> <span data-ttu-id="615cf-114">例如，如果**skip_CR**和**skip_LF**都**true**和当前分隔符是管道符号 (0x7C)、 BizTalk Server 接受所有以下内容作为有效一组记录中的分隔符： 0x7C 0x0D 0x0A、 0x7C 0x0D、 0x7C 0x0A 和 0x7C。</span><span class="sxs-lookup"><span data-stu-id="615cf-114">For example, if **skip_CR** and **skip_LF** are both **true** and the current delimiter is the pipe symbol (0x7C), BizTalk Server accepts all of the following as valid delimiters within a single set of records: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A, and 0x7C.</span></span> <span data-ttu-id="615cf-115">使用此类组分隔符的记录不能迁移，而且需要在 BizTalk Server 中的自定义分析器代码。</span><span class="sxs-lookup"><span data-stu-id="615cf-115">Records using such sets of delimiters cannot be migrated and require custom parser code in BizTalk Server.</span></span>  
  
 <span data-ttu-id="615cf-116">尽管 BizTalk Server 具有一种类型的分隔符，但它会解释的旧批注，以便轻松地迁移的记录。</span><span class="sxs-lookup"><span data-stu-id="615cf-116">Although BizTalk Server has only one type of delimiter, it interprets the old annotations so that records migrate easily.</span></span> <span data-ttu-id="615cf-117">如果 BizTalk Server 架构具有值**def_record_delimdef_field_delim**， **def_subfield_delim**，并且这些引用中**delimiter_type**作为**inherit_record**，依此类推，BizTalk Server 检索相应值，并将其存储在本地。</span><span class="sxs-lookup"><span data-stu-id="615cf-117">If a BizTalk Server schema has values for **def_record_delimdef_field_delim**, **def_subfield_delim**, and these are referenced in **delimiter_type** as **inherit_record**, and so on, BizTalk Server retrieves the corresponding value and stores it locally.</span></span>  
  
 <span data-ttu-id="615cf-118">此外，BizTalk Server 将添加包含无子级的标记位置记录的字段。</span><span class="sxs-lookup"><span data-stu-id="615cf-118">In addition, BizTalk Server adds fields for tagged positional records without children.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615cf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="615cf-119">See Also</span></span>  
 [<span data-ttu-id="615cf-120">架构生成和验证的已知问题</span><span class="sxs-lookup"><span data-stu-id="615cf-120">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)