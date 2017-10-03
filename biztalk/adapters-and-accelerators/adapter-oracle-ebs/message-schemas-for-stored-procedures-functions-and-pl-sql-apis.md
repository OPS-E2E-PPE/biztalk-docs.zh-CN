---
title: "消息存储的过程、 函数和 PL SQL Api 的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d707f10-470d-4390-bb5b-0301c326f375
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6364716793e3638d157e1441e369133dc79bda95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a>存储的过程、 函数和 PL/SQL Api 的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]曲面基础 Oracle 数据库存储的过程、 函数和 PL/SQL Api （存储的过程和函数在一个包内的） 作为操作。 本部分介绍的消息结构和用于调用存储的过程、 函数和 PL/SQL Api 的操作。  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a>消息结构的存储的过程、 函数和 PL/SQL Api  
 操作中加以表示的函数和存储的过程遵循请求-响应消息交换模式。 下表显示这些请求和响应消息的结构。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|存储的过程请求|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|在消息正文中支持 Oracle IN 和 IN OUT 参数|  
|存储的过程响应|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|在消息正文中支持 Oracle 出和 IN OUT 参数|  
|函数请求|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|在消息正文中支持 Oracle IN 和 IN OUT 参数|  
|函数响应|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|在消息正文中支持 Oracle 出和 IN OUT 参数<br /><br /> 函数返回值返回在\<[FN_NAME] 结果 > 元素。 这是在响应消息中的第一个元素。 它位于之前任何参数。|  
|PL/SQL API 请求|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|相同函数或存储的过程|  
|打包的过程或函数响应|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|相同函数或存储的过程|  
  
 实体说明：  
  
 [VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程以执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PRM1_NAME] = Oracle 参数的名称。 请参阅受支持的参数方向为每个消息的说明列。  
  
 [PACKAGE_NAME] = 包含目标的过程或函数的包的名称。  
  
 Oracle 数据库支持的存储的过程和函数重载。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过将一个重载字符串追加到每个重载的项目的目标命名空间中支持此功能。 此字符串的值是"overload1"的第一个重载，"overload2"的第二个重载中，依次类推。 下面的示例演示两个重载的存储过程的消息结构。  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a>消息操作的存储的过程、 函数和 PL/SQL Api  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于存储的过程、 函数和 PL/SQL API 操作的以下的消息操作。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|存储的过程请求|过程 / [架构] / [SP_NAME]|过程/SCOTT/SP_INSERT|  
|存储的过程响应|过程 / [架构] / [SP_NAME] / 响应|过程/SCOTT/SP_INSERT/响应|  
|函数请求|函数 / [架构] / [FN_NAME]|函数/SCOTT/FN_GETID|  
|函数响应|函数 / [架构] / [FN_NAME] / 响应|函数/SCOTT/FN_GETID/响应|  
|PL/SQL API 请求|[架构] /Package/ [PACKAGE_NAME] / [SP_NAME]|SCOTT/包/客户/SP_INSERT|  
|打包存储的过程响应|[架构] /Package/ [PACKAGE_NAME] / [SP_NAME] / 响应|SCOTT/包/客户/SP_INSERT/响应|  
|封装的函数请求|[架构] /Package/ [PACKAGE_NAME] / [FN_NAME]|SCOTT/包/客户/FN_GETID|  
|封装的函数响应|[架构] /Package/ [PACKAGE_NAME] / [FN_NAME] / 响应|SCOTT/包/客户/FN_GETID/响应|  
|重载的存储的过程请求|[架构] /Procedure/ [SP_NAME] / [重载]|SCOTT/过程/SP_INSERT/overload1|  
|重载存储的过程响应|[架构] /Procedure/ [SP_NAME] / [重载] / 响应|SCOTT/过程/SP_INSERT/overload1/响应|  
  
 实体说明：  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程以执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PACKAGE_NAME] = 包含目标的过程或函数的包的名称。  
  
 [重载] = 重载的参数。 可能的值为 overload1、 overload2，依次类推。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)