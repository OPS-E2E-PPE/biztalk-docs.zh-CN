---
title: "函数和过程与 Oracle 数据库中的 REF CURSOR 参数上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IN REF CURSOR
- REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: 691c4aca-3454-41d6-b211-a4d37f215331
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a918553cd687d80a5898c7171981dffbcf7b092c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>对函数和过程与 Oracle 数据库中的 REF CURSOR 参数的操作
REF CURSOR 是表示指向服务器端结果集通过执行查询生成的指针的 PL/SQL 数据类型。 REF CURSOR 类型使输入和输出流的数据非常适合传输大量数据传入和传出的 PL/SQL 代码。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供支持强类型和弱类型 (SYS_REFCURSOR) REF Cursor，可在缩小，传递给 PL/SQL 过程和函数中或在 OUT 参数。  
  
-   **在 REF CURSOR**。 适配器客户端必须使用在 REF CURSOR，通过提供对 Oracle 数据库打开 REF CURSOR 的 PL/SQL 代码 （作为字符串）。 适配器创建变量并将它打开的 REF CURSOR，调用函数或与该变量的过程。 因此，在 REF CURSOR 参数中 PL/SQL 存储过程和函数应表示为将 PL/SQL 代码块作为标记出 REF CURSOR 变量输入值的字符串"？"。  
  
-   **REF CURSOR 出**。 出 REF CURSOR 参数将返回为强类型或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数声明为存储过程或函数定义中的强类型或弱类型化的 REF CURSOR 在 Oracle 服务器上。  
  
-   **在出 REF CURSOR 参数**。 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的出 REF CURSOR 参数，它不能在出 REF CURSOR 参数支持单一类型。 为此，它将在出 REF CURSOR 参数视为两个不同的参数： 请求消息和响应消息中的 OUT 参数中的 IN 参数。  
  
 有关详细信息：  
  
-   调用函数或过程涉及使用 REF CURSOR 参数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)。  
  
-   调用的函数或过程涉及使用 WCF 服务模型的 REF CURSOR 参数，请参阅[运行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
-   所支持的 REF CURSOR 的 XML 结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[REF CURSOR 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用连接到 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)