---
title: 对于复合 Operation2 消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ff8ec57d3c94e2191b1615593f0047e01b0e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967990"
---
# <a name="message-schemas-for-the-composite-operation"></a>复合操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]使您可以执行对 Oracle 数据库的复合操作。 复合操作可以包含多个操作，并按任何顺序。 有关哪些操作可以包含在复合操作的信息，请参阅[Oracle 数据库中运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)。  
  
 有关如何执行复合操作使用的信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。  
  
## <a name="message-structure-for-the-composite-operation"></a>复合操作的消息结构  
 因为复合操作包含多个单个操作;复合操作的消息结构包含各个操作的消息的结构。 复合操作消息遵循请求-响应消息交换模式。  
  
 下表显示了包含插入操作的复合操作的请求和响应消息的结构，打包的存储的过程，不接受任何输入参数和删除操作。  
  
|运算|XML 消息|  
|---------------|-----------------|  
|复合操作请求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|复合操作的响应|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.OracleDB/2007/03  
  
 [PROJECT_NAME] = 包含复合操作架构的 BizTalk 项目的名称。  
  
 [COMPOSITE_SCHEMA_NAME] = 由用户提供的复合操作架构的名称。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 名称表;例如，员工。  
  
 [FIELD1_NAME] = 表字段名称;例如，名称。  
  
 [SP_NAME] = 打包的存储的过程来执行;例如，ADD_EMP_DETAILS。  
  
 [PRM1_NAME] = 存储过程中的 Oracle 参数的名称。  
  
## <a name="message-action-for-the-composite-operation"></a>复合操作的消息操作  
 复合操作的消息操作是"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”>  
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)