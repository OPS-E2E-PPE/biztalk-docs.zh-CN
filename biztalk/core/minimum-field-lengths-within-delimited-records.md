---
title: 分隔记录中的最小的字段长度 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d803eb311bda7c27db5a05830f7a84f9b9857e8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263637"
---
# <a name="minimum-field-lengths-within-delimited-records"></a><span data-ttu-id="195f5-102">分隔记录中的最小的字段长度</span><span class="sxs-lookup"><span data-stu-id="195f5-102">Minimum Field Lengths Within Delimited Records</span></span>
<span data-ttu-id="195f5-103">根据定义，位置记录中的字段都定义为具体特定的确切长度。</span><span class="sxs-lookup"><span data-stu-id="195f5-103">By definition, the fields in positional records are all defined to have specific exact lengths.</span></span> <span data-ttu-id="195f5-104">您还可以将分隔记录中的字段定义为具有最小长度。</span><span class="sxs-lookup"><span data-stu-id="195f5-104">Fields in delimited records can also be defined to have a minimum length.</span></span> <span data-ttu-id="195f5-105">这种特性定义的 **[填充字符的最小长度**属性**Field 元素**和**字段特性**节点。</span><span class="sxs-lookup"><span data-stu-id="195f5-105">This characteristic is defined by the **[Minimum Length with Pad Character** property of **Field Element** and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="195f5-106">提供的一个非零值时**填充字符的最小长度**属性，平面文件汇编器将确定的字段关联的数据字符数是否小于设置**填充字符的最小长度**属性，相关的填充字符将用于构成差异。</span><span class="sxs-lookup"><span data-stu-id="195f5-106">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file assembler will determine whether the number of data characters associated with the field is smaller than the setting of the **Minimum Length with Pad Character** property, the relevant pad character will be used to make up the difference.</span></span>  
  
 <span data-ttu-id="195f5-107">之前或之后的数据字符根据的设置，将添加的填充字符**理由**字段的属性。</span><span class="sxs-lookup"><span data-stu-id="195f5-107">The pad characters will be added before or after the data characters based on the setting of the **Justification** property for the field.</span></span> <span data-ttu-id="195f5-108">当**理由**属性设置为**左**，将在数据个字符后添加需要满足的最小长度任何填充字符。</span><span class="sxs-lookup"><span data-stu-id="195f5-108">When the **Justification** property is set to **Left**, any pad characters required to meet the minimum length will be added after the data characters.</span></span> <span data-ttu-id="195f5-109">当**理由**属性设置为**右**，将在数据字符之前添加需要满足的最小长度任何填充字符。</span><span class="sxs-lookup"><span data-stu-id="195f5-109">When the **Justification** property is set to **Right**, any pad characters required to meet the minimum length will be added before the data characters.</span></span>  
  
 <span data-ttu-id="195f5-110">提供的一个非零值时**填充字符的最小长度**属性，平面文件反汇编程序将检查的开头或末尾 (基于的设置**理由**属性) 的字段值存在相关的填充字符，并且如果有，填充字符将被放弃，并不会出现在正在构造的等效 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="195f5-110">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file disassembler will examine the beginning or end (based on the setting of the **Justification** property) of the field value for the presence of the relevant pad character, and if present, the pad characters will be discarded and not appear in the equivalent XML message being constructed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195f5-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="195f5-111">See Also</span></span>  
-  [<span data-ttu-id="195f5-112">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="195f5-112">Field Considerations</span></span>](../core/field-considerations.md)   
-  <span data-ttu-id="195f5-113">**两端对齐 （的平面文件架构的节点属性）** 和**填充字符 （节点属性的平面文件架构） 的最小长度**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="195f5-113">**Justification (Node Property of Flat File Schemas)** and **Minimum Length with Pad Character (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>