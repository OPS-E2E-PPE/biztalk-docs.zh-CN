---
title: 支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作 |Microsoft 文档
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
ms.openlocfilehash: 40bad547627669bb22a6b32f05d96c6c7b2f68c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215717"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a>支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开在根级别以下的出站操作：  
  
-   **ExecuteNonQuery**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回多个结果集。 此函数的输入的参数包括字符串参数 （整个 PL/SQL 块中要执行） 和字符串 (OutRefCursorNames) 的数组。 OutRefCursorNames 中指定每个字符串值假定为 PL/SQL 块返回 REF CURSOR 具有相同的名称与 REF CURSOR 的输出的参数名称。 此函数还采用 OUT 参数 (OutRefCursors)，这是数据集的数组。 有关数据集的信息，请参阅 Oracle 文档： [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)。 此操作的返回值的整数数据类型，并指示受影响的行数。  
  
-   **ExecuteReader**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要作为数据集返回的结果集。 此操作采用字符串参数作为输入，并返回一个数据集。  
  
-   **ExecuteScalar**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回一个值。 如果返回值是一个结果集，仅第一行的第一列中的值则返回以 XML 字符串格式。  
  
> [!NOTE]
>  -   ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作不支持用户定义类型 (Udt)。  
> -   您还可以设置中的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 它是必需的设置 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文，如果任何操作针对的是 Oracle E-business Suite （接口表、 接口视图、 并发程序或请求中的项目设置）。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)