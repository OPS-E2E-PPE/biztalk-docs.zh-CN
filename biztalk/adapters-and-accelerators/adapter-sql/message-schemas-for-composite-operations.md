---
title: 复合操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716e87dd2973572d473f6637e12c5a80ac6cf847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015289"
---
# <a name="message-schemas-for-composite-operations"></a>复合操作的消息架构
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使您可以执行复合操作上的 SQL Server 数据库。 复合操作可以包含多个操作，包括 Insert、 Update 和删除表和视图操作和对存储过程的操作。 复合操作可以按任意顺序包含这些操作。  
  
 有关详细信息：  
  
- 复合操作，请参阅[支持复合操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)。  
  
- 如何执行复合操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[使用 SQL 适配器的 SQL Server 中运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)。  
  
## <a name="message-structure-for-the-composite-operation"></a>复合操作的消息结构  
 因为复合操作包含多个单个操作;复合操作的消息结构包含各个操作的消息的结构。 复合操作包含在表、 视图和存储的过程的操作，如复合操作消息遵循请求-响应消息交换模式。  
  
 下表显示了包含插入操作的复合操作的请求和响应消息的结构，不接受任何存储的过程输入参数和删除操作。  
  
|运算|XML 消息|  
|---------------|-----------------|  
|复合操作请求|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|复合操作的响应|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [PROJECT_NAME] = 包含复合操作架构的 BizTalk 项目的名称。  
  
 [COMPOSITE_SCHEMA_NAME] = 由用户提供的复合操作架构的名称。  
  
 [架构] = 集合的 SQL Server 项目;例如，dbo。  
  
 [TABLE_NAME] = 名称表;例如，员工。  
  
 [FIELD1_NAME] = 表字段名称;例如，名称。  
  
 [SP_NAME] = 存储的过程来执行;例如，ADD_EMP_DETAILS。  
  
## <a name="message-action-for-the-composite-operation"></a>复合操作的消息操作  
 复合操作的消息操作是"CompositeOperation。"  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)