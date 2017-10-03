---
title: "SAP 适配器中的 SAPParameter 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapparameter-class-in-the-sap-adapter"></a><span data-ttu-id="73d93-102">SAP 适配器中 SAPParameter 类</span><span class="sxs-lookup"><span data-stu-id="73d93-102">SAPParameter class in the SAP adapter</span></span>
<span data-ttu-id="73d93-103">以下部分列出的方法和属性**SAPParameter**类。</span><span class="sxs-lookup"><span data-stu-id="73d93-103">The following section lists the methods and properties for the **SAPParameter** class.</span></span> <span data-ttu-id="73d93-104">该项派生自**System.Data.Common.DbParameter**。</span><span class="sxs-lookup"><span data-stu-id="73d93-104">This is derived from **System.Data.Common.DbParameter**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="73d93-105">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="73d93-105">Supported Properties</span></span>  
  
|<span data-ttu-id="73d93-106">Name</span><span class="sxs-lookup"><span data-stu-id="73d93-106">Name</span></span>|<span data-ttu-id="73d93-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="73d93-107">Get/Set</span></span>|<span data-ttu-id="73d93-108">Description</span><span class="sxs-lookup"><span data-stu-id="73d93-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="73d93-109">**DbType**</span><span class="sxs-lookup"><span data-stu-id="73d93-109">**DbType**</span></span>|<span data-ttu-id="73d93-110">获取</span><span class="sxs-lookup"><span data-stu-id="73d93-110">Get</span></span>|<span data-ttu-id="73d93-111">如果返回参数的 DbType。</span><span class="sxs-lookup"><span data-stu-id="73d93-111">DbType if the parameter returned.</span></span> <span data-ttu-id="73d93-112">无法设置。</span><span class="sxs-lookup"><span data-stu-id="73d93-112">Cannot be set.</span></span>|  
|<span data-ttu-id="73d93-113">**方向**</span><span class="sxs-lookup"><span data-stu-id="73d93-113">**Direction**</span></span>|<span data-ttu-id="73d93-114">获取和设置</span><span class="sxs-lookup"><span data-stu-id="73d93-114">Get and Set</span></span>|<span data-ttu-id="73d93-115">不支持的 ParameterDirection.ReturnValue。</span><span class="sxs-lookup"><span data-stu-id="73d93-115">ParameterDirection.ReturnValue not supported.</span></span>|  
|<span data-ttu-id="73d93-116">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="73d93-116">**IsNullable**</span></span>|-|<span data-ttu-id="73d93-117">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-117">Not supported.</span></span>|  
|<span data-ttu-id="73d93-118">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="73d93-118">**ParameterName**</span></span>|<span data-ttu-id="73d93-119">获取和设置</span><span class="sxs-lookup"><span data-stu-id="73d93-119">Get and Set</span></span>|<span data-ttu-id="73d93-120">参数的名称。</span><span class="sxs-lookup"><span data-stu-id="73d93-120">Name of the parameter.</span></span>|  
|<span data-ttu-id="73d93-121">**Size**</span><span class="sxs-lookup"><span data-stu-id="73d93-121">**Size**</span></span>|-|<span data-ttu-id="73d93-122">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-122">Not supported.</span></span>|  
|<span data-ttu-id="73d93-123">**SourceColumn**</span><span class="sxs-lookup"><span data-stu-id="73d93-123">**SourceColumn**</span></span>|-|<span data-ttu-id="73d93-124">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-124">Not supported.</span></span>|  
|<span data-ttu-id="73d93-125">**SourceColumnNullMapping**</span><span class="sxs-lookup"><span data-stu-id="73d93-125">**SourceColumnNullMapping**</span></span>|-|<span data-ttu-id="73d93-126">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-126">Not supported.</span></span>|  
|<span data-ttu-id="73d93-127">**源版本**</span><span class="sxs-lookup"><span data-stu-id="73d93-127">**SourceVersion**</span></span>|-|<span data-ttu-id="73d93-128">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-128">Not supported.</span></span>|  
|<span data-ttu-id="73d93-129">**值**</span><span class="sxs-lookup"><span data-stu-id="73d93-129">**Value**</span></span>|<span data-ttu-id="73d93-130">获取和设置</span><span class="sxs-lookup"><span data-stu-id="73d93-130">Get and Set</span></span>|<span data-ttu-id="73d93-131">参数值</span><span class="sxs-lookup"><span data-stu-id="73d93-131">Value of the parameter</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="73d93-132">支持的方法</span><span class="sxs-lookup"><span data-stu-id="73d93-132">Supported Methods</span></span>  
  
|<span data-ttu-id="73d93-133">Name</span><span class="sxs-lookup"><span data-stu-id="73d93-133">Name</span></span>|<span data-ttu-id="73d93-134">Description</span><span class="sxs-lookup"><span data-stu-id="73d93-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="73d93-135">**ResetDbType()**</span><span class="sxs-lookup"><span data-stu-id="73d93-135">**ResetDbType()**</span></span>|<span data-ttu-id="73d93-136">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="73d93-136">Not supported.</span></span>|  
  
## <a name="supported-constructors"></a><span data-ttu-id="73d93-137">支持的构造函数</span><span class="sxs-lookup"><span data-stu-id="73d93-137">Supported Constructors</span></span>  
  
|<span data-ttu-id="73d93-138">Name</span><span class="sxs-lookup"><span data-stu-id="73d93-138">Name</span></span>|<span data-ttu-id="73d93-139">Description</span><span class="sxs-lookup"><span data-stu-id="73d93-139">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="73d93-140">**SAPParameter()**</span><span class="sxs-lookup"><span data-stu-id="73d93-140">**SAPParameter()**</span></span>|<span data-ttu-id="73d93-141">SAP 参数实例。</span><span class="sxs-lookup"><span data-stu-id="73d93-141">SAP parameter instance.</span></span>|  
|<span data-ttu-id="73d93-142">**SAPParameter(string)**</span><span class="sxs-lookup"><span data-stu-id="73d93-142">**SAPParameter(string)**</span></span>|<span data-ttu-id="73d93-143">SAP 使用 SAP 参数名称的参数。</span><span class="sxs-lookup"><span data-stu-id="73d93-143">SAP parameter with SAP parameter name.</span></span>|  
|<span data-ttu-id="73d93-144">**SAPParameter (string，DbType)**</span><span class="sxs-lookup"><span data-stu-id="73d93-144">**SAPParameter(string, DbType)**</span></span>|<span data-ttu-id="73d93-145">SAP 参数名称和 DbType SAP 参数。</span><span class="sxs-lookup"><span data-stu-id="73d93-145">SAP parameter with SAP parameter name and DbType.</span></span>|  
|<span data-ttu-id="73d93-146">**SAPParameter （字符串、 对象）**</span><span class="sxs-lookup"><span data-stu-id="73d93-146">**SAPParameter(string, object)**</span></span>|<span data-ttu-id="73d93-147">SAP SAP 参数名称和值的参数。</span><span class="sxs-lookup"><span data-stu-id="73d93-147">SAP parameter with SAP parameter name and value.</span></span> <span data-ttu-id="73d93-148">复杂类型有类型 DataTable 的值和 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="73d93-148">Complex types have value of type DataTable and XML string.</span></span>|  
|<span data-ttu-id="73d93-149">**SAPParameter (string，ParameterDirection)**</span><span class="sxs-lookup"><span data-stu-id="73d93-149">**SAPParameter(string, ParameterDirection)**</span></span>|<span data-ttu-id="73d93-150">与 SAP 参数名称和参数方向的 SAP 参数。</span><span class="sxs-lookup"><span data-stu-id="73d93-150">SAP parameter with SAP parameter name and parameter direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73d93-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73d93-151">See Also</span></span>  
 [<span data-ttu-id="73d93-152">使用 SAP 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="73d93-152">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)