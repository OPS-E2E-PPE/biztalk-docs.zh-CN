---
title: SAP 数据提供程序疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e0d5406ceb728d28906665fff262edab1623e3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372436"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a><span data-ttu-id="f9f95-102">SAP 数据提供程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="f9f95-102">Troubleshoot Issues with the Data Provider for SAP</span></span>
<span data-ttu-id="f9f95-103">本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9f95-103">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
##  <a name="BKMK_SAPUnknownParam"></a> <span data-ttu-id="f9f95-104">使用 SAP 数据提供程序的未知的参数错误</span><span class="sxs-lookup"><span data-stu-id="f9f95-104">Unknown Parameter error using the Data Provider for SAP</span></span>  
 <span data-ttu-id="f9f95-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="f9f95-105">**Problem**</span></span>  
  
 <span data-ttu-id="f9f95-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]时出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="f9f95-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] gives the following error:</span></span>  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 <span data-ttu-id="f9f95-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="f9f95-107">**Cause**</span></span>  
  
 <span data-ttu-id="f9f95-108">自定义 RFC、 Z_EXTRACT_DATA_OO，SAP 系统中安装了不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="f9f95-108">The custom RFC, Z_EXTRACT_DATA_OO, installed in your SAP system is not the latest.</span></span> <span data-ttu-id="f9f95-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义 RFC，Z_EXTRACT_DATA_OO，来执行 SAP 表的 SELECT 操作。</span><span class="sxs-lookup"><span data-stu-id="f9f95-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC, Z_EXTRACT_DATA_OO, to perform SELECT operations on the SAP table.</span></span>  
  
 <span data-ttu-id="f9f95-110">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f9f95-110">**Resolution**</span></span>  
  
 <span data-ttu-id="f9f95-111">为可用的最新版本，必须更新自定义 RFC。</span><span class="sxs-lookup"><span data-stu-id="f9f95-111">You must update the custom RFC to the latest available version.</span></span> <span data-ttu-id="f9f95-112">此 RFC，Z_EXTRACT_DATA_OO，现 adapterpacknoversion 了。</span><span class="sxs-lookup"><span data-stu-id="f9f95-112">This RFC, Z_EXTRACT_DATA_OO, is available with the adapterpacknoversion.</span></span> <span data-ttu-id="f9f95-113">有关如何安装和卸载自定义 RFC 的详细信息，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="f9f95-113">For more information about how to install and uninstall the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPOOM"></a> <span data-ttu-id="f9f95-114">内存不足异常时从 SAP 表中选择数据</span><span class="sxs-lookup"><span data-stu-id="f9f95-114">Out of memory exceptions when selecting data from an SAP table</span></span>  
 <span data-ttu-id="f9f95-115">**问题**</span><span class="sxs-lookup"><span data-stu-id="f9f95-115">**Problem**</span></span>  
  
 <span data-ttu-id="f9f95-116">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]选择 SAP 系统中的数据时，会引发内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="f9f95-116">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] throws an out of memory exception when selecting data from an SAP system.</span></span>  
  
 <span data-ttu-id="f9f95-117">**原因**</span><span class="sxs-lookup"><span data-stu-id="f9f95-117">**Cause**</span></span>  
  
 <span data-ttu-id="f9f95-118">默认情况下，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一次检索 10,000 行。</span><span class="sxs-lookup"><span data-stu-id="f9f95-118">By default, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] retrieves 10,000 rows at a time.</span></span> <span data-ttu-id="f9f95-119">此外，每一批行从 SAP 系统中检索存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="f9f95-119">Also, each batch of rows retrieved from the SAP system is stored in the memory.</span></span> <span data-ttu-id="f9f95-120">因此，</span><span class="sxs-lookup"><span data-stu-id="f9f95-120">So,</span></span>  
  
- <span data-ttu-id="f9f95-121">如果从中检索数据的表包含大量行，或</span><span class="sxs-lookup"><span data-stu-id="f9f95-121">If the table from which data is being retrieved contains a large number of rows, or</span></span>  
  
- <span data-ttu-id="f9f95-122">如果表包含占用大量内存的数据类型的列</span><span class="sxs-lookup"><span data-stu-id="f9f95-122">If the table contains columns of data types that consume a significant amount of memory,</span></span>  
  
  <span data-ttu-id="f9f95-123">内存使用情况[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]显著增加，可能会导致内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="f9f95-123">The memory consumption by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] increases significantly and may result in an out of memory exception.</span></span>  
  
  <span data-ttu-id="f9f95-124">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f9f95-124">**Resolution**</span></span>  
  
  <span data-ttu-id="f9f95-125">你可以最大的 SAP 系统检索的行数。</span><span class="sxs-lookup"><span data-stu-id="f9f95-125">You can change the maximum number of rows retrieved from the SAP system.</span></span> <span data-ttu-id="f9f95-126">您可以通过使用 SELECT 语句中指定 batchsize 选项来实现。</span><span class="sxs-lookup"><span data-stu-id="f9f95-126">You can do so by specifying a 'batchsize' option with the SELECT statement.</span></span> <span data-ttu-id="f9f95-127">例如：</span><span class="sxs-lookup"><span data-stu-id="f9f95-127">For example:</span></span>  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 <span data-ttu-id="f9f95-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在一次检索仅 1000年行，并因此不会消耗大量内存。</span><span class="sxs-lookup"><span data-stu-id="f9f95-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] now retrieves only 1000 rows at a time and hence does not consume large amount of memory.</span></span>  
  
##  <a name="BKMK_SAPQueryExcep"></a> <span data-ttu-id="f9f95-129">执行查询，采用具有日期值的参数时出现异常</span><span class="sxs-lookup"><span data-stu-id="f9f95-129">Exception while executing a query that takes parameters with date values</span></span>  
 <span data-ttu-id="f9f95-130">**问题**</span><span class="sxs-lookup"><span data-stu-id="f9f95-130">**Problem**</span></span>  
  
 <span data-ttu-id="f9f95-131">执行使用 EXECQUERY 命令具有采用日期值参数的查询时出现以下异常：</span><span class="sxs-lookup"><span data-stu-id="f9f95-131">You get the following exception when you execute a query using the EXECQUERY command that has a parameter which takes a date value:</span></span>  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 <span data-ttu-id="f9f95-132">**原因**</span><span class="sxs-lookup"><span data-stu-id="f9f95-132">**Cause**</span></span>  
  
 <span data-ttu-id="f9f95-133">在执行时使用 EXECQUERY 命令的查询，始终必须以 YYYYMMDD 格式表示指定日期值。</span><span class="sxs-lookup"><span data-stu-id="f9f95-133">When executing queries using the EXECQUERY command, you must always specify date values in YYYYMMDD format.</span></span>  
  
 <span data-ttu-id="f9f95-134">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f9f95-134">**Resolution**</span></span>  
  
 <span data-ttu-id="f9f95-135">请确保以 YYYYMMDD 格式表示指定日期值。</span><span class="sxs-lookup"><span data-stu-id="f9f95-135">Make sure you specify date values in YYYYMMDD format.</span></span> <span data-ttu-id="f9f95-136">例如：</span><span class="sxs-lookup"><span data-stu-id="f9f95-136">For example:</span></span>  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a> <span data-ttu-id="f9f95-137">执行查询使用 EXECQUERY 命令 NO_VARIANT 异常</span><span class="sxs-lookup"><span data-stu-id="f9f95-137">NO_VARIANT exception executing queries using the EXECQUERY command</span></span>  
 <span data-ttu-id="f9f95-138">**问题**</span><span class="sxs-lookup"><span data-stu-id="f9f95-138">**Problem**</span></span>  
  
 <span data-ttu-id="f9f95-139">执行一个查询使用 EXECQUERY 命令时出现以下异常：</span><span class="sxs-lookup"><span data-stu-id="f9f95-139">You get the following exception when you execute a query using the EXECQUERY command:</span></span>  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 <span data-ttu-id="f9f95-140">**原因**</span><span class="sxs-lookup"><span data-stu-id="f9f95-140">**Cause**</span></span>  
  
 <span data-ttu-id="f9f95-141">可以有两个可能的原因，此异常：</span><span class="sxs-lookup"><span data-stu-id="f9f95-141">There can be two probable causes for this exception:</span></span>  
  
1. <span data-ttu-id="f9f95-142">要执行的查询有 SAP 系统中定义的变体。</span><span class="sxs-lookup"><span data-stu-id="f9f95-142">The query you are trying to execute has variants defined in the SAP system.</span></span> <span data-ttu-id="f9f95-143">变体是指已保存的一组选择条件可以执行 SAP 查询时指定的。</span><span class="sxs-lookup"><span data-stu-id="f9f95-143">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="f9f95-144">例如，变体可用于指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="f9f95-144">For example, you can use variants to specify default values for queries.</span></span>  
  
2. <span data-ttu-id="f9f95-145">查询尝试执行都不具有 variant 类型的定义，也不需要传递的参数值。</span><span class="sxs-lookup"><span data-stu-id="f9f95-145">The query you are trying to execute neither has a variant defined nor it expects a parameter value to be passed.</span></span>  
  
   <span data-ttu-id="f9f95-146">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f9f95-146">**Resolution**</span></span>  
  
3. <span data-ttu-id="f9f95-147">对于原因 1，请确保指定的名称与查询关联的变体。</span><span class="sxs-lookup"><span data-stu-id="f9f95-147">For reason 1, make sure you specify the name of the variant associated with the query.</span></span> <span data-ttu-id="f9f95-148">例如：</span><span class="sxs-lookup"><span data-stu-id="f9f95-148">For example:</span></span>  
  
   ```  
   EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
   ```  
  
4. <span data-ttu-id="f9f95-149">原因 2，请确保指定的查询命令时提供的虚拟参数名称和值。</span><span class="sxs-lookup"><span data-stu-id="f9f95-149">For reason 2, make sure you provide a dummy parameter name and value while specifying the query command.</span></span> <span data-ttu-id="f9f95-150">例如，如果"myquery"查询不需要任何参数来执行，EXECQUERY 命令必须指定为：</span><span class="sxs-lookup"><span data-stu-id="f9f95-150">For example, if “myquery” query does not require any parameter to execute, the EXECQUERY command must be specified as:</span></span>  
  
   ```  
   EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="f9f95-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9f95-151">See Also</span></span>  
[<span data-ttu-id="f9f95-152">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="f9f95-152">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)