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
ms.openlocfilehash: a0d44d12bab47aba1335261970a11199b86803a2
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752877"
---
# <a name="message-schemas-for-functions-and-procedures"></a><span data-ttu-id="2bdc9-102">函数和过程的消息架构</span><span class="sxs-lookup"><span data-stu-id="2bdc9-102">Message Schemas for Functions and Procedures</span></span>
<span data-ttu-id="2bdc9-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]表面 Oracle 数据库函数和存储的过程的操作。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces Oracle database functions and stored procedures as operations.</span></span> <span data-ttu-id="2bdc9-104">本部分介绍的消息结构和操作用来调用函数和过程。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-104">This section describes the message structure and actions used to invoke functions and procedures.</span></span>  

## <a name="message-structure-of-functions-and-procedures"></a><span data-ttu-id="2bdc9-105">消息结构的函数和过程</span><span class="sxs-lookup"><span data-stu-id="2bdc9-105">Message Structure of Functions and Procedures</span></span>  
 <span data-ttu-id="2bdc9-106">操作提供的函数和存储的过程遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-106">The operations surfaced for functions and stored procedures follow a request-response message exchange pattern.</span></span> <span data-ttu-id="2bdc9-107">下表显示了这些请求和响应消息的结构。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-107">The following table shows the structure of these request and response messages.</span></span>  

|<span data-ttu-id="2bdc9-108">运算</span><span class="sxs-lookup"><span data-stu-id="2bdc9-108">Operation</span></span>|<span data-ttu-id="2bdc9-109">XML 消息</span><span class="sxs-lookup"><span data-stu-id="2bdc9-109">XML Message</span></span>|<span data-ttu-id="2bdc9-110">Description</span><span class="sxs-lookup"><span data-stu-id="2bdc9-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="2bdc9-111">存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-111">Stored Procedure Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="2bdc9-112">消息正文中支持 Oracle IN 和在 OUT 参数</span><span class="sxs-lookup"><span data-stu-id="2bdc9-112">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="2bdc9-113">存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-113">Stored Procedure Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="2bdc9-114">消息正文中支持 Oracle 出和在 OUT 参数</span><span class="sxs-lookup"><span data-stu-id="2bdc9-114">Supports Oracle OUT and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="2bdc9-115">函数请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-115">Function Request</span></span>|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|<span data-ttu-id="2bdc9-116">消息正文中支持 Oracle IN 和在 OUT 参数</span><span class="sxs-lookup"><span data-stu-id="2bdc9-116">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="2bdc9-117">函数响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-117">Function Response</span></span>|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|<span data-ttu-id="2bdc9-118">消息正文中支持 Oracle 出和在 OUT 参数</span><span class="sxs-lookup"><span data-stu-id="2bdc9-118">Supports Oracle OUT and IN OUT parameters in the message body</span></span><br /><br /> <span data-ttu-id="2bdc9-119">的中返回函数返回值`<[FN_NAME]Result\>`元素。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-119">- The function return value is returned in the `<[FN_NAME]Result\>` element.</span></span> <span data-ttu-id="2bdc9-120">这是在响应消息中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-120">This is the first element in the response message.</span></span> <span data-ttu-id="2bdc9-121">这是所有参数之前。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-121">It comes before any parameters.</span></span>|  
|<span data-ttu-id="2bdc9-122">打包的过程或函数请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-122">Packaged Procedure or Function Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="2bdc9-123">函数或存储的过程相同</span><span class="sxs-lookup"><span data-stu-id="2bdc9-123">Same as Function or Stored Procedure</span></span>|  
|<span data-ttu-id="2bdc9-124">打包的过程或函数响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-124">Packaged Procedure or Function Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="2bdc9-125">函数或存储的过程相同</span><span class="sxs-lookup"><span data-stu-id="2bdc9-125">Same as Function or Stored Procedure</span></span>|  

 <span data-ttu-id="2bdc9-126">`[SCHEMA]` = Oracle 项目; 的集合例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-126">`[SCHEMA]` = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="2bdc9-127">`[SP_NAME]` = 要执行; 存储的过程例如，SP_INSERT。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-127">`[SP_NAME]` = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="2bdc9-128">`[FN_NAME]` = 要执行; 函数例如，FN_GETID。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-128">`[FN_NAME]` = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="2bdc9-129">`[PRM1_NAME]` = Oracle 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-129">`[PRM1_NAME]` = The name of the Oracle parameter.</span></span> <span data-ttu-id="2bdc9-130">请参阅说明列中的每条消息的支持的参数说明。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-130">See the Description column for supported parameter directions for each message.</span></span>  

 <span data-ttu-id="2bdc9-131">`[PACKAGE_NAME]` = 包含目标的过程或函数的包的名称。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-131">`[PACKAGE_NAME]` = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="2bdc9-132">Oracle database 支持的存储的过程和函数重载。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-132">The Oracle database supports overloading for stored procedures and functions.</span></span> <span data-ttu-id="2bdc9-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持此功能通过将重载字符串追加到每个重载的项目的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports this capability by appending an overload string to the target namespace for each overloaded artifact.</span></span> <span data-ttu-id="2bdc9-134">此字符串的值是"overload1"用于第一个重载，"overload2"的第二个重载中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-134">The value of this string is "overload1" for the first overload, "overload2" for the second overload, and so on.</span></span> <span data-ttu-id="2bdc9-135">下面的示例显示了两个重载的存储过程的消息结构。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-135">The following example shows the message structure for two overloaded stored procedures.</span></span>  

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

## <a name="message-actions-of-functions-and-procedures"></a><span data-ttu-id="2bdc9-136">消息操作的函数和过程</span><span class="sxs-lookup"><span data-stu-id="2bdc9-136">Message Actions of Functions and Procedures</span></span>  
 <span data-ttu-id="2bdc9-137">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对存储过程和函数操作中使用以下的消息操作。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-137">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the following message actions for stored procedure and function operations.</span></span>  


|               <span data-ttu-id="2bdc9-138">消息</span><span class="sxs-lookup"><span data-stu-id="2bdc9-138">Message</span></span>                |                                              <span data-ttu-id="2bdc9-139">操作</span><span class="sxs-lookup"><span data-stu-id="2bdc9-139">Action</span></span>                                              |                                          <span data-ttu-id="2bdc9-140">示例</span><span class="sxs-lookup"><span data-stu-id="2bdc9-140">Example</span></span>                                           |
|--------------------------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|       <span data-ttu-id="2bdc9-141">存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-141">Stored Procedure Request</span></span>       |            `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]`            |          `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT`           |
|      <span data-ttu-id="2bdc9-142">存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-142">Stored Procedure Response</span></span>       |       `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/response`        |      `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response`      |
|           <span data-ttu-id="2bdc9-143">函数请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-143">Function Request</span></span>           |            `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]`             |           `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID`            |
|          <span data-ttu-id="2bdc9-144">函数响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-144">Function Response</span></span>           |        `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]/response`        |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response`       |
|  <span data-ttu-id="2bdc9-145">打包的存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-145">Packaged Stored Procedure Request</span></span>   |     `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]`      |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT`       |
|  <span data-ttu-id="2bdc9-146">打包的存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-146">Packaged Stored Procedure Response</span></span>  | `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response` |  `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response`   |
|      <span data-ttu-id="2bdc9-147">封装的函数请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-147">Packaged Function Request</span></span>       |     `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]`      |       `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID`        |
|      <span data-ttu-id="2bdc9-148">封装的函数响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-148">Packaged Function Response</span></span>      | `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response` |   `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response`   |
| <span data-ttu-id="2bdc9-149">重载的存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="2bdc9-149">Overloaded Stored Procedure Request</span></span>  |      `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]`       |     `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1`      |
| <span data-ttu-id="2bdc9-150">重载的存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="2bdc9-150">Overloaded Stored Procedure Response</span></span> |  `http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response`  | `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response` |

 <span data-ttu-id="2bdc9-151">`[SCHEMA]` = Oracle 项目; 的集合例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-151">`[SCHEMA]` = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="2bdc9-152">`[SP_NAME]` = 要执行; 存储的过程例如，SP_INSERT。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-152">`[SP_NAME]` = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="2bdc9-153">`[FN_NAME]` = 要执行; 函数例如，FN_GETID。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-153">`[FN_NAME]` = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="2bdc9-154">`[PACKAGE_NAME]` = 包含目标的过程或函数的包的名称。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-154">`[PACKAGE_NAME]` = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="2bdc9-155">`[OVERLOAD]` = 该重载的参数。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-155">`[OVERLOAD]` = The Overload parameter.</span></span> <span data-ttu-id="2bdc9-156">可能的值为 overload1、 overload2，等等。</span><span class="sxs-lookup"><span data-stu-id="2bdc9-156">The possible values are overload1, overload2, and so on.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2bdc9-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bdc9-157">See Also</span></span>  
 [<span data-ttu-id="2bdc9-158">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="2bdc9-158">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
