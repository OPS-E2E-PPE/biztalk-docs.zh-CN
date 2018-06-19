---
title: 调用函数和 Oracle 数据库使用 WCF 服务模型中的过程 |Microsoft 文档
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
ms.openlocfilehash: 9f1fac59fc77b0cf52abe789db8feb2305043708
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966355"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="22171-102">调用函数和 Oracle 数据库使用 WCF 服务模型中的过程</span><span class="sxs-lookup"><span data-stu-id="22171-102">Invoke Functions and Procedures in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="22171-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现过程、 函数和包作为操作。</span><span class="sxs-lookup"><span data-stu-id="22171-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces procedures, functions, and packages as operations.</span></span> <span data-ttu-id="22171-104">在 WCF 服务模型会将这些操作表示为 WCF 客户端上的方法。</span><span class="sxs-lookup"><span data-stu-id="22171-104">In the WCF service model these operations are represented as methods on a WCF client.</span></span> <span data-ttu-id="22171-105">WCF 服务模型和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="22171-105">The WCF service model and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="22171-106">**支持函数**。</span><span class="sxs-lookup"><span data-stu-id="22171-106">**Support functions**.</span></span> <span data-ttu-id="22171-107">Oracle 函数的返回值呈现为 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-107">The RETURN value of the Oracle function is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="22171-108">Oracle 参数作为 （与相应的方向定义下面） 的参数提供给 WCF 客户端方法。</span><span class="sxs-lookup"><span data-stu-id="22171-108">Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="22171-109">**支持过程**。</span><span class="sxs-lookup"><span data-stu-id="22171-109">**Support procedures**.</span></span> <span data-ttu-id="22171-110">OUT 参数 Oracle 过程的第一个呈现为 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-110">The first OUT parameter of the Oracle procedure is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="22171-111">所有其他 Oracle 参数作为 （与相应的方向定义下面） 的参数提供给 WCF 客户端方法。</span><span class="sxs-lookup"><span data-stu-id="22171-111">All other Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="22171-112">**支持 Oracle 包**。</span><span class="sxs-lookup"><span data-stu-id="22171-112">**Support Oracle packages**.</span></span> <span data-ttu-id="22171-113">该操作的名称和其参数类型的命名空间是由包名称限定的。</span><span class="sxs-lookup"><span data-stu-id="22171-113">The name of the operation and the namespace of its parameter types are qualified by the package name.</span></span>  
  
-   <span data-ttu-id="22171-114">**支持重载函数和过程**。</span><span class="sxs-lookup"><span data-stu-id="22171-114">**Support overloaded functions and procedures**.</span></span>  
  
-   <span data-ttu-id="22171-115">**支持 IN、 OUT 和 IN 出的过程和函数的基本 Oracle 数据类型的参数**。</span><span class="sxs-lookup"><span data-stu-id="22171-115">**Support IN, OUT and IN OUT parameters for basic Oracle data types for both procedures and functions**.</span></span> <span data-ttu-id="22171-116">OUT 参数中加以表示为**出**作为 WCF 客户端方法的参数和 IN OUT 参数进行展示**ref**参数。</span><span class="sxs-lookup"><span data-stu-id="22171-116">OUT parameters are surfaced as **out** parameters on the WCF client method and IN OUT parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="22171-117">**支持 IN、 扩展和 IN 出过程和函数，以及函数返回值的 REF CURSOR 参数**。</span><span class="sxs-lookup"><span data-stu-id="22171-117">**Support IN, OUT, and IN OUT REF CURSOR parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="22171-118">有关详细信息，请参阅[执行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-118">For more information, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="22171-119">**中支持，扩展和 IN 出记录类型参数的过程和函数，以及函数返回值**。</span><span class="sxs-lookup"><span data-stu-id="22171-119">**Support IN, OUT, and IN OUT RECORD type parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="22171-120">有关详细信息，请参阅[执行操作使用记录类型使用 WCF 服务模型的 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-120">For more information, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="22171-121">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="22171-121">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="22171-122">中的示例此主题使用 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 重载过程。</span><span class="sxs-lookup"><span data-stu-id="22171-122">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT overloaded procedure.</span></span> <span data-ttu-id="22171-123">此过程从基于帐户 ID 或帐户名称 SCOTT/帐户表中读取一条记录。</span><span class="sxs-lookup"><span data-stu-id="22171-123">This procedure reads a record from the SCOTT/ACCOUNT table based on either an account ID or an account name.</span></span> <span data-ttu-id="22171-124">一个脚本来生成此过程和下表提供的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="22171-124">A script to generate this procedure and table is supplied with the SDK samples.</span></span> <span data-ttu-id="22171-125">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-125">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="22171-126">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="22171-126">The WCF Client Class</span></span>  
 <span data-ttu-id="22171-127">下表显示 WCF 客户端和有关过程，生成的方法的名称的函数和包[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面。</span><span class="sxs-lookup"><span data-stu-id="22171-127">The following table shows the name of the WCF client and the method generated for procedures, functions and packages that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces.</span></span> <span data-ttu-id="22171-128">除非函数或过程重载函数，单个 WCF 客户端用于调用的所有在架构中，所有在架构中，过程或函数的所有函数和包中的过程。</span><span class="sxs-lookup"><span data-stu-id="22171-128">Unless a function or procedure is overloaded, a single WCF client is used to invoke all of the functions in a schema, all of the procedures in a schema, or all of the functions and procedures in a package.</span></span>  
  
|<span data-ttu-id="22171-129">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="22171-129">Oracle Artifact</span></span>|<span data-ttu-id="22171-130">WCF 客户端操作名称</span><span class="sxs-lookup"><span data-stu-id="22171-130">WCF Client Operation Name</span></span>|<span data-ttu-id="22171-131">示例</span><span class="sxs-lookup"><span data-stu-id="22171-131">Example</span></span>|  
|---------------------|-------------------------------|-------------|  
|<span data-ttu-id="22171-132">过程</span><span class="sxs-lookup"><span data-stu-id="22171-132">Procedure</span></span>|<span data-ttu-id="22171-133">[架构]ProcedureClient。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span></span>|<span data-ttu-id="22171-134">SCOTTProcedureClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="22171-134">SCOTTProcedureClient.MYPROC</span></span>|  
|<span data-ttu-id="22171-135">函数</span><span class="sxs-lookup"><span data-stu-id="22171-135">Function</span></span>|<span data-ttu-id="22171-136">[架构]FunctionClient。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span></span>|<span data-ttu-id="22171-137">SCOTTProcedureClient.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="22171-137">SCOTTProcedureClient.MYFUNC</span></span>|  
|<span data-ttu-id="22171-138">包 （过程或函数）</span><span class="sxs-lookup"><span data-stu-id="22171-138">Package (procedure or function)</span></span>|<span data-ttu-id="22171-139">[架构]包 [包名称] 客户端。[PROC_NAME 或 FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-139">[SCHEMA]Package[PACKAGE_NAME]Client.[PROC_NAME or FUNC_NAME]</span></span>|<span data-ttu-id="22171-140">SCOTTPackageMYPACKAGEClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="22171-140">SCOTTPackageMYPACKAGEClient.MYPROC</span></span>|  
  
 <span data-ttu-id="22171-141">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="22171-141">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="22171-142">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="22171-142">[PROC_NAME] = The name of an Oracle procedure; for example, MYPROC.</span></span>  
  
 <span data-ttu-id="22171-143">[FUNC_NAME] = Oracle 函数中; 的名称例如，MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="22171-143">[FUNC_NAME] = The name of an Oracle function; for example, MYFUNC.</span></span>  
  
 <span data-ttu-id="22171-144">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="22171-144">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="22171-145">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 Oracle 记录类型参数和返回值，以及返回 REF CURSOR 参数作为包含 Oracle 记录的行数据 （或字段） 的复杂 XML 类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="22171-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents Oracle RECORD type parameters and return values as well as the result sets returned by REF CURSOR parameters as complex XML types that contain the row data (or fields) of an Oracle record.</span></span> <span data-ttu-id="22171-146">在 WCF 服务模型中，上述每种 XML 类型表示为一个.NET 类;类的属性表示记录类型或 REF CURSOR 结果集的字段。</span><span class="sxs-lookup"><span data-stu-id="22171-146">In the WCF service model, each of these XML types is represented as a .NET class; the properties of the class represent the fields of the RECORD type or REF CURSOR result set.</span></span> <span data-ttu-id="22171-147">Oracle 记录类型始终表示为强类型化.NET 类。</span><span class="sxs-lookup"><span data-stu-id="22171-147">Oracle RECORD types are always represented as strongly-typed .NET classes.</span></span> <span data-ttu-id="22171-148">REF CURSOR 结果集，但是，可以表示为强类型化或弱类型基于 REF CURSOR 本身是否声明为强类型化或弱类型的记录。</span><span class="sxs-lookup"><span data-stu-id="22171-148">A REF CURSOR result set, however, can be represented as either strongly-typed or weakly-typed records based on whether the REF CURSOR itself is declared as strongly-typed or weakly-typed.</span></span> <span data-ttu-id="22171-149">表示 REF CURSOR 或记录类型参数 （或返回值） 中一个基于过程、 函数或包的唯一命名空间中的生成的类。</span><span class="sxs-lookup"><span data-stu-id="22171-149">The classes that represent REF CURSOR or RECORD type parameters (or return values) are generated in a unique namespace based on the procedure, function, or package.</span></span> <span data-ttu-id="22171-150">下表显示这些命名空间。</span><span class="sxs-lookup"><span data-stu-id="22171-150">The following table shows these namespaces.</span></span>  
  
|<span data-ttu-id="22171-151">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="22171-151">Oracle Artifact</span></span>|<span data-ttu-id="22171-152">命名空间</span><span class="sxs-lookup"><span data-stu-id="22171-152">Namespace</span></span>|<span data-ttu-id="22171-153">示例</span><span class="sxs-lookup"><span data-stu-id="22171-153">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="22171-154">过程</span><span class="sxs-lookup"><span data-stu-id="22171-154">Procedure</span></span>|<span data-ttu-id="22171-155">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-155">[BASE_NS].</span></span> <span data-ttu-id="22171-156">[架构]。过程。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-156">[SCHEMA].Procedure.[PROC_NAME]</span></span>|<span data-ttu-id="22171-157">microsoft.lobservices.oracledb._2007._03.SCOTT。Procedure.MYPROC</span><span class="sxs-lookup"><span data-stu-id="22171-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span></span>|  
|<span data-ttu-id="22171-158">函数</span><span class="sxs-lookup"><span data-stu-id="22171-158">Function</span></span>|<span data-ttu-id="22171-159">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-159">[BASE_NS].</span></span> <span data-ttu-id="22171-160">[架构]。函数。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-160">[SCHEMA].Function.[FUNC_NAME]</span></span>|<span data-ttu-id="22171-161">microsoft.lobservices.oracledb._2007._03.SCOTT。Function.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="22171-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span></span>|  
|<span data-ttu-id="22171-162">包 （过程）</span><span class="sxs-lookup"><span data-stu-id="22171-162">Package (Procedure)</span></span>|<span data-ttu-id="22171-163">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-163">[BASE_NS].</span></span> <span data-ttu-id="22171-164">[架构]。包。[PACKAGE_NAME]。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span></span>|<span data-ttu-id="22171-165">microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYPROC</span><span class="sxs-lookup"><span data-stu-id="22171-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span></span>|  
|<span data-ttu-id="22171-166">包 （函数）</span><span class="sxs-lookup"><span data-stu-id="22171-166">Package (Function)</span></span>|<span data-ttu-id="22171-167">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-167">[BASE_NS].</span></span> <span data-ttu-id="22171-168">[架构]。包。[PACKAGE_NAME]。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span></span>|<span data-ttu-id="22171-169">microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="22171-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span></span>|  
|<span data-ttu-id="22171-170">泛型记录集 （弱类型）</span><span class="sxs-lookup"><span data-stu-id="22171-170">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="22171-171">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="22171-171">[BASE_NS]</span></span>|<span data-ttu-id="22171-172">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="22171-172">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="22171-173">[BASE_NS] = 基适配器命名空间;microsoft.lobservices.oracledb._2007._03。</span><span class="sxs-lookup"><span data-stu-id="22171-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="22171-174">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="22171-174">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="22171-175">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="22171-175">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="22171-176">[FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="22171-176">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="22171-177">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="22171-177">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="22171-178">有关如何将这些命名空间用于记录参数的信息，请参阅[执行操作使用记录类型使用 WCF 服务模型的 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-178">For information about how these namespaces are used for RECORD parameters, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span> <span data-ttu-id="22171-179">有关如何将这些命名空间用于 REF CURSOR 参数的信息，请参阅[执行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-179">For information about how these namespaces are used for REF CURSOR parameters, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="22171-180">一般情况下，Oracle 参数和返回值映射，如下所示的 WCF 客户端方法中：</span><span class="sxs-lookup"><span data-stu-id="22171-180">In general, the Oracle parameters and return values are mapped as follows in the WCF client method:</span></span>  
  
-   <span data-ttu-id="22171-181">Oracle IN 参数映射到.NET （输入） 参数。</span><span class="sxs-lookup"><span data-stu-id="22171-181">Oracle IN parameters are mapped to .NET (input) parameters.</span></span>  
  
-   <span data-ttu-id="22171-182">Oracle OUT 参数映射到.NET**出**参数。</span><span class="sxs-lookup"><span data-stu-id="22171-182">Oracle OUT parameters are mapped to .NET **out** parameters.</span></span>  
  
-   <span data-ttu-id="22171-183">Oracle IN OUT 参数映射到.NET **ref**参数。</span><span class="sxs-lookup"><span data-stu-id="22171-183">Oracle IN OUT parameters are mapped to .NET **ref** parameters.</span></span>  
  
-   <span data-ttu-id="22171-184">函数返回值将映射到方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-184">Function RETURN values are mapped to the method return value.</span></span>  
  
 <span data-ttu-id="22171-185">但是，存在两个重要的例外：</span><span class="sxs-lookup"><span data-stu-id="22171-185">However, two important exceptions exist:</span></span>  
  
-   <span data-ttu-id="22171-186">Oracle IN 出 REF CURSOR 参数将被拆分为输入的字符串和输出 (**出**) 记录集。</span><span class="sxs-lookup"><span data-stu-id="22171-186">Oracle IN OUT REF CURSOR parameters are split into an input string and an output (**out**) record set.</span></span> <span data-ttu-id="22171-187">这是因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CUSROR 参数作为字符串，并为复杂类型 （记录集） 的出 REF CURSOR 参数，不能这些组合到单个参数。</span><span class="sxs-lookup"><span data-stu-id="22171-187">This is because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CUSROR parameters as strings and OUT REF CURSOR parameters as complex types (record sets), these cannot be combined into a single parameter.</span></span>  
  
-   <span data-ttu-id="22171-188">先出 Oracle 过程中的参数映射到的 WCF 客户端方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-188">The first OUT parameter in an Oracle procedure is mapped to the return value of the WCF client method.</span></span> <span data-ttu-id="22171-189">这是标准的 WCF 行为。</span><span class="sxs-lookup"><span data-stu-id="22171-189">This is standard WCF behavior.</span></span>  
  
 <span data-ttu-id="22171-190">下面的示例演示一个简单的 Oracle 过程 （SCOTT 架构中加载） 过程的一部分和生成来调用它的 WCF 客户端方法的签名。</span><span class="sxs-lookup"><span data-stu-id="22171-190">The following example shows part of a simple Oracle procedure (loaded in the SCOTT schema) and the signature of the WCF client method that is generated to invoke it.</span></span> <span data-ttu-id="22171-191">Oracle 过程具有三个 IN 参数、 三个 IN OUT 参数，和三个 OUT 参数;但是，WCF 客户端方法未映射的第一个输出参数的参数。</span><span class="sxs-lookup"><span data-stu-id="22171-191">The Oracle procedure has three IN parameters, three IN OUT parameters, and three OUT parameters; however, the WCF client method does not map a parameter for the first OUT parameter.</span></span> <span data-ttu-id="22171-192">而被映射到方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-192">Instead it is mapped to the method return value.</span></span>  
  
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
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a><span data-ttu-id="22171-193">对重载的过程、 函数和包的支持</span><span class="sxs-lookup"><span data-stu-id="22171-193">Support for Overloaded Procedures, Functions and Packages</span></span>  
 <span data-ttu-id="22171-194">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持通过将是唯一的字符串追加到的节点 ID 和命名空间，它会显示为每个重载的项目重载过程、 函数和包。</span><span class="sxs-lookup"><span data-stu-id="22171-194">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports overloaded procedures, functions, and packages by appending a unique string to the node ID and the namespace that it surfaces for each overloaded artifact.</span></span> <span data-ttu-id="22171-195">此字符串为"overload1"的第一个重载，"overload2"下一步重载中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="22171-195">This string is "overload1" for the first overload, "overload2" for the next overload, and so on.</span></span>  
  
 <span data-ttu-id="22171-196">WCF 服务模型中由唯一的 WCF 客户端表示每个重载的过程或函数。</span><span class="sxs-lookup"><span data-stu-id="22171-196">In the WCF service model each overloaded procedure or function is represented by a unique WCF client.</span></span> <span data-ttu-id="22171-197">这是不同于在架构中，所有在架构中，过程的函数的所有的非重载情况或所有的过程和函数在包中的都同一个 WCF 客户端通过调用。</span><span class="sxs-lookup"><span data-stu-id="22171-197">This is different from the non-overloaded case in which all of the functions in a SCHEMA, all of the procedures in a SCHEMA, or all of the procedures and functions in a PACKAGE are invoked by the same WCF client.</span></span> <span data-ttu-id="22171-198">下表显示 WCF 客户端名称和为重载的过程、 函数和包生成的方法。</span><span class="sxs-lookup"><span data-stu-id="22171-198">The following table shows the WCF client name and method generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="22171-199">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="22171-199">Oracle Artifact</span></span>|<span data-ttu-id="22171-200">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="22171-200">WCF Client Name</span></span>|<span data-ttu-id="22171-201">示例</span><span class="sxs-lookup"><span data-stu-id="22171-201">Example</span></span>|  
|---------------------|---------------------|-------------|  
|<span data-ttu-id="22171-202">重载的包 （过程）</span><span class="sxs-lookup"><span data-stu-id="22171-202">Overloaded Package (Procedure)</span></span>|<span data-ttu-id="22171-203">[架构]包 [PACKAGE_NAME] [PROC_NAME]] [OVERLOAD_ID] 客户端。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span></span>|<span data-ttu-id="22171-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span><span class="sxs-lookup"><span data-stu-id="22171-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span></span>|  
|<span data-ttu-id="22171-205">重载的包 （函数）</span><span class="sxs-lookup"><span data-stu-id="22171-205">Overloaded Package (Function)</span></span>|<span data-ttu-id="22171-206">[架构]包 [PACKAGE_NAME] [FUNC_NAME]] [OVERLOAD_ID] 客户端。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="22171-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span></span>|<span data-ttu-id="22171-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="22171-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span></span>|  
  
 <span data-ttu-id="22171-208">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="22171-208">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="22171-209">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="22171-209">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="22171-210">[FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="22171-210">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="22171-211">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="22171-211">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="22171-212">[OVERLOAD_ID] = 标识重载的项目中; 的唯一字符串"overload1"、"overload2"，依次类推。</span><span class="sxs-lookup"><span data-stu-id="22171-212">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span>  
  
 <span data-ttu-id="22171-213">下表显示为重载的过程、 函数和包生成的命名空间。</span><span class="sxs-lookup"><span data-stu-id="22171-213">The following table shows the namespace generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="22171-214">Oracle 项目</span><span class="sxs-lookup"><span data-stu-id="22171-214">Oracle Artifact</span></span>|<span data-ttu-id="22171-215">命名空间</span><span class="sxs-lookup"><span data-stu-id="22171-215">Namespace</span></span>|<span data-ttu-id="22171-216">示例</span><span class="sxs-lookup"><span data-stu-id="22171-216">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="22171-217">包 （过程）</span><span class="sxs-lookup"><span data-stu-id="22171-217">Package (Procedure)</span></span>|<span data-ttu-id="22171-218">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-218">[BASE_NS].</span></span> <span data-ttu-id="22171-219">[架构]。包。[PACKAGE_NAME]。[PROC_NAME][OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="22171-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span></span>|<span data-ttu-id="22171-220">microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYPROC.overload1</span><span class="sxs-lookup"><span data-stu-id="22171-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span></span>|  
|<span data-ttu-id="22171-221">包 （函数）</span><span class="sxs-lookup"><span data-stu-id="22171-221">Package (Function)</span></span>|<span data-ttu-id="22171-222">[BASE_NS]。</span><span class="sxs-lookup"><span data-stu-id="22171-222">[BASE_NS].</span></span> <span data-ttu-id="22171-223">[架构]。包。[PACKAGE_NAME]。[FUNC_NAME]。[OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="22171-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span></span>|<span data-ttu-id="22171-224">microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYFUNC.overload1</span><span class="sxs-lookup"><span data-stu-id="22171-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span></span>|  
|<span data-ttu-id="22171-225">泛型记录集 （弱类型）</span><span class="sxs-lookup"><span data-stu-id="22171-225">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="22171-226">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="22171-226">[BASE_NS]</span></span>|<span data-ttu-id="22171-227">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="22171-227">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="22171-228">[BASE_NS] = 基适配器命名空间;microsoft.lobservices.oracledb._2007._03。</span><span class="sxs-lookup"><span data-stu-id="22171-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="22171-229">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="22171-229">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="22171-230">[PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。</span><span class="sxs-lookup"><span data-stu-id="22171-230">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="22171-231">[FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。</span><span class="sxs-lookup"><span data-stu-id="22171-231">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="22171-232">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="22171-232">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="22171-233">[OVERLOAD_ID] = 标识重载的项目中; 的唯一字符串"overload1"、"overload2"，依次类推。</span><span class="sxs-lookup"><span data-stu-id="22171-233">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span> <span data-ttu-id="22171-234">在字符串中的数字值是由 Oracle 数据库维护的项目重载 ID。</span><span class="sxs-lookup"><span data-stu-id="22171-234">The numeric value in the string is the overload ID for the artifact maintained by the Oracle database.</span></span>  
  
 <span data-ttu-id="22171-235">下面的示例演示 WCF 客户端和 ACCOUNT_PKG 包中的重载 GET_ACCOUNT 过程生成的方法签名。</span><span class="sxs-lookup"><span data-stu-id="22171-235">The following example shows the WCF clients and the method signatures generated for the overloaded GET_ACCOUNT procedure in the ACCOUNT_PKG package.</span></span> <span data-ttu-id="22171-236">（Oracle 声明是包含。）此示例演示如何为每个重载生成唯一的 WCF 客户端和如何为每个客户端生成的方法返回的记录集的唯一命名空间中。</span><span class="sxs-lookup"><span data-stu-id="22171-236">(The Oracle declarations are included.) This example shows how a unique WCF client is generated for each overload and how the method generated for each client returns a record set in a unique namespace.</span></span>  
  
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
  
## <a name="invoking-functions-and-procedures"></a><span data-ttu-id="22171-237">调用函数和过程</span><span class="sxs-lookup"><span data-stu-id="22171-237">Invoking Functions and Procedures</span></span>  
 <span data-ttu-id="22171-238">若要使用 WCF 客户端调用一个函数或过程，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="22171-238">To invoke a function or a procedure by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="22171-239">生成用于目标函数、 过程或包的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="22171-239">Generate a WCF client class for the target function, procedure, or package.</span></span> <span data-ttu-id="22171-240">此类应包含的操作，将在目标项目上调用的方法。</span><span class="sxs-lookup"><span data-stu-id="22171-240">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22171-241">在[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，重载函数和过程出现在**可用类别和操作**框以 [名称].1、 [名称].2，[NAME].3，依次类推，其中 [名称] 是重载的项目和的数字值的名称是对 Oracle 数据库的重载 ID。</span><span class="sxs-lookup"><span data-stu-id="22171-241">In the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], overloaded functions and procedures appear in the **Available categories and operations** box as [NAME].1, [NAME].2, [NAME].3, and so on, where [NAME] is the name of the overloaded artifact and the numeric value is the overload ID on the Oracle database.</span></span>  
  
2.  <span data-ttu-id="22171-242">创建 WCF 客户端类的实例并调用其方法来调用的函数或过程。</span><span class="sxs-lookup"><span data-stu-id="22171-242">Create an instance of the WCF client class and call its methods to invoke the function or procedure.</span></span>  
  
 <span data-ttu-id="22171-243">有关详细信息，有关如何创建一个 WCF 客户端类，在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-243">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="22171-244">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库执行事务内的每个操作。</span><span class="sxs-lookup"><span data-stu-id="22171-244">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22171-245">表示 REF CURSOR 和记录类型参数或返回值函数或过程 （和包） 中的类为每个函数或过程声明中的唯一命名空间。</span><span class="sxs-lookup"><span data-stu-id="22171-245">The classes that represent REF CURSOR and RECORD type parameters or return values in functions or procedures (and packages) are declared in a unique namespace for each function or procedure.</span></span> <span data-ttu-id="22171-246">例如，这意味着，每个 WCF 客户端方法中，用作两个不同函数中的返回值的包 REF CURSOR 类型将唯一的命名空间中声明。</span><span class="sxs-lookup"><span data-stu-id="22171-246">This means, for example, that a PACKAGE REF CURSOR type that is used as a return value in two different functions will be declared in a unique namespace for each WCF client method.</span></span> <span data-ttu-id="22171-247">您必须声明单独的变量以保存这些不同的返回值或相应地转换该变量，在调用 WCF 客户端方法之一时。</span><span class="sxs-lookup"><span data-stu-id="22171-247">You must either declare separate variables to hold these different return values or appropriately cast the variable when you invoke one of the WCF client methods.</span></span>  
  
 <span data-ttu-id="22171-248">下面的示例演示如何调用的重载的 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 过程从 /SCOTT/ACCOUNT 表中获取的客户记录。</span><span class="sxs-lookup"><span data-stu-id="22171-248">The following example demonstrates calling the overloaded /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT procedure to get account records from the /SCOTT/ACCOUNT table.</span></span> <span data-ttu-id="22171-249">首先通过调用 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 过程中创建新的记录。</span><span class="sxs-lookup"><span data-stu-id="22171-249">First a new record is created by calling the /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT procedure.</span></span> <span data-ttu-id="22171-250">请阅读新记录后两次通过调用 GET_ACCOUNT 的不同重载。</span><span class="sxs-lookup"><span data-stu-id="22171-250">Then the new record is read back twice by calling different overloads of GET_ACCOUNT.</span></span> <span data-ttu-id="22171-251">此示例使用三个 WCF 客户端，一个用于 CREATE_ACCOUNT 过程，两个分别用于 GET_ACCOUNT 重载。</span><span class="sxs-lookup"><span data-stu-id="22171-251">This example uses three WCF clients, one for the CREATE_ACCOUNT procedure and one each for the GET_ACCOUNT overloads.</span></span> <span data-ttu-id="22171-252">使用别名来区分命名空间用于 GET_ACCOUNT 的返回值。</span><span class="sxs-lookup"><span data-stu-id="22171-252">Aliases are used to distinguish between namespaces used for the return value of GET_ACCOUNT.</span></span> <span data-ttu-id="22171-253">完整示例位于 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="22171-253">A full sample is available in the SDK samples.</span></span> <span data-ttu-id="22171-254">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="22171-254">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22171-255">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22171-255">See Also</span></span>  
 [<span data-ttu-id="22171-256">通过使用 WCF 服务模型开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="22171-256">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)