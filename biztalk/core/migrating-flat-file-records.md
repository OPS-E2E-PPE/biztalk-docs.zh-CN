---
title: "迁移平面文件记录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28daa8426dff3d9cbe9330430e4ba3de64410e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-flat-file-records"></a>迁移平面文件记录
Microsoft [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] 和 Microsoft [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] 在解析和序列化过程中仅支持在平面文件记录中使用单字符分隔符。 此限制是通过更灵活地处理分隔符偏移量。 [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]还支持在记录、 字段和子字段上设置不同的分隔符。 相反，尽管 Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 仅支持一种类型的分隔符（子分隔符），但却支持多字符分隔符。 分隔符处理方面的改进可能会影响 [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] 和 [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] 平面文件记录在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中的处理方式。  
  
 三种架构批注控制分隔符中的处理[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]，两个用于分析 (**skip_CR**， **skip_LF**)，和一个用于序列化 (**append_newline**). [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]解释，如下所示时迁移记录这些批注：  
  
-   如果**skip_CR**批注包含的值**true**和当前的分隔符不回车符 (0x0D)[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将返回一个回车符添加到当前的分隔符。 例如，如果当前分隔符为管道符号 (0x7C)，则最终分隔符将为管道符号后跟回车符 (0x7C 0x0D)。 如果当前分隔符为回车符，它将保持作为单个回车符无论的值如何**skip_CR**。  
  
-   如果**skip_LF**批注包含的值**true**，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]添加换行到当前的分隔符字符 (0x0A)。 请注意，在前面的示例，其中当前分隔符是管道符号 (0x7C)，三个字符分隔符结果 (0x7C 0x0D 0x0A) 如果这两个**skip_CR**和**skip_LF**是**true**.  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]忽略该设置的**append_newline**批注。  
  
 虽然对批注的这些解释可确保在大部分情况下迁移都不会出现问题，但在某些情况下仍可能出现迁移失败的情况。 例如，如果**skip_CR**和**skip_LF**都**true**和当前分隔符是管道符号 (0x7C)[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]接受的所有以下为一组记录中的有效分隔符： 0x7C 0x0D 0x0A、 0x7C 0x0D、 0x7C 0x0A 和 0x7C。 使用这种分隔符集的记录不能进行迁移，需要在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中自定义解析程序代码。  
  
 虽然 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 只有一种类型的分隔符，但它可解释旧的批注，因此可以轻松迁移记录。 如果[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]或[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]架构具有值**def_record_delimdef_field_delim**， **def_subfield_delim**，并且这些引用中**delimiter_type**作为**inherit_record**，依此类推，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]检索相应值，并将其存储在本地。  
  
 此外，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 还会为没有子记录的标记位置记录添加字段。  
  
## <a name="see-also"></a>另请参阅  
 [架构生成和验证已知的问题](../core/known-issues-with-schema-generation-and-validation.md)