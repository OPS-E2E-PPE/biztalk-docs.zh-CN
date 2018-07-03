---
title: Siebel 适配器的 SiebelParameter 类 |Microsoft Docs
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
ms.openlocfilehash: cff2f0f5324dfacd118bc59dccfa524819acaa75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021947"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a><span data-ttu-id="0eeb1-102">Siebel 适配器的 SiebelParameter 类</span><span class="sxs-lookup"><span data-stu-id="0eeb1-102">SiebelParameter class in the Siebel adapter</span></span>
<span data-ttu-id="0eeb1-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供了`DbParameter`实现启用的 ADO.NET 客户端，若要指定特定命令的参数。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbParameter` implementation to enable an ADO.NET client to specify parameters for a particular command.</span></span> <span data-ttu-id="0eeb1-104">使用的实例`System.Data.Common.DbCommand`的类[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，客户端程序可以获取的实例`System.Data.Common.DbParameter`类。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-104">Using an instance of the `System.Data.Common.DbCommand` class of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], a client program can obtain an instance of the `System.Data.Common.DbParameter` class.</span></span>  

```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  

 <span data-ttu-id="0eeb1-105">或者，可以使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="0eeb1-105">Alternatively, the following approach can be used:</span></span>  

```  

//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  

 <span data-ttu-id="0eeb1-106">`SiebelParameter`类继承自`DbParameter`。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-106">The `SiebelParameter` class inherits from `DbParameter`.</span></span>  <span data-ttu-id="0eeb1-107">命名空间中存在`Microsoft.Data.SiebelClient`。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-107">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  

## <a name="supported-properties"></a><span data-ttu-id="0eeb1-108">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="0eeb1-108">Supported Properties</span></span>  
 <span data-ttu-id="0eeb1-109">`SiebelParameter`类支持以下`DbParameter`*公共*属性：</span><span class="sxs-lookup"><span data-stu-id="0eeb1-109">The `SiebelParameter` class supports the following `DbParameter`*public* properties:</span></span>  


|       <span data-ttu-id="0eeb1-110">“属性”</span><span class="sxs-lookup"><span data-stu-id="0eeb1-110">Name</span></span>        |   <span data-ttu-id="0eeb1-111">获取/设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-111">Get/Set</span></span>   |                                                                                                            <span data-ttu-id="0eeb1-112">Description</span><span class="sxs-lookup"><span data-stu-id="0eeb1-112">Description</span></span>                                                                                                            |
|-------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="0eeb1-113">**DbType**</span><span class="sxs-lookup"><span data-stu-id="0eeb1-113">**DbType**</span></span>     | <span data-ttu-id="0eeb1-114">获取和设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-114">Get and Set</span></span> |                                               <span data-ttu-id="0eeb1-115">参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-115">Data type of the parameter.</span></span> <span data-ttu-id="0eeb1-116">请参阅[基本 Siebel 数据类型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-116">See [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>                                               |
|   <span data-ttu-id="0eeb1-117">**方向**</span><span class="sxs-lookup"><span data-stu-id="0eeb1-117">**Direction**</span></span>   | <span data-ttu-id="0eeb1-118">获取和设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-118">Get and Set</span></span> | <span data-ttu-id="0eeb1-119">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="0eeb1-119">The following values are supported:</span></span><br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput` |
|  <span data-ttu-id="0eeb1-120">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="0eeb1-120">**IsNullable**</span></span>   | <span data-ttu-id="0eeb1-121">获取和设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-121">Get and Set</span></span> |                                                                               <span data-ttu-id="0eeb1-122">该属性不受支持，并将引发异常，如果调用。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-122">The property is not supported, and will throw an exception if called.</span></span>                                                                               |
| <span data-ttu-id="0eeb1-123">**参数名**</span><span class="sxs-lookup"><span data-stu-id="0eeb1-123">**ParameterName**</span></span> | <span data-ttu-id="0eeb1-124">获取和设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-124">Get and Set</span></span> |                                  <span data-ttu-id="0eeb1-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持此属性对于 ADO.NET 客户端指定的参数名称。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports this property for an ADO.NET client to specify the parameter name.</span></span>                                  |
|     <span data-ttu-id="0eeb1-126">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="0eeb1-126">**Value**</span></span>     | <span data-ttu-id="0eeb1-127">获取和设置</span><span class="sxs-lookup"><span data-stu-id="0eeb1-127">Get and Set</span></span> |                                                    <span data-ttu-id="0eeb1-128">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]表示以字符串形式的参数值。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-128">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] represents parameter values as strings.</span></span>                                                    |

###  <a name="BKMK_Datatypes"></a> <span data-ttu-id="0eeb1-129">支持的数据类型</span><span class="sxs-lookup"><span data-stu-id="0eeb1-129">Supported Data Types</span></span>  
 <span data-ttu-id="0eeb1-130">下表总结了简单 Siebel 字段类型[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-130">The following table summarizes the simple Siebel field types that [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports.</span></span> <span data-ttu-id="0eeb1-131">有关更详细的覆盖范围，请参阅[基本 Siebel 数据类型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-131">For more detailed coverage, see [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>  

|<span data-ttu-id="0eeb1-132">Siebel 字段类型</span><span class="sxs-lookup"><span data-stu-id="0eeb1-132">Siebel Field Type</span></span>|<span data-ttu-id="0eeb1-133">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="0eeb1-133">.NET Type</span></span>|<span data-ttu-id="0eeb1-134">XML 架构类型</span><span class="sxs-lookup"><span data-stu-id="0eeb1-134">XML Schema Type</span></span>|  
|-----------------------|---------------|---------------------|  
|<span data-ttu-id="0eeb1-135">DTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="0eeb1-135">DTYPE_BOOL</span></span>|<span data-ttu-id="0eeb1-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="0eeb1-136">Boolean</span></span>|<span data-ttu-id="0eeb1-137">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="0eeb1-137">xsd:boolean</span></span>|  
|<span data-ttu-id="0eeb1-138">DTYPE_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="0eeb1-138">DTYPE_CURRENCY</span></span>|<span data-ttu-id="0eeb1-139">Decimal</span><span class="sxs-lookup"><span data-stu-id="0eeb1-139">Decimal</span></span>|<span data-ttu-id="0eeb1-140">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="0eeb1-140">xsd:decimal</span></span>|  
|<span data-ttu-id="0eeb1-141">DTYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="0eeb1-141">DTYPE_DATE</span></span>|<span data-ttu-id="0eeb1-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-142">DateTime</span></span>|<span data-ttu-id="0eeb1-143">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-143">xsd:dateTime</span></span>|  
|<span data-ttu-id="0eeb1-144">DTYPE_DATETIME</span><span class="sxs-lookup"><span data-stu-id="0eeb1-144">DTYPE_DATETIME</span></span>|<span data-ttu-id="0eeb1-145">DateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-145">DateTime</span></span>|<span data-ttu-id="0eeb1-146">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-146">xsd:dateTime</span></span>|  
|<span data-ttu-id="0eeb1-147">DTYPE_ UTCDATETIME</span><span class="sxs-lookup"><span data-stu-id="0eeb1-147">DTYPE_ UTCDATETIME</span></span>|<span data-ttu-id="0eeb1-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-148">DateTime</span></span>|<span data-ttu-id="0eeb1-149">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-149">xsd:dateTime</span></span>|  
|<span data-ttu-id="0eeb1-150">DTYPE_ID</span><span class="sxs-lookup"><span data-stu-id="0eeb1-150">DTYPE_ID</span></span>|<span data-ttu-id="0eeb1-151">String</span><span class="sxs-lookup"><span data-stu-id="0eeb1-151">String</span></span>|<span data-ttu-id="0eeb1-152">xsd:string</span><span class="sxs-lookup"><span data-stu-id="0eeb1-152">xsd:string</span></span>|  
|<span data-ttu-id="0eeb1-153">DTYPE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="0eeb1-153">DTYPE_INTEGER</span></span>|<span data-ttu-id="0eeb1-154">Integer</span><span class="sxs-lookup"><span data-stu-id="0eeb1-154">Integer</span></span>|<span data-ttu-id="0eeb1-155">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0eeb1-155">xsd:int</span></span>|  
|<span data-ttu-id="0eeb1-156">DTYPE_NOTE</span><span class="sxs-lookup"><span data-stu-id="0eeb1-156">DTYPE_NOTE</span></span>|<span data-ttu-id="0eeb1-157">String</span><span class="sxs-lookup"><span data-stu-id="0eeb1-157">String</span></span>|<span data-ttu-id="0eeb1-158">xsd:string</span><span class="sxs-lookup"><span data-stu-id="0eeb1-158">xsd:string</span></span>|  
|<span data-ttu-id="0eeb1-159">DTYPE_NUMBER</span><span class="sxs-lookup"><span data-stu-id="0eeb1-159">DTYPE_NUMBER</span></span>|<span data-ttu-id="0eeb1-160">Decimal</span><span class="sxs-lookup"><span data-stu-id="0eeb1-160">Decimal</span></span>|<span data-ttu-id="0eeb1-161">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="0eeb1-161">xsd:decimal</span></span>|  
|<span data-ttu-id="0eeb1-162">DTYPE_PHONE</span><span class="sxs-lookup"><span data-stu-id="0eeb1-162">DTYPE_PHONE</span></span>|<span data-ttu-id="0eeb1-163">String</span><span class="sxs-lookup"><span data-stu-id="0eeb1-163">String</span></span>|<span data-ttu-id="0eeb1-164">xsd:string</span><span class="sxs-lookup"><span data-stu-id="0eeb1-164">xsd:string</span></span>|  
|<span data-ttu-id="0eeb1-165">DTYPE_TEXT</span><span class="sxs-lookup"><span data-stu-id="0eeb1-165">DTYPE_TEXT</span></span>|<span data-ttu-id="0eeb1-166">String</span><span class="sxs-lookup"><span data-stu-id="0eeb1-166">String</span></span>|<span data-ttu-id="0eeb1-167">xsd:string</span><span class="sxs-lookup"><span data-stu-id="0eeb1-167">xsd:string</span></span>|  
|<span data-ttu-id="0eeb1-168">DTYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="0eeb1-168">DTYPE_TIME</span></span>|<span data-ttu-id="0eeb1-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-169">DateTime</span></span>|<span data-ttu-id="0eeb1-170">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0eeb1-170">xsd:dateTime</span></span>|  

## <a name="supported-methods"></a><span data-ttu-id="0eeb1-171">受支持的方法</span><span class="sxs-lookup"><span data-stu-id="0eeb1-171">Supported Methods</span></span>  
 <span data-ttu-id="0eeb1-172">`SiebelParameter`类不重写中的任何特殊方法`DbParameter`。</span><span class="sxs-lookup"><span data-stu-id="0eeb1-172">The `SiebelParameter` class does not override any special methods in `DbParameter`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0eeb1-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eeb1-173">See Also</span></span>  
 [<span data-ttu-id="0eeb1-174">使用 Siebel 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="0eeb1-174">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)