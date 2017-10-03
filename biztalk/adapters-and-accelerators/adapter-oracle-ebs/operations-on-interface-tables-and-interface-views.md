---
title: "对接口表和接口视图的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c7f3453-848f-42df-b092-725d9ff466cf
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ec9b7c5f952b6be60a3c3463e6ea0682faa9d4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-interface-tables-and-interface-views"></a>对接口表和接口视图的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]呈现一套标准的操作 （选择、 插入、 更新和删除的每个接口表） 和 Oracle E-business Suite 中每个接口视图的选择操作。 通过使用这些操作，你可以执行选择、 插入、 更新和删除限定由目标接口表，WHERE 子句的语句和限定由目标接口视图在 WHERE 子句的 SELECT 语句。 这些操作也称为数据操作语言 (DML) 操作。  
  
> [!IMPORTANT]
>  你可以执行对接口表和界面视图的操作之前，必须将这些项目中的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。 有关应用程序上下文以及如何将其设置的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

## <a name="supported-dml-operations"></a>支持的 DML 操作  
 下表显示的 DML 操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持：  
  
|运算|Description|  
|---------------|-----------------|  
|选择|执行基于提供的列名称和一个筛选器字符串，指定的 SQL WHERE 子句列表的目标接口表或接口视图上的选择操作。<br /><br /> 选择操作的返回值是一个强类型化结果集包含指定的列和行。|  
|Insert|执行对目标接口表的插入操作。 基于提供的记录集目标接口表中插入的操作支持多个记录插入。<br /><br /> 插入操作的返回值是插入的行数。<br /><br /> **InlineValue**<br /><br /> 对于插入操作中的所有简单数据记录，你可以选择通过指定调用一个可选属性的值覆盖记录的值**InlineValue**。 InlineValue 属性可用来计算的值插入接口表，例如填充到日期列的主键列使用序列或将其插入 （使用 SYSDATE） 的系统日期。 例如，在以下的 INSERT 语句：<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> 即使"2008年-06-21T15:52:19"为 TRNS_DATE 的值指定为值**InlineValue**属性，"SYSDATE，"会插入到目标接口表 （系统日期）。<br /><br /> 在使用 InlineValue 属性：<br /><br /> -请避免使用 InlineValue 属性的常量值。 例如，在 INSERT 语句中，如果你指定`<EMPNAME InlineValue="John"/>`然后它将导致错误。 这是因为 InlineValue 属性的值作为传递根据-于 Oracle，并在此情况下*John*传递给 Oracle E-business Suite，这不是预期值 (预期值是*John*)。 你将必须使用在员工名称的前后的单引号。 例如： `<EMPNAME InlineValue="’John’"/>`。<br /><br /> -如果你想要用于该 InlineValue 属性的 select 查询，必须用括号括起来的 SELECT 语句，并还确保 select 查询提取单个记录。 例如： `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`。<br /><br /> **注意：**如果元素被标记为 NOT NULL Oracle E-business Suite 中，你必须指定该元素的值，即使你指定的内联值。 如果不这样做将导致架构验证失败。|  
|Update|执行更新操作的目标接口表。 要更新的记录都由一个筛选器字符串，指定的 SQL WHERE 子句指定。 模板记录中指定的更新的值。<br /><br /> 对于更新操作的返回值是更新的行数。|  
|DELETE|执行基于筛选器字符串中指定的 SQL WHERE 子句的目标接口表删除操作。<br /><br /> 删除操作的返回值是删除的行数。|  

## <a name="important-details"></a>重要详细信息  
  -   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]呈现组相同的标准操作 （选择、 插入、 更新和删除的每个表） 和基础的 Oracle 数据库中每个视图的选择操作。 在上面的 DML 操作还可用于的基础的 Oracle 数据库表和视图。  

 -   不需要设置要执行的 Oracle 数据库中的表和视图上的操作的应用程序上下文。 但是，对于自定义的 Oracle E-business Suite 应用程序，用户可能或可能不为接口表进行注册的基数据库表。 如果未作为接口表注册数据库表，它位于下**表**中的子节点**项目基于视图**节点或在**架构基于视图**节点在设计时使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
    这些表是与 Oracle 电子商务应用程序相关联。 因此在这些表上的任何操作，必须设置应用程序上下文。 请参阅设置应用程序上下文[此处输入链接说明](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)