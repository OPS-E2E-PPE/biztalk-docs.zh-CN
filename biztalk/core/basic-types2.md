---
title: "基本 Types2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a><span data-ttu-id="36c00-102">基本类型</span><span class="sxs-lookup"><span data-stu-id="36c00-102">Basic Types</span></span>
<span data-ttu-id="36c00-103">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器仅提供了对 JD Edwards EnterpriseOne 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="36c00-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access only to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="36c00-104">业务功能元数据使用业务功能接口读取，用于查找业务功能列表和相关联的数据结构。</span><span class="sxs-lookup"><span data-stu-id="36c00-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="36c00-105">对于所有业务功能方法，元数据都是强类型数据。</span><span class="sxs-lookup"><span data-stu-id="36c00-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="36c00-106">所有业务函数方法都有相同的调用约定： 是针对派生，整个系统的三个参数和指向的数据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="36c00-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="36c00-107">下表显示了业务功能数据类型的表示方式。</span><span class="sxs-lookup"><span data-stu-id="36c00-107">The following table shows how business function data types are represented.</span></span>  
  
|<span data-ttu-id="36c00-108">JD Edwards EnterpriseOne 数据类型</span><span class="sxs-lookup"><span data-stu-id="36c00-108">JD Edwards EnterpriseOne Data Type</span></span>|<span data-ttu-id="36c00-109">Description</span><span class="sxs-lookup"><span data-stu-id="36c00-109">Description</span></span>|<span data-ttu-id="36c00-110">WDSL 转换</span><span class="sxs-lookup"><span data-stu-id="36c00-110">WDSL Conversion</span></span>|  
|----------------------------------------|-----------------|---------------------|  
|<span data-ttu-id="36c00-111">char</span><span class="sxs-lookup"><span data-stu-id="36c00-111">char</span></span>|<span data-ttu-id="36c00-112">字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="36c00-112">Character string.</span></span>|<span data-ttu-id="36c00-113">xsd:string of 1</span><span class="sxs-lookup"><span data-stu-id="36c00-113">xsd:string of 1</span></span>|  
|<span data-ttu-id="36c00-114">int</span><span class="sxs-lookup"><span data-stu-id="36c00-114">int</span></span>|<span data-ttu-id="36c00-115">短整数。</span><span class="sxs-lookup"><span data-stu-id="36c00-115">Short integer.</span></span>|<span data-ttu-id="36c00-116">xsd:short</span><span class="sxs-lookup"><span data-stu-id="36c00-116">xsd:short</span></span>|  
|<span data-ttu-id="36c00-117">long</span><span class="sxs-lookup"><span data-stu-id="36c00-117">long</span></span>|<span data-ttu-id="36c00-118">长整型。</span><span class="sxs-lookup"><span data-stu-id="36c00-118">Long integer.</span></span>|<span data-ttu-id="36c00-119">xsd:short</span><span class="sxs-lookup"><span data-stu-id="36c00-119">xsd:short</span></span>|  
|<span data-ttu-id="36c00-120">字符串</span><span class="sxs-lookup"><span data-stu-id="36c00-120">String</span></span>|<span data-ttu-id="36c00-121">请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="36c00-121">See [Handling String Values](../core/handling-string-values2.md).</span></span>|<span data-ttu-id="36c00-122">xsd:string</span><span class="sxs-lookup"><span data-stu-id="36c00-122">xsd:string</span></span>|  
|<span data-ttu-id="36c00-123">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="36c00-123">JDEDATE</span></span>|<span data-ttu-id="36c00-124">日期的特殊实现。</span><span class="sxs-lookup"><span data-stu-id="36c00-124">Special implementation of dates.</span></span>|<span data-ttu-id="36c00-125">xsd:date</span><span class="sxs-lookup"><span data-stu-id="36c00-125">xsd:date</span></span>|  
|<span data-ttu-id="36c00-126">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="36c00-126">MATH_NUMERIC</span></span>|<span data-ttu-id="36c00-127">浮动点数的特殊实现，包括货币值。</span><span class="sxs-lookup"><span data-stu-id="36c00-127">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="36c00-128">32 个 xsd: string</span><span class="sxs-lookup"><span data-stu-id="36c00-128">xsd:string of 32</span></span>|  
|<span data-ttu-id="36c00-129">Byte</span><span class="sxs-lookup"><span data-stu-id="36c00-129">Byte</span></span>|<span data-ttu-id="36c00-130">单个无符号字符。</span><span class="sxs-lookup"><span data-stu-id="36c00-130">Single unsigned character.</span></span>|<span data-ttu-id="36c00-131">xsd:string of 1</span><span class="sxs-lookup"><span data-stu-id="36c00-131">xsd:string of 1</span></span>|  
|<span data-ttu-id="36c00-132">JDEUTIME</span><span class="sxs-lookup"><span data-stu-id="36c00-132">JDEUTIME</span></span>|<span data-ttu-id="36c00-133">包括日期和时间的组件。</span><span class="sxs-lookup"><span data-stu-id="36c00-133">Includes both date and time components.</span></span><br /><br /> <span data-ttu-id="36c00-134">数据类型存储的所有日期/时间并执行以协调世界时 (UTC) 的所有日期/时间计算。</span><span class="sxs-lookup"><span data-stu-id="36c00-134">The data type stores all dates/times and performs all date/time calculations in Coordinated Universal Time (UTC).</span></span>|<span data-ttu-id="36c00-135">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="36c00-135">xsd:dateTime</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36c00-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36c00-136">See Also</span></span>  
 <span data-ttu-id="36c00-137">[使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type1.md) </span><span class="sxs-lookup"><span data-stu-id="36c00-137">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type1.md) </span></span>  
 <span data-ttu-id="36c00-138">[处理字符串值](../core/handling-string-values2.md) </span><span class="sxs-lookup"><span data-stu-id="36c00-138">[Handling String Values](../core/handling-string-values2.md) </span></span>  
 [<span data-ttu-id="36c00-139">附录 b： 数据类型</span><span class="sxs-lookup"><span data-stu-id="36c00-139">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)