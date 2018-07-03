---
title: 对包含 REF CURSOR Parameters1 函数和过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6801c1e-7992-40a0-bab7-87957840cedd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7227d6fd100714c0b467f0b43537b364af98d37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978646"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>对包含 REF CURSOR 参数函数和过程的操作
REF CURSOR 是 PL/SQL 数据类型表示的指针指向服务器端结果集生成的执行查询。 REF CURSOR 类型支持输入和输出数据的流，适合用于传输大量数据传入和传出 PL/SQL 代码。 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>强类型化和弱类型化 REF Cursor
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供可以传递到 PL/SQL 过程和函数作为 IN 和 OUT 参数的强类型化和弱类型 (SYS_REFCURSOR) REF Cursor 的支持。  
  
- **REF CURSOR 中**。 适配器客户端必须通过提供的 Oracle 数据库打开 REF CURSOR 的 PL/SQL 代码 （如字符串） 使用 IN REF CURSOR。 适配器创建变量并将其设置打开的 REF CURSOR 并调用函数或使用该变量的过程。 因此，在 REF CURSOR 参数中 PL/SQL 存储过程和函数应表示为字符串将作为输入值标记出 REF CURSOR 变量的 PL/SQL 代码块的"？"。  
  
- **REF CURSOR 出**。 出 REF CURSOR 参数返回为强类型化或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数被声明为存储过程或函数定义中的强类型化或弱类型化的 REF CURSOR 在 Oracle 服务器上。  
  
- **在 OUT REF CURSOR 参数**。  因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的 OUT REF CURSOR 参数，它不能在 OUT REF CURSOR 参数支持一种类型。 出于此原因，它将 IN 出 REF CURSOR 参数视为两个不同的参数： IN 参数在请求消息和响应消息中的一个输出参数。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)