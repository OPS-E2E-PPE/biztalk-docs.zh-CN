---
title: SQLEXECUTE 操作的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7efc6a59e9dd4c163388803763a7b90a13b31
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a>SQLEXECUTE 操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现强类型的项目在 LOB 系统中存在的元数据，并公开这些项目上的标准操作。 但是，有一些的情形其中的应用程序可能需要根据应用程序中的业务逻辑的任意 SQL 语句的执行。 例如，你可能希望：  
  
-   执行上不显示的数据库项目的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
-   执行数据定义语言操作;例如，创建一个表。  
  
-   在未出现在设计时; 一个数据库项目上执行操作例如，更新中创建由业务逻辑的临时表的记录。  
  
-   执行对表比显示操作的更复杂 DML 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 对于范例执行包含对 JOIN 子句的查询。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现调用 SQLEXECUTE 操作来支持这种情况下的特殊操作。 通过使用此操作，你可以指定任意 SQL 语句[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle 数据库执行。 你还可以指定 SQL 语句的输入参数的多个块。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行一次为每个参数集的 SQL 语句并返回任何输出作为泛型的 （弱类型） 的记录集。  
  
> [!NOTE]
>  你可以将传递 IN 和到过程、 函数和 SQLEXECUTE 操作中的包在 OUT 参数。 调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回扩展的值和到客户端在 OUT 参数。 如果你想要调用过程、 函数或包，Microsoft 建议您这样做通过调用专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开，以便这些 Oracle 项目。  
  
 下面的 XML 演示 SQLEXECUTE 操作的结构：  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 [语句] = 要执行; 的 SQL 语句例如，"选择 * 从 emp WHERE empno =: emp_no"。  
  
 [PARAM_SPEC] = SQL 语句和其数据类型; 中的 IN 参数的列表例如，"emp_no 数"。  
  
 [PARAM_VAL_1] = 的第一个参数的值。  
  
 每个\<PARAMETERDATA\>部分包含一组完整的\<参数\>相匹配的架构中的元素\<PARAMETERSCHEMA\>部分。 \<PARAMETERSET\>可以包含多个\<PARAMETERDATA\>部分。 如果出现这种情况，SQL 语句执行多次，一次针对每个参数集。  
  
## <a name="see-also"></a>另请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)