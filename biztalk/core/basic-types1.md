---
title: "基本类型 1> |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a><span data-ttu-id="54c17-102">基本类型</span><span class="sxs-lookup"><span data-stu-id="54c17-102">Basic Types</span></span>
<span data-ttu-id="54c17-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供仅到 JD Edwards OneWorld 业务函数的访问。</span><span class="sxs-lookup"><span data-stu-id="54c17-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access only to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="54c17-104">业务功能元数据使用业务功能接口读取，用于查找业务功能列表和相关联的数据结构。</span><span class="sxs-lookup"><span data-stu-id="54c17-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="54c17-105">对于所有业务功能方法，元数据都是强类型数据。</span><span class="sxs-lookup"><span data-stu-id="54c17-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="54c17-106">所有业务函数方法都有相同的调用约定： 是针对派生，整个系统的三个参数和指向的数据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="54c17-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="54c17-107">下表显示了业务函数数据类型是如何表示的。</span><span class="sxs-lookup"><span data-stu-id="54c17-107">The following table shows how the business function data types are represented.</span></span>  
  
 <span data-ttu-id="54c17-108">**业务函数数据类型**</span><span class="sxs-lookup"><span data-stu-id="54c17-108">**Business function data types**</span></span>  
  
|<span data-ttu-id="54c17-109">JD Edwards OneWorld 数据类型</span><span class="sxs-lookup"><span data-stu-id="54c17-109">JD Edwards OneWorld Data Type</span></span>|<span data-ttu-id="54c17-110">Description</span><span class="sxs-lookup"><span data-stu-id="54c17-110">Description</span></span>|<span data-ttu-id="54c17-111">WDSL 转换</span><span class="sxs-lookup"><span data-stu-id="54c17-111">WDSL Conversion</span></span>|  
|-----------------------------------|-----------------|---------------------|  
|<span data-ttu-id="54c17-112">char</span><span class="sxs-lookup"><span data-stu-id="54c17-112">char</span></span>|<span data-ttu-id="54c17-113">字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="54c17-113">Character string.</span></span>|<span data-ttu-id="54c17-114">xsd:string of 1</span><span class="sxs-lookup"><span data-stu-id="54c17-114">xsd:string of 1</span></span>|  
|<span data-ttu-id="54c17-115">int</span><span class="sxs-lookup"><span data-stu-id="54c17-115">int</span></span>|<span data-ttu-id="54c17-116">短整数。</span><span class="sxs-lookup"><span data-stu-id="54c17-116">Short integer.</span></span>|<span data-ttu-id="54c17-117">xsd:short</span><span class="sxs-lookup"><span data-stu-id="54c17-117">xsd:short</span></span>|  
|<span data-ttu-id="54c17-118">long</span><span class="sxs-lookup"><span data-stu-id="54c17-118">long</span></span>|<span data-ttu-id="54c17-119">长整型。</span><span class="sxs-lookup"><span data-stu-id="54c17-119">Long integer.</span></span>|<span data-ttu-id="54c17-120">xsd:short</span><span class="sxs-lookup"><span data-stu-id="54c17-120">xsd:short</span></span>|  
|<span data-ttu-id="54c17-121">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-121">String</span></span>|<span data-ttu-id="54c17-122">请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="54c17-122">See [Handling String Values](../core/handling-string-values1.md).</span></span>|<span data-ttu-id="54c17-123">xsd:string</span><span class="sxs-lookup"><span data-stu-id="54c17-123">xsd:string</span></span>|  
|<span data-ttu-id="54c17-124">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="54c17-124">JDEDATE</span></span>|<span data-ttu-id="54c17-125">日期的特殊实现。</span><span class="sxs-lookup"><span data-stu-id="54c17-125">Special implementation of dates.</span></span>|<span data-ttu-id="54c17-126">xsd:date</span><span class="sxs-lookup"><span data-stu-id="54c17-126">xsd:date</span></span>|  
|<span data-ttu-id="54c17-127">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="54c17-127">MATH_NUMERIC</span></span>|<span data-ttu-id="54c17-128">浮动点数的特殊实现，包括货币值。</span><span class="sxs-lookup"><span data-stu-id="54c17-128">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="54c17-129">32 个 xsd: string</span><span class="sxs-lookup"><span data-stu-id="54c17-129">xsd:string of 32</span></span>|  
|<span data-ttu-id="54c17-130">Byte</span><span class="sxs-lookup"><span data-stu-id="54c17-130">Byte</span></span>|<span data-ttu-id="54c17-131">单个无符号字符。</span><span class="sxs-lookup"><span data-stu-id="54c17-131">Single unsigned character.</span></span>|<span data-ttu-id="54c17-132">xsd:string of 1</span><span class="sxs-lookup"><span data-stu-id="54c17-132">xsd:string of 1</span></span>|  
  
 <span data-ttu-id="54c17-133">下表包含 JD Edwards OneWorld 中的基本类型列表及其映射到 Microsoft .NET Framework 的方式。</span><span class="sxs-lookup"><span data-stu-id="54c17-133">The following table contains the list of basic types in JD Edwards OneWorld and how they map to the Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="54c17-134">**基本类型和它们如何映射到 Microsoft.NET Framework**</span><span class="sxs-lookup"><span data-stu-id="54c17-134">**Basic types and how they map to the Microsoft .NET Framework**</span></span>  
  
|<span data-ttu-id="54c17-135">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="54c17-135">JD Edwards OneWorld XE</span></span>|<span data-ttu-id="54c17-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="54c17-136">.NET Framework</span></span>|  
|----------------------------|--------------------|  
|<span data-ttu-id="54c17-137">char</span><span class="sxs-lookup"><span data-stu-id="54c17-137">char</span></span>|<span data-ttu-id="54c17-138">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-138">String</span></span>|  
|<span data-ttu-id="54c17-139">int</span><span class="sxs-lookup"><span data-stu-id="54c17-139">int</span></span>|<span data-ttu-id="54c17-140">Short</span><span class="sxs-lookup"><span data-stu-id="54c17-140">Short</span></span>|  
|<span data-ttu-id="54c17-141">long</span><span class="sxs-lookup"><span data-stu-id="54c17-141">long</span></span>|<span data-ttu-id="54c17-142">Short</span><span class="sxs-lookup"><span data-stu-id="54c17-142">Short</span></span>|  
|<span data-ttu-id="54c17-143">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-143">String</span></span>|<span data-ttu-id="54c17-144">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-144">String</span></span>|  
|<span data-ttu-id="54c17-145">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="54c17-145">JDEDATE</span></span>|<span data-ttu-id="54c17-146">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="54c17-146">System.DateTime</span></span>|  
|<span data-ttu-id="54c17-147">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="54c17-147">MATH_NUMERIC</span></span>|<span data-ttu-id="54c17-148">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-148">String</span></span>|  
|<span data-ttu-id="54c17-149">Byte</span><span class="sxs-lookup"><span data-stu-id="54c17-149">Byte</span></span>|<span data-ttu-id="54c17-150">字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-150">String</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="54c17-151">如果只有一个参数，且返回参数为 void，则占位符将替换为类，输出部分将成为返回值。</span><span class="sxs-lookup"><span data-stu-id="54c17-151">If there is only one argument, and the return argument is void, the holder is replaced by the class, and the out portion becomes the return value.</span></span> <span data-ttu-id="54c17-152">例如：</span><span class="sxs-lookup"><span data-stu-id="54c17-152">For example:</span></span>  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 <span data-ttu-id="54c17-153">下面是一个方法签名示例：</span><span class="sxs-lookup"><span data-stu-id="54c17-153">The following is an example of method signatures:</span></span>  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a><span data-ttu-id="54c17-154">有限字符串</span><span class="sxs-lookup"><span data-stu-id="54c17-154">Character-Limited Strings</span></span>  
 <span data-ttu-id="54c17-155">在 JD Edwards OneWorld 中，一些字符串是有字符限制的。</span><span class="sxs-lookup"><span data-stu-id="54c17-155">In JD Edwards OneWorld, some strings are character-limited.</span></span> <span data-ttu-id="54c17-156">任何多余的字符将导致出错。</span><span class="sxs-lookup"><span data-stu-id="54c17-156">Any extra character causes an error.</span></span> <span data-ttu-id="54c17-157">若要查看字符串中的字符限制，您可以使用 Microsoft 适配器向导。</span><span class="sxs-lookup"><span data-stu-id="54c17-157">To see the limit of characters in the strings, you can use the Microsoft Adapter Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c17-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54c17-158">See Also</span></span>  
 <span data-ttu-id="54c17-159">[使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type2.md) </span><span class="sxs-lookup"><span data-stu-id="54c17-159">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type2.md) </span></span>  
 <span data-ttu-id="54c17-160">[处理字符串值](../core/handling-string-values1.md) </span><span class="sxs-lookup"><span data-stu-id="54c17-160">[Handling String Values](../core/handling-string-values1.md) </span></span>  
 [<span data-ttu-id="54c17-161">附录 a： 数据类型</span><span class="sxs-lookup"><span data-stu-id="54c17-161">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)