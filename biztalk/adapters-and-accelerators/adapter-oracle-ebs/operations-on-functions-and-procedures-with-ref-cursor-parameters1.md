---
title: 对函数和过程与 REF CURSOR Parameters1 操作 |Microsoft 文档
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
ms.openlocfilehash: dee169bca7546c404edaccce6b7a1835e3c209a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215485"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>对函数和过程与 REF CURSOR 参数的操作
REF CURSOR 是表示指向服务器端结果集通过执行查询生成的指针的 PL/SQL 数据类型。 REF CURSOR 类型使输入和输出流的数据非常适合传输大量数据传入和传出的 PL/SQL 代码。 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>强类型和弱类型化的 REF Cursor
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供强类型和弱类型 (SYS_REFCURSOR) REF Cursor，可传递给 PL/SQL 过程和函数作为输入和输出参数的支持。  
  
-   **在 REF CURSOR**。 适配器客户端必须使用在 REF CURSOR，通过提供对 Oracle 数据库打开 REF CURSOR 的 PL/SQL 代码 （作为字符串）。 适配器创建变量并将它打开的 REF CURSOR，调用函数或与该变量的过程。 因此，在 REF CURSOR 参数中 PL/SQL 存储过程和函数应表示为将 PL/SQL 代码块作为标记出 REF CURSOR 变量输入值的字符串"？"。  
  
-   **REF CURSOR 出**。 出 REF CURSOR 参数将返回为强类型或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数声明为存储过程或函数定义中的强类型或弱类型化的 REF CURSOR 在 Oracle 服务器上。  
  
-   **在出 REF CURSOR 参数**。  因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的出 REF CURSOR 参数，它不能在出 REF CURSOR 参数支持单一类型。 为此，它将在出 REF CURSOR 参数视为两个不同的参数： 请求消息和响应消息中的 OUT 参数中的 IN 参数。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)