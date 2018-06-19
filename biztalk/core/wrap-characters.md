---
title: 自动换行字符 |Microsoft 文档
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
ms.openlocfilehash: f95ed10811232b15762c31bfc435ac7772a53b3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290029"
---
# <a name="wrap-characters"></a><span data-ttu-id="f4190-102">自动换行字符</span><span class="sxs-lookup"><span data-stu-id="f4190-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="f4190-103">概述</span><span class="sxs-lookup"><span data-stu-id="f4190-103">Overview</span></span>
<span data-ttu-id="f4190-104">环绕符是单个字符，用于环绕字段中的数据字符，以便取消这些数据字符原本具有的特殊意义。</span><span class="sxs-lookup"><span data-stu-id="f4190-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="f4190-105">例如，如果您将某个平面文件记录定义为具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="f4190-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
-   <span data-ttu-id="f4190-106">名称 = Record1</span><span class="sxs-lookup"><span data-stu-id="f4190-106">Name = Record1</span></span>  
  
-   <span data-ttu-id="f4190-107">带分隔符</span><span class="sxs-lookup"><span data-stu-id="f4190-107">Delimited</span></span>  
  
-   <span data-ttu-id="f4190-108">子分隔符 = 逗号字符 (,)</span><span class="sxs-lookup"><span data-stu-id="f4190-108">Child delimiter = comma character (,)</span></span>  
  
-   <span data-ttu-id="f4190-109">子顺序 = 中缀</span><span class="sxs-lookup"><span data-stu-id="f4190-109">Child order = infix</span></span>  
  
-   <span data-ttu-id="f4190-110">转义符 = 反斜杠字符 (\\)</span><span class="sxs-lookup"><span data-stu-id="f4190-110">Escape character = backslash character (\\)</span></span>  
  
-   <span data-ttu-id="f4190-111">标记 = RECORD1</span><span class="sxs-lookup"><span data-stu-id="f4190-111">Tag = RECORD1</span></span>  
  
-   <span data-ttu-id="f4190-112">名为 Field1、Field2 和 Field3 的三个字段均定义为使用数字符号字符 (#) 作为其环绕符。</span><span class="sxs-lookup"><span data-stu-id="f4190-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
 <span data-ttu-id="f4190-113">则以下平面文件数据适用于记录：</span><span class="sxs-lookup"><span data-stu-id="f4190-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="f4190-114">数据分解到 XML 的以下片段中。</span><span class="sxs-lookup"><span data-stu-id="f4190-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="f4190-115">请注意，环绕粗体数据字符 field1、field2 和 field3 的环绕符 (#) 已删除。</span><span class="sxs-lookup"><span data-stu-id="f4190-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="f4190-116">当平面文件汇编器执行反向操作，将 XML 版本的记录转换为其等效的平面文件记录时之前, 和之后的每个字段，以生成的原始序列的数据字符的则都会插入换行字符平面文件的字符。</span><span class="sxs-lookup"><span data-stu-id="f4190-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="f4190-117">定义的转义符可与定义的环绕符一起使用。</span><span class="sxs-lookup"><span data-stu-id="f4190-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="f4190-118">例如，假定按如下所示更改 Field1 的值（以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="f4190-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="f4190-119">当使用所提供记录和字段定义组装此 XML 片断时，将生成以下平面文件字符的序列（以粗体显示转义的数字符号字符序列）：</span><span class="sxs-lookup"><span data-stu-id="f4190-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="f4190-120">在创建使用 BizTalk 编辑器的平面文件架构，你可以定义整个架构使用的默认换行字符**默认换行字符**和**默认换行字符类型**的属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="f4190-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="f4190-121">然后，你可以配置要使用此默认换行字符或自定义的、 特定于字段的换行字符使用的架构中的每个单独的字段**换行字符**和**换行字符类型**属性的**Field 元素**或**字段特性**平面文件架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="f4190-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4190-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4190-122">See Also</span></span>  
- [<span data-ttu-id="f4190-123">如何解释的特殊字符作为字段值的一部分</span><span class="sxs-lookup"><span data-stu-id="f4190-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="f4190-124">自动换行字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="f4190-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="f4190-125">默认换行字符的平面文件架构 （节点属性</span><span class="sxs-lookup"><span data-stu-id="f4190-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="f4190-126">默认换行字符类型的平面文件架构 （节点属性</span><span class="sxs-lookup"><span data-stu-id="f4190-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="f4190-127">自动换行字符的平面文件架构 （节点属性</span><span class="sxs-lookup"><span data-stu-id="f4190-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="f4190-128">自动换行字符类型的平面文件架构 （节点属性</span><span class="sxs-lookup"><span data-stu-id="f4190-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>