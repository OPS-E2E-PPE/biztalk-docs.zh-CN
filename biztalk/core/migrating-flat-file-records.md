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
ms.openlocfilehash: 58efef3b1eed3a52942b6284685bc55824e6a627
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394466"
---
# <a name="migrate-flat-file-records"></a>迁移平面文件记录

## <a name="overview"></a>概述
Microsoft BizTalk Server 支持多字符分隔符，但它支持只有一个类型的分隔符-子分隔符。 
  
 三个架构批注来控制分隔符的 BizTalk Server 中的处理： 两个用于解析 (**skip_CR**， **skip_LF**)，一个用于序列化 (**append_newline**)。 BizTalk Server 将解释这些批注在迁移记录时，如下所示：  
  
- 如果**skip_CR**批注的值为**true**和当前分隔符不是回车符 (0x0D)，BizTalk Server 将向当前分隔符添加回车符。 例如，如果当前分隔符管道符号 (0x7C)，则最终分隔符为管道符号后跟回车符 (0x7C 0x0D)。 如果当前分隔符为回车符，它保留为单个回车符而不考虑的值**skip_CR**。  
  
- 如果**skip_LF**批注的值为**true**，BizTalk Server 将添加一个换行符 (0x0A) 字符向当前分隔符。 请注意，在上面的案例，其中当前分隔符为管道符号 (0x7C)，一个三字符分隔符会产生 (0x7C 0x0D 0x0A) 如果这两个**skip_CR**并**skip_LF**是**true**.  
  
- BizTalk Server 会忽略的设置**append_newline**批注。  
  
  虽然这些批注的解释，请确保在大部分情况下迁移不会出现问题，迁移将失败，其中某些情况下。 例如，如果**skip_CR**并**skip_LF**都是**true**和当前分隔符为管道符号 (0x7C)，BizTalk Server 接受所有以下内容作为有效单个记录集中的分隔符：0x7C 0x0D 0x0A 0x7C 0x0D、 0x7C 0x0A 和 0x7C。 使用这种分隔符集的记录不能迁移，需要在 BizTalk Server 中的自定义解析程序代码。  
  
  尽管 BizTalk Server 具有只有一个类型的分隔符，但它可解释旧的批注，以便可以轻松迁移记录。 如果 BizTalk Server 架构都具有值**def_record_delimdef_field_delim**， **def_subfield_delim**，并在引用这些**delimiter_type**作为**inherit_record**，依此类推，BizTalk Server 检索相应的值并将其存储在本地。  
  
  此外，BizTalk Server 将添加无子级的标记位置记录的字段。  
  
## <a name="see-also"></a>请参阅  
 [架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)