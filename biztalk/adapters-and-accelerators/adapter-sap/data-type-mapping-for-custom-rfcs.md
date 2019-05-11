---
title: 自定义 Rfc 的数据类型映射 |Microsoft Docs
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
ms.openlocfilehash: 0d6934847a5c5a9482a9c4f1dc8026c50aec6295
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373547"
---
# <a name="data-type-mapping-for-custom-rfcs"></a><span data-ttu-id="68fda-102">自定义 Rfc 的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="68fda-102">Data Type Mapping for Custom RFCs</span></span>
<span data-ttu-id="68fda-103">下表提供了有关 SAP 数据类型和它们如何映射到.NET 数据类型为 Z_EXTRACT_DATA_OO RFC 的信息。</span><span class="sxs-lookup"><span data-stu-id="68fda-103">The following table provides information about SAP data types and how they are mapped to .NET data types for the Z_EXTRACT_DATA_OO RFC.</span></span> <span data-ttu-id="68fda-104">使用此自定义 RFC [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="68fda-104">This custom RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68fda-105">为 Z_EXECUTE_SAP_QUERY，使用这种[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]要执行 EXECQUERY 命令，所有 SAP 数据类型都转换为.NET 字符串类型。</span><span class="sxs-lookup"><span data-stu-id="68fda-105">For the Z_EXECUTE_SAP_QUERY, which is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute the EXECQUERY command, all SAP data types are converted to .NET string types.</span></span>  
  
|<span data-ttu-id="68fda-106">SAP 数据类型</span><span class="sxs-lookup"><span data-stu-id="68fda-106">SAP Data Type</span></span>|<span data-ttu-id="68fda-107">.NET 数据类型</span><span class="sxs-lookup"><span data-stu-id="68fda-107">.NET Data Type</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="68fda-108">ACCP</span><span class="sxs-lookup"><span data-stu-id="68fda-108">ACCP</span></span>|<span data-ttu-id="68fda-109">-   Int32</span><span class="sxs-lookup"><span data-stu-id="68fda-109">-   Int32</span></span><br /><span data-ttu-id="68fda-110">-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="68fda-110">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="68fda-111">CHAR</span><span class="sxs-lookup"><span data-stu-id="68fda-111">CHAR</span></span>|<span data-ttu-id="68fda-112">String</span><span class="sxs-lookup"><span data-stu-id="68fda-112">String</span></span>|  
|<span data-ttu-id="68fda-113">CLNT</span><span class="sxs-lookup"><span data-stu-id="68fda-113">CLNT</span></span>|<span data-ttu-id="68fda-114">String</span><span class="sxs-lookup"><span data-stu-id="68fda-114">String</span></span>|  
|<span data-ttu-id="68fda-115">CUKY</span><span class="sxs-lookup"><span data-stu-id="68fda-115">CUKY</span></span>|<span data-ttu-id="68fda-116">String</span><span class="sxs-lookup"><span data-stu-id="68fda-116">String</span></span>|  
|<span data-ttu-id="68fda-117">当前</span><span class="sxs-lookup"><span data-stu-id="68fda-117">CURR</span></span>|<span data-ttu-id="68fda-118">如果精度应小于或等于 28，十进制</span><span class="sxs-lookup"><span data-stu-id="68fda-118">Decimal, if precision less than or equal to 28</span></span><br /><br /> <span data-ttu-id="68fda-119">字符串，如果精度大于 28</span><span class="sxs-lookup"><span data-stu-id="68fda-119">String, if precision greater than 28</span></span>|  
|<span data-ttu-id="68fda-120">DATS</span><span class="sxs-lookup"><span data-stu-id="68fda-120">DATS</span></span>|<span data-ttu-id="68fda-121">-   DateTime</span><span class="sxs-lookup"><span data-stu-id="68fda-121">-   DateTime</span></span><br /><span data-ttu-id="68fda-122">-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="68fda-122">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="68fda-123">DEC</span><span class="sxs-lookup"><span data-stu-id="68fda-123">DEC</span></span>|<span data-ttu-id="68fda-124">Decimal</span><span class="sxs-lookup"><span data-stu-id="68fda-124">Decimal</span></span>|  
|<span data-ttu-id="68fda-125">FLTP</span><span class="sxs-lookup"><span data-stu-id="68fda-125">FLTP</span></span>|<span data-ttu-id="68fda-126">双精度</span><span class="sxs-lookup"><span data-stu-id="68fda-126">Double</span></span>|  
|<span data-ttu-id="68fda-127">INT1</span><span class="sxs-lookup"><span data-stu-id="68fda-127">INT1</span></span>|<span data-ttu-id="68fda-128">Byte</span><span class="sxs-lookup"><span data-stu-id="68fda-128">Byte</span></span>|  
|<span data-ttu-id="68fda-129">INT2</span><span class="sxs-lookup"><span data-stu-id="68fda-129">INT2</span></span>|<span data-ttu-id="68fda-130">Int16</span><span class="sxs-lookup"><span data-stu-id="68fda-130">Int16</span></span>|  
|<span data-ttu-id="68fda-131">INT4</span><span class="sxs-lookup"><span data-stu-id="68fda-131">INT4</span></span>|<span data-ttu-id="68fda-132">Int32</span><span class="sxs-lookup"><span data-stu-id="68fda-132">Int32</span></span>|  
|<span data-ttu-id="68fda-133">LANG</span><span class="sxs-lookup"><span data-stu-id="68fda-133">LANG</span></span>|<span data-ttu-id="68fda-134">String</span><span class="sxs-lookup"><span data-stu-id="68fda-134">String</span></span>|  
|<span data-ttu-id="68fda-135">NUMC</span><span class="sxs-lookup"><span data-stu-id="68fda-135">NUMC</span></span>|<span data-ttu-id="68fda-136">-Int32，如果字段长度小于或等于为 9</span><span class="sxs-lookup"><span data-stu-id="68fda-136">-   Int32, if field length less than or equal to 9</span></span><br /><span data-ttu-id="68fda-137">-Int64，如果字段长度大于 9 且小于或等于 19</span><span class="sxs-lookup"><span data-stu-id="68fda-137">-   Int64, if field length greater than 9 and less than or equal to 19</span></span><br /><span data-ttu-id="68fda-138">-如果字符串大于 19</span><span class="sxs-lookup"><span data-stu-id="68fda-138">-   String, if greater than 19</span></span><br /><span data-ttu-id="68fda-139">-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="68fda-139">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="68fda-140">PREC</span><span class="sxs-lookup"><span data-stu-id="68fda-140">PREC</span></span>|<span data-ttu-id="68fda-141">Int16</span><span class="sxs-lookup"><span data-stu-id="68fda-141">Int16</span></span>|  
|<span data-ttu-id="68fda-142">QUAN</span><span class="sxs-lookup"><span data-stu-id="68fda-142">QUAN</span></span>|<span data-ttu-id="68fda-143">Decimal</span><span class="sxs-lookup"><span data-stu-id="68fda-143">Decimal</span></span>|  
|<span data-ttu-id="68fda-144">RAW</span><span class="sxs-lookup"><span data-stu-id="68fda-144">RAW</span></span>|<span data-ttu-id="68fda-145">Byte]</span><span class="sxs-lookup"><span data-stu-id="68fda-145">Byte []</span></span>|  
|<span data-ttu-id="68fda-146">RSTR</span><span class="sxs-lookup"><span data-stu-id="68fda-146">RSTR</span></span>|<span data-ttu-id="68fda-147">Byte]</span><span class="sxs-lookup"><span data-stu-id="68fda-147">Byte []</span></span>|  
|<span data-ttu-id="68fda-148">SSTR</span><span class="sxs-lookup"><span data-stu-id="68fda-148">SSTR</span></span>|<span data-ttu-id="68fda-149">String</span><span class="sxs-lookup"><span data-stu-id="68fda-149">String</span></span>|  
|<span data-ttu-id="68fda-150">STRG</span><span class="sxs-lookup"><span data-stu-id="68fda-150">STRG</span></span>|<span data-ttu-id="68fda-151">String</span><span class="sxs-lookup"><span data-stu-id="68fda-151">String</span></span>|  
|<span data-ttu-id="68fda-152">TIMS</span><span class="sxs-lookup"><span data-stu-id="68fda-152">TIMS</span></span>|<span data-ttu-id="68fda-153">-   TimeSpan</span><span class="sxs-lookup"><span data-stu-id="68fda-153">-   TimeSpan</span></span><br /><span data-ttu-id="68fda-154">-字符串，如果**disabledatavalidation**在 SELECT 或 EXEC 语句中设置选项。</span><span class="sxs-lookup"><span data-stu-id="68fda-154">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="68fda-155">UNIT</span><span class="sxs-lookup"><span data-stu-id="68fda-155">UNIT</span></span>|<span data-ttu-id="68fda-156">String</span><span class="sxs-lookup"><span data-stu-id="68fda-156">String</span></span>|  
|<span data-ttu-id="68fda-157">LCHR</span><span class="sxs-lookup"><span data-stu-id="68fda-157">LCHR</span></span>|<span data-ttu-id="68fda-158">String</span><span class="sxs-lookup"><span data-stu-id="68fda-158">String</span></span>|  
|<span data-ttu-id="68fda-159">LRAW</span><span class="sxs-lookup"><span data-stu-id="68fda-159">LRAW</span></span>|<span data-ttu-id="68fda-160">Byte]</span><span class="sxs-lookup"><span data-stu-id="68fda-160">Byte []</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68fda-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="68fda-161">See Also</span></span>  
 [<span data-ttu-id="68fda-162">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="68fda-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)