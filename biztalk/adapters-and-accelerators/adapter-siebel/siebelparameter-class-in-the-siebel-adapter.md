---
title: Siebel 适配器中的 SiebelParameter 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27df4b207b23cd04f7d29a2a18ec4ab032836e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222485"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a><span data-ttu-id="a8156-102">Siebel 适配器中 SiebelParameter 类</span><span class="sxs-lookup"><span data-stu-id="a8156-102">SiebelParameter class in the Siebel adapter</span></span>
<span data-ttu-id="a8156-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供`DbParameter`实现，若要启用的 ADO.NET 客户端可以指定特定命令的参数。</span><span class="sxs-lookup"><span data-stu-id="a8156-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbParameter` implementation to enable an ADO.NET client to specify parameters for a particular command.</span></span> <span data-ttu-id="a8156-104">使用的实例`System.Data.Common.DbCommand`类[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，客户端程序可以获取的实例`System.Data.Common.DbParameter`类。</span><span class="sxs-lookup"><span data-stu-id="a8156-104">Using an instance of the `System.Data.Common.DbCommand` class of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], a client program can obtain an instance of the `System.Data.Common.DbParameter` class.</span></span>  
  
```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  
  
 <span data-ttu-id="a8156-105">或者，可以使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="a8156-105">Alternatively, the following approach can be used:</span></span>  
  
```  
  
//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  
  
 <span data-ttu-id="a8156-106">`SiebelParameter`类继承自`DbParameter`。</span><span class="sxs-lookup"><span data-stu-id="a8156-106">The `SiebelParameter` class inherits from `DbParameter`.</span></span>  <span data-ttu-id="a8156-107">命名空间中存在`Microsoft.Data.SiebelClient`。</span><span class="sxs-lookup"><span data-stu-id="a8156-107">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="a8156-108">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="a8156-108">Supported Properties</span></span>  
 <span data-ttu-id="a8156-109">`SiebelParameter`类支持以下`DbParameter`*公共*属性：</span><span class="sxs-lookup"><span data-stu-id="a8156-109">The `SiebelParameter` class supports the following `DbParameter`*public* properties:</span></span>  
  
|<span data-ttu-id="a8156-110">Name</span><span class="sxs-lookup"><span data-stu-id="a8156-110">Name</span></span>|<span data-ttu-id="a8156-111">Get/Set</span><span class="sxs-lookup"><span data-stu-id="a8156-111">Get/Set</span></span>|<span data-ttu-id="a8156-112">Description</span><span class="sxs-lookup"><span data-stu-id="a8156-112">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="a8156-113">**DbType**</span><span class="sxs-lookup"><span data-stu-id="a8156-113">**DbType**</span></span>|<span data-ttu-id="a8156-114">获取和设置</span><span class="sxs-lookup"><span data-stu-id="a8156-114">Get and Set</span></span>|<span data-ttu-id="a8156-115">参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8156-115">Data type of the parameter.</span></span> <span data-ttu-id="a8156-116">请参阅[基本 Siebel 数据类型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a8156-116">See [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>|  
|<span data-ttu-id="a8156-117">**方向**</span><span class="sxs-lookup"><span data-stu-id="a8156-117">**Direction**</span></span>|<span data-ttu-id="a8156-118">获取和设置</span><span class="sxs-lookup"><span data-stu-id="a8156-118">Get and Set</span></span>|<span data-ttu-id="a8156-119">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="a8156-119">The following values are supported:</span></span><br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput`|  
|<span data-ttu-id="a8156-120">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="a8156-120">**IsNullable**</span></span>|<span data-ttu-id="a8156-121">获取和设置</span><span class="sxs-lookup"><span data-stu-id="a8156-121">Get and Set</span></span>|<span data-ttu-id="a8156-122">属性不受支持，并将引发异常，如果调用。</span><span class="sxs-lookup"><span data-stu-id="a8156-122">The property is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="a8156-123">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="a8156-123">**ParameterName**</span></span>|<span data-ttu-id="a8156-124">获取和设置</span><span class="sxs-lookup"><span data-stu-id="a8156-124">Get and Set</span></span>|<span data-ttu-id="a8156-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持此属性对于的 ADO.NET 客户端可以指定参数名称。</span><span class="sxs-lookup"><span data-stu-id="a8156-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports this property for an ADO.NET client to specify the parameter name.</span></span>|  
|<span data-ttu-id="a8156-126">**值**</span><span class="sxs-lookup"><span data-stu-id="a8156-126">**Value**</span></span>|<span data-ttu-id="a8156-127">获取和设置</span><span class="sxs-lookup"><span data-stu-id="a8156-127">Get and Set</span></span>|<span data-ttu-id="a8156-128">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]表示作为字符串的参数值。</span><span class="sxs-lookup"><span data-stu-id="a8156-128">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] represents parameter values as strings.</span></span>|  
  
###  <a name="BKMK_Datatypes"></a><span data-ttu-id="a8156-129">支持的数据类型</span><span class="sxs-lookup"><span data-stu-id="a8156-129">Supported Data Types</span></span>  
 <span data-ttu-id="a8156-130">下表总结了简单 Siebel 字段类型[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="a8156-130">The following table summarizes the simple Siebel field types that [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports.</span></span> <span data-ttu-id="a8156-131">有关更详细说明，请参阅[基本 Siebel 数据类型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a8156-131">For more detailed coverage, see [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>  
  
|<span data-ttu-id="a8156-132">Siebel 字段类型</span><span class="sxs-lookup"><span data-stu-id="a8156-132">Siebel Field Type</span></span>|<span data-ttu-id="a8156-133">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="a8156-133">.NET Type</span></span>|<span data-ttu-id="a8156-134">XML 架构类型</span><span class="sxs-lookup"><span data-stu-id="a8156-134">XML Schema Type</span></span>|  
|-----------------------|---------------|---------------------|  
|<span data-ttu-id="a8156-135">DTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="a8156-135">DTYPE_BOOL</span></span>|<span data-ttu-id="a8156-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="a8156-136">Boolean</span></span>|<span data-ttu-id="a8156-137">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="a8156-137">xsd:boolean</span></span>|  
|<span data-ttu-id="a8156-138">DTYPE_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="a8156-138">DTYPE_CURRENCY</span></span>|<span data-ttu-id="a8156-139">Decimal</span><span class="sxs-lookup"><span data-stu-id="a8156-139">Decimal</span></span>|<span data-ttu-id="a8156-140">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="a8156-140">xsd:decimal</span></span>|  
|<span data-ttu-id="a8156-141">DTYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="a8156-141">DTYPE_DATE</span></span>|<span data-ttu-id="a8156-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-142">DateTime</span></span>|<span data-ttu-id="a8156-143">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-143">xsd:dateTime</span></span>|  
|<span data-ttu-id="a8156-144">DTYPE_DATETIME</span><span class="sxs-lookup"><span data-stu-id="a8156-144">DTYPE_DATETIME</span></span>|<span data-ttu-id="a8156-145">DateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-145">DateTime</span></span>|<span data-ttu-id="a8156-146">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-146">xsd:dateTime</span></span>|  
|<span data-ttu-id="a8156-147">DTYPE_ UTCDATETIME</span><span class="sxs-lookup"><span data-stu-id="a8156-147">DTYPE_ UTCDATETIME</span></span>|<span data-ttu-id="a8156-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-148">DateTime</span></span>|<span data-ttu-id="a8156-149">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-149">xsd:dateTime</span></span>|  
|<span data-ttu-id="a8156-150">DTYPE_ID</span><span class="sxs-lookup"><span data-stu-id="a8156-150">DTYPE_ID</span></span>|<span data-ttu-id="a8156-151">字符串</span><span class="sxs-lookup"><span data-stu-id="a8156-151">String</span></span>|<span data-ttu-id="a8156-152">xsd:string</span><span class="sxs-lookup"><span data-stu-id="a8156-152">xsd:string</span></span>|  
|<span data-ttu-id="a8156-153">DTYPE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="a8156-153">DTYPE_INTEGER</span></span>|<span data-ttu-id="a8156-154">Integer</span><span class="sxs-lookup"><span data-stu-id="a8156-154">Integer</span></span>|<span data-ttu-id="a8156-155">xsd:int</span><span class="sxs-lookup"><span data-stu-id="a8156-155">xsd:int</span></span>|  
|<span data-ttu-id="a8156-156">DTYPE_NOTE</span><span class="sxs-lookup"><span data-stu-id="a8156-156">DTYPE_NOTE</span></span>|<span data-ttu-id="a8156-157">字符串</span><span class="sxs-lookup"><span data-stu-id="a8156-157">String</span></span>|<span data-ttu-id="a8156-158">xsd:string</span><span class="sxs-lookup"><span data-stu-id="a8156-158">xsd:string</span></span>|  
|<span data-ttu-id="a8156-159">DTYPE_NUMBER</span><span class="sxs-lookup"><span data-stu-id="a8156-159">DTYPE_NUMBER</span></span>|<span data-ttu-id="a8156-160">Decimal</span><span class="sxs-lookup"><span data-stu-id="a8156-160">Decimal</span></span>|<span data-ttu-id="a8156-161">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="a8156-161">xsd:decimal</span></span>|  
|<span data-ttu-id="a8156-162">DTYPE_PHONE</span><span class="sxs-lookup"><span data-stu-id="a8156-162">DTYPE_PHONE</span></span>|<span data-ttu-id="a8156-163">字符串</span><span class="sxs-lookup"><span data-stu-id="a8156-163">String</span></span>|<span data-ttu-id="a8156-164">xsd:string</span><span class="sxs-lookup"><span data-stu-id="a8156-164">xsd:string</span></span>|  
|<span data-ttu-id="a8156-165">DTYPE_TEXT</span><span class="sxs-lookup"><span data-stu-id="a8156-165">DTYPE_TEXT</span></span>|<span data-ttu-id="a8156-166">字符串</span><span class="sxs-lookup"><span data-stu-id="a8156-166">String</span></span>|<span data-ttu-id="a8156-167">xsd:string</span><span class="sxs-lookup"><span data-stu-id="a8156-167">xsd:string</span></span>|  
|<span data-ttu-id="a8156-168">DTYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="a8156-168">DTYPE_TIME</span></span>|<span data-ttu-id="a8156-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-169">DateTime</span></span>|<span data-ttu-id="a8156-170">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="a8156-170">xsd:dateTime</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="a8156-171">支持的方法</span><span class="sxs-lookup"><span data-stu-id="a8156-171">Supported Methods</span></span>  
 <span data-ttu-id="a8156-172">`SiebelParameter`类不重写中的任何特殊方法`DbParameter`。</span><span class="sxs-lookup"><span data-stu-id="a8156-172">The `SiebelParameter` class does not override any special methods in `DbParameter`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8156-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8156-173">See Also</span></span>  
 [<span data-ttu-id="a8156-174">扩展 Siebel 适配器 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="a8156-174">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)