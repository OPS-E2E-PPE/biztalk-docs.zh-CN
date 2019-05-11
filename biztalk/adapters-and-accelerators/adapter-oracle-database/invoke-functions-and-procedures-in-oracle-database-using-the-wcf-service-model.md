---
title: 调用函数和使用 WCF 服务模型的 Oracle 数据库中的过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 097916c7fcf971563ef70c933e348c214aceeab5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529057"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="a93e2-102">调用函数和使用 WCF 服务模型的 Oracle 数据库中的过程</span><span class="sxs-lookup"><span data-stu-id="a93e2-102">Invoke Functions and Procedures in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="a93e2-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]过程、 函数和包作为操作的图面。</span><span class="sxs-lookup"><span data-stu-id="a93e2-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces procedures, functions, and packages as operations.</span></span> <span data-ttu-id="a93e2-104">在 WCF 服务模型中这些操作表示为 WCF 客户端上的方法。</span><span class="sxs-lookup"><span data-stu-id="a93e2-104">In the WCF service model these operations are represented as methods on a WCF client.</span></span> <span data-ttu-id="a93e2-105">WCF 服务模型和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a93e2-105">The WCF service model and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="a93e2-106">**支持函数**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-106">**Support functions**.</span></span> <span data-ttu-id="a93e2-107">Oracle 函数的返回值显示为 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="a93e2-107">The RETURN value of the Oracle function is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="a93e2-108">Oracle 参数作为参数 （使用适当的方向的定义如下） 提供给 WCF 客户端方法。</span><span class="sxs-lookup"><span data-stu-id="a93e2-108">Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="a93e2-109">**支持过程**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-109">**Support procedures**.</span></span> <span data-ttu-id="a93e2-110">OUT 参数 Oracle 过程的第一个显示为 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="a93e2-110">The first OUT parameter of the Oracle procedure is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="a93e2-111">所有其他 Oracle 参数作为参数 （使用适当的方向的定义如下） 提供给 WCF 客户端方法。</span><span class="sxs-lookup"><span data-stu-id="a93e2-111">All other Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="a93e2-112">**支持 Oracle 包**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-112">**Support Oracle packages**.</span></span> <span data-ttu-id="a93e2-113">操作的名称和其参数类型的命名空间进行限定按包名称。</span><span class="sxs-lookup"><span data-stu-id="a93e2-113">The name of the operation and the namespace of its parameter types are qualified by the package name.</span></span>  
  
-   <span data-ttu-id="a93e2-114">**支持重载函数和过程**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-114">**Support overloaded functions and procedures**.</span></span>  
  
-   <span data-ttu-id="a93e2-115">**支持 IN，OUT 和 OUT 参数的过程和函数的基本 Oracle 数据类型为 IN**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-115">**Support IN, OUT and IN OUT parameters for basic Oracle data types for both procedures and functions**.</span></span> <span data-ttu-id="a93e2-116">OUT 参数显示为**出**WCF 客户端方法的参数和在 OUT 参数显示为**ref**参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-116">OUT parameters are surfaced as **out** parameters on the WCF client method and IN OUT parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="a93e2-117">**支持 IN、 扩展，并在输出的过程和函数，以及函数返回值的 REF CURSOR 参数**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-117">**Support IN, OUT, and IN OUT REF CURSOR parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="a93e2-118">有关详细信息，请参阅[执行的操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-118">For more information, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="a93e2-119">**中支持，扩展，IN 出记录类型的过程和函数的参数，以及函数返回值**。</span><span class="sxs-lookup"><span data-stu-id="a93e2-119">**Support IN, OUT, and IN OUT RECORD type parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="a93e2-120">有关详细信息，请参阅[执行的操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-120">For more information, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a93e2-121">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="a93e2-121">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a93e2-122">中的示例本主题使用 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 重载过程。</span><span class="sxs-lookup"><span data-stu-id="a93e2-122">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT overloaded procedure.</span></span> <span data-ttu-id="a93e2-123">此过程从基于帐户 ID 或帐户名称 SCOTT/帐户表中读取一条记录。</span><span class="sxs-lookup"><span data-stu-id="a93e2-123">This procedure reads a record from the SCOTT/ACCOUNT table based on either an account ID or an account name.</span></span> <span data-ttu-id="a93e2-124">使用 SDK 示例提供了一个脚本来生成此过程和表。</span><span class="sxs-lookup"><span data-stu-id="a93e2-124">A script to generate this procedure and table is supplied with the SDK samples.</span></span> <span data-ttu-id="a93e2-125">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-125">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a93e2-126">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="a93e2-126">The WCF Client Class</span></span>  
 <span data-ttu-id="a93e2-127">下表显示的名称以及 WCF 客户端的过程，生成的方法的函数和包，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面。</span><span class="sxs-lookup"><span data-stu-id="a93e2-127">The following table shows the name of the WCF client and the method generated for procedures, functions and packages that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces.</span></span> <span data-ttu-id="a93e2-128">除非重载函数或过程，单个 WCF 客户端用于调用的所有在架构中，所有架构中的过程或函数的所有函数和在包中的过程。</span><span class="sxs-lookup"><span data-stu-id="a93e2-128">Unless a function or procedure is overloaded, a single WCF client is used to invoke all of the functions in a schema, all of the procedures in a schema, or all of the functions and procedures in a package.</span></span>  
  
|<span data-ttu-id="a93e2-129">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="a93e2-129">Oracle Artifact</span></span>|<span data-ttu-id="a93e2-130">WCF 客户端操作名称</span><span class="sxs-lookup"><span data-stu-id="a93e2-130">WCF Client Operation Name</span></span>|<span data-ttu-id="a93e2-131">示例</span><span class="sxs-lookup"><span data-stu-id="a93e2-131">Example</span></span>|  
|---------------------|-------------------------------|-------------|  
|<span data-ttu-id="a93e2-132">过程</span><span class="sxs-lookup"><span data-stu-id="a93e2-132">Procedure</span></span>|<span data-ttu-id="a93e2-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span></span>|<span data-ttu-id="a93e2-134">SCOTTProcedureClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="a93e2-134">SCOTTProcedureClient.MYPROC</span></span>|  
|<span data-ttu-id="a93e2-135">函数</span><span class="sxs-lookup"><span data-stu-id="a93e2-135">Function</span></span>|<span data-ttu-id="a93e2-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span></span>|<span data-ttu-id="a93e2-137">SCOTTProcedureClient.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="a93e2-137">SCOTTProcedureClient.MYFUNC</span></span>|  
|<span data-ttu-id="a93e2-138">包 （过程或函数）</span><span class="sxs-lookup"><span data-stu-id="a93e2-138">Package (procedure or function)</span></span>|<span data-ttu-id="a93e2-139">[架构]包 [PACKAGE_NAME] 客户端。[PROC_NAME 或 FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-139">[SCHEMA]Package[PACKAGE_NAME]Client.[PROC_NAME or FUNC_NAME]</span></span>|<span data-ttu-id="a93e2-140">SCOTTPackageMYPACKAGEClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="a93e2-140">SCOTTPackageMYPACKAGEClient.MYPROC</span></span>|  
  
 <span data-ttu-id="a93e2-141">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a93e2-141">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a93e2-142">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-142">[PROC_NAME] = The name of an Oracle procedure; for example, MYPROC.</span></span>  
  
 <span data-ttu-id="a93e2-143">[FUNC_NAME] = Oracle 函数; 的名称例如，MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-143">[FUNC_NAME] = The name of an Oracle function; for example, MYFUNC.</span></span>  
  
 <span data-ttu-id="a93e2-144">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="a93e2-144">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="a93e2-145">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 Oracle 记录类型参数和返回值，以及作为复杂包含 Oracle 记录的行数据 （或字段） 的 XML 类型返回的 REF CURSOR 参数的结果集。</span><span class="sxs-lookup"><span data-stu-id="a93e2-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents Oracle RECORD type parameters and return values as well as the result sets returned by REF CURSOR parameters as complex XML types that contain the row data (or fields) of an Oracle record.</span></span> <span data-ttu-id="a93e2-146">在 WCF 服务模型中，每个 XML 类型表示为一个.NET 类;类的属性表示的字段的记录类型或 REF 游标结果集。</span><span class="sxs-lookup"><span data-stu-id="a93e2-146">In the WCF service model, each of these XML types is represented as a .NET class; the properties of the class represent the fields of the RECORD type or REF CURSOR result set.</span></span> <span data-ttu-id="a93e2-147">Oracle 记录类型始终表示为强类型化.NET 类。</span><span class="sxs-lookup"><span data-stu-id="a93e2-147">Oracle RECORD types are always represented as strongly-typed .NET classes.</span></span> <span data-ttu-id="a93e2-148">REF CURSOR 结果集，但是，可以表示为强类型化或弱类型基于 REF CURSOR 本身是否声明为强类型化或弱类型的记录。</span><span class="sxs-lookup"><span data-stu-id="a93e2-148">A REF CURSOR result set, however, can be represented as either strongly-typed or weakly-typed records based on whether the REF CURSOR itself is declared as strongly-typed or weakly-typed.</span></span> <span data-ttu-id="a93e2-149">表示 REF CURSOR 或记录类型参数 （或返回值） 中基于过程、 函数或包的唯一命名空间中的生成的类。</span><span class="sxs-lookup"><span data-stu-id="a93e2-149">The classes that represent REF CURSOR or RECORD type parameters (or return values) are generated in a unique namespace based on the procedure, function, or package.</span></span> <span data-ttu-id="a93e2-150">下表显示了这些命名空间。</span><span class="sxs-lookup"><span data-stu-id="a93e2-150">The following table shows these namespaces.</span></span>  
  
|<span data-ttu-id="a93e2-151">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="a93e2-151">Oracle Artifact</span></span>|<span data-ttu-id="a93e2-152">命名空间</span><span class="sxs-lookup"><span data-stu-id="a93e2-152">Namespace</span></span>|<span data-ttu-id="a93e2-153">示例</span><span class="sxs-lookup"><span data-stu-id="a93e2-153">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="a93e2-154">过程</span><span class="sxs-lookup"><span data-stu-id="a93e2-154">Procedure</span></span>|<span data-ttu-id="a93e2-155">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-155">[BASE_NS].</span></span> <span data-ttu-id="a93e2-156">[SCHEMA].Procedure.[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-156">[SCHEMA].Procedure.[PROC_NAME]</span></span>|<span data-ttu-id="a93e2-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span><span class="sxs-lookup"><span data-stu-id="a93e2-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span></span>|  
|<span data-ttu-id="a93e2-158">函数</span><span class="sxs-lookup"><span data-stu-id="a93e2-158">Function</span></span>|<span data-ttu-id="a93e2-159">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-159">[BASE_NS].</span></span> <span data-ttu-id="a93e2-160">[SCHEMA].Function.[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-160">[SCHEMA].Function.[FUNC_NAME]</span></span>|<span data-ttu-id="a93e2-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="a93e2-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span></span>|  
|<span data-ttu-id="a93e2-162">包 （过程）</span><span class="sxs-lookup"><span data-stu-id="a93e2-162">Package (Procedure)</span></span>|<span data-ttu-id="a93e2-163">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-163">[BASE_NS].</span></span> <span data-ttu-id="a93e2-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span></span>|<span data-ttu-id="a93e2-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span><span class="sxs-lookup"><span data-stu-id="a93e2-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span></span>|  
|<span data-ttu-id="a93e2-166">包 （函数）</span><span class="sxs-lookup"><span data-stu-id="a93e2-166">Package (Function)</span></span>|<span data-ttu-id="a93e2-167">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-167">[BASE_NS].</span></span> <span data-ttu-id="a93e2-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span></span>|<span data-ttu-id="a93e2-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="a93e2-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span></span>|  
|<span data-ttu-id="a93e2-170">通用记录集 （弱类型）</span><span class="sxs-lookup"><span data-stu-id="a93e2-170">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="a93e2-171">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="a93e2-171">[BASE_NS]</span></span>|<span data-ttu-id="a93e2-172">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="a93e2-172">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="a93e2-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span><span class="sxs-lookup"><span data-stu-id="a93e2-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="a93e2-174">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a93e2-174">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a93e2-175">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-175">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="a93e2-176">[FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-176">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="a93e2-177">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="a93e2-177">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="a93e2-178">有关如何使用这些命名空间的记录参数的信息，请参阅[执行的操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-178">For information about how these namespaces are used for RECORD parameters, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span> <span data-ttu-id="a93e2-179">有关如何使用这些命名空间的 REF CURSOR 参数的信息，请参阅[执行的操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-179">For information about how these namespaces are used for REF CURSOR parameters, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="a93e2-180">一般情况下，Oracle 参数和返回值被映射，如下所示中的 WCF 客户端方法：</span><span class="sxs-lookup"><span data-stu-id="a93e2-180">In general, the Oracle parameters and return values are mapped as follows in the WCF client method:</span></span>  
  
- <span data-ttu-id="a93e2-181">Oracle IN 参数将映射到.NET （输入） 参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-181">Oracle IN parameters are mapped to .NET (input) parameters.</span></span>  
  
- <span data-ttu-id="a93e2-182">Oracle OUT 参数映射到.NET**出**参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-182">Oracle OUT parameters are mapped to .NET **out** parameters.</span></span>  
  
- <span data-ttu-id="a93e2-183">Oracle 在 OUT 参数映射到.NET **ref**参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-183">Oracle IN OUT parameters are mapped to .NET **ref** parameters.</span></span>  
  
- <span data-ttu-id="a93e2-184">函数返回值映射到方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="a93e2-184">Function RETURN values are mapped to the method return value.</span></span>  
  
  <span data-ttu-id="a93e2-185">但是，存在两个重要的例外情况：</span><span class="sxs-lookup"><span data-stu-id="a93e2-185">However, two important exceptions exist:</span></span>  
  
- <span data-ttu-id="a93e2-186">Oracle IN 出 REF CURSOR 参数拆分输入的字符串和一个输出 (**出**) 记录集。</span><span class="sxs-lookup"><span data-stu-id="a93e2-186">Oracle IN OUT REF CURSOR parameters are split into an input string and an output (**out**) record set.</span></span> <span data-ttu-id="a93e2-187">这是因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CUSROR 参数作为字符串，并为复杂类型 （记录集） 的出 REF CURSOR 参数，这些不能组合到单个参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-187">This is because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CUSROR parameters as strings and OUT REF CURSOR parameters as complex types (record sets), these cannot be combined into a single parameter.</span></span>  
  
- <span data-ttu-id="a93e2-188">OUT 参数在 Oracle 过程中的第一个映射到 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="a93e2-188">The first OUT parameter in an Oracle procedure is mapped to the return value of the WCF client method.</span></span> <span data-ttu-id="a93e2-189">这是标准的 WCF 行为。</span><span class="sxs-lookup"><span data-stu-id="a93e2-189">This is standard WCF behavior.</span></span>  
  
  <span data-ttu-id="a93e2-190">下面的示例演示 （SCOTT 架构中加载） 的简单 Oracle 过程的一部分而生成，以调用它的 WCF 客户端方法的签名。</span><span class="sxs-lookup"><span data-stu-id="a93e2-190">The following example shows part of a simple Oracle procedure (loaded in the SCOTT schema) and the signature of the WCF client method that is generated to invoke it.</span></span> <span data-ttu-id="a93e2-191">Oracle 过程具有三个 IN 参数、 三个在 OUT 参数，和三个输出参数但是，WCF 客户端方法没有映射输出参数的第一个的参数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-191">The Oracle procedure has three IN parameters, three IN OUT parameters, and three OUT parameters; however, the WCF client method does not map a parameter for the first OUT parameter.</span></span> <span data-ttu-id="a93e2-192">相反，它将映射到方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="a93e2-192">Instead it is mapped to the method return value.</span></span>  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime\> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime\> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime\> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a><span data-ttu-id="a93e2-193">对重载的过程、 函数和包的支持</span><span class="sxs-lookup"><span data-stu-id="a93e2-193">Support for Overloaded Procedures, Functions and Packages</span></span>  
 <span data-ttu-id="a93e2-194">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持通过将唯一字符串追加到的节点 ID 和命名空间，它会显示出的每个重载的项目重载过程、 函数和包。</span><span class="sxs-lookup"><span data-stu-id="a93e2-194">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports overloaded procedures, functions, and packages by appending a unique string to the node ID and the namespace that it surfaces for each overloaded artifact.</span></span> <span data-ttu-id="a93e2-195">此字符串是"overload1"用于第一个重载，"overload2"下一步的重载，等等。</span><span class="sxs-lookup"><span data-stu-id="a93e2-195">This string is "overload1" for the first overload, "overload2" for the next overload, and so on.</span></span>  
  
 <span data-ttu-id="a93e2-196">在 WCF 服务模型中由唯一的 WCF 客户端表示每个重载的过程或函数。</span><span class="sxs-lookup"><span data-stu-id="a93e2-196">In the WCF service model each overloaded procedure or function is represented by a unique WCF client.</span></span> <span data-ttu-id="a93e2-197">这不同于在架构中，在架构中，过程的所有函数的所有非过载情况或者的过程和函数在包中的所有调用的同一个 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="a93e2-197">This is different from the non-overloaded case in which all of the functions in a SCHEMA, all of the procedures in a SCHEMA, or all of the procedures and functions in a PACKAGE are invoked by the same WCF client.</span></span> <span data-ttu-id="a93e2-198">下表显示 WCF 客户端名称和为重载的过程、 函数和包生成的方法。</span><span class="sxs-lookup"><span data-stu-id="a93e2-198">The following table shows the WCF client name and method generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="a93e2-199">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="a93e2-199">Oracle Artifact</span></span>|<span data-ttu-id="a93e2-200">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="a93e2-200">WCF Client Name</span></span>|<span data-ttu-id="a93e2-201">示例</span><span class="sxs-lookup"><span data-stu-id="a93e2-201">Example</span></span>|  
|---------------------|---------------------|-------------|  
|<span data-ttu-id="a93e2-202">重载的包 （过程）</span><span class="sxs-lookup"><span data-stu-id="a93e2-202">Overloaded Package (Procedure)</span></span>|<span data-ttu-id="a93e2-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span></span>|<span data-ttu-id="a93e2-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span><span class="sxs-lookup"><span data-stu-id="a93e2-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span></span>|  
|<span data-ttu-id="a93e2-205">重载的包 （函数）</span><span class="sxs-lookup"><span data-stu-id="a93e2-205">Overloaded Package (Function)</span></span>|<span data-ttu-id="a93e2-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="a93e2-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span></span>|<span data-ttu-id="a93e2-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="a93e2-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span></span>|  
  
 <span data-ttu-id="a93e2-208">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a93e2-208">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a93e2-209">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-209">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="a93e2-210">[FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-210">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="a93e2-211">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="a93e2-211">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="a93e2-212">[OVERLOAD_ID] = 标识重载的项目; 的唯一字符串"overload1"、"overload2"等。</span><span class="sxs-lookup"><span data-stu-id="a93e2-212">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span>  
  
 <span data-ttu-id="a93e2-213">下表显示了为重载的过程、 函数和包生成的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a93e2-213">The following table shows the namespace generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="a93e2-214">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="a93e2-214">Oracle Artifact</span></span>|<span data-ttu-id="a93e2-215">命名空间</span><span class="sxs-lookup"><span data-stu-id="a93e2-215">Namespace</span></span>|<span data-ttu-id="a93e2-216">示例</span><span class="sxs-lookup"><span data-stu-id="a93e2-216">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="a93e2-217">包 （过程）</span><span class="sxs-lookup"><span data-stu-id="a93e2-217">Package (Procedure)</span></span>|<span data-ttu-id="a93e2-218">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-218">[BASE_NS].</span></span> <span data-ttu-id="a93e2-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="a93e2-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span></span>|<span data-ttu-id="a93e2-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span><span class="sxs-lookup"><span data-stu-id="a93e2-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span></span>|  
|<span data-ttu-id="a93e2-221">包 （函数）</span><span class="sxs-lookup"><span data-stu-id="a93e2-221">Package (Function)</span></span>|<span data-ttu-id="a93e2-222">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="a93e2-222">[BASE_NS].</span></span> <span data-ttu-id="a93e2-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="a93e2-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span></span>|<span data-ttu-id="a93e2-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span><span class="sxs-lookup"><span data-stu-id="a93e2-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span></span>|  
|<span data-ttu-id="a93e2-225">通用记录集 （弱类型）</span><span class="sxs-lookup"><span data-stu-id="a93e2-225">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="a93e2-226">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="a93e2-226">[BASE_NS]</span></span>|<span data-ttu-id="a93e2-227">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="a93e2-227">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="a93e2-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span><span class="sxs-lookup"><span data-stu-id="a93e2-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="a93e2-229">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a93e2-229">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a93e2-230">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-230">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="a93e2-231">[FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="a93e2-231">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="a93e2-232">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="a93e2-232">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="a93e2-233">[OVERLOAD_ID] = 标识重载的项目; 的唯一字符串"overload1"、"overload2"等。</span><span class="sxs-lookup"><span data-stu-id="a93e2-233">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span> <span data-ttu-id="a93e2-234">在字符串中的数字值是由 Oracle 数据库维护的项目重载 ID。</span><span class="sxs-lookup"><span data-stu-id="a93e2-234">The numeric value in the string is the overload ID for the artifact maintained by the Oracle database.</span></span>  
  
 <span data-ttu-id="a93e2-235">下面的示例演示在 WCF 客户端和 ACCOUNT_PKG 包中的重载 GET_ACCOUNT 过程生成的方法签名。</span><span class="sxs-lookup"><span data-stu-id="a93e2-235">The following example shows the WCF clients and the method signatures generated for the overloaded GET_ACCOUNT procedure in the ACCOUNT_PKG package.</span></span> <span data-ttu-id="a93e2-236">（Oracle 声明包含。）此示例演示如何为每个重载生成唯一的 WCF 客户端和如何为每个客户端生成的方法返回的记录集的唯一命名空间中。</span><span class="sxs-lookup"><span data-stu-id="a93e2-236">(The Oracle declarations are included.) This example shows how a unique WCF client is generated for each overload and how the method generated for each client returns a record set in a unique namespace.</span></span>  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a><span data-ttu-id="a93e2-237">调用函数和过程</span><span class="sxs-lookup"><span data-stu-id="a93e2-237">Invoking Functions and Procedures</span></span>  
 <span data-ttu-id="a93e2-238">若要通过使用 WCF 客户端调用一个函数或过程，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a93e2-238">To invoke a function or a procedure by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="a93e2-239">生成用于目标函数、 过程或包的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="a93e2-239">Generate a WCF client class for the target function, procedure, or package.</span></span> <span data-ttu-id="a93e2-240">此类应包含将在目标项目调用操作方法。</span><span class="sxs-lookup"><span data-stu-id="a93e2-240">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a93e2-241">在[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，重载函数和过程出现在**可用类别和操作**框为 [NAME].1、 [名称].2，[NAME].3，依次类推，其中 [名称] 是重载的项目和数字值的名称是对 Oracle 数据库的重载 ID。</span><span class="sxs-lookup"><span data-stu-id="a93e2-241">In the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], overloaded functions and procedures appear in the **Available categories and operations** box as [NAME].1, [NAME].2, [NAME].3, and so on, where [NAME] is the name of the overloaded artifact and the numeric value is the overload ID on the Oracle database.</span></span>  
  
2. <span data-ttu-id="a93e2-242">创建 WCF 客户端类的实例并调用其方法调用的函数或过程。</span><span class="sxs-lookup"><span data-stu-id="a93e2-242">Create an instance of the WCF client class and call its methods to invoke the function or procedure.</span></span>  
  
   <span data-ttu-id="a93e2-243">有关更多详细信息，有关如何创建 WCF 客户端类，并在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[具有 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-243">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="a93e2-244">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle 数据库上执行一个事务内的每个操作。</span><span class="sxs-lookup"><span data-stu-id="a93e2-244">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a93e2-245">表示 REF CURSOR 和记录类型参数或返回值的函数或过程 （和包） 中的类为每个函数或过程声明中的唯一命名空间。</span><span class="sxs-lookup"><span data-stu-id="a93e2-245">The classes that represent REF CURSOR and RECORD type parameters or return values in functions or procedures (and packages) are declared in a unique namespace for each function or procedure.</span></span> <span data-ttu-id="a93e2-246">例如，这意味着，将为每个 WCF 客户端方法声明中唯一的命名空间用作中两个不同的函数的返回值的包 REF CURSOR 类型。</span><span class="sxs-lookup"><span data-stu-id="a93e2-246">This means, for example, that a PACKAGE REF CURSOR type that is used as a return value in two different functions will be declared in a unique namespace for each WCF client method.</span></span> <span data-ttu-id="a93e2-247">您必须声明不同的变量来保存这些不同的返回值或相应地转换该变量时调用的 WCF 客户端方法之一。</span><span class="sxs-lookup"><span data-stu-id="a93e2-247">You must either declare separate variables to hold these different return values or appropriately cast the variable when you invoke one of the WCF client methods.</span></span>  
  
 <span data-ttu-id="a93e2-248">下面的示例演示如何调用重载的 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 过程从 /SCOTT/ACCOUNT 表获取帐户记录。</span><span class="sxs-lookup"><span data-stu-id="a93e2-248">The following example demonstrates calling the overloaded /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT procedure to get account records from the /SCOTT/ACCOUNT table.</span></span> <span data-ttu-id="a93e2-249">首先通过调用 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 过程创建一个新的记录。</span><span class="sxs-lookup"><span data-stu-id="a93e2-249">First a new record is created by calling the /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT procedure.</span></span> <span data-ttu-id="a93e2-250">然后，读取新记录后两次通过调用 GET_ACCOUNT 的不同重载。</span><span class="sxs-lookup"><span data-stu-id="a93e2-250">Then the new record is read back twice by calling different overloads of GET_ACCOUNT.</span></span> <span data-ttu-id="a93e2-251">此示例使用三个 WCF 客户端，一个用于 CREATE_ACCOUNT 过程，分别用于 GET_ACCOUNT 重载。</span><span class="sxs-lookup"><span data-stu-id="a93e2-251">This example uses three WCF clients, one for the CREATE_ACCOUNT procedure and one each for the GET_ACCOUNT overloads.</span></span> <span data-ttu-id="a93e2-252">使用别名来区分 GET_ACCOUNT 的返回值使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a93e2-252">Aliases are used to distinguish between namespaces used for the return value of GET_ACCOUNT.</span></span> <span data-ttu-id="a93e2-253">可在 SDK 示例的完整示例。</span><span class="sxs-lookup"><span data-stu-id="a93e2-253">A full sample is available in the SDK samples.</span></span> <span data-ttu-id="a93e2-254">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="a93e2-254">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a93e2-255">请参阅</span><span class="sxs-lookup"><span data-stu-id="a93e2-255">See Also</span></span>  
 [<span data-ttu-id="a93e2-256">使用 WCF 服务模型开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="a93e2-256">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)