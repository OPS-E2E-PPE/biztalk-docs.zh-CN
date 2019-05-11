---
title: 对界面表和界面视图的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c7f3453-848f-42df-b092-725d9ff466cf
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8a2c6f62915622badda2001e60fc84f3ee7659
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375313"
---
# <a name="operations-on-interface-tables-and-interface-views"></a>对界面表和界面视图的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]显示一组标准操作 （Select、 Insert、 Update 和 Delete 的每个接口表，） 和 Oracle E-business Suite 中的每个接口视图的选择操作。 通过使用这些操作，可以执行 SELECT、 INSERT、 UPDATE 和删除语句限定由目标接口表，WHERE 子句和 SELECT 语句由目标界面视图上的 WHERE 子句限定。 这些操作也称为数据操作语言 (DML) 操作。  
  
> [!IMPORTANT]
>  您可以执行对界面表和界面视图的操作之前，必须设置这些项目中的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。 有关应用程序上下文以及如何将其设置的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

## <a name="supported-dml-operations"></a>支持的 DML 操作  
 下表显示的 DML 操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持：  
  
|操作|Description|  
|---------------|-----------------|  
|选择|执行基于提供的列名称和一个筛选器字符串，指定 SQL WHERE 子句列表的目标接口表或界面视图上的选择操作。<br /><br /> 选择操作的返回值是强类型化结果集包含指定的列和行。|  
|Insert|执行插入操作的目标接口表。 插入的操作支持多个记录插入到目标接口表基于提供的记录集。<br /><br /> 插入操作的返回值是插入的行数。<br /><br /> **InlineValue**<br /><br /> 对于插入操作中的所有简单的数据记录，你可以选择通过指定一个名为可选属性的值来覆盖记录的值**InlineValue**。 InlineValue 属性可用来将计算的值插入到接口表，例如填充到日期列的主键列使用一个序列，或将其插入 （使用 SYSDATE） 的系统日期。 例如，在下面的 INSERT 语句：<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> 即使"2008年-06-21T15:52:19"为 TRNS_DATE 的值指定为值**InlineValue**属性，"SYSDATE，"（系统日期） 将插入到目标接口表。<br /><br /> 同时使用 InlineValue 属性：<br /><br /> -避免 InlineValue 属性使用的常量值。 例如，在 INSERT 语句中，如果指定`<EMPNAME InlineValue="John"/>`则它将导致错误。 这是因为 InlineValue 属性的值以的方式传递的是到 Oracle，并且在此情况下*John*传递给 Oracle E-business Suite，不是预期值 (预期值是*John*)。 您将必须使用单引号雇员姓名。 例如： `<EMPNAME InlineValue="’John’"/>`。<br /><br /> -如果你想要使用的 select 查询 InlineValue 属性，必须将 SELECT 语句括在括号中，并还确保在 select 查询提取单个记录。 例如： `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`。<br /><br /> **注意：** 如果元素标记为 NOT NULL Oracle E-business Suite 中，您必须指定该元素的值，即使您指定的内联值。 无法执行此操作将导致架构验证失败。|  
|Update|执行更新操作的目标接口表。 由一个筛选器字符串，指定 SQL WHERE 子句指定要更新的记录。 模板记录中指定的更新的值。<br /><br /> 对于更新操作的返回值是更新的行数。|  
|DELETE|执行基于筛选器字符串中指定的 SQL WHERE 子句的目标接口表删除操作。<br /><br /> 删除操作的返回值是删除的行数。|  

## <a name="important-details"></a>重要详细信息  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]组相同的标准操作 （Select、 Insert、 Update 和 Delete 的每个表，） 和选择操作为基础的 Oracle 数据库中每个视图的图面。 在上面的 DML 操作也是有效的基础的 Oracle 数据库表和视图。  

  - 不需要设置要在 Oracle 数据库中执行对表和视图的操作的应用程序上下文。 但是，对于自定义 Oracle E-business Suite 应用程序，用户可能会或可能无法注册接口表为基础数据库表。 如果数据库表未注册为接口表，它位于下**表**中的子节点**项目基于视图**节点中或在**架构基于视图**节点在使用时的设计时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
    这些表与相关联的 Oracle 电子商务应用程序。 因此对于这些表上的任何操作，必须设置应用程序上下文。 请参阅设置应用程序上下文[此处输入链接说明](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)