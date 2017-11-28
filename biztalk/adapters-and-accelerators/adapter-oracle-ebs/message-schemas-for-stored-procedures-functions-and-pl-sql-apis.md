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
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="fc800-102">存储的过程、 函数和 PL/SQL Api 的消息架构</span><span class="sxs-lookup"><span data-stu-id="fc800-102">Message Schemas for Stored Procedures, Functions, and PL/SQL APIs</span></span>
<span data-ttu-id="fc800-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]曲面基础 Oracle 数据库存储的过程、 函数和 PL/SQL Api （存储的过程和函数在一个包内的） 作为操作。</span><span class="sxs-lookup"><span data-stu-id="fc800-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces the underlying Oracle database stored procedures, functions, and PL/SQL APIs (stored procedures and functions within a package) as operations.</span></span> <span data-ttu-id="fc800-104">本部分介绍的消息结构和用于调用存储的过程、 函数和 PL/SQL Api 的操作。</span><span class="sxs-lookup"><span data-stu-id="fc800-104">This section describes the message structure and actions used to invoke stored procedures, functions, and PL/SQL APIs.</span></span>  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="fc800-105">消息结构的存储的过程、 函数和 PL/SQL Api</span><span class="sxs-lookup"><span data-stu-id="fc800-105">Message Structure of Stored Procedures, Functions, and PL/SQL APIs</span></span>  
 <span data-ttu-id="fc800-106">操作中加以表示的函数和存储的过程遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="fc800-106">The operations surfaced for functions and stored procedures follow a request-response message exchange pattern.</span></span> <span data-ttu-id="fc800-107">下表显示这些请求和响应消息的结构。</span><span class="sxs-lookup"><span data-stu-id="fc800-107">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc800-108">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="fc800-108">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="fc800-109">运算</span><span class="sxs-lookup"><span data-stu-id="fc800-109">Operation</span></span>|<span data-ttu-id="fc800-110">XML 消息</span><span class="sxs-lookup"><span data-stu-id="fc800-110">XML Message</span></span>|<span data-ttu-id="fc800-111">Description</span><span class="sxs-lookup"><span data-stu-id="fc800-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="fc800-112">存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="fc800-112">Stored Procedure Request</span></span>|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="fc800-113">在消息正文中支持 Oracle IN 和 IN OUT 参数</span><span class="sxs-lookup"><span data-stu-id="fc800-113">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="fc800-114">存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="fc800-114">Stored Procedure Response</span></span>|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="fc800-115">在消息正文中支持 Oracle 出和 IN OUT 参数</span><span class="sxs-lookup"><span data-stu-id="fc800-115">Supports Oracle OUT and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="fc800-116">函数请求</span><span class="sxs-lookup"><span data-stu-id="fc800-116">Function Request</span></span>|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|<span data-ttu-id="fc800-117">在消息正文中支持 Oracle IN 和 IN OUT 参数</span><span class="sxs-lookup"><span data-stu-id="fc800-117">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="fc800-118">函数响应</span><span class="sxs-lookup"><span data-stu-id="fc800-118">Function Response</span></span>|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|<span data-ttu-id="fc800-119">在消息正文中支持 Oracle 出和 IN OUT 参数</span><span class="sxs-lookup"><span data-stu-id="fc800-119">Supports Oracle OUT and IN OUT parameters in the message body</span></span><br /><br /> <span data-ttu-id="fc800-120">函数返回值返回在\<[FN_NAME] 结果 > 元素。</span><span class="sxs-lookup"><span data-stu-id="fc800-120">The function return value is returned in the \<[FN_NAME]Result> element.</span></span> <span data-ttu-id="fc800-121">这是在响应消息中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="fc800-121">This is the first element in the response message.</span></span> <span data-ttu-id="fc800-122">它位于之前任何参数。</span><span class="sxs-lookup"><span data-stu-id="fc800-122">It comes before any parameters.</span></span>|  
|<span data-ttu-id="fc800-123">PL/SQL API 请求</span><span class="sxs-lookup"><span data-stu-id="fc800-123">PL/SQL API Request</span></span>|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="fc800-124">相同函数或存储的过程</span><span class="sxs-lookup"><span data-stu-id="fc800-124">Same as Function or Stored Procedure</span></span>|  
|<span data-ttu-id="fc800-125">打包的过程或函数响应</span><span class="sxs-lookup"><span data-stu-id="fc800-125">Packaged Procedure or Function Response</span></span>|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="fc800-126">相同函数或存储的过程</span><span class="sxs-lookup"><span data-stu-id="fc800-126">Same as Function or Stored Procedure</span></span>|  
  
 <span data-ttu-id="fc800-127">实体说明：</span><span class="sxs-lookup"><span data-stu-id="fc800-127">Entity descriptions:</span></span>  
  
 <span data-ttu-id="fc800-128">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05。</span><span class="sxs-lookup"><span data-stu-id="fc800-128">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05.</span></span>  
  
 <span data-ttu-id="fc800-129">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="fc800-129">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="fc800-130">[SP_NAME] = 存储的过程以执行;例如，SP_INSERT。</span><span class="sxs-lookup"><span data-stu-id="fc800-130">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  
  
 <span data-ttu-id="fc800-131">[FN_NAME] = 函数来执行;例如，FN_GETID。</span><span class="sxs-lookup"><span data-stu-id="fc800-131">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  
  
 <span data-ttu-id="fc800-132">[PRM1_NAME] = Oracle 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="fc800-132">[PRM1_NAME] = The name of the Oracle parameter.</span></span> <span data-ttu-id="fc800-133">请参阅受支持的参数方向为每个消息的说明列。</span><span class="sxs-lookup"><span data-stu-id="fc800-133">See the Description column for supported parameter directions for each message.</span></span>  
  
 <span data-ttu-id="fc800-134">[PACKAGE_NAME] = 包含目标的过程或函数的包的名称。</span><span class="sxs-lookup"><span data-stu-id="fc800-134">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  
  
 <span data-ttu-id="fc800-135">Oracle 数据库支持的存储的过程和函数重载。</span><span class="sxs-lookup"><span data-stu-id="fc800-135">The Oracle database supports overloading for stored procedures and functions.</span></span> <span data-ttu-id="fc800-136">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过将一个重载字符串追加到每个重载的项目的目标命名空间中支持此功能。</span><span class="sxs-lookup"><span data-stu-id="fc800-136">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports this capability by appending an overload string to the target namespace for each overloaded artifact.</span></span> <span data-ttu-id="fc800-137">此字符串的值是"overload1"的第一个重载，"overload2"的第二个重载中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="fc800-137">The value of this string is "overload1" for the first overload, "overload2" for the second overload, and so on.</span></span> <span data-ttu-id="fc800-138">下面的示例演示两个重载的存储过程的消息结构。</span><span class="sxs-lookup"><span data-stu-id="fc800-138">The following example shows the message structure for two overloaded stored procedures.</span></span>  
  
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
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="fc800-139">消息操作的存储的过程、 函数和 PL/SQL Api</span><span class="sxs-lookup"><span data-stu-id="fc800-139">Message Actions of Stored Procedures, Functions, and PL/SQL APIs</span></span>  
 <span data-ttu-id="fc800-140">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于存储的过程、 函数和 PL/SQL API 操作的以下的消息操作。</span><span class="sxs-lookup"><span data-stu-id="fc800-140">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for stored procedure, function, and PL/SQL API operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc800-141">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="fc800-141">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="fc800-142">消息</span><span class="sxs-lookup"><span data-stu-id="fc800-142">Message</span></span>|<span data-ttu-id="fc800-143">操作</span><span class="sxs-lookup"><span data-stu-id="fc800-143">Action</span></span>|<span data-ttu-id="fc800-144">示例</span><span class="sxs-lookup"><span data-stu-id="fc800-144">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="fc800-145">存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="fc800-145">Stored Procedure Request</span></span>|<span data-ttu-id="fc800-146">过程 / [架构] / [SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="fc800-146">Procedures/[SCHEMA]/[SP_NAME]</span></span>|<span data-ttu-id="fc800-147">过程/SCOTT/SP_INSERT</span><span class="sxs-lookup"><span data-stu-id="fc800-147">Procedures/SCOTT/SP_INSERT</span></span>|  
|<span data-ttu-id="fc800-148">存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="fc800-148">Stored Procedure Response</span></span>|<span data-ttu-id="fc800-149">过程 / [架构] / [SP_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="fc800-149">Procedures/[SCHEMA]/[SP_NAME]/response</span></span>|<span data-ttu-id="fc800-150">过程/SCOTT/SP_INSERT/响应</span><span class="sxs-lookup"><span data-stu-id="fc800-150">Procedures/SCOTT/SP_INSERT/response</span></span>|  
|<span data-ttu-id="fc800-151">函数请求</span><span class="sxs-lookup"><span data-stu-id="fc800-151">Function Request</span></span>|<span data-ttu-id="fc800-152">函数 / [架构] / [FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="fc800-152">Functions/[SCHEMA]/[FN_NAME]</span></span>|<span data-ttu-id="fc800-153">函数/SCOTT/FN_GETID</span><span class="sxs-lookup"><span data-stu-id="fc800-153">Functions/SCOTT/FN_GETID</span></span>|  
|<span data-ttu-id="fc800-154">函数响应</span><span class="sxs-lookup"><span data-stu-id="fc800-154">Function Response</span></span>|<span data-ttu-id="fc800-155">函数 / [架构] / [FN_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="fc800-155">Functions/[SCHEMA]/[FN_NAME]/response</span></span>|<span data-ttu-id="fc800-156">函数/SCOTT/FN_GETID/响应</span><span class="sxs-lookup"><span data-stu-id="fc800-156">Functions/SCOTT/FN_GETID/response</span></span>|  
|<span data-ttu-id="fc800-157">PL/SQL API 请求</span><span class="sxs-lookup"><span data-stu-id="fc800-157">PL/SQL API Request</span></span>|<span data-ttu-id="fc800-158">[架构] /Package/ [PACKAGE_NAME] / [SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="fc800-158">[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]</span></span>|<span data-ttu-id="fc800-159">SCOTT/包/客户/SP_INSERT</span><span class="sxs-lookup"><span data-stu-id="fc800-159">SCOTT/Package/CUSTOMER/SP_INSERT</span></span>|  
|<span data-ttu-id="fc800-160">打包存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="fc800-160">Packaged Stored Procedure Response</span></span>|<span data-ttu-id="fc800-161">[架构] /Package/ [PACKAGE_NAME] / [SP_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="fc800-161">[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response</span></span>|<span data-ttu-id="fc800-162">SCOTT/包/客户/SP_INSERT/响应</span><span class="sxs-lookup"><span data-stu-id="fc800-162">SCOTT/Package/CUSTOMER/SP_INSERT/response</span></span>|  
|<span data-ttu-id="fc800-163">封装的函数请求</span><span class="sxs-lookup"><span data-stu-id="fc800-163">Packaged Function Request</span></span>|<span data-ttu-id="fc800-164">[架构] /Package/ [PACKAGE_NAME] / [FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="fc800-164">[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]</span></span>|<span data-ttu-id="fc800-165">SCOTT/包/客户/FN_GETID</span><span class="sxs-lookup"><span data-stu-id="fc800-165">SCOTT/Package/CUSTOMER/FN_GETID</span></span>|  
|<span data-ttu-id="fc800-166">封装的函数响应</span><span class="sxs-lookup"><span data-stu-id="fc800-166">Packaged Function Response</span></span>|<span data-ttu-id="fc800-167">[架构] /Package/ [PACKAGE_NAME] / [FN_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="fc800-167">[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response</span></span>|<span data-ttu-id="fc800-168">SCOTT/包/客户/FN_GETID/响应</span><span class="sxs-lookup"><span data-stu-id="fc800-168">SCOTT/Package/CUSTOMER/FN_GETID/response</span></span>|  
|<span data-ttu-id="fc800-169">重载的存储的过程请求</span><span class="sxs-lookup"><span data-stu-id="fc800-169">Overloaded Stored Procedure Request</span></span>|<span data-ttu-id="fc800-170">[架构] /Procedure/ [SP_NAME] / [重载]</span><span class="sxs-lookup"><span data-stu-id="fc800-170">[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]</span></span>|<span data-ttu-id="fc800-171">SCOTT/过程/SP_INSERT/overload1</span><span class="sxs-lookup"><span data-stu-id="fc800-171">SCOTT/Procedure/SP_INSERT/overload1</span></span>|  
|<span data-ttu-id="fc800-172">重载存储的过程响应</span><span class="sxs-lookup"><span data-stu-id="fc800-172">Overloaded Stored Procedure Response</span></span>|<span data-ttu-id="fc800-173">[架构] /Procedure/ [SP_NAME] / [重载] / 响应</span><span class="sxs-lookup"><span data-stu-id="fc800-173">[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response</span></span>|<span data-ttu-id="fc800-174">SCOTT/过程/SP_INSERT/overload1/响应</span><span class="sxs-lookup"><span data-stu-id="fc800-174">SCOTT/Procedure/SP_INSERT/overload1/response</span></span>|  
  
 <span data-ttu-id="fc800-175">实体说明：</span><span class="sxs-lookup"><span data-stu-id="fc800-175">Entity descriptions:</span></span>  
  
 <span data-ttu-id="fc800-176">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="fc800-176">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="fc800-177">[SP_NAME] = 存储的过程以执行;例如，SP_INSERT。</span><span class="sxs-lookup"><span data-stu-id="fc800-177">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  
  
 <span data-ttu-id="fc800-178">[FN_NAME] = 函数来执行;例如，FN_GETID。</span><span class="sxs-lookup"><span data-stu-id="fc800-178">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  
  
 <span data-ttu-id="fc800-179">[PACKAGE_NAME] = 包含目标的过程或函数的包的名称。</span><span class="sxs-lookup"><span data-stu-id="fc800-179">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  
  
 <span data-ttu-id="fc800-180">[重载] = 重载的参数。</span><span class="sxs-lookup"><span data-stu-id="fc800-180">[OVERLOAD] = The Overload parameter.</span></span> <span data-ttu-id="fc800-181">可能的值为 overload1、 overload2，依次类推。</span><span class="sxs-lookup"><span data-stu-id="fc800-181">The possible values are overload1, overload2, and so on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc800-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc800-182">See Also</span></span>  
 [<span data-ttu-id="fc800-183">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="fc800-183">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)