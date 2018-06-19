---
title: 特殊 LOB Operations1 的消息架构 |Microsoft 文档
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
ms.openlocfilehash: b57e329d1de4740cac230cbb1e8151697d293dc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962579"
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊 LOB 操作的消息架构
Read_\<LOBColName\>和 Update_\<LOBColName\>操作中加以表示的表和视图包含 LOB 列，其中\<LOBColName\>是表中的 LOB 列或视图。 这些操作，可以读取或写入 LOB 数据作为 base64Binary 编码数据的流。 它们对单个列的单个行中的 LOB 数据的操作。  
  
 有关概述 Read_\<LOBColName\>和 Update_\<LOBColName\>操作和 Oracle LOB 数据类型支持，请参阅[接口表、 界面视图、 表上的操作和包含 LOB 数据的视图](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  
  
## <a name="message-structure-of-lob-data-type-operations"></a>LOB 数据类型操作的消息结构  
 下表显示请求和响应消息的结构为 Read_\<LOBColName\>和 Update_\<LOBColName\>操作。 该操作的目标表中的消息操作指定，也会出现在目标命名空间。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|Read_\<LOBColName\>|`<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`|LOB 数据行相匹配的位置中返回筛选器元素中指定的子句。 Where 子句应匹配只有一行。 如果存在多个匹配的行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。|  
|Read_\<LOBColName\>响应|`<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>`|LOB 数据作为 base64Binary 编码数据的流返回。|  
|Update_\<LOBColName\>|`<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`|LOB 数据中的行的匹配 where 子句的筛选器元素中指定更新中的数据\<数据\>元素。 Where 子句应匹配只有一行。 如果存在多个匹配的行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]引发异常。<br /><br /> **请注意**更新 BLOB 列时\<数据\>元素必须始终包含一个 base64 编码值。 CLOB 和 NCLOB、\<数据\>元素可包含字符串值。|  
|Update_\<LOBColName\>响应|`<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`|返回一个空响应。|  
  
 实体说明：  
  
 [VERSION] = 消息版本字符串;例如，"http://schemas.microsoft.com/OracleEBS/2008/05"。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 包含目标的 LOB 列; 的表例如，客户。  
  
 [LOBCol_Name] = LOB 列; 的名称例如，照片。  
  
 [WHERE_clause] = An Oracle 数据库的 SELECT 语句的 WHERE 子句，匹配单个行;例如，ID = 1。  
  
 [LOB_DATA] = base64Binary 类型中的 LOB 列数据。  
  
> [!IMPORTANT]
>  Read_ 消息结构\<LOBColName\>和 Update_\<LOBColName\>视图上的操作相同表只是该操作的命名空间指定视图而不是表：`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-lob-data-type-operations"></a>LOB 数据类型操作的消息操作  
 下表显示使用的消息操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为 Read_\<LOBColName\>和 Update_\<LOBColName\>对表的操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用表名称和消息操作中指定的 LOB 列名称来确定目标表和 LOB 操作的列。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|操作|示例|  
|---------------|------------|-------------|  
|Read_\<LOBColName\>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|Read_\<LOBColName\>响应|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|Update_\<LOBColName\>|**为 BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|**为 BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|Update_\<LOBColName\>响应|**为 BLOB**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|**为 BLOB**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> **CLOB 和 NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 实体说明：  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 包含目标的 LOB 列; 的表例如，客户。 (SCOTT。CUSTOMER 表是由安装这些示例中包含的 SQL 脚本。）  
  
 [LOBCol_Name] = LOB 列; 的名称例如，照片。  
  
> [!IMPORTANT]
>  Read_ 的消息操作\<LOBColName\>和 Update_\<LOBColName\>视图上的操作类似于用于表，只是操作的操作指定了一个视图，而不是表： `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle E-Business Suite 的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)