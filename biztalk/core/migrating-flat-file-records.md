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
ms.openlocfilehash: c719a1be93458de456cb528c415e18e7a193bf71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="migrating-flat-file-records"></a>迁移平面文件记录
Microsoft [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] 和 Microsoft [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] 在解析和序列化过程中仅支持在平面文件记录中使用单字符分隔符。 此限制是通过更灵活地处理分隔符偏移量。 [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]还支持在记录、 字段和子字段上设置不同的分隔符。 Microsoft BizTalk Server 与此相反，支持多字符分隔符，但它支持的分隔符的一种类型-子分隔符。 分隔符处理中的改进可能会影响如何[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]平面文件记录在 BizTalk Server 中得到处理。  
  
 三种架构批注控制分隔符中的处理[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]，两个用于分析 (**skip_CR**， **skip_LF**)，和一个用于序列化 (**append_newline**). BizTalk Server 解释，如下所示时迁移记录这些批注：  
  
-   如果**skip_CR**批注包含的值**true**和当前的分隔符不回车符 (0x0D)，BizTalk Server 将返回一个回车符添加到当前的分隔符。 例如，如果当前分隔符为管道符号 (0x7C)，则最终分隔符将为管道符号后跟回车符 (0x7C 0x0D)。 如果当前分隔符为回车符，它将保持作为单个回车符无论的值如何**skip_CR**。  
  
-   如果**skip_LF**批注包含的值**true**，BizTalk Server 将换行添加到当前的分隔符字符 (0x0A)。 请注意，在前面的示例，其中当前分隔符是管道符号 (0x7C)，三个字符分隔符结果 (0x7C 0x0D 0x0A) 如果这两个**skip_CR**和**skip_LF**是**true**.  
  
-   BizTalk Server 忽略该设置的**append_newline**批注。  
  
 虽然对批注的这些解释可确保在大部分情况下迁移都不会出现问题，但在某些情况下仍可能出现迁移失败的情况。 例如，如果**skip_CR**和**skip_LF**都**true**和当前分隔符是管道符号 (0x7C)[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]接受的所有以下为一组记录中的有效分隔符： 0x7C 0x0D 0x0A、 0x7C 0x0D、 0x7C 0x0A 和 0x7C。 使用此类组分隔符的记录不能迁移，而且需要在 BizTalk Server 中的自定义分析器代码。  
  
 尽管 BizTalk Server 具有一种类型的分隔符，但它会解释的旧批注，以便轻松地迁移的记录。 如果[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]或[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]架构具有值**def_record_delimdef_field_delim**， **def_subfield_delim**，并且这些引用中**delimiter_type**作为**inherit_record**，依此类推，BizTalk Server 检索相应值，并将其存储在本地。  
  
 此外，BizTalk Server 将添加包含无子级的标记位置记录的字段。  
  
## <a name="see-also"></a>另请参阅  
 [架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)