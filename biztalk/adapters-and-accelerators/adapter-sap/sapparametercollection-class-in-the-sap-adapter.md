---
title: SAP 适配器 SAPParameterCollection 类 |Microsoft Docs
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
ms.openlocfilehash: c94dc7e8219a2439d58fbfea78fc7fe9c42b64bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372920"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a><span data-ttu-id="d4bd7-102">SAP 适配器 SAPParameterCollection 类</span><span class="sxs-lookup"><span data-stu-id="d4bd7-102">SAPParameterCollection class in the SAP adapter</span></span>
<span data-ttu-id="d4bd7-103">以下部分列出的方法和属性**SAPParameterCollection**类。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-103">The following section lists the methods and properties for the **SAPParameterCollection** class.</span></span> <span data-ttu-id="d4bd7-104">这派生自**System.Data.Common.DbParameterCollection**。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-104">This is derived from **System.Data.Common.DbParameterCollection**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="d4bd7-105">支持的属性</span><span class="sxs-lookup"><span data-stu-id="d4bd7-105">Supported Properties</span></span>  
  
|<span data-ttu-id="d4bd7-106">“属性”</span><span class="sxs-lookup"><span data-stu-id="d4bd7-106">Name</span></span>|<span data-ttu-id="d4bd7-107">获取/设置</span><span class="sxs-lookup"><span data-stu-id="d4bd7-107">Get/Set</span></span>|<span data-ttu-id="d4bd7-108">Description</span><span class="sxs-lookup"><span data-stu-id="d4bd7-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="d4bd7-109">**Count**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-109">**Count**</span></span>|<span data-ttu-id="d4bd7-110">获取</span><span class="sxs-lookup"><span data-stu-id="d4bd7-110">Get</span></span>|<span data-ttu-id="d4bd7-111">集合中的参数数目。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-111">Number of parameters in the collection.</span></span>|  
|<span data-ttu-id="d4bd7-112">**IsFixedSize**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-112">**IsFixedSize**</span></span>|<span data-ttu-id="d4bd7-113">获取</span><span class="sxs-lookup"><span data-stu-id="d4bd7-113">Get</span></span>|<span data-ttu-id="d4bd7-114">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-114">Not supported.</span></span> <span data-ttu-id="d4bd7-115">返回 false。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-115">Returns false.</span></span>|  
|<span data-ttu-id="d4bd7-116">**IsReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-116">**IsReadOnly**</span></span>|<span data-ttu-id="d4bd7-117">获取</span><span class="sxs-lookup"><span data-stu-id="d4bd7-117">Get</span></span>|<span data-ttu-id="d4bd7-118">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-118">Not supported.</span></span> <span data-ttu-id="d4bd7-119">返回 false。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-119">Returns false.</span></span>|  
|<span data-ttu-id="d4bd7-120">**IsSynchronized**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-120">**IsSynchronized**</span></span>|<span data-ttu-id="d4bd7-121">获取</span><span class="sxs-lookup"><span data-stu-id="d4bd7-121">Get</span></span>|<span data-ttu-id="d4bd7-122">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-122">Not supported.</span></span> <span data-ttu-id="d4bd7-123">返回 false。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-123">Returns false.</span></span>|  
|<span data-ttu-id="d4bd7-124">**SyncRoot**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-124">**SyncRoot**</span></span>|<span data-ttu-id="d4bd7-125">获取</span><span class="sxs-lookup"><span data-stu-id="d4bd7-125">Get</span></span>|<span data-ttu-id="d4bd7-126">返回的锁对象。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-126">Returns the lock object.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="d4bd7-127">受支持的方法</span><span class="sxs-lookup"><span data-stu-id="d4bd7-127">Supported Methods</span></span>  
  
|<span data-ttu-id="d4bd7-128">“属性”</span><span class="sxs-lookup"><span data-stu-id="d4bd7-128">Name</span></span>|<span data-ttu-id="d4bd7-129">Description</span><span class="sxs-lookup"><span data-stu-id="d4bd7-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d4bd7-130">**Add(SAPParameter)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-130">**Add(SAPParameter)**</span></span>|<span data-ttu-id="d4bd7-131">参数不能属于多个 ParameterCollection。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-131">Parameter cannot belong to more than one ParameterCollection.</span></span>|  
|<span data-ttu-id="d4bd7-132">**Add(object)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-132">**Add(object)**</span></span>|<span data-ttu-id="d4bd7-133">SAPParameter 类型应为对象。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-133">Object should be of SAPParameter type.</span></span>|  
|<span data-ttu-id="d4bd7-134">**AddRange(System.Array)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-134">**AddRange(System.Array)**</span></span>|<span data-ttu-id="d4bd7-135">将添加 SAPParameter 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-135">Adds an array of SAPParameter instances.</span></span>|  
|<span data-ttu-id="d4bd7-136">**Clear()**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-136">**Clear()**</span></span>|<span data-ttu-id="d4bd7-137">清除集合中的参数。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-137">Clears the parameters in the collection.</span></span>|  
|<span data-ttu-id="d4bd7-138">**Contains(object)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-138">**Contains(object)**</span></span>|<span data-ttu-id="d4bd7-139">基于参数实例的检查。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-139">Checks based on parameter instance.</span></span>|  
|<span data-ttu-id="d4bd7-140">**Contains(string)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-140">**Contains(string)**</span></span>|<span data-ttu-id="d4bd7-141">检查基于参数名称。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-141">Checks based on parameter name.</span></span>|  
|<span data-ttu-id="d4bd7-142">**CopyTo(SAPParameter[], int)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-142">**CopyTo(SAPParameter[], int)**</span></span>|<span data-ttu-id="d4bd7-143">副本到 SAPParameter 类型的数组的参数列表。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-143">Copies parameter list to an array of SAPParameter types.</span></span>|  
|<span data-ttu-id="d4bd7-144">**CopyTo(System.Array, int)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-144">**CopyTo(System.Array, int)**</span></span>|<span data-ttu-id="d4bd7-145">复制到一个数组的参数列表。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-145">Copies parameter list to an array.</span></span>|  
|<span data-ttu-id="d4bd7-146">**GetEnumerator()**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-146">**GetEnumerator()**</span></span>|<span data-ttu-id="d4bd7-147">获取一个枚举器的参数集合中。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-147">Gets an enumerator for the parameters in the collection.</span></span>|  
|<span data-ttu-id="d4bd7-148">**IndexOf(object)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-148">**IndexOf(object)**</span></span>|<span data-ttu-id="d4bd7-149">基于 SAPParameter 实例的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-149">Index of parameter based on SAPParameter instance.</span></span>|  
|<span data-ttu-id="d4bd7-150">**IndexOf(string)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-150">**IndexOf(string)**</span></span>|<span data-ttu-id="d4bd7-151">基于 SAPParameter 名称的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-151">Index of parameter based on SAPParameter name.</span></span>|  
|<span data-ttu-id="d4bd7-152">**Insert(int, object)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-152">**Insert(int, object)**</span></span>|<span data-ttu-id="d4bd7-153">将 SAPParameter 插入到集合。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-153">Inserts an SAPParameter into the collection.</span></span>|  
|<span data-ttu-id="d4bd7-154">**Remove(object)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-154">**Remove(object)**</span></span>|<span data-ttu-id="d4bd7-155">为基于实例的集合中移除 SAPParameter。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-155">Removes an SAPParameter into the collection based on instance.</span></span>|  
|<span data-ttu-id="d4bd7-156">**RemoveAt(int)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-156">**RemoveAt(int)**</span></span>|<span data-ttu-id="d4bd7-157">集合中给定索引处移除 SAPParameter。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-157">Removes an SAPParameter into the collection at a given index.</span></span>|  
|<span data-ttu-id="d4bd7-158">**RemoveAt(string)**</span><span class="sxs-lookup"><span data-stu-id="d4bd7-158">**RemoveAt(string)**</span></span>|<span data-ttu-id="d4bd7-159">删除 SAPParameter 到基于名称的集合。</span><span class="sxs-lookup"><span data-stu-id="d4bd7-159">Removes an SAPParameter into the collection based on name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4bd7-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4bd7-160">See Also</span></span>  
 [<span data-ttu-id="d4bd7-161">扩展 ADO.NET 接口，与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="d4bd7-161">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)