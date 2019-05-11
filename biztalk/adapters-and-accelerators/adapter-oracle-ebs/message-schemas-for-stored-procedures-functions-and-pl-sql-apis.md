---
title: 消息架构的存储的过程、 函数和 PL SQL Api |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d707f10-470d-4390-bb5b-0301c326f375
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 518cdfa65b6083247784d37a2c49431f3631d9c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375399"
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a>存储的过程、 函数和 PL/SQL Api 的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]表面基础 Oracle 数据库的存储的过程、 函数和 PL/SQL Api （存储的过程和函数在包中的） 作为操作。 本部分介绍的消息结构和用于调用存储的过程、 函数和 PL/SQL Api 的操作。  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a>消息结构的存储的过程、 函数和 PL/SQL Api  
 操作提供的函数和存储的过程遵循请求-响应消息交换模式。 下表显示了这些请求和响应消息的结构。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|操作|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|存储的过程请求|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|消息正文中支持 Oracle IN 和在 OUT 参数|  
|存储的过程响应|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|消息正文中支持 Oracle 出和在 OUT 参数|  
|函数请求|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|消息正文中支持 Oracle IN 和在 OUT 参数|  
|函数响应|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|消息正文中支持 Oracle 出和在 OUT 参数<br /><br /> 函数返回值中返回\<[FN_NAME] 结果\>元素。 这是在响应消息中的第一个元素。 这是所有参数之前。|  
|PL/SQL API 请求|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|函数或存储的过程相同|  
|打包的过程或函数响应|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|函数或存储的过程相同|  
  
 实体说明：  
  
 [VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05.  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程来执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PRM1_NAME] = Oracle 参数的名称。 请参阅说明列中的每条消息的支持的参数说明。  
  
 [PACKAGE_NAME] = 包，其中包含目标的过程或函数的名称。  
  
 Oracle database 支持的存储的过程和函数重载。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持此功能通过将重载字符串追加到每个重载的项目的目标命名空间。 此字符串的值是"overload1"用于第一个重载，"overload2"的第二个重载中，依次类推。 下面的示例显示了两个重载的存储过程的消息结构。  
  
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
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下的消息操作使用的存储的过程、 函数和 PL/SQL API 操作。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|存储的过程请求|Procedures/[SCHEMA]/[SP_NAME]|Procedures/SCOTT/SP_INSERT|  
|存储的过程响应|Procedures/[SCHEMA]/[SP_NAME]/response|Procedures/SCOTT/SP_INSERT/response|  
|函数请求|Functions/[SCHEMA]/[FN_NAME]|Functions/SCOTT/FN_GETID|  
|函数响应|Functions/[SCHEMA]/[FN_NAME]/response|Functions/SCOTT/FN_GETID/response|  
|PL/SQL API 请求|[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]|SCOTT/Package/CUSTOMER/SP_INSERT|  
|打包的存储的过程响应|[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response|SCOTT/Package/CUSTOMER/SP_INSERT/response|  
|封装的函数请求|[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]|SCOTT/Package/CUSTOMER/FN_GETID|  
|封装的函数响应|[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response|SCOTT/Package/CUSTOMER/FN_GETID/response|  
|重载的存储的过程请求|[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]|SCOTT/Procedure/SP_INSERT/overload1|  
|重载的存储的过程响应|[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response|SCOTT/Procedure/SP_INSERT/overload1/response|  
  
 实体说明：  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [SP_NAME] = 存储的过程来执行;例如，SP_INSERT。  
  
 [FN_NAME] = 函数来执行;例如，FN_GETID。  
  
 [PACKAGE_NAME] = 包，其中包含目标的过程或函数的名称。  
  
 [重载] = 重载的参数。 可能的值为 overload1、 overload2，等等。  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)