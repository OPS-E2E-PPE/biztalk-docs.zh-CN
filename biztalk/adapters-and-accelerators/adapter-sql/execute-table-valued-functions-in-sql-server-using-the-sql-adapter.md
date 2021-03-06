---
title: 在使用 SQL 适配器的 SQL Server 中执行表值函数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fb8c81c-9384-4eba-b0a0-baed1782245b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48597c430bf2c77956476cbd689ec29bdc44b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369525"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a>在使用 SQL 适配器的 SQL Server 中执行表值函数
SQL Server 中的 Transact SQL 和 CLR 表值函数作为中的操作[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。 中的操作名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是相同的值在 SQL Server 中的函数的表的名称。  
  
 表值函数中的所有参数都都在相应的操作。 如果未指定输入的参数对于表值函数，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在内部调用函数的 DEFAULT 关键字。 这意味着表值函数的执行定义该函数时指定的默认值。  
  
 有关详细信息：  
  
- 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 BizTalk Server 中调用 SQL Server 中的表值函数，请参阅[Invoking Table-Valued 函数通过使用 BizTalk Server 的 SQL Server 中](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)。  
  
- 消息结构和表值函数的 SOAP 操作，请参见[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)