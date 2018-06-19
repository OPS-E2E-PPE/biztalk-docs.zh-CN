---
title: 有关 Siebel 的数据提供程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217757"
---
# <a name="about-the-data-provider-for-siebel"></a><span data-ttu-id="79531-102">有关 Siebel 的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="79531-102">About the Data Provider for Siebel</span></span>
## <a name="overview"></a><span data-ttu-id="79531-103">概述</span><span class="sxs-lookup"><span data-stu-id="79531-103">Overview</span></span>
<span data-ttu-id="79531-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]之上生成[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="79531-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is built on top of the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="79531-105">你可以使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]到：</span><span class="sxs-lookup"><span data-stu-id="79531-105">You can use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] to:</span></span>  
  
-   <span data-ttu-id="79531-106">编写的 ADO.NET 客户端可以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="79531-106">Write an ADO.NET client to connect to the Siebel system.</span></span> <span data-ttu-id="79531-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]公开某些使您能够使用提供程序接口的类。</span><span class="sxs-lookup"><span data-stu-id="79531-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
-   <span data-ttu-id="79531-108">Siebel 业务组件上运行 SELECT 查询</span><span class="sxs-lookup"><span data-stu-id="79531-108">Run a SELECT query on a Siebel business component</span></span>
  
-   <span data-ttu-id="79531-109">在 Siebel 业务服务上运行的 EXEC 查询</span><span class="sxs-lookup"><span data-stu-id="79531-109">Run an EXEC query on a Siebel business service</span></span>
  
-   <span data-ttu-id="79531-110">使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="79531-110">Use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Integration Services (SSIS)</span></span>
  
<span data-ttu-id="79531-111">[.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)位于用于信息的重大资源：</span><span class="sxs-lookup"><span data-stu-id="79531-111">[Use  the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) is a great resource for information on:</span></span>  
  
-   <span data-ttu-id="79531-112">通过 ADO.NET 接口扩展[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79531-112">The ADO.NET interfaces extended by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span></span>  
  
-   <span data-ttu-id="79531-113">要连接到 Siebel 系统的连接字符串</span><span class="sxs-lookup"><span data-stu-id="79531-113">The connection string to connect to a Siebel system</span></span>  
  
-   <span data-ttu-id="79531-114">SELECT 和 EXEC 语句的语法</span><span class="sxs-lookup"><span data-stu-id="79531-114">Syntax for the SELECT and EXEC statements</span></span>  
  
-   <span data-ttu-id="79531-115">使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SSIS</span><span class="sxs-lookup"><span data-stu-id="79531-115">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="79531-116">限制</span><span class="sxs-lookup"><span data-stu-id="79531-116">Limitations</span></span>
<span data-ttu-id="79531-117">以下已知的限制[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79531-117">The following are known limitations of the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span></span>  
  
-   <span data-ttu-id="79531-118">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]别名支持为表的名称，在 SELECT 子句中，但不是在 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="79531-118">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause, but not in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="79531-119">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法创建表，具有特殊字符，列名称的"]"。</span><span class="sxs-lookup"><span data-stu-id="79531-119">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to create a table with column names that have the special character, "]".</span></span> <span data-ttu-id="79531-120">可以通过包括另一个右方括号转义特殊字符。</span><span class="sxs-lookup"><span data-stu-id="79531-120">You can escape the special character by including another closing square bracket.</span></span> <span data-ttu-id="79531-121">因此，你应包括"]]"而不是"]"。</span><span class="sxs-lookup"><span data-stu-id="79531-121">So, you should include"]]" instead of "]".</span></span>  
  
-   <span data-ttu-id="79531-122">由于出现超时处理由基础 Siebel 客户端 API，问题[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持命令和连接超时。</span><span class="sxs-lookup"><span data-stu-id="79531-122">Due to issues with timeout handling by the underlying Siebel client API, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="79531-123">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持异步命令的行为。</span><span class="sxs-lookup"><span data-stu-id="79531-123">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
-   <span data-ttu-id="79531-124">使用 SQL Server Integration Services (SSIS) 项目，使用时[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法检索包含与多个 8000 个字符的值的列的数据。</span><span class="sxs-lookup"><span data-stu-id="79531-124">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="79531-125">这是由于依据的 SSIS 限制：</span><span class="sxs-lookup"><span data-stu-id="79531-125">This is due to an SSIS restriction according to which:</span></span>  
  
    -   <span data-ttu-id="79531-126">不支持大于 4000 个字符在 SSIS 变量的值。</span><span class="sxs-lookup"><span data-stu-id="79531-126">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
    -   <span data-ttu-id="79531-127">不支持大于 4000 宽字符的值。</span><span class="sxs-lookup"><span data-stu-id="79531-127">Values greater than 4000 wide characters are not supported.</span></span>  
  
    -   <span data-ttu-id="79531-128">不支持大于 8000 单字节字符的值。</span><span class="sxs-lookup"><span data-stu-id="79531-128">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
-   <span data-ttu-id="79531-129">EXEC 操作将不起作用时使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]与 SQL Server Integration Services (SSIS)。</span><span class="sxs-lookup"><span data-stu-id="79531-129">The EXEC operation will not be functional while using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] with SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="79531-130">因此，例如，适配器客户端将不能在 Siebel 中执行业务服务 (使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 时使用 SSIS 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="79531-130">So, for example, adapter clients will not be able to execute a business service in Siebel (using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) while using the data providers with SSIS.</span></span> 

## <a name="see-also"></a><span data-ttu-id="79531-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79531-131">See also</span></span>
[<span data-ttu-id="79531-132">Siebel 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="79531-132">Limitations of the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[<span data-ttu-id="79531-133">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="79531-133">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)