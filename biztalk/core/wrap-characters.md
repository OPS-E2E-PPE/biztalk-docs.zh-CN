---
title: 自动换行字符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb046f40af842bf49834873090b8c3864f37dcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262086"
---
# <a name="wrap-characters"></a><span data-ttu-id="35b80-102">自动换行字符</span><span class="sxs-lookup"><span data-stu-id="35b80-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="35b80-103">概述</span><span class="sxs-lookup"><span data-stu-id="35b80-103">Overview</span></span>
<span data-ttu-id="35b80-104">环绕符是单个字符，用于包装以便取消这些数据字符的任何其他可能需要任何特殊含义的字段中的数据字符。</span><span class="sxs-lookup"><span data-stu-id="35b80-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="35b80-105">例如，如果平面文件记录定义为具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="35b80-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="35b80-106">名称 = Record1</span><span class="sxs-lookup"><span data-stu-id="35b80-106">Name = Record1</span></span>  
  
- <span data-ttu-id="35b80-107">带分隔符</span><span class="sxs-lookup"><span data-stu-id="35b80-107">Delimited</span></span>  
  
- <span data-ttu-id="35b80-108">子分隔符 = 逗号字符 （，）</span><span class="sxs-lookup"><span data-stu-id="35b80-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="35b80-109">子顺序 = 中缀</span><span class="sxs-lookup"><span data-stu-id="35b80-109">Child order = infix</span></span>  
  
- <span data-ttu-id="35b80-110">转义符 = 反斜杠字符 (\\)</span><span class="sxs-lookup"><span data-stu-id="35b80-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="35b80-111">标记 = RECORD1</span><span class="sxs-lookup"><span data-stu-id="35b80-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="35b80-112">名为 Field1，Field2 和 Field3 的三个字段，每个定义要使用数字符号字符 （#） 作为其环绕符。</span><span class="sxs-lookup"><span data-stu-id="35b80-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
  <span data-ttu-id="35b80-113">然后以下平面文件数据适用于该记录。</span><span class="sxs-lookup"><span data-stu-id="35b80-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="35b80-114">数据被拆装成以下 XML 片断。</span><span class="sxs-lookup"><span data-stu-id="35b80-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="35b80-115">请注意，已删除环绕粗体数据字符 field1，field2 和 field3 的环绕符 （#）。</span><span class="sxs-lookup"><span data-stu-id="35b80-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="35b80-116">当平面文件组装器执行反向操作，将记录的 XML 版本转换为其等效的平面文件记录时，换行字符被插入之前和之后的每个字段，无法完成的原始序列的数据字符平面文件字符。</span><span class="sxs-lookup"><span data-stu-id="35b80-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="35b80-117">可以与定义的环绕符结合使用定义的转义符。</span><span class="sxs-lookup"><span data-stu-id="35b80-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="35b80-118">例如，假设 Field1 的值更改，如下所示 （以粗体显示）。</span><span class="sxs-lookup"><span data-stu-id="35b80-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="35b80-119">当使用提供的记录和字段定义组装此 XML 片段生成以下平面文件字符序列 （以粗体显示转义的数字符号字符序列）。</span><span class="sxs-lookup"><span data-stu-id="35b80-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="35b80-120">在创建时使用 BizTalk 编辑器的平面文件架构，可以定义整个架构使用默认环绕符**默认的环绕符**并**默认环绕符类型**的属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="35b80-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="35b80-121">然后，可以配置每个单独的字段中要使用此默认环绕符或自定义的特定于字段的换行字符使用的架构**环绕符**并**环绕符类型**属性**Field 元素**或**字段属性**平面文件架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="35b80-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35b80-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="35b80-122">See Also</span></span>  
- [<span data-ttu-id="35b80-123">将特殊字符作为字段值的一部分进行解释的方法</span><span class="sxs-lookup"><span data-stu-id="35b80-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="35b80-124">自动换行字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="35b80-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="35b80-125">默认的环绕符 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="35b80-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="35b80-126">默认环绕符类型 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="35b80-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="35b80-127">环绕符 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="35b80-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="35b80-128">环绕符类型 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="35b80-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>