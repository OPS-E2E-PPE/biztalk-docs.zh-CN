---
title: REF CURSOR 的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e41359bd9fa7a54a68de49bfe115ca7c563dfdb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979014"
---
# <a name="message-schemas-for-ref-cursors"></a>REF CURSOR 的消息架构
REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。 REF CURSOR 类型启用输入和输出流的数据非常适合用于传输大量数据传入和传出 PL/SQL 代码块。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] 为出将强类型化和弱类型化 REF CURSOR 参数传递给 PL/SQL 过程和函数中，并在 OUT 参数提供支持。  
  
 在 Oracle 数据库中，REF CURSOR 类型可以是强类型化或弱类型：  
  
- 使用作为中的 RETURN 子句声明强类型化 REF CURSOR `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`。 强类型化的 REF CURSOR 变量可以仅表示包含数据类型与其声明它的 REF CURSOR 类型相匹配的结果集。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]返回强类型化结果集的强类型化 REF CURSOR。  
  
- 弱类型化 REF 游标未声明为中的 RETURN 子句`TYPE WeakCurType IS REF CURSOR;`。 Oracle 还提供了一种特殊的 REF CURSOR 类型称为可用于声明弱类型化的 REF CURSOR 变量的 SYS_REFCURSOR。 弱类型化的 REF CURSOR 变量可以表示包含任何类型的行数据的结果集。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为弱类型化 REF CURSOR 返回弱类型化结果集的通用记录。  
  
## <a name="in-ref-cursor-parameters"></a>中的 REF CURSOR 参数  
 没有 ODP.NET API 创建 REF CURSOR 的 Oracle 服务器上，因此[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能提供的功能，可以创建和维护 REF CURSOR 变量的客户端程序。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，但是，启用客户端将在 REF CURSOR 参数传递给函数或存储的过程，通过指定返回 REF CURSOR 的 PL/SQL 代码块。 适配器使用此代码以创建并打开 Oracle 服务器; 上的 REF CURSOR 变量然后，它将调用该函数或存储过程中使用此变量作为 IN 参数。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN REF CURSOR 参数表示为包含 PL/SQL 代码块的字符串。 在此块中，用问号 （？） 指定 REF CURSOR 的位置。 PL/SQL 代码块可以包含包含 SQL 查询; 打开 FOR 语句也可以包含函数或过程调用中的 OUT 参数中返回打开的 REF CURSOR。  
  
 下面演示了如何通过调用存储的过程或函数，以打开 REF CURSOR 指定 IN REF CURSOR。  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 下面演示了如何使用 SELECT 查询以打开 REF CURSOR 指定 IN REF CURSOR。  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a>扩展的 REF CURSOR 参数  
 出 REF CURSOR 参数返回为强类型化或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数被声明为存储过程或函数定义中的强类型化或弱类型化的 REF CURSOR 在 Oracle 服务器上。 强类型化结果集返回强类型化 REF CURSOR 参数的和为弱类型化 REF CURSOR 参数返回弱类型化结果集 （例如，参数以 SYS_REFCURSOR 类型声明）。  
  
 下面显示了强类型化 OUT REF CURSOR 参数的 XML。  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 下面显示了弱类型化 OUT REF CURSOR 参数的 XML。  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a>在扩展的 REF CURSOR 参数  
 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的 OUT REF CURSOR 参数，它不能在 OUT REF CURSOR 参数支持一种类型。 出于此原因，它将 IN 出 REF CURSOR 参数视为两个不同的参数： IN 参数在请求消息和响应消息中的一个输出参数。  
  
 若要避免在服务模型编程中，名称冲突[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将字符串"_IN"追加到请求消息中的 IN 参数，因此，对于给定的参数名为 [PARAM_NAME]，创建两个参数：  
  
-   [PARAM_NAME] _IN 存储的过程或函数请求消息中是一个在 REF CURSOR 参数。 它包含返回 REF CURSOR 的 PL/SQL 语句 （select 查询或存储的过程或函数调用）。  
  
-   [PARAM_NAME] 存储的过程或函数响应消息中是一个 OUT REF CURSOR 参数。 它包含出 REF CURSOR 作为强类型化或弱类型化结果集。  
  
> [!IMPORTANT]
>  该适配器不能支持的过程或包含 IN 参数名为 [PARAM_NAME] _IN 和名为 [PARAM_NAME] 的 IN 出 REF CURSOR 参数的函数。 这是因为该适配器需要一个名为 [PARAM_NAME] _IN 来表示 REF CURSOR 参数的输入参数并不能在请求消息中指定这两个参数。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)