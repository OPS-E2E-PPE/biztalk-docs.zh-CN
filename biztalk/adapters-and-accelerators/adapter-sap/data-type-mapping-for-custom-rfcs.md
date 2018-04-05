---
title: 数据类型映射自定义的 Rfc |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-custom-rfcs"></a><span data-ttu-id="0c844-102">自定义的 Rfc 的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="0c844-102">Data Type Mapping for Custom RFCs</span></span>
<span data-ttu-id="0c844-103">下表提供了有关 SAP 数据类型和它们如何映射到.NET 数据类型为 Z_EXTRACT_DATA_OO RFC 的信息。</span><span class="sxs-lookup"><span data-stu-id="0c844-103">The following table provides information about SAP data types and how they are mapped to .NET data types for the Z_EXTRACT_DATA_OO RFC.</span></span> <span data-ttu-id="0c844-104">使用此自定义的 RFC [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0c844-104">This custom RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c844-105">为 Z_EXECUTE_SAP_QUERY，后者由[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]若要执行 EXECQUERY 命令，所有 SAP 数据类型将都转换成.NET 字符串类型。</span><span class="sxs-lookup"><span data-stu-id="0c844-105">For the Z_EXECUTE_SAP_QUERY, which is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute the EXECQUERY command, all SAP data types are converted to .NET string types.</span></span>  
  
|<span data-ttu-id="0c844-106">SAP 数据类型</span><span class="sxs-lookup"><span data-stu-id="0c844-106">SAP Data Type</span></span>|<span data-ttu-id="0c844-107">.NET 数据类型</span><span class="sxs-lookup"><span data-stu-id="0c844-107">.NET Data Type</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="0c844-108">ACCP</span><span class="sxs-lookup"><span data-stu-id="0c844-108">ACCP</span></span>|<span data-ttu-id="0c844-109">-Int32</span><span class="sxs-lookup"><span data-stu-id="0c844-109">-   Int32</span></span><br /><span data-ttu-id="0c844-110">的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="0c844-110">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="0c844-111">CHAR</span><span class="sxs-lookup"><span data-stu-id="0c844-111">CHAR</span></span>|<span data-ttu-id="0c844-112">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-112">String</span></span>|  
|<span data-ttu-id="0c844-113">CLNT</span><span class="sxs-lookup"><span data-stu-id="0c844-113">CLNT</span></span>|<span data-ttu-id="0c844-114">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-114">String</span></span>|  
|<span data-ttu-id="0c844-115">CUKY</span><span class="sxs-lookup"><span data-stu-id="0c844-115">CUKY</span></span>|<span data-ttu-id="0c844-116">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-116">String</span></span>|  
|<span data-ttu-id="0c844-117">CURR</span><span class="sxs-lookup"><span data-stu-id="0c844-117">CURR</span></span>|<span data-ttu-id="0c844-118">如果精度应小于或等于 28 的 decimal</span><span class="sxs-lookup"><span data-stu-id="0c844-118">Decimal, if precision less than or equal to 28</span></span><br /><br /> <span data-ttu-id="0c844-119">字符串，如果精度大于 28</span><span class="sxs-lookup"><span data-stu-id="0c844-119">String, if precision greater than 28</span></span>|  
|<span data-ttu-id="0c844-120">DAT</span><span class="sxs-lookup"><span data-stu-id="0c844-120">DATS</span></span>|<span data-ttu-id="0c844-121">-DateTime</span><span class="sxs-lookup"><span data-stu-id="0c844-121">-   DateTime</span></span><br /><span data-ttu-id="0c844-122">的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="0c844-122">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="0c844-123">DEC</span><span class="sxs-lookup"><span data-stu-id="0c844-123">DEC</span></span>|<span data-ttu-id="0c844-124">Decimal</span><span class="sxs-lookup"><span data-stu-id="0c844-124">Decimal</span></span>|  
|<span data-ttu-id="0c844-125">FLTP</span><span class="sxs-lookup"><span data-stu-id="0c844-125">FLTP</span></span>|<span data-ttu-id="0c844-126">双精度</span><span class="sxs-lookup"><span data-stu-id="0c844-126">Double</span></span>|  
|<span data-ttu-id="0c844-127">INT1</span><span class="sxs-lookup"><span data-stu-id="0c844-127">INT1</span></span>|<span data-ttu-id="0c844-128">Byte</span><span class="sxs-lookup"><span data-stu-id="0c844-128">Byte</span></span>|  
|<span data-ttu-id="0c844-129">INT2</span><span class="sxs-lookup"><span data-stu-id="0c844-129">INT2</span></span>|<span data-ttu-id="0c844-130">Int16</span><span class="sxs-lookup"><span data-stu-id="0c844-130">Int16</span></span>|  
|<span data-ttu-id="0c844-131">INT4</span><span class="sxs-lookup"><span data-stu-id="0c844-131">INT4</span></span>|<span data-ttu-id="0c844-132">Int32</span><span class="sxs-lookup"><span data-stu-id="0c844-132">Int32</span></span>|  
|<span data-ttu-id="0c844-133">LANG</span><span class="sxs-lookup"><span data-stu-id="0c844-133">LANG</span></span>|<span data-ttu-id="0c844-134">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-134">String</span></span>|  
|<span data-ttu-id="0c844-135">NUMC</span><span class="sxs-lookup"><span data-stu-id="0c844-135">NUMC</span></span>|<span data-ttu-id="0c844-136">-Int32，如果字段长度小于或等于为 9</span><span class="sxs-lookup"><span data-stu-id="0c844-136">-   Int32, if field length less than or equal to 9</span></span><br /><span data-ttu-id="0c844-137">-Int64，如果字段长度大于 9 且小于或等于 19</span><span class="sxs-lookup"><span data-stu-id="0c844-137">-   Int64, if field length greater than 9 and less than or equal to 19</span></span><br /><span data-ttu-id="0c844-138">的字符串，如果大于 19</span><span class="sxs-lookup"><span data-stu-id="0c844-138">-   String, if greater than 19</span></span><br /><span data-ttu-id="0c844-139">的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="0c844-139">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="0c844-140">PREC</span><span class="sxs-lookup"><span data-stu-id="0c844-140">PREC</span></span>|<span data-ttu-id="0c844-141">Int16</span><span class="sxs-lookup"><span data-stu-id="0c844-141">Int16</span></span>|  
|<span data-ttu-id="0c844-142">QUAN</span><span class="sxs-lookup"><span data-stu-id="0c844-142">QUAN</span></span>|<span data-ttu-id="0c844-143">Decimal</span><span class="sxs-lookup"><span data-stu-id="0c844-143">Decimal</span></span>|  
|<span data-ttu-id="0c844-144">RAW</span><span class="sxs-lookup"><span data-stu-id="0c844-144">RAW</span></span>|<span data-ttu-id="0c844-145">Byte]</span><span class="sxs-lookup"><span data-stu-id="0c844-145">Byte []</span></span>|  
|<span data-ttu-id="0c844-146">RSTR</span><span class="sxs-lookup"><span data-stu-id="0c844-146">RSTR</span></span>|<span data-ttu-id="0c844-147">Byte]</span><span class="sxs-lookup"><span data-stu-id="0c844-147">Byte []</span></span>|  
|<span data-ttu-id="0c844-148">SSTR</span><span class="sxs-lookup"><span data-stu-id="0c844-148">SSTR</span></span>|<span data-ttu-id="0c844-149">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-149">String</span></span>|  
|<span data-ttu-id="0c844-150">STRG</span><span class="sxs-lookup"><span data-stu-id="0c844-150">STRG</span></span>|<span data-ttu-id="0c844-151">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-151">String</span></span>|  
|<span data-ttu-id="0c844-152">TIMS</span><span class="sxs-lookup"><span data-stu-id="0c844-152">TIMS</span></span>|<span data-ttu-id="0c844-153">-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="0c844-153">-   TimeSpan</span></span><br /><span data-ttu-id="0c844-154">的字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="0c844-154">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="0c844-155">单元</span><span class="sxs-lookup"><span data-stu-id="0c844-155">UNIT</span></span>|<span data-ttu-id="0c844-156">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-156">String</span></span>|  
|<span data-ttu-id="0c844-157">LCHR</span><span class="sxs-lookup"><span data-stu-id="0c844-157">LCHR</span></span>|<span data-ttu-id="0c844-158">字符串</span><span class="sxs-lookup"><span data-stu-id="0c844-158">String</span></span>|  
|<span data-ttu-id="0c844-159">LRAW</span><span class="sxs-lookup"><span data-stu-id="0c844-159">LRAW</span></span>|<span data-ttu-id="0c844-160">Byte]</span><span class="sxs-lookup"><span data-stu-id="0c844-160">Byte []</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c844-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c844-161">See Also</span></span>  
 [<span data-ttu-id="0c844-162">消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="0c844-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)