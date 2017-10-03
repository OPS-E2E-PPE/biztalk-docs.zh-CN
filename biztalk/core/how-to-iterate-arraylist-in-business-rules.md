---
title: "如何循环访问业务规则中的 ArrayList |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95896b63e5bb982a4778b05970900c989ebc66b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a><span data-ttu-id="eea24-102">如何循环访问业务规则中的 ArrayList</span><span class="sxs-lookup"><span data-stu-id="eea24-102">How to Iterate ArrayList in Business Rules</span></span>
<span data-ttu-id="eea24-103">本部分提供了循环访问的成员的一个示例**ArrayList**业务规则中。</span><span class="sxs-lookup"><span data-stu-id="eea24-103">This section provides an example of iterating through members of an **ArrayList** in business rules.</span></span>  
  
 <span data-ttu-id="eea24-104">假定您有**ArrayList**采用一系列**MyClass**对象。</span><span class="sxs-lookup"><span data-stu-id="eea24-104">Assume you have an **ArrayList** with a collection of **MyClass** objects.</span></span> <span data-ttu-id="eea24-105">该业务规则应与下面所列相似：</span><span class="sxs-lookup"><span data-stu-id="eea24-105">Your business rules would look like the following.</span></span>  
  
## <a name="rule-a"></a><span data-ttu-id="eea24-106">规则 A</span><span class="sxs-lookup"><span data-stu-id="eea24-106">Rule A</span></span>  
 <span data-ttu-id="eea24-107">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="eea24-107">IF 1==1</span></span>  
  
 <span data-ttu-id="eea24-108">THEN Assert (ArrayList.GetEnumerator) </span><span class="sxs-lookup"><span data-stu-id="eea24-108">THEN Assert (ArrayList.GetEnumerator)</span></span>  
  
 <span data-ttu-id="eea24-109">**IEnumerator**类型被声明到工作内存中，因为规则条件 (1 = = 1) 始终计算结果为 true。</span><span class="sxs-lookup"><span data-stu-id="eea24-109">An **IEnumerator** type is asserted into the working memory, because the rule condition (1==1) always evaluates to true.</span></span>  
  
## <a name="rule-b"></a><span data-ttu-id="eea24-110">规则 B</span><span class="sxs-lookup"><span data-stu-id="eea24-110">Rule B</span></span>  
 <span data-ttu-id="eea24-111">IF IEnumerator.MoveNext</span><span class="sxs-lookup"><span data-stu-id="eea24-111">IF IEnumerator.MoveNext</span></span>  
  
 <span data-ttu-id="eea24-112">THEN    Assert (IEnumerator.get_Current)</span><span class="sxs-lookup"><span data-stu-id="eea24-112">THEN    Assert (IEnumerator.get_Current)</span></span>  
  
 <span data-ttu-id="eea24-113">Update (IEnumerator)</span><span class="sxs-lookup"><span data-stu-id="eea24-113">Update (IEnumerator)</span></span>  
  
 <span data-ttu-id="eea24-114">由于此规则通过循环**ArrayList**，每个**MyClass**到工作内存断言集合中的对象。</span><span class="sxs-lookup"><span data-stu-id="eea24-114">As the rule iterates through the **ArrayList**, each **MyClass** object in the collection is asserted into the working memory.</span></span>  
  
## <a name="rule-c"></a><span data-ttu-id="eea24-115">规则 C</span><span class="sxs-lookup"><span data-stu-id="eea24-115">Rule C</span></span>  
 <span data-ttu-id="eea24-116">IF MyClass.MyProperty==2</span><span class="sxs-lookup"><span data-stu-id="eea24-116">IF MyClass.MyProperty==2</span></span>  
  
 <span data-ttu-id="eea24-117">然后\<做些什么...></span><span class="sxs-lookup"><span data-stu-id="eea24-117">THEN \<Do Something...></span></span>  
  
 <span data-ttu-id="eea24-118">当对象的属性值与条件中所列值匹配时，此规则将执行操作。</span><span class="sxs-lookup"><span data-stu-id="eea24-118">This rule executes action(s) when the property value of the object is matched in the condition.</span></span>