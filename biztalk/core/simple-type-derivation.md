---
title: 简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b1904c96c2786abad283db7133a9755c8743d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998494"
---
# <a name="simple-type-derivation"></a><span data-ttu-id="367a1-102">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="367a1-102">Simple Type Derivation</span></span>
<span data-ttu-id="367a1-103">XML 架构定义 (XSD) 语言提供了定义简单类型的变体的若干机制（基于现有简单类型的派生），如下所示：</span><span class="sxs-lookup"><span data-stu-id="367a1-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
- <span data-ttu-id="367a1-104">**限制**。</span><span class="sxs-lookup"><span data-stu-id="367a1-104">**Restriction**.</span></span> <span data-ttu-id="367a1-105">通过使用限制机制进行简单类型派生将引入对该类型的可能值的限制。</span><span class="sxs-lookup"><span data-stu-id="367a1-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="367a1-106">例如，数字类型的最小和/或最大值，或者字符串类型的最小和最大长度。</span><span class="sxs-lookup"><span data-stu-id="367a1-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
- <span data-ttu-id="367a1-107">**列表**。</span><span class="sxs-lookup"><span data-stu-id="367a1-107">**List**.</span></span> <span data-ttu-id="367a1-108">通过使用列表机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为由特定类型的空格分隔的值的列表组成。</span><span class="sxs-lookup"><span data-stu-id="367a1-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
- <span data-ttu-id="367a1-109">**联合**。</span><span class="sxs-lookup"><span data-stu-id="367a1-109">**Union**.</span></span> <span data-ttu-id="367a1-110">通过使用联合机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为多个指定类型之一的单个值。</span><span class="sxs-lookup"><span data-stu-id="367a1-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
  <span data-ttu-id="367a1-111">本部分将详细介绍这些简单类型派生，包括如何通过在“属性”窗口中设置相应节点属性定义这些派生以及如何构造相应 XSD。</span><span class="sxs-lookup"><span data-stu-id="367a1-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="367a1-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="367a1-112">In This Section</span></span>  
  
-   [<span data-ttu-id="367a1-113">使用限制机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="367a1-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="367a1-114">使用列表机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="367a1-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="367a1-115">使用联合机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="367a1-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)