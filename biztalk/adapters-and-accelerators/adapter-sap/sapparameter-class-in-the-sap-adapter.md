---
title: SAP 适配器 SAPParameter 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f87932d7add9723d67e0af822a8d6f389b59fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372945"
---
# <a name="sapparameter-class-in-the-sap-adapter"></a><span data-ttu-id="3793c-102">SAP 适配器 SAPParameter 类</span><span class="sxs-lookup"><span data-stu-id="3793c-102">SAPParameter class in the SAP adapter</span></span>
<span data-ttu-id="3793c-103">以下部分列出的方法和属性**SAPParameter**类。</span><span class="sxs-lookup"><span data-stu-id="3793c-103">The following section lists the methods and properties for the **SAPParameter** class.</span></span> <span data-ttu-id="3793c-104">这派生自**System.Data.Common.DbParameter**。</span><span class="sxs-lookup"><span data-stu-id="3793c-104">This is derived from **System.Data.Common.DbParameter**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="3793c-105">支持的属性</span><span class="sxs-lookup"><span data-stu-id="3793c-105">Supported Properties</span></span>  
  
|<span data-ttu-id="3793c-106">“属性”</span><span class="sxs-lookup"><span data-stu-id="3793c-106">Name</span></span>|<span data-ttu-id="3793c-107">获取/设置</span><span class="sxs-lookup"><span data-stu-id="3793c-107">Get/Set</span></span>|<span data-ttu-id="3793c-108">Description</span><span class="sxs-lookup"><span data-stu-id="3793c-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="3793c-109">**DbType**</span><span class="sxs-lookup"><span data-stu-id="3793c-109">**DbType**</span></span>|<span data-ttu-id="3793c-110">获取</span><span class="sxs-lookup"><span data-stu-id="3793c-110">Get</span></span>|<span data-ttu-id="3793c-111">如果返回参数的 DbType。</span><span class="sxs-lookup"><span data-stu-id="3793c-111">DbType if the parameter returned.</span></span> <span data-ttu-id="3793c-112">无法设置。</span><span class="sxs-lookup"><span data-stu-id="3793c-112">Cannot be set.</span></span>|  
|<span data-ttu-id="3793c-113">**方向**</span><span class="sxs-lookup"><span data-stu-id="3793c-113">**Direction**</span></span>|<span data-ttu-id="3793c-114">获取和设置</span><span class="sxs-lookup"><span data-stu-id="3793c-114">Get and Set</span></span>|<span data-ttu-id="3793c-115">ParameterDirection.ReturnValue 不受支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-115">ParameterDirection.ReturnValue not supported.</span></span>|  
|<span data-ttu-id="3793c-116">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="3793c-116">**IsNullable**</span></span>|-|<span data-ttu-id="3793c-117">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-117">Not supported.</span></span>|  
|<span data-ttu-id="3793c-118">**ParameterName**</span><span class="sxs-lookup"><span data-stu-id="3793c-118">**ParameterName**</span></span>|<span data-ttu-id="3793c-119">获取和设置</span><span class="sxs-lookup"><span data-stu-id="3793c-119">Get and Set</span></span>|<span data-ttu-id="3793c-120">参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3793c-120">Name of the parameter.</span></span>|  
|<span data-ttu-id="3793c-121">**大小**</span><span class="sxs-lookup"><span data-stu-id="3793c-121">**Size**</span></span>|-|<span data-ttu-id="3793c-122">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-122">Not supported.</span></span>|  
|<span data-ttu-id="3793c-123">**SourceColumn**</span><span class="sxs-lookup"><span data-stu-id="3793c-123">**SourceColumn**</span></span>|-|<span data-ttu-id="3793c-124">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-124">Not supported.</span></span>|  
|<span data-ttu-id="3793c-125">**SourceColumnNullMapping**</span><span class="sxs-lookup"><span data-stu-id="3793c-125">**SourceColumnNullMapping**</span></span>|-|<span data-ttu-id="3793c-126">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-126">Not supported.</span></span>|  
|<span data-ttu-id="3793c-127">**SourceVersion**</span><span class="sxs-lookup"><span data-stu-id="3793c-127">**SourceVersion**</span></span>|-|<span data-ttu-id="3793c-128">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-128">Not supported.</span></span>|  
|<span data-ttu-id="3793c-129">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3793c-129">**Value**</span></span>|<span data-ttu-id="3793c-130">获取和设置</span><span class="sxs-lookup"><span data-stu-id="3793c-130">Get and Set</span></span>|<span data-ttu-id="3793c-131">参数的值</span><span class="sxs-lookup"><span data-stu-id="3793c-131">Value of the parameter</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="3793c-132">受支持的方法</span><span class="sxs-lookup"><span data-stu-id="3793c-132">Supported Methods</span></span>  
  
|<span data-ttu-id="3793c-133">“属性”</span><span class="sxs-lookup"><span data-stu-id="3793c-133">Name</span></span>|<span data-ttu-id="3793c-134">Description</span><span class="sxs-lookup"><span data-stu-id="3793c-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3793c-135">**ResetDbType()**</span><span class="sxs-lookup"><span data-stu-id="3793c-135">**ResetDbType()**</span></span>|<span data-ttu-id="3793c-136">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3793c-136">Not supported.</span></span>|  
  
## <a name="supported-constructors"></a><span data-ttu-id="3793c-137">受支持的构造函数</span><span class="sxs-lookup"><span data-stu-id="3793c-137">Supported Constructors</span></span>  
  
|<span data-ttu-id="3793c-138">“属性”</span><span class="sxs-lookup"><span data-stu-id="3793c-138">Name</span></span>|<span data-ttu-id="3793c-139">Description</span><span class="sxs-lookup"><span data-stu-id="3793c-139">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3793c-140">**SAPParameter()**</span><span class="sxs-lookup"><span data-stu-id="3793c-140">**SAPParameter()**</span></span>|<span data-ttu-id="3793c-141">参数的 SAP 实例。</span><span class="sxs-lookup"><span data-stu-id="3793c-141">SAP parameter instance.</span></span>|  
|<span data-ttu-id="3793c-142">**SAPParameter(string)**</span><span class="sxs-lookup"><span data-stu-id="3793c-142">**SAPParameter(string)**</span></span>|<span data-ttu-id="3793c-143">SAP 与 SAP 的参数名的参数。</span><span class="sxs-lookup"><span data-stu-id="3793c-143">SAP parameter with SAP parameter name.</span></span>|  
|<span data-ttu-id="3793c-144">**SAPParameter(string, DbType)**</span><span class="sxs-lookup"><span data-stu-id="3793c-144">**SAPParameter(string, DbType)**</span></span>|<span data-ttu-id="3793c-145">使用 SAP 参数名称和 DbType SAP 参数。</span><span class="sxs-lookup"><span data-stu-id="3793c-145">SAP parameter with SAP parameter name and DbType.</span></span>|  
|<span data-ttu-id="3793c-146">**SAPParameter(string, object)**</span><span class="sxs-lookup"><span data-stu-id="3793c-146">**SAPParameter(string, object)**</span></span>|<span data-ttu-id="3793c-147">SAP 使用 SAP 参数名称和值的参数。</span><span class="sxs-lookup"><span data-stu-id="3793c-147">SAP parameter with SAP parameter name and value.</span></span> <span data-ttu-id="3793c-148">复杂类型具有 DataTable 类型的值和 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="3793c-148">Complex types have value of type DataTable and XML string.</span></span>|  
|<span data-ttu-id="3793c-149">**SAPParameter(string, ParameterDirection)**</span><span class="sxs-lookup"><span data-stu-id="3793c-149">**SAPParameter(string, ParameterDirection)**</span></span>|<span data-ttu-id="3793c-150">SAP 具有 SAP 参数名称和参数方向的参数。</span><span class="sxs-lookup"><span data-stu-id="3793c-150">SAP parameter with SAP parameter name and parameter direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3793c-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3793c-151">See Also</span></span>  
 [<span data-ttu-id="3793c-152">扩展 ADO.NET 接口，与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="3793c-152">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)