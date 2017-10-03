---
title: "有关过程和函数消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4acfb29e-8774-4eb7-ba10-2dcb93d2b41a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374b4d3365ec3aaac86fb5004969cd4cc189271d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-procedures-and-functions"></a>有关过程和函数的消息架构
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]曲面 SQL Server 数据库存储的过程和标量和表值的函数作为操作。 本部分介绍的消息结构和操作用于调用过程和函数。  
  
## <a name="message-structure-of-procedures-and-functions"></a>消息结构的过程和函数  
 操作中加以表示的过程和函数遵循请求-响应消息交换模式。 下表显示这些请求和响应消息的结构。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|存储的过程请求|`<[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|-|  
|存储的过程响应|`<[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[SP_NAME]Result>      <DataSet>        <any>[Value]</any>       <any>[Value]</any>       …     </DataSet>   </[SP_NAME]Result>   <ReturnValue>[Value]</ReturnValue> </[SP_NAME]Response>`|存储过程的返回值是数据集的数组。|  
|强类型的存储的过程请求|`<[STRNG_SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[STRNG_SP_NAME]>`|-|  
|强类型的存储的过程响应|`<[STRNG_SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">     <StoredProcedureResultSet0>          <StoredProcedureResultSet0 xmlns:ns1="http://schemas.microsoft.com/Sql/2008/05/ProcedureResultSets/[SCHEMA]/[STRNG_SP_NAME]">               <[PRM1_NAME]>value1<[PRM1_NAME]>               <[PRM2_NAME]>value2</[PRM2_NAME]>               …         </StoredProcedureResultSet0>     </StoredProcedureResultSet0>    <ReturnValue>[Value]</ReturnValue> </[STRNG_SP_NAME]Response>`|强类型的存储过程的返回值是强类型数据的数组。|  
|标量函数请求|`<[SCLR_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[PRM_NAME]>value</[PRM_NAME]> </[SCLR_FN_NAME]>`|-|  
|标量函数响应|`<[SCLR_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[SCLR_FN_NAME]Result>return_value</[SCLR_FN_NAME]Result>   <[PRM_NAME]>value</[PRM_NAME]>   </[SCLR_FN_NAME]Response>`|-|  
|表值的函数请求|`<[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[TBL_FN_NAME]>`|-|  
|表值的函数响应|`<[TBL_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[TBL_FN_NAME]Result>      <[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">         <[PRM1_NAME]>value1</[PRM1_NAME]>         <[PRM2_NAME]>value2</[PRM2_NAME]>         ...      </[TBL_FN_NAME]">        ...      </[TBL_FN_NAME]Result> </[TBL_FN_NAME]Response>`||  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
 [SP_NAME] = 存储的过程以执行;例如，ADD_EMP_DETAILS。  
  
 [STRNG_SP_NAME] = 强类型化存储的过程以执行;例如，GET_EMP_DETAILS。  
  
 [SCLR_FN_NAME] = 要执行; 标量函数例如，GET_EMP_ID。  
  
 [TBL_FN_NAME] = 要执行; 表值函数例如，TVF_EMPLOYEE。  
  
 [PRM_NAME] = SQL Server 参数的名称。  
  
## <a name="message-actions-of-functions-and-procedures"></a>消息操作的函数和过程  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]针对存储过程和函数操作中使用以下的消息操作。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|存储的过程请求|过程 / [架构] / [SP_NAME]|过程/dbo/ADD_EMP_DETAILS|  
|存储的过程响应|过程 / [架构] / [SP_NAME] / 响应|过程/dbo/ADD_EMP_DETAILS/响应|  
|强类型的存储的过程请求|TypedProcedure / [架构] / [STRNG_SP_NAME]|TypedProcedure/dbo/GET_EMP_DETAILS|  
|强类型的存储的过程响应|TypedProcedure / [架构] / [STRNG_SP_NAME] / 响应|TypedProcedure/dbo/GET_EMP_DETAILS/响应|  
|对于 XML 存储过程请求|XmlProcedure / [架构] / [SP_NAME]|XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML|  
|对于 XML 存储过程响应|XmlProcedure / [架构] / [SP_NAME] / 响应|XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML/响应|  
|标量函数请求|ScalarFunction / [架构] / [SCLR_FN_NAME]|ScalarFunction/dbo/GET_EMP_ID|  
|标量函数响应|ScalarFunction / [架构] / [SCLR_FN_NAME] / 响应|ScalarFunction/dbo/GET_EMP_ID/响应|  
|表值的函数请求|TableFunction / [架构] / [TBL_FN_NAME]|TableFunction/dbo/TVF_EMPLOYEE|  
|表值的函数响应|TableFunction / [架构] / [TBL_FN_NAME] / 响应|TableFunction/dbo/TVF_EMPLOYEE/响应|  
  
 [SP_NAME] = 存储的过程以执行;例如，ADD_EMP_DETAILS。  
  
 [STRNG_SP_NAME] = 强类型化存储的过程以执行;例如，GET_EMP_DETAILS。  
  
 [SCLR_FN_NAME] = 要执行; 标量函数例如，GET_EMP_ID。  
  
 [TBL_FN_NAME] = 要执行; 表值函数的名称例如，TVF_EMPLOYEE。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 SQL Server 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)