---
title: "SAP 适配器中的 SAPDataReader 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="ca774-102">SAP 适配器中 SAPDataReader 类</span><span class="sxs-lookup"><span data-stu-id="ca774-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="ca774-103">以下部分列出的方法和属性**SAPDataReader**类。</span><span class="sxs-lookup"><span data-stu-id="ca774-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="ca774-104">该项派生自**System.Data.Common.DbDataReader**。</span><span class="sxs-lookup"><span data-stu-id="ca774-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="ca774-105">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="ca774-105">Supported Properties</span></span>  
  
|<span data-ttu-id="ca774-106">Name</span><span class="sxs-lookup"><span data-stu-id="ca774-106">Name</span></span>|<span data-ttu-id="ca774-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="ca774-107">Get/Set</span></span>|<span data-ttu-id="ca774-108">Description</span><span class="sxs-lookup"><span data-stu-id="ca774-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="ca774-109">**深度**</span><span class="sxs-lookup"><span data-stu-id="ca774-109">**Depth**</span></span>|<span data-ttu-id="ca774-110">获取</span><span class="sxs-lookup"><span data-stu-id="ca774-110">Get</span></span>|<span data-ttu-id="ca774-111">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="ca774-111">Not supported.</span></span> <span data-ttu-id="ca774-112">返回 0。</span><span class="sxs-lookup"><span data-stu-id="ca774-112">Returns 0.</span></span>|  
|<span data-ttu-id="ca774-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="ca774-113">**FieldCount**</span></span>|<span data-ttu-id="ca774-114">获取</span><span class="sxs-lookup"><span data-stu-id="ca774-114">Get</span></span>|<span data-ttu-id="ca774-115">中的当前记录集的字段数</span><span class="sxs-lookup"><span data-stu-id="ca774-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="ca774-116">**关闭**</span><span class="sxs-lookup"><span data-stu-id="ca774-116">**IsClosed**</span></span>|<span data-ttu-id="ca774-117">获取</span><span class="sxs-lookup"><span data-stu-id="ca774-117">Get</span></span>|<span data-ttu-id="ca774-118">返回数据读取器的状态</span><span class="sxs-lookup"><span data-stu-id="ca774-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="ca774-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="ca774-119">**RecordsAffected**</span></span>|<span data-ttu-id="ca774-120">获取</span><span class="sxs-lookup"><span data-stu-id="ca774-120">Get</span></span>|<span data-ttu-id="ca774-121">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="ca774-121">Not supported.</span></span> <span data-ttu-id="ca774-122">将返回-1</span><span class="sxs-lookup"><span data-stu-id="ca774-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="ca774-123">支持的方法</span><span class="sxs-lookup"><span data-stu-id="ca774-123">Supported Methods</span></span>  
  
|<span data-ttu-id="ca774-124">Name</span><span class="sxs-lookup"><span data-stu-id="ca774-124">Name</span></span>|<span data-ttu-id="ca774-125">Description</span><span class="sxs-lookup"><span data-stu-id="ca774-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ca774-126">**Close （)**</span><span class="sxs-lookup"><span data-stu-id="ca774-126">**Close()**</span></span>|<span data-ttu-id="ca774-127">关闭 DataReader</span><span class="sxs-lookup"><span data-stu-id="ca774-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="ca774-128">**获取 [方法]**<sup>*</sup></span><span class="sxs-lookup"><span data-stu-id="ca774-128">**Get [methods]** <sup>*</sup></span></span><br /><br /> <span data-ttu-id="ca774-129">其中 [方法] 是预期的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ca774-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="ca774-130">例如</span><span class="sxs-lookup"><span data-stu-id="ca774-130">E.g.</span></span> <span data-ttu-id="ca774-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="ca774-131">GetInt32(int)</span></span>|<span data-ttu-id="ca774-132">获取列的值基于期望的数据类型</span><span class="sxs-lookup"><span data-stu-id="ca774-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="ca774-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="ca774-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="ca774-134">不提供支持。</span><span class="sxs-lookup"><span data-stu-id="ca774-134">Not supported.</span></span> <span data-ttu-id="ca774-135">返回 false。</span><span class="sxs-lookup"><span data-stu-id="ca774-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca774-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca774-136">See Also</span></span>  
 [<span data-ttu-id="ca774-137">使用 SAP 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="ca774-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)