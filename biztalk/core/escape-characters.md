---
title: 对字符进行转义 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6f1ff202c1ffa96bc696415ab7ec1024ae57e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970644"
---
# <a name="escape-characters"></a><span data-ttu-id="6a758-102">转义字符</span><span class="sxs-lookup"><span data-stu-id="6a758-102">Escape Characters</span></span>

## <a name="overview"></a><span data-ttu-id="6a758-103">概述</span><span class="sxs-lookup"><span data-stu-id="6a758-103">Overview</span></span>
<span data-ttu-id="6a758-104">：转义符是取消其后紧跟字符的任何特殊意义的单个字符。</span><span class="sxs-lookup"><span data-stu-id="6a758-104">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="6a758-105">例如，如果您将某个平面文件记录定义为具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="6a758-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="6a758-106">名称 = Record1</span><span class="sxs-lookup"><span data-stu-id="6a758-106">Name = Record1</span></span>  
  
- <span data-ttu-id="6a758-107">带分隔符</span><span class="sxs-lookup"><span data-stu-id="6a758-107">Delimited</span></span>  
  
- <span data-ttu-id="6a758-108">子分隔符 = 逗号字符 (,)</span><span class="sxs-lookup"><span data-stu-id="6a758-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="6a758-109">子顺序 = 前缀</span><span class="sxs-lookup"><span data-stu-id="6a758-109">Child order = prefix</span></span>  
  
- <span data-ttu-id="6a758-110">转义符 = 反斜杠字符 (\\)</span><span class="sxs-lookup"><span data-stu-id="6a758-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="6a758-111">标记 = RECORD1</span><span class="sxs-lookup"><span data-stu-id="6a758-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="6a758-112">名为 Field1 和 Field2 的两个字段</span><span class="sxs-lookup"><span data-stu-id="6a758-112">Two fields named Field1 and Field2</span></span>  
  
  <span data-ttu-id="6a758-113">则以下平面文件数据适用于记录：</span><span class="sxs-lookup"><span data-stu-id="6a758-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 <span data-ttu-id="6a758-114">数据将被拆装为以下 XML 片断：</span><span class="sxs-lookup"><span data-stu-id="6a758-114">The data will be disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 <span data-ttu-id="6a758-115">请注意转义字符序列`\,`指示后的平面文件记录的行上，已转换为不带转义字符数据中的单个逗号字符 Field1 的等效 XML 记录中。</span><span class="sxs-lookup"><span data-stu-id="6a758-115">Note that the escape character sequence `\,` indicated on the line following the flat file record, has been converted to a single comma character without the escape character in the data for Field1 in the equivalent XML record.</span></span> <span data-ttu-id="6a758-116">此外，该逗号字符未像其他两个逗号一样被解释为字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="6a758-116">Furthermore, that comma character was not interpreted as a field delimiter like the other two commas are.</span></span>  
  
 <span data-ttu-id="6a758-117">当平面文件组装器执行反向操作（将记录的 XML 版本转换为其等效平面文件记录）时，转义符将插入到 Field1 中间逗号的前面，以表示它应被解释为数据而不是字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="6a758-117">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the escape character will be inserted before the comma in the middle of Field1, thereby indicating that it should be interpreted as data rather than as a field delimiter.</span></span>  
  
 <span data-ttu-id="6a758-118">在创建时使用 BizTalk 编辑器的平面文件架构，可以定义的整个架构使用默认转义符**默认转义符**并**默认转义符类型**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="6a758-118">When creating a flat file schema using BizTalk Editor, you can define a default escape character for the entire schema using the **Default Escape Character** and **Default Escape Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="6a758-119">然后，可以配置每个记录中要使用此默认转义符或自定义的特定于记录的转义字符使用的架构**转义符]** 和**转义符类型**的属性**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="6a758-119">Then, you can configure each individual record in the schema to either use this default escape character or a custom, record-specific escape character using the **Escape Character]** and **Escape Character Type** properties of the **Record** node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a758-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a758-120">See Also</span></span>  
- [<span data-ttu-id="6a758-121">将特殊字符作为字段值的一部分进行解释的方法</span><span class="sxs-lookup"><span data-stu-id="6a758-121">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="6a758-122">转义字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="6a758-122">Escape character properties  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="6a758-123">默认的转义符 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="6a758-123">Default Escape Character (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="6a758-124">默认转义符类型 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="6a758-124">Default Escape Character Type (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="6a758-125">转义符 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="6a758-125">Escape Character (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="6a758-126">转义符类型 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="6a758-126">Escape Character Type (Node Property of Flat File Schemas)</span></span>