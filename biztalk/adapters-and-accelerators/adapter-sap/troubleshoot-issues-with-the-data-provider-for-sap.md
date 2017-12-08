---
title: "解决与适用于 SAP 的数据提供程序的问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a><span data-ttu-id="bbb51-102">解决与适用于 SAP 的数据提供程序的问题</span><span class="sxs-lookup"><span data-stu-id="bbb51-102">Troubleshoot Issues with the Data Provider for SAP</span></span>
<span data-ttu-id="bbb51-103">本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bbb51-103">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
##  <a name="BKMK_SAPUnknownParam"></a><span data-ttu-id="bbb51-104">使用 Data Provider for SAP 的未知的参数错误</span><span class="sxs-lookup"><span data-stu-id="bbb51-104">Unknown Parameter error using the Data Provider for SAP</span></span>  
 <span data-ttu-id="bbb51-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="bbb51-105">**Problem**</span></span>  
  
 <span data-ttu-id="bbb51-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="bbb51-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] gives the following error:</span></span>  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 <span data-ttu-id="bbb51-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bbb51-107">**Cause**</span></span>  
  
 <span data-ttu-id="bbb51-108">自定义的 RFC、 Z_EXTRACT_DATA_OO，SAP 系统中安装的不是最新。</span><span class="sxs-lookup"><span data-stu-id="bbb51-108">The custom RFC, Z_EXTRACT_DATA_OO, installed in your SAP system is not the latest.</span></span> <span data-ttu-id="bbb51-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC，Z_EXTRACT_DATA_OO，执行对 SAP 表选择操作。</span><span class="sxs-lookup"><span data-stu-id="bbb51-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC, Z_EXTRACT_DATA_OO, to perform SELECT operations on the SAP table.</span></span>  
  
 <span data-ttu-id="bbb51-110">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bbb51-110">**Resolution**</span></span>  
  
 <span data-ttu-id="bbb51-111">你必须为可用的最新版本更新的自定义的 RFC。</span><span class="sxs-lookup"><span data-stu-id="bbb51-111">You must update the custom RFC to the latest available version.</span></span> <span data-ttu-id="bbb51-112">此 RFC、 Z_EXTRACT_DATA_OO，都可以进行 adapterpacknoversion。</span><span class="sxs-lookup"><span data-stu-id="bbb51-112">This RFC, Z_EXTRACT_DATA_OO, is available with the adapterpacknoversion.</span></span> <span data-ttu-id="bbb51-113">有关如何安装和卸载自定义的 RFC 的详细信息，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb51-113">For more information about how to install and uninstall the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPOOM"></a><span data-ttu-id="bbb51-114">取消从 SAP 表中选择数据时的内存异常</span><span class="sxs-lookup"><span data-stu-id="bbb51-114">Out of memory exceptions when selecting data from an SAP table</span></span>  
 <span data-ttu-id="bbb51-115">**问题**</span><span class="sxs-lookup"><span data-stu-id="bbb51-115">**Problem**</span></span>  
  
 <span data-ttu-id="bbb51-116">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从 SAP 系统中选择数据时将引发内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="bbb51-116">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] throws an out of memory exception when selecting data from an SAP system.</span></span>  
  
 <span data-ttu-id="bbb51-117">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bbb51-117">**Cause**</span></span>  
  
 <span data-ttu-id="bbb51-118">默认情况下，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一次检索 10,000 行。</span><span class="sxs-lookup"><span data-stu-id="bbb51-118">By default, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] retrieves 10,000 rows at a time.</span></span> <span data-ttu-id="bbb51-119">此外，每个批行从 SAP 系统中检索存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="bbb51-119">Also, each batch of rows retrieved from the SAP system is stored in the memory.</span></span> <span data-ttu-id="bbb51-120">因此，</span><span class="sxs-lookup"><span data-stu-id="bbb51-120">So,</span></span>  
  
-   <span data-ttu-id="bbb51-121">如果从中检索数据的表包含大量行，或</span><span class="sxs-lookup"><span data-stu-id="bbb51-121">If the table from which data is being retrieved contains a large number of rows, or</span></span>  
  
-   <span data-ttu-id="bbb51-122">如果表包含占用的内存，相当多的数据类型的列</span><span class="sxs-lookup"><span data-stu-id="bbb51-122">If the table contains columns of data types that consume a significant amount of memory,</span></span>  
  
 <span data-ttu-id="bbb51-123">内存使用情况[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]显著提高，并可能会导致内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="bbb51-123">The memory consumption by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] increases significantly and may result in an out of memory exception.</span></span>  
  
 <span data-ttu-id="bbb51-124">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bbb51-124">**Resolution**</span></span>  
  
 <span data-ttu-id="bbb51-125">你可以更改最大从 SAP 系统中检索的行数。</span><span class="sxs-lookup"><span data-stu-id="bbb51-125">You can change the maximum number of rows retrieved from the SAP system.</span></span> <span data-ttu-id="bbb51-126">你可以做到这一点与 SELECT 语句中指定了 batchsize 选项。</span><span class="sxs-lookup"><span data-stu-id="bbb51-126">You can do so by specifying a 'batchsize' option with the SELECT statement.</span></span> <span data-ttu-id="bbb51-127">例如：</span><span class="sxs-lookup"><span data-stu-id="bbb51-127">For example:</span></span>  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 <span data-ttu-id="bbb51-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在一次检索仅 1000年行，因此不会不会占用大量的内存。</span><span class="sxs-lookup"><span data-stu-id="bbb51-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] now retrieves only 1000 rows at a time and hence does not consume large amount of memory.</span></span>  
  
##  <a name="BKMK_SAPQueryExcep"></a><span data-ttu-id="bbb51-129">执行查询采用带日期值的参数时出现异常</span><span class="sxs-lookup"><span data-stu-id="bbb51-129">Exception while executing a query that takes parameters with date values</span></span>  
 <span data-ttu-id="bbb51-130">**问题**</span><span class="sxs-lookup"><span data-stu-id="bbb51-130">**Problem**</span></span>  
  
 <span data-ttu-id="bbb51-131">执行一个查询使用采用日期值的参数的 EXECQUERY 命令时，则会得到以下异常：</span><span class="sxs-lookup"><span data-stu-id="bbb51-131">You get the following exception when you execute a query using the EXECQUERY command that has a parameter which takes a date value:</span></span>  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 <span data-ttu-id="bbb51-132">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bbb51-132">**Cause**</span></span>  
  
 <span data-ttu-id="bbb51-133">在执行查询使用 EXECQUERY 命令时，你始终必须采用 YYYYMMDD 格式指定日期值。</span><span class="sxs-lookup"><span data-stu-id="bbb51-133">When executing queries using the EXECQUERY command, you must always specify date values in YYYYMMDD format.</span></span>  
  
 <span data-ttu-id="bbb51-134">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bbb51-134">**Resolution**</span></span>  
  
 <span data-ttu-id="bbb51-135">请确保采用 YYYYMMDD 格式指定日期值。</span><span class="sxs-lookup"><span data-stu-id="bbb51-135">Make sure you specify date values in YYYYMMDD format.</span></span> <span data-ttu-id="bbb51-136">例如：</span><span class="sxs-lookup"><span data-stu-id="bbb51-136">For example:</span></span>  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a><span data-ttu-id="bbb51-137">执行查询使用 EXECQUERY 命令 NO_VARIANT 异常</span><span class="sxs-lookup"><span data-stu-id="bbb51-137">NO_VARIANT exception executing queries using the EXECQUERY command</span></span>  
 <span data-ttu-id="bbb51-138">**问题**</span><span class="sxs-lookup"><span data-stu-id="bbb51-138">**Problem**</span></span>  
  
 <span data-ttu-id="bbb51-139">执行一个查询使用 EXECQUERY 命令时，则会得到以下异常：</span><span class="sxs-lookup"><span data-stu-id="bbb51-139">You get the following exception when you execute a query using the EXECQUERY command:</span></span>  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 <span data-ttu-id="bbb51-140">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bbb51-140">**Cause**</span></span>  
  
 <span data-ttu-id="bbb51-141">可以有两个可能的原因，此异常：</span><span class="sxs-lookup"><span data-stu-id="bbb51-141">There can be two probable causes for this exception:</span></span>  
  
1.  <span data-ttu-id="bbb51-142">试图执行的查询具有在 SAP 系统中定义的变体。</span><span class="sxs-lookup"><span data-stu-id="bbb51-142">The query you are trying to execute has variants defined in the SAP system.</span></span> <span data-ttu-id="bbb51-143">变体，请参阅为已保存的一组可以执行的 SAP 查询时指定的选择条件。</span><span class="sxs-lookup"><span data-stu-id="bbb51-143">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="bbb51-144">例如，可以使用变体指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="bbb51-144">For example, you can use variants to specify default values for queries.</span></span>  
  
2.  <span data-ttu-id="bbb51-145">查询尝试执行都不具有 variant 类型的定义，也不期望将传递参数值。</span><span class="sxs-lookup"><span data-stu-id="bbb51-145">The query you are trying to execute neither has a variant defined nor it expects a parameter value to be passed.</span></span>  
  
 <span data-ttu-id="bbb51-146">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bbb51-146">**Resolution**</span></span>  
  
1.  <span data-ttu-id="bbb51-147">对于原因 1，请确保指定与查询关联的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="bbb51-147">For reason 1, make sure you specify the name of the variant associated with the query.</span></span> <span data-ttu-id="bbb51-148">例如：</span><span class="sxs-lookup"><span data-stu-id="bbb51-148">For example:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  <span data-ttu-id="bbb51-149">对于原因 2，请确保指定的查询命令时提供 dummy 参数名称和值。</span><span class="sxs-lookup"><span data-stu-id="bbb51-149">For reason 2, make sure you provide a dummy parameter name and value while specifying the query command.</span></span> <span data-ttu-id="bbb51-150">例如，如果"myquery"查询不需要执行任何参数，EXECQUERY 命令必须指定为：</span><span class="sxs-lookup"><span data-stu-id="bbb51-150">For example, if “myquery” query does not require any parameter to execute, the EXECQUERY command must be specified as:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bbb51-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbb51-151">See Also</span></span>  
[<span data-ttu-id="bbb51-152">故障排除 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="bbb51-152">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)