---
title: 支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30669e4f055e6a9783b87d78e774944370421b70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374530"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a>支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开的根级别以下的出站操作：  
  
-   **ExecuteNonQuery**:此操作用于在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回多个结果集。 此函数的输入的参数包括字符串参数 （在整个 PL/SQL 块中执行） 和一个字符串 (OutRefCursorNames) 数组。 OutRefCursorNames 中指定每个字符串值被假定为与 PL/SQL 块具有相同名称返回 REF CURSOR 的 REF CURSOR 的输出的参数名称。 此函数还采用一个输出参数 (OutRefCursors)，这是数据集的数组。 有关数据集的信息，请参阅 Oracle 文档，网址[ http://go.microsoft.com/fwlink/?LinkId=124538 ](http://go.microsoft.com/fwlink/?LinkId=124538)。 此操作的返回值是整数数据类型，并指示受影响的行数。  
  
-   **ExecuteReader**:此操作用于在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要作为数据集返回的结果集。 此操作采用字符串参数作为输入，并返回一个数据集。  
  
-   **ExecuteScalar**:此操作用于在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回一个值。 如果返回值是结果集，仅第一行的第一列中的值是以 XML 字符串格式返回。  
  
> [!NOTE]
> - ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作不是支持用户定义类型 (Udt)。  
>   - 此外可以设置中的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 为强制设置 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文，如果 Oracle E-business Suite （接口表、 界面视图、 并发程序或请求中的某个项目针对的任何操作设置）。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)