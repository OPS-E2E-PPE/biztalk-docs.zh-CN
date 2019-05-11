---
title: 如何循环访问业务规则中的 ArrayList |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9753ce1208312ade51950cd36a1df4210d763268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384872"
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a><span data-ttu-id="7c012-102">如何循环访问业务规则中的 ArrayList</span><span class="sxs-lookup"><span data-stu-id="7c012-102">How to Iterate ArrayList in Business Rules</span></span>
<span data-ttu-id="7c012-103">本部分举例说明循环访问的成员**ArrayList**业务规则中。</span><span class="sxs-lookup"><span data-stu-id="7c012-103">This section provides an example of iterating through members of an **ArrayList** in business rules.</span></span>  
  
 <span data-ttu-id="7c012-104">假设您有**ArrayList**了一系列**MyClass**对象。</span><span class="sxs-lookup"><span data-stu-id="7c012-104">Assume you have an **ArrayList** with a collection of **MyClass** objects.</span></span> <span data-ttu-id="7c012-105">您的业务规则如以下所示。</span><span class="sxs-lookup"><span data-stu-id="7c012-105">Your business rules would look like the following.</span></span>  
  
## <a name="rule-a"></a><span data-ttu-id="7c012-106">规则 A</span><span class="sxs-lookup"><span data-stu-id="7c012-106">Rule A</span></span>  
 <span data-ttu-id="7c012-107">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="7c012-107">IF 1==1</span></span>  
  
 <span data-ttu-id="7c012-108">THEN Assert (ArrayList.GetEnumerator)</span><span class="sxs-lookup"><span data-stu-id="7c012-108">THEN Assert (ArrayList.GetEnumerator)</span></span>  
  
 <span data-ttu-id="7c012-109">**IEnumerator**类型将添加到工作内存中，因为规则条件 (1 = = 1) 计算结果始终为 true。</span><span class="sxs-lookup"><span data-stu-id="7c012-109">An **IEnumerator** type is asserted into the working memory, because the rule condition (1==1) always evaluates to true.</span></span>  
  
## <a name="rule-b"></a><span data-ttu-id="7c012-110">规则 B</span><span class="sxs-lookup"><span data-stu-id="7c012-110">Rule B</span></span>  
 <span data-ttu-id="7c012-111">IF IEnumerator.MoveNext</span><span class="sxs-lookup"><span data-stu-id="7c012-111">IF IEnumerator.MoveNext</span></span>  
  
 <span data-ttu-id="7c012-112">THEN    Assert (IEnumerator.get_Current)</span><span class="sxs-lookup"><span data-stu-id="7c012-112">THEN    Assert (IEnumerator.get_Current)</span></span>  
  
 <span data-ttu-id="7c012-113">更新 (IEnumerator)</span><span class="sxs-lookup"><span data-stu-id="7c012-113">Update (IEnumerator)</span></span>  
  
 <span data-ttu-id="7c012-114">因为规则循环访问**ArrayList**，则每个**MyClass**添加到工作内存中集合中的对象。</span><span class="sxs-lookup"><span data-stu-id="7c012-114">As the rule iterates through the **ArrayList**, each **MyClass** object in the collection is asserted into the working memory.</span></span>  
  
## <a name="rule-c"></a><span data-ttu-id="7c012-115">规则 C</span><span class="sxs-lookup"><span data-stu-id="7c012-115">Rule C</span></span>  
 <span data-ttu-id="7c012-116">IF MyClass.MyProperty==2</span><span class="sxs-lookup"><span data-stu-id="7c012-116">IF MyClass.MyProperty==2</span></span>  
  
 <span data-ttu-id="7c012-117">然后\<执行一些操作...\></span><span class="sxs-lookup"><span data-stu-id="7c012-117">THEN \<Do Something...\></span></span>  
  
 <span data-ttu-id="7c012-118">该对象的属性值匹配条件中时，此规则将执行操作。</span><span class="sxs-lookup"><span data-stu-id="7c012-118">This rule executes action(s) when the property value of the object is matched in the condition.</span></span>