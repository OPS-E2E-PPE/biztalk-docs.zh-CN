---
title: 消息函数和过程的架构 |Microsoft 文档
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
ms.openlocfilehash: 6fc8c09499914dd075fe6a46fbc230a4bed104e0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "25964563"
---
# <a name="message-schemas-for-functions-and-procedures"></a>函数和过程的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]曲面 Oracle 数据库函数和存储的过程作为操作。 本部分介绍的消息结构和用于调用函数和过程的操作。  
  
## <a name="message-structure-of-functions-and-procedures"></a>函数和过程的消息结构  
 操作中加以表示的函数和存储的过程遵循请求-响应消息交换模式。 下表显示这些请求和响应消息的结构。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|存储的过程请求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|在消息正文中支持 Oracle IN 和 IN OUT 参数|  
|存储的过程响应|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|在消息正文中支持 Oracle 出和 IN OUT 参数|  
|函数请求|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|在消息正文中支持 Oracle IN 和 IN OUT 参数|  
|函数响应|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|在消息正文中支持 Oracle 出和 IN OUT 参数<br /><br /> 的在中返回函数的返回值\<[FN_NAME] 结果\>元素。 这是在响应消息中的第一个元素。 它位于之前任何参数。|  
|打包的过程或函数请求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|相同函数或存储的过程|  
|打包的过程或函数响应|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|相同函数或存储的过程|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程以执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PRM1_NAME] = Oracle 参数的名称。 请参阅受支持的参数方向为每个消息的说明列。  
  
 [PACKAGE_NAME] = 包含目标的过程或函数的包的名称。  
  
 Oracle 数据库支持的存储的过程和函数重载。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过将一个重载字符串追加到每个重载的项目的目标命名空间中支持此功能。 此字符串的值是"overload1"的第一个重载，"overload2"的第二个重载中，依次类推。 下面的示例演示两个重载的存储过程的消息结构。  
  
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
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|存储的过程请求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT|  
|存储的过程响应|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response|  
|函数请求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID|  
|函数响应|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response|  
|打包的存储的过程请求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT|  
|打包存储的过程响应|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response|  
|封装的函数请求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID|  
|封装的函数响应|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response|  
|重载的存储的过程请求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1|  
|重载存储的过程响应|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程以执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PACKAGE_NAME] = 包含目标的过程或函数的包的名称。  
  
 [重载] = 重载的参数。 可能的值为 overload1、 overload2，依次类推。  
  
## <a name="see-also"></a>另请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)