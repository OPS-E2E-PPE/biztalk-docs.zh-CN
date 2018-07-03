---
title: 消息架构的函数和过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a821de5ac4a05165f33fa7035880d239bd6892b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008574"
---
# <a name="message-schemas-for-functions-and-procedures"></a>函数和过程的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]表面 Oracle 数据库函数和存储的过程的操作。 本部分介绍的消息结构和操作用来调用函数和过程。  

## <a name="message-structure-of-functions-and-procedures"></a>消息结构的函数和过程  
 操作提供的函数和存储的过程遵循请求-响应消息交换模式。 下表显示了这些请求和响应消息的结构。  

|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|存储的过程请求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|消息正文中支持 Oracle IN 和在 OUT 参数|  
|存储的过程响应|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|消息正文中支持 Oracle 出和在 OUT 参数|  
|函数请求|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|消息正文中支持 Oracle IN 和在 OUT 参数|  
|函数响应|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|消息正文中支持 Oracle 出和在 OUT 参数<br /><br /> 的中返回函数返回值\<[FN_NAME] 结果\>元素。 这是在响应消息中的第一个元素。 这是所有参数之前。|  
|打包的过程或函数请求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|函数或存储的过程相同|  
|打包的过程或函数响应|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|函数或存储的过程相同|  

 [架构] = Oracle 集合项目;例如，SCOTT。  

 [SP_NAME] = 存储的过程来执行;例如，SP_INSERT。  

 [FN_NAME] = 函数来执行;例如，FN_GETID。  

 [PRM1_NAME] = Oracle 参数的名称。 请参阅说明列中的每条消息的支持的参数说明。  

 [PACKAGE_NAME] = 包，其中包含目标的过程或函数的名称。  

 Oracle database 支持的存储的过程和函数重载。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持此功能通过将重载字符串追加到每个重载的项目的目标命名空间。 此字符串的值是"overload1"用于第一个重载，"overload2"的第二个重载中，依次类推。 下面的示例显示了两个重载的存储过程的消息结构。  

```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  

Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  

## <a name="message-actions-of-functions-and-procedures"></a>消息操作的函数和过程  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对存储过程和函数操作中使用以下的消息操作。  


|               消息                |                                              操作                                              |                                          示例                                           |
|--------------------------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|       存储的过程请求       |            http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Procedure/ [SP_NAME]            |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT           |
|      存储的过程响应       |       http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Procedure/ [SP_NAME] / 响应        |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response      |
|           函数请求           |            http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Function/ [FN_NAME]             |           http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID            |
|          函数响应           |        http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Function/ [FN_NAME] / 响应        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response       |
|  打包的存储的过程请求   |     http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Package/ [PACKAGE_NAME] / [SP_NAME]      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT       |
|  打包的存储的过程响应  | http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Package/ [PACKAGE_NAME] / [SP_NAME] / 响应 |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response   |
|      封装的函数请求       |     http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Package/ [PACKAGE_NAME] / [FN_NAME]      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID        |
|      封装的函数响应      | http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Package/ [PACKAGE_NAME] / [FN_NAME] / 响应 |   http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response   |
| 重载的存储的过程请求  |      http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Procedure/ [SP_NAME] / [重载]       |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1      |
| 重载的存储的过程响应 |  http://Microsoft.LobServices.OracleDB/2007/03/[架构] /Procedure/ [SP_NAME] / [重载] / 响应  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response |

 [架构] = Oracle 集合项目;例如，SCOTT。  

 [SP_NAME] = 存储的过程来执行;例如，SP_INSERT。  

 [FN_NAME] = 函数来执行;例如，FN_GETID。  

 [PACKAGE_NAME] = 包，其中包含目标的过程或函数的名称。  

 [重载] = 重载的参数。 可能的值为 overload1、 overload2，等等。  

## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)