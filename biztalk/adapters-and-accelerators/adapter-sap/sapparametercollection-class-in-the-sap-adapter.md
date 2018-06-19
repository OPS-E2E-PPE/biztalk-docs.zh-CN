---
title: SAP 适配器中的 SAPParameterCollection 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218037"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a><span data-ttu-id="641db-102">SAP 适配器中 SAPParameterCollection 类</span><span class="sxs-lookup"><span data-stu-id="641db-102">SAPParameterCollection class in the SAP adapter</span></span>
<span data-ttu-id="641db-103">以下部分列出的方法和属性**SAPParameterCollection**类。</span><span class="sxs-lookup"><span data-stu-id="641db-103">The following section lists the methods and properties for the **SAPParameterCollection** class.</span></span> <span data-ttu-id="641db-104">该项派生自**System.Data.Common.DbParameterCollection**。</span><span class="sxs-lookup"><span data-stu-id="641db-104">This is derived from **System.Data.Common.DbParameterCollection**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="641db-105">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="641db-105">Supported Properties</span></span>  
  
|<span data-ttu-id="641db-106">Name</span><span class="sxs-lookup"><span data-stu-id="641db-106">Name</span></span>|<span data-ttu-id="641db-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="641db-107">Get/Set</span></span>|<span data-ttu-id="641db-108">Description</span><span class="sxs-lookup"><span data-stu-id="641db-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="641db-109">**Count**</span><span class="sxs-lookup"><span data-stu-id="641db-109">**Count**</span></span>|<span data-ttu-id="641db-110">获取</span><span class="sxs-lookup"><span data-stu-id="641db-110">Get</span></span>|<span data-ttu-id="641db-111">集合中的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="641db-111">Number of parameters in the collection.</span></span>|  
|<span data-ttu-id="641db-112">**IsFixedSize**</span><span class="sxs-lookup"><span data-stu-id="641db-112">**IsFixedSize**</span></span>|<span data-ttu-id="641db-113">获取</span><span class="sxs-lookup"><span data-stu-id="641db-113">Get</span></span>|<span data-ttu-id="641db-114">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="641db-114">Not supported.</span></span> <span data-ttu-id="641db-115">返回 false。</span><span class="sxs-lookup"><span data-stu-id="641db-115">Returns false.</span></span>|  
|<span data-ttu-id="641db-116">**IsReadOnly**</span><span class="sxs-lookup"><span data-stu-id="641db-116">**IsReadOnly**</span></span>|<span data-ttu-id="641db-117">获取</span><span class="sxs-lookup"><span data-stu-id="641db-117">Get</span></span>|<span data-ttu-id="641db-118">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="641db-118">Not supported.</span></span> <span data-ttu-id="641db-119">返回 false。</span><span class="sxs-lookup"><span data-stu-id="641db-119">Returns false.</span></span>|  
|<span data-ttu-id="641db-120">**IsSynchronized**</span><span class="sxs-lookup"><span data-stu-id="641db-120">**IsSynchronized**</span></span>|<span data-ttu-id="641db-121">获取</span><span class="sxs-lookup"><span data-stu-id="641db-121">Get</span></span>|<span data-ttu-id="641db-122">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="641db-122">Not supported.</span></span> <span data-ttu-id="641db-123">返回 false。</span><span class="sxs-lookup"><span data-stu-id="641db-123">Returns false.</span></span>|  
|<span data-ttu-id="641db-124">**SyncRoot**</span><span class="sxs-lookup"><span data-stu-id="641db-124">**SyncRoot**</span></span>|<span data-ttu-id="641db-125">获取</span><span class="sxs-lookup"><span data-stu-id="641db-125">Get</span></span>|<span data-ttu-id="641db-126">返回的锁对象。</span><span class="sxs-lookup"><span data-stu-id="641db-126">Returns the lock object.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="641db-127">支持的方法</span><span class="sxs-lookup"><span data-stu-id="641db-127">Supported Methods</span></span>  
  
|<span data-ttu-id="641db-128">Name</span><span class="sxs-lookup"><span data-stu-id="641db-128">Name</span></span>|<span data-ttu-id="641db-129">Description</span><span class="sxs-lookup"><span data-stu-id="641db-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="641db-130">**Add(SAPParameter)**</span><span class="sxs-lookup"><span data-stu-id="641db-130">**Add(SAPParameter)**</span></span>|<span data-ttu-id="641db-131">参数不能属于多个 ParameterCollection。</span><span class="sxs-lookup"><span data-stu-id="641db-131">Parameter cannot belong to more than one ParameterCollection.</span></span>|  
|<span data-ttu-id="641db-132">**Add(object)**</span><span class="sxs-lookup"><span data-stu-id="641db-132">**Add(object)**</span></span>|<span data-ttu-id="641db-133">SAPParameter 类型应为对象。</span><span class="sxs-lookup"><span data-stu-id="641db-133">Object should be of SAPParameter type.</span></span>|  
|<span data-ttu-id="641db-134">**AddRange(System.Array)**</span><span class="sxs-lookup"><span data-stu-id="641db-134">**AddRange(System.Array)**</span></span>|<span data-ttu-id="641db-135">将添加 SAPParameter 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="641db-135">Adds an array of SAPParameter instances.</span></span>|  
|<span data-ttu-id="641db-136">**Clear （)**</span><span class="sxs-lookup"><span data-stu-id="641db-136">**Clear()**</span></span>|<span data-ttu-id="641db-137">清除集合中的参数。</span><span class="sxs-lookup"><span data-stu-id="641db-137">Clears the parameters in the collection.</span></span>|  
|<span data-ttu-id="641db-138">**Contains(object)**</span><span class="sxs-lookup"><span data-stu-id="641db-138">**Contains(object)**</span></span>|<span data-ttu-id="641db-139">基于参数实例的检查。</span><span class="sxs-lookup"><span data-stu-id="641db-139">Checks based on parameter instance.</span></span>|  
|<span data-ttu-id="641db-140">**Contains(string)**</span><span class="sxs-lookup"><span data-stu-id="641db-140">**Contains(string)**</span></span>|<span data-ttu-id="641db-141">检查基于参数名称。</span><span class="sxs-lookup"><span data-stu-id="641db-141">Checks based on parameter name.</span></span>|  
|<span data-ttu-id="641db-142">**CopyTo （SAPParameter []，int）**</span><span class="sxs-lookup"><span data-stu-id="641db-142">**CopyTo(SAPParameter[], int)**</span></span>|<span data-ttu-id="641db-143">到 SAPParameter 类型数组的副本参数列表。</span><span class="sxs-lookup"><span data-stu-id="641db-143">Copies parameter list to an array of SAPParameter types.</span></span>|  
|<span data-ttu-id="641db-144">**CopyTo (System.Array，int)**</span><span class="sxs-lookup"><span data-stu-id="641db-144">**CopyTo(System.Array, int)**</span></span>|<span data-ttu-id="641db-145">指向数组的副本参数列表。</span><span class="sxs-lookup"><span data-stu-id="641db-145">Copies parameter list to an array.</span></span>|  
|<span data-ttu-id="641db-146">**GetEnumerator()**</span><span class="sxs-lookup"><span data-stu-id="641db-146">**GetEnumerator()**</span></span>|<span data-ttu-id="641db-147">集合中获取参数的枚举数。</span><span class="sxs-lookup"><span data-stu-id="641db-147">Gets an enumerator for the parameters in the collection.</span></span>|  
|<span data-ttu-id="641db-148">**IndexOf(object)**</span><span class="sxs-lookup"><span data-stu-id="641db-148">**IndexOf(object)**</span></span>|<span data-ttu-id="641db-149">基于 SAPParameter 实例的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="641db-149">Index of parameter based on SAPParameter instance.</span></span>|  
|<span data-ttu-id="641db-150">**IndexOf(string)**</span><span class="sxs-lookup"><span data-stu-id="641db-150">**IndexOf(string)**</span></span>|<span data-ttu-id="641db-151">基于 SAPParameter 名称的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="641db-151">Index of parameter based on SAPParameter name.</span></span>|  
|<span data-ttu-id="641db-152">**Insert （int、 对象）**</span><span class="sxs-lookup"><span data-stu-id="641db-152">**Insert(int, object)**</span></span>|<span data-ttu-id="641db-153">将 SAPParameter 插入到集合。</span><span class="sxs-lookup"><span data-stu-id="641db-153">Inserts an SAPParameter into the collection.</span></span>|  
|<span data-ttu-id="641db-154">**Remove(object)**</span><span class="sxs-lookup"><span data-stu-id="641db-154">**Remove(object)**</span></span>|<span data-ttu-id="641db-155">删除 SAPParameter 到基于实例的集合。</span><span class="sxs-lookup"><span data-stu-id="641db-155">Removes an SAPParameter into the collection based on instance.</span></span>|  
|<span data-ttu-id="641db-156">**RemoveAt(int)**</span><span class="sxs-lookup"><span data-stu-id="641db-156">**RemoveAt(int)**</span></span>|<span data-ttu-id="641db-157">删除 SAPParameter 到给定索引处的集合。</span><span class="sxs-lookup"><span data-stu-id="641db-157">Removes an SAPParameter into the collection at a given index.</span></span>|  
|<span data-ttu-id="641db-158">**RemoveAt(string)**</span><span class="sxs-lookup"><span data-stu-id="641db-158">**RemoveAt(string)**</span></span>|<span data-ttu-id="641db-159">删除 SAPParameter 到基于名称的集合。</span><span class="sxs-lookup"><span data-stu-id="641db-159">Removes an SAPParameter into the collection based on name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="641db-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="641db-160">See Also</span></span>  
 [<span data-ttu-id="641db-161">使用 SAP 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="641db-161">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)