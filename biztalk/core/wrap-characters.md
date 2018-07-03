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
ms.openlocfilehash: b7d88c412c94505600443d351a150b6ca8a6876a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996590"
---
# <a name="wrap-characters"></a><span data-ttu-id="b0c07-102">自动换行字符</span><span class="sxs-lookup"><span data-stu-id="b0c07-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="b0c07-103">概述</span><span class="sxs-lookup"><span data-stu-id="b0c07-103">Overview</span></span>
<span data-ttu-id="b0c07-104">环绕符是单个字符，用于环绕字段中的数据字符，以便取消这些数据字符原本具有的特殊意义。</span><span class="sxs-lookup"><span data-stu-id="b0c07-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="b0c07-105">例如，如果您将某个平面文件记录定义为具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="b0c07-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="b0c07-106">名称 = Record1</span><span class="sxs-lookup"><span data-stu-id="b0c07-106">Name = Record1</span></span>  
  
- <span data-ttu-id="b0c07-107">带分隔符</span><span class="sxs-lookup"><span data-stu-id="b0c07-107">Delimited</span></span>  
  
- <span data-ttu-id="b0c07-108">子分隔符 = 逗号字符 (,)</span><span class="sxs-lookup"><span data-stu-id="b0c07-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="b0c07-109">子顺序 = 中缀</span><span class="sxs-lookup"><span data-stu-id="b0c07-109">Child order = infix</span></span>  
  
- <span data-ttu-id="b0c07-110">转义符 = 反斜杠字符 (\\)</span><span class="sxs-lookup"><span data-stu-id="b0c07-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="b0c07-111">标记 = RECORD1</span><span class="sxs-lookup"><span data-stu-id="b0c07-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="b0c07-112">名为 Field1、Field2 和 Field3 的三个字段均定义为使用数字符号字符 (#) 作为其环绕符。</span><span class="sxs-lookup"><span data-stu-id="b0c07-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
  <span data-ttu-id="b0c07-113">则以下平面文件数据适用于记录：</span><span class="sxs-lookup"><span data-stu-id="b0c07-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="b0c07-114">数据被拆装成以下 XML 片断。</span><span class="sxs-lookup"><span data-stu-id="b0c07-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="b0c07-115">请注意，环绕粗体数据字符 field1、field2 和 field3 的环绕符 (#) 已删除。</span><span class="sxs-lookup"><span data-stu-id="b0c07-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="b0c07-116">当平面文件组装器执行反向操作，将记录的 XML 版本转换为其等效的平面文件记录时，换行字符被插入之前和之后的每个字段，无法完成的原始序列的数据字符平面文件字符。</span><span class="sxs-lookup"><span data-stu-id="b0c07-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="b0c07-117">定义的转义符可与定义的环绕符一起使用。</span><span class="sxs-lookup"><span data-stu-id="b0c07-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="b0c07-118">例如，假定按如下所示更改 Field1 的值（以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="b0c07-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="b0c07-119">当使用所提供记录和字段定义组装此 XML 片断时，将生成以下平面文件字符的序列（以粗体显示转义的数字符号字符序列）：</span><span class="sxs-lookup"><span data-stu-id="b0c07-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="b0c07-120">在创建时使用 BizTalk 编辑器的平面文件架构，可以定义整个架构使用默认环绕符**默认的环绕符**并**默认环绕符类型**的属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="b0c07-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="b0c07-121">然后，可以配置每个单独的字段中要使用此默认环绕符或自定义的特定于字段的换行字符使用的架构**环绕符**并**环绕符类型**属性**Field 元素**或**字段属性**平面文件架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="b0c07-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0c07-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0c07-122">See Also</span></span>  
- [<span data-ttu-id="b0c07-123">将特殊字符作为字段值的一部分进行解释的方法</span><span class="sxs-lookup"><span data-stu-id="b0c07-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="b0c07-124">自动换行字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="b0c07-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="b0c07-125">默认的环绕符 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="b0c07-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="b0c07-126">默认环绕符类型 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="b0c07-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="b0c07-127">环绕符 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="b0c07-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="b0c07-128">环绕符类型 （平面文件架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="b0c07-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>