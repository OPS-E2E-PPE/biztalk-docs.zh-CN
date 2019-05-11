---
title: 基本类型 1> |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c1cfd31eacd56c19e5b1daf2288be098d9448c3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529140"
---
# <a name="basic-types"></a><span data-ttu-id="891aa-102">基本类型</span><span class="sxs-lookup"><span data-stu-id="891aa-102">Basic Types</span></span>
<span data-ttu-id="891aa-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供仅到 JD Edwards OneWorld 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="891aa-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access only to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="891aa-104">业务功能元数据使用业务功能接口读取和用于查找业务功能的列表和关联数据结构。</span><span class="sxs-lookup"><span data-stu-id="891aa-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="891aa-105">在所有情况下，对于所有业务功能方法为强类型元数据。</span><span class="sxs-lookup"><span data-stu-id="891aa-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="891aa-106">所有业务功能方法都具有相同的调用约定： 系统派生的三个参数和数据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="891aa-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="891aa-107">下表显示了业务函数数据类型的表示方式。</span><span class="sxs-lookup"><span data-stu-id="891aa-107">The following table shows how the business function data types are represented.</span></span>  
  
 <span data-ttu-id="891aa-108">**业务函数数据类型**</span><span class="sxs-lookup"><span data-stu-id="891aa-108">**Business function data types**</span></span>  
  
|<span data-ttu-id="891aa-109">JD Edwards OneWorld Data Type</span><span class="sxs-lookup"><span data-stu-id="891aa-109">JD Edwards OneWorld Data Type</span></span>|<span data-ttu-id="891aa-110">Description</span><span class="sxs-lookup"><span data-stu-id="891aa-110">Description</span></span>|<span data-ttu-id="891aa-111">WDSL 转换</span><span class="sxs-lookup"><span data-stu-id="891aa-111">WDSL Conversion</span></span>|  
|-----------------------------------|-----------------|---------------------|  
|<span data-ttu-id="891aa-112">char</span><span class="sxs-lookup"><span data-stu-id="891aa-112">char</span></span>|<span data-ttu-id="891aa-113">字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="891aa-113">Character string.</span></span>|<span data-ttu-id="891aa-114">xsd: string 的 1</span><span class="sxs-lookup"><span data-stu-id="891aa-114">xsd:string of 1</span></span>|  
|<span data-ttu-id="891aa-115">ssNoversion</span><span class="sxs-lookup"><span data-stu-id="891aa-115">int</span></span>|<span data-ttu-id="891aa-116">短整数。</span><span class="sxs-lookup"><span data-stu-id="891aa-116">Short integer.</span></span>|<span data-ttu-id="891aa-117">xsd:short</span><span class="sxs-lookup"><span data-stu-id="891aa-117">xsd:short</span></span>|  
|<span data-ttu-id="891aa-118">long</span><span class="sxs-lookup"><span data-stu-id="891aa-118">long</span></span>|<span data-ttu-id="891aa-119">长整型。</span><span class="sxs-lookup"><span data-stu-id="891aa-119">Long integer.</span></span>|<span data-ttu-id="891aa-120">xsd:short</span><span class="sxs-lookup"><span data-stu-id="891aa-120">xsd:short</span></span>|  
|<span data-ttu-id="891aa-121">String</span><span class="sxs-lookup"><span data-stu-id="891aa-121">String</span></span>|<span data-ttu-id="891aa-122">请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="891aa-122">See [Handling String Values](../core/handling-string-values1.md).</span></span>|<span data-ttu-id="891aa-123">xsd:string</span><span class="sxs-lookup"><span data-stu-id="891aa-123">xsd:string</span></span>|  
|<span data-ttu-id="891aa-124">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="891aa-124">JDEDATE</span></span>|<span data-ttu-id="891aa-125">数据的特殊实现。</span><span class="sxs-lookup"><span data-stu-id="891aa-125">Special implementation of dates.</span></span>|<span data-ttu-id="891aa-126">xsd:date</span><span class="sxs-lookup"><span data-stu-id="891aa-126">xsd:date</span></span>|  
|<span data-ttu-id="891aa-127">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="891aa-127">MATH_NUMERIC</span></span>|<span data-ttu-id="891aa-128">浮点数字，其中包括货币值的特殊实现。</span><span class="sxs-lookup"><span data-stu-id="891aa-128">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="891aa-129">32 个 xsd: string</span><span class="sxs-lookup"><span data-stu-id="891aa-129">xsd:string of 32</span></span>|  
|<span data-ttu-id="891aa-130">Byte</span><span class="sxs-lookup"><span data-stu-id="891aa-130">Byte</span></span>|<span data-ttu-id="891aa-131">单个无符号的字符。</span><span class="sxs-lookup"><span data-stu-id="891aa-131">Single unsigned character.</span></span>|<span data-ttu-id="891aa-132">xsd: string 的 1</span><span class="sxs-lookup"><span data-stu-id="891aa-132">xsd:string of 1</span></span>|  
  
 <span data-ttu-id="891aa-133">下表包含 JD Edwards OneWorld 以及它们如何映射到 Microsoft.NET Framework 中的基本类型的列表。</span><span class="sxs-lookup"><span data-stu-id="891aa-133">The following table contains the list of basic types in JD Edwards OneWorld and how they map to the Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="891aa-134">**基本类型以及它们如何映射到 Microsoft.NET Framework**</span><span class="sxs-lookup"><span data-stu-id="891aa-134">**Basic types and how they map to the Microsoft .NET Framework**</span></span>  
  
|<span data-ttu-id="891aa-135">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="891aa-135">JD Edwards OneWorld XE</span></span>|<span data-ttu-id="891aa-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="891aa-136">.NET Framework</span></span>|  
|----------------------------|--------------------|  
|<span data-ttu-id="891aa-137">char</span><span class="sxs-lookup"><span data-stu-id="891aa-137">char</span></span>|<span data-ttu-id="891aa-138">String</span><span class="sxs-lookup"><span data-stu-id="891aa-138">String</span></span>|  
|<span data-ttu-id="891aa-139">ssNoversion</span><span class="sxs-lookup"><span data-stu-id="891aa-139">int</span></span>|<span data-ttu-id="891aa-140">Short</span><span class="sxs-lookup"><span data-stu-id="891aa-140">Short</span></span>|  
|<span data-ttu-id="891aa-141">long</span><span class="sxs-lookup"><span data-stu-id="891aa-141">long</span></span>|<span data-ttu-id="891aa-142">Short</span><span class="sxs-lookup"><span data-stu-id="891aa-142">Short</span></span>|  
|<span data-ttu-id="891aa-143">String</span><span class="sxs-lookup"><span data-stu-id="891aa-143">String</span></span>|<span data-ttu-id="891aa-144">String</span><span class="sxs-lookup"><span data-stu-id="891aa-144">String</span></span>|  
|<span data-ttu-id="891aa-145">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="891aa-145">JDEDATE</span></span>|<span data-ttu-id="891aa-146">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="891aa-146">System.DateTime</span></span>|  
|<span data-ttu-id="891aa-147">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="891aa-147">MATH_NUMERIC</span></span>|<span data-ttu-id="891aa-148">String</span><span class="sxs-lookup"><span data-stu-id="891aa-148">String</span></span>|  
|<span data-ttu-id="891aa-149">Byte</span><span class="sxs-lookup"><span data-stu-id="891aa-149">Byte</span></span>|<span data-ttu-id="891aa-150">String</span><span class="sxs-lookup"><span data-stu-id="891aa-150">String</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="891aa-151">如果只有一个参数，且返回参数为 void，占位符将替换为类，并输出部分将成为返回值。</span><span class="sxs-lookup"><span data-stu-id="891aa-151">If there is only one argument, and the return argument is void, the holder is replaced by the class, and the out portion becomes the return value.</span></span> <span data-ttu-id="891aa-152">例如：</span><span class="sxs-lookup"><span data-stu-id="891aa-152">For example:</span></span>  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 <span data-ttu-id="891aa-153">以下是方法签名的示例：</span><span class="sxs-lookup"><span data-stu-id="891aa-153">The following is an example of method signatures:</span></span>  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a><span data-ttu-id="891aa-154">有限字符串</span><span class="sxs-lookup"><span data-stu-id="891aa-154">Character-Limited Strings</span></span>  
 <span data-ttu-id="891aa-155">在 JD Edwards OneWorld 中一些字符串是有字符限制。</span><span class="sxs-lookup"><span data-stu-id="891aa-155">In JD Edwards OneWorld, some strings are character-limited.</span></span> <span data-ttu-id="891aa-156">任何多余的字符将导致错误。</span><span class="sxs-lookup"><span data-stu-id="891aa-156">Any extra character causes an error.</span></span> <span data-ttu-id="891aa-157">若要查看字符串中的字符的限制，可以使用 Microsoft 适配器向导。</span><span class="sxs-lookup"><span data-stu-id="891aa-157">To see the limit of characters in the strings, you can use the Microsoft Adapter Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891aa-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="891aa-158">See Also</span></span>  
 <span data-ttu-id="891aa-159">[使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type2.md) </span><span class="sxs-lookup"><span data-stu-id="891aa-159">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type2.md) </span></span>  
 <span data-ttu-id="891aa-160">[处理字符串值](../core/handling-string-values1.md) </span><span class="sxs-lookup"><span data-stu-id="891aa-160">[Handling String Values](../core/handling-string-values1.md) </span></span>  
 [<span data-ttu-id="891aa-161">附录 a:数据类型</span><span class="sxs-lookup"><span data-stu-id="891aa-161">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)