---
title: "REF CURSOR 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bddfde0b0897c7d8c21a20126d2fa1d2f0f8c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-ref-cursors"></a>REF CURSOR 的消息架构
REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。 REF CURSOR 类型启用输入和输出流的数据以及适合传输大量数据传入和传出的 PL/SQL 代码块。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]提供对缩小将强类型和弱类型 REF CURSOR 参数传递给 PL/SQL 过程和函数中，和 IN OUT 参数的支持。  
  
 在 Oracle 数据库中，REF CURSOR 类型可以是强类型或弱类型：  
  
-   使用 RETURN 子句中声明强类型化的 REF CURSOR `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`。 强类型化的 REF CURSOR 变量只能表示包含数据与其声明其 REF CURSOR 类型的类型相匹配的结果集。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]返回强类型的结果集为强类型化的 REF CURSOR。  
  
-   弱类型化的 REF CURSOR 声明没有返回作为 in 子句`TYPE WeakCurType IS REF CURSOR;`。 Oracle 还提供了一种特殊的 REF CURSOR 类型，调用 SYS_REFCURSOR 可用来声明弱类型 REF CURSOR 变量。 弱类型 REF CURSOR 变量可以表示包含任何类型的行数据的结果集。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为弱类型化的 REF CURSOR 返回的泛型记录弱类型化结果集。  
  
## <a name="in-ref-cursor-parameters"></a>在 REF CURSOR 参数  
 没有 ODP.NET API 创建 REF CURSOR 在 Oracle 服务器上，因此[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]无法提供客户端程序来创建和维护 REF CURSOR 变量的功能。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，但是，让客户端将在 REF CURSOR 参数传递给函数或存储的过程，通过指定的返回 REF CURSOR 的 PL/SQL 代码块。 适配器使用此代码来创建并打开在 Oracle 服务器; 上的 REF CURSOR 变量然后，它将调用函数或存储过程使用此变量作为 IN 参数。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CURSOR 参数为包含 PL/SQL 代码块的字符串。 在此块中，用问号 （？） 指定 REF CURSOR 的位置。 PL/SQL 代码块可以包含包含 SQL 查询; 打开 FOR 语句也可以包含一个函数或过程调用中的 OUT 参数中返回打开的 REF CURSOR。  
  
 下面演示如何通过调用存储的过程或函数，以打开 REF CURSOR 中指定 IN REF CURSOR。  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 下面演示如何通过使用 SELECT 查询以打开 REF CURSOR 中指定 IN REF CURSOR。  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a>OUT REF CURSOR 参数  
 出 REF CURSOR 参数将返回为强类型或弱类型化结果集。 返回的结果集的类型取决于是否 REF CURSOR 参数声明为存储过程或函数定义中的强类型或弱类型化的 REF CURSOR 在 Oracle 服务器上。 强类型化结果集返回强类型化的 REF CURSOR 参数和弱类型化结果集返回弱类型 REF CURSOR 参数 （例如，参数与 SYS_REFCURSOR 类型声明）。  
  
 下面显示了强类型出 REF CURSOR 参数的 XML。  
  
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
  
 下图显示弱类型出 REF CURSOR 参数的 XML。  
  
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
  
## <a name="in-out-ref-cursor-parameters"></a>IN 出 REF CURSOR 参数  
 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的出 REF CURSOR 参数，它不能在出 REF CURSOR 参数支持单一类型。 为此，它将在出 REF CURSOR 参数视为两个不同的参数： 请求消息和响应消息中的 OUT 参数中的 IN 参数。  
  
 若要避免在服务模型编程中，名称冲突[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将字符串"_IN"附加到请求消息中的 IN 参数，这样，为给定的参数名为 [PARAM_NAME]，创建两个参数：  
  
-   [PARAM_NAME] _IN 中的存储的过程或函数的请求消息是一个在 REF CURSOR 参数。 它包含返回 REF CURSOR 的 PL/SQL 语句 （select 查询或存储的过程或函数调用）。  
  
-   [PARAM_NAME] 中的存储的过程或函数响应消息是一个 OUT REF CURSOR 参数。 它包含出 REF CURSOR 作为强类型或弱类型化结果集。  
  
> [!IMPORTANT]
>  适配器不能支持的过程或包含一个名为 [PARAM_NAME] _IN 和名为 [PARAM_NAME] IN 出 REF CURSOR 参数的 IN 参数的函数。 这是因为该适配器需要一个名为 [PARAM_NAME] _IN 来表示对 REF CURSOR 参数的输入参数并且不能在请求消息中指定这两个参数。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)