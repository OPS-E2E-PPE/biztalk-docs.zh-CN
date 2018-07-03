---
title: 对 Oracle 数据库中的 REF CURSOR 参数包含函数和过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IN REF CURSOR
- REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: 691c4aca-3454-41d6-b211-a4d37f215331
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b1d3ac6ff54fa15c300962e7ecfdae91414bff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014806"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>对 Oracle 数据库中的 REF CURSOR 参数包含函数和过程的操作
REF CURSOR 是 PL/SQL 数据类型表示的指针指向服务器端结果集生成的执行查询。 REF CURSOR 类型支持输入和输出数据的流，适合用于传输大量数据传入和传出 PL/SQL 代码。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供强类型化和弱类型 (SYS_REFCURSOR) REF Cursor，可缩小，传递给 PL/SQL 过程和函数中，或在 OUT 参数的支持。  
  
- **REF CURSOR 中**。 适配器客户端必须通过提供的 Oracle 数据库打开 REF CURSOR 的 PL/SQL 代码 （如字符串） 使用 IN REF CURSOR。 适配器创建变量并将其设置打开的 REF CURSOR 并调用函数或使用该变量的过程。 因此，在 REF CURSOR 参数中 PL/SQL 存储过程和函数应表示为字符串将作为输入值标记出 REF CURSOR 变量的 PL/SQL 代码块的"？"。  
  
- **REF CURSOR 出**。 出 REF CURSOR 参数返回为强类型化或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数被声明为存储过程或函数定义中的强类型化或弱类型化的 REF CURSOR 在 Oracle 服务器上。  
  
- **在 OUT REF CURSOR 参数**。 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的 OUT REF CURSOR 参数，它不能在 OUT REF CURSOR 参数支持一种类型。 出于此原因，它将 IN 出 REF CURSOR 参数视为两个不同的参数： IN 参数在请求消息和响应消息中的一个输出参数。  
  
  有关详细信息：  
  
- 调用的函数或过程涉及使用 REF CURSOR 参数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)。  
  
- 调用的函数或过程涉及使用 WCF 服务模型的 REF CURSOR 参数，请参阅[运行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
- 所支持的 REF CURSOR 的 XML 结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[REF CURSORS 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用适配器连接到 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)