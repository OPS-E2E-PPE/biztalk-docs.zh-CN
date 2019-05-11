---
title: 对于特殊 LOB Operations1 消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc8461bf0f70515344206e677d2fa95d8c2858a1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528960"
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊 LOB 操作的消息架构
Read_\<LOBColName\>和 Update_\<LOBColName\>操作提供的表和视图包含 LOB 列，其中\<LOBColName\>是表中的 LOB 列或视图。 这些操作，可读取或写入 LOB 数据作为流 base64Binary 编码数据。 它们对单个列的单个行中的 LOB 数据的操作。  
  
 有关概述 Read_\<LOBColName\>和 Update_\<LOBColName\>操作和 Oracle LOB 数据类型的支持，请参阅[对界面表、 界面视图、 表的操作和包含 LOB 数据的视图](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  
  
## <a name="message-structure-of-lob-data-type-operations"></a>LOB 数据类型操作的消息结构  
 下表显示了请求和响应消息的结构 Read_\<LOBColName\>和 Update_\<LOBColName\>操作。 该操作的目标表中的消息操作指定和也会出现在目标命名空间。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|           操作            |                                                                                  XML 消息                                                                                  |                                                                                                                                                                                                                                                              Description                                                                                                                                                                                                                                                              |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      Read_\<LOBColName\>       |                           `<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`                           |                                                                                                           LOB 数据的匹配位置的行中返回筛选器元素中指定的子句。 Where 子句应匹配只有一行。 如果多个匹配行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。                                                                                                            |
|  Read_\<LOBColName\>响应  | `<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>` |                                                                                                                                                                                                                                  LOB 数据返回为 base64Binary 编码数据的流。                                                                                                                                                                                                                                   |
|     Update_\<LOBColName\>      |            `<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`            | LOB 数据中的行的匹配 where 子句筛选器元素中指定更新中的数据\<数据\>元素。 Where 子句应匹配只有一行。 如果多个匹配行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。<br /><br /> **请注意**更新 BLOB 列时\<数据\>元素必须始终包含一个 base64 编码值。 CLOB 和 NCLOB、\<数据\>元素可以具有字符串值。 |
| Update_\<LOBColName\>响应 |                                 `<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`                                  |                                                                                                                                                                                                                                                    返回一个空响应。                                                                                                                                                                                                                                                     |
  
 实体说明：  
  
 [VERSION] = 消息版本字符串;例如，"<http://schemas.microsoft.com/OracleEBS/2008/05>"。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 表包含目标的 LOB 列;例如，客户。  
  
 [LOBCol_Name] = LOB 列; 的名称例如，照片。  
  
 [WHERE_clause] = Oracle 数据库的 SELECT 语句 WHERE 子句相匹配的单个行;例如，ID = 1。  
  
 [LOB_DATA] = base64Binary 类型中的 LOB 列数据。  
  
> [!IMPORTANT]
>  Read_ 消息结构\<LOBColName\>和 Update_\<LOBColName\>视图上的操作不相同的表，只不过该操作的命名空间指定一个视图，而不是一个表：`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-lob-data-type-operations"></a>LOB 数据类型操作的消息操作  
 下表显示了使用的消息操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为 Read_\<LOBColName\>和 Update_\<LOBColName\>对表的操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用表名称和消息操作中指定的 LOB 列名称来确定目标表和 LOB 列的操作。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|操作|操作|示例|  
|---------------|------------|-------------|  
|Read_\<LOBColName\>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|Read_\<LOBColName\>响应|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|Update_\<LOBColName\>|**对于 BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|**对于 BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|Update_\<LOBColName\>响应|**对于 BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|**对于 BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 实体说明：  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 表包含目标的 LOB 列;例如，客户。 (SCOTT。CUSTOMER 表已安装的示例中包含的 SQL 脚本。）  
  
 [LOBCol_Name] = LOB 列; 的名称例如，照片。  
  
> [!IMPORTANT]
>  Read_ 的消息操作\<LOBColName\>和 Update_\<LOBColName\>视图上的操作类似于用于表格，只是操作的操作指定一个视图，而不是一个表： `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)