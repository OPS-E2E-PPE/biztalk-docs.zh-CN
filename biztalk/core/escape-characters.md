---
title: "转义字符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e961a205b77a9944a497d6e6cbed0df71f63e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="escape-characters"></a><span data-ttu-id="25268-102">转义字符</span><span class="sxs-lookup"><span data-stu-id="25268-102">Escape Characters</span></span>

## <a name="overview"></a><span data-ttu-id="25268-103">概述</span><span class="sxs-lookup"><span data-stu-id="25268-103">Overview</span></span>
<span data-ttu-id="25268-104">：转义符是取消其后紧跟字符的任何特殊意义的单个字符。</span><span class="sxs-lookup"><span data-stu-id="25268-104">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="25268-105">例如，如果您将某个平面文件记录定义为具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="25268-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
-   <span data-ttu-id="25268-106">名称 = Record1</span><span class="sxs-lookup"><span data-stu-id="25268-106">Name = Record1</span></span>  
  
-   <span data-ttu-id="25268-107">带分隔符</span><span class="sxs-lookup"><span data-stu-id="25268-107">Delimited</span></span>  
  
-   <span data-ttu-id="25268-108">子分隔符 = 逗号字符 (,)</span><span class="sxs-lookup"><span data-stu-id="25268-108">Child delimiter = comma character (,)</span></span>  
  
-   <span data-ttu-id="25268-109">子顺序 = 前缀</span><span class="sxs-lookup"><span data-stu-id="25268-109">Child order = prefix</span></span>  
  
-   <span data-ttu-id="25268-110">转义符 = 反斜杠字符 (\\)</span><span class="sxs-lookup"><span data-stu-id="25268-110">Escape character = backslash character (\\)</span></span>  
  
-   <span data-ttu-id="25268-111">标记 = RECORD1</span><span class="sxs-lookup"><span data-stu-id="25268-111">Tag = RECORD1</span></span>  
  
-   <span data-ttu-id="25268-112">名为 Field1 和 Field2 的两个字段</span><span class="sxs-lookup"><span data-stu-id="25268-112">Two fields named Field1 and Field2</span></span>  
  
 <span data-ttu-id="25268-113">则以下平面文件数据适用于记录：</span><span class="sxs-lookup"><span data-stu-id="25268-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 <span data-ttu-id="25268-114">数据将被拆装为以下 XML 片断：</span><span class="sxs-lookup"><span data-stu-id="25268-114">The data will be disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 <span data-ttu-id="25268-115">请注意，转义的字符序列`\,`指示行的下平面文件记录，已转换为一个逗号字符不在数据中的转义字符的情况下为 Field1 等效 XML 记录中。</span><span class="sxs-lookup"><span data-stu-id="25268-115">Note that the escape character sequence `\,` indicated on the line following the flat file record, has been converted to a single comma character without the escape character in the data for Field1 in the equivalent XML record.</span></span> <span data-ttu-id="25268-116">此外，该逗号字符未像其他两个逗号一样被解释为字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="25268-116">Furthermore, that comma character was not interpreted as a field delimiter like the other two commas are.</span></span>  
  
 <span data-ttu-id="25268-117">当平面文件组装器执行反向操作（将记录的 XML 版本转换为其等效平面文件记录）时，转义符将插入到 Field1 中间逗号的前面，以表示它应被解释为数据而不是字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="25268-117">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the escape character will be inserted before the comma in the middle of Field1, thereby indicating that it should be interpreted as data rather than as a field delimiter.</span></span>  
  
 <span data-ttu-id="25268-118">在创建使用 BizTalk 编辑器的平面文件架构，你可以定义整个架构使用的默认转义字符**默认转义字符**和**默认转义字符类型**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="25268-118">When creating a flat file schema using BizTalk Editor, you can define a default escape character for the entire schema using the **Default Escape Character** and **Default Escape Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="25268-119">然后，你可以配置为使用此默认转义字符或自定义的、 特定记录的转义字符使用架构中的每个单独的记录**转义符]**和**转义字符类型**属性**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="25268-119">Then, you can configure each individual record in the schema to either use this default escape character or a custom, record-specific escape character using the **Escape Character]** and **Escape Character Type** properties of the **Record** node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25268-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25268-120">See Also</span></span>  
- [<span data-ttu-id="25268-121">如何解释的特殊字符作为字段值的一部分</span><span class="sxs-lookup"><span data-stu-id="25268-121">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="25268-122">转义字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="25268-122">Escape character properties  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="25268-123">默认转义字符 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="25268-123">Default Escape Character (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="25268-124">默认转义字符类型 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="25268-124">Default Escape Character Type (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="25268-125">转义字符 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="25268-125">Escape Character (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="25268-126">转义字符类型 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="25268-126">Escape Character Type (Node Property of Flat File Schemas)</span></span>