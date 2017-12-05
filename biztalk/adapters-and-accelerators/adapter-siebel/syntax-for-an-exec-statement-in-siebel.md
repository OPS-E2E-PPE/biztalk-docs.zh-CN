---
title: "为 Siebel 中 EXEC 语句的语法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4db9ca810860ea64ffa474725dc485fecfaa5e78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a><span data-ttu-id="9adf0-102">Siebel 中 EXEC 语句的的语法</span><span class="sxs-lookup"><span data-stu-id="9adf0-102">Syntax for an EXEC Statement in Siebel</span></span>
<span data-ttu-id="9adf0-103">使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，ADO.NET 客户端还可以在执行运算 EXEC [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9adf0-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can also perform an EXEC operation on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="9adf0-104">EXEC 语句的语法是：</span><span class="sxs-lookup"><span data-stu-id="9adf0-104">The syntax for the EXEC statement is:</span></span>  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 <span data-ttu-id="9adf0-105">在前面的语法中，`\<value 1..n\>`表示一组未命名参数。</span><span class="sxs-lookup"><span data-stu-id="9adf0-105">In the preceding syntax, `\<value 1..n\>` represents a set of unnamed parameters.</span></span> <span data-ttu-id="9adf0-106">这些是硬编码值。</span><span class="sxs-lookup"><span data-stu-id="9adf0-106">These are hard-coded values.</span></span> <span data-ttu-id="9adf0-107">它们通常表示参数中。</span><span class="sxs-lookup"><span data-stu-id="9adf0-107">They usually represent IN parameters.</span></span>  <span data-ttu-id="9adf0-108">它们还可以表示 INOUT 参数。</span><span class="sxs-lookup"><span data-stu-id="9adf0-108">They can also represent INOUT parameters.</span></span> <span data-ttu-id="9adf0-109">但是，如果硬编码的值用于 INOUT 参数，执行 EXEC 语句后无法检索到该参数与关联的输出值。</span><span class="sxs-lookup"><span data-stu-id="9adf0-109">However, if a hard-coded value is used for an INOUT parameter, the output value associated with that parameter cannot be retrieved after the EXEC statement is executed.</span></span>  
  
 <span data-ttu-id="9adf0-110">`@parameter 1..n`语法表示一组命名的参数，可以为 IN、 INOUT 或 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="9adf0-110">The `@parameter 1..n` syntax represents a set of named parameters, which can be IN, INOUT, or OUT parameters.</span></span> <span data-ttu-id="9adf0-111">输出参数的后面必须跟**输出**关键字。</span><span class="sxs-lookup"><span data-stu-id="9adf0-111">The output parameters must be followed by the **OUTPUT** keyword.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9adf0-112">**输出**OUT 参数而不是与 INOUT 参数关键字必须仅与一起使用。</span><span class="sxs-lookup"><span data-stu-id="9adf0-112">The **OUTPUT** keyword must only be used with OUT parameters and not with INOUT parameters.</span></span>  
  
 <span data-ttu-id="9adf0-113">若要指定参数值内联，使用`@parameter 1..n = <value>`语法。</span><span class="sxs-lookup"><span data-stu-id="9adf0-113">To specify parameter values inline, use the `@parameter 1..n = <value>` syntax.</span></span>  
  
 <span data-ttu-id="9adf0-114">所有参数必须都是以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="9adf0-114">All parameters must be comma-separated.</span></span>  
  
 <span data-ttu-id="9adf0-115">EXEC 语句的示例如下：</span><span class="sxs-lookup"><span data-stu-id="9adf0-115">The following are examples of EXEC statements:</span></span>  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="9adf0-116">每个参数的名称 (如`@In`在前面的示例) Siebel 业务服务方法中的相应自变量名称必须匹配。</span><span class="sxs-lookup"><span data-stu-id="9adf0-116">Every parameter name (like `@In` in the preceding example) must match the corresponding argument name in the Siebel Business Service method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9adf0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9adf0-117">See Also</span></span>  
 [<span data-ttu-id="9adf0-118">使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="9adf0-118">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)