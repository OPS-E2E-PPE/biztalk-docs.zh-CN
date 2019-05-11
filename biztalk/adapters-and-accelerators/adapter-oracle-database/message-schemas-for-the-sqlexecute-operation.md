---
title: SQLEXECUTE 操作的消息架构 |Microsoft Docs
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
ms.openlocfilehash: dbf495f6e9e749cb9668dd3ff52c361b8e248ba1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376765"
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a>SQLEXECUTE 操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] LOB 系统中的项目的强类型元数据的图面，并公开这些项目上的标准操作。 但是，有一个应用程序需要由应用程序中的业务逻辑驱动的任意 SQL 语句执行的方案。 例如，您可能希望：  
  
- 不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
- 执行数据定义语言操作;例如，创建一个表。  
  
- 如果没有安装在设计时; 一个数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。  
  
- 执行更复杂表上显示的操作比的 DML 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 对于范例执行包含 JOIN 子句的查询。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示名为 SQLEXECUTE 操作来支持这种情况下的特殊操作。 通过使用此操作，可以指定任意 SQL 语句为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle 数据库执行。 此外可以指定多个输入参数的 SQL 语句的块。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行每组参数一次的 SQL 语句并返回作为泛型 （弱类型化） 记录集的任何输出。  
  
> [!NOTE]
>  可以将传递在和中 OUT 参数到过程、 函数和 SQLEXECUTE 操作中的包。 调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回输出的值并向客户端在 OUT 参数。 如果你想要调用过程、 函数或包，Microsoft 建议您这样做的调用专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对这些 Oracle 项目公开。  
  
 以下 XML 显示了 SQLEXECUTE 操作的结构：  
  
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
  
 [语句] = 的 SQL 语句来执行;例如，"选择 * 从 emp WHERE empno =: emp_no"。  
  
 [PARAM_SPEC] = SQL 语句和其数据类型; 中的 IN 参数的列表例如，"emp_no 数"。  
  
 [PARAM_VAL_1] = 第一个参数的值。  
  
 每个\<PARAMETERDATA\>部分包含一组完整的\<参数\>相匹配的架构中的元素\<PARAMETERSCHEMA\>部分。 \<PARAMETERSET\>可以包含多个\<PARAMETERDATA\>部分。 如果这种情况，SQL 语句执行多次，一次针对每个参数集。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)