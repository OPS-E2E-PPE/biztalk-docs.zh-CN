---
title: 简单类型派生 |Microsoft 文档
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
ms.openlocfilehash: fcc74796de8543f1e0f895d0b3dff705aeb2930e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270789"
---
# <a name="simple-type-derivation"></a><span data-ttu-id="ad078-102">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ad078-102">Simple Type Derivation</span></span>
<span data-ttu-id="ad078-103">XML 架构定义 (XSD) 语言提供了定义简单类型的变体的若干机制（基于现有简单类型的派生），如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad078-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
-   <span data-ttu-id="ad078-104">**限制**。</span><span class="sxs-lookup"><span data-stu-id="ad078-104">**Restriction**.</span></span> <span data-ttu-id="ad078-105">通过使用限制机制进行简单类型派生将引入对该类型的可能值的限制。</span><span class="sxs-lookup"><span data-stu-id="ad078-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="ad078-106">例如，数字类型的最小和/或最大值，或者字符串类型的最小和最大长度。</span><span class="sxs-lookup"><span data-stu-id="ad078-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
-   <span data-ttu-id="ad078-107">**列表**。</span><span class="sxs-lookup"><span data-stu-id="ad078-107">**List**.</span></span> <span data-ttu-id="ad078-108">通过使用列表机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为由特定类型的空格分隔的值的列表组成。</span><span class="sxs-lookup"><span data-stu-id="ad078-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
-   <span data-ttu-id="ad078-109">**联合**。</span><span class="sxs-lookup"><span data-stu-id="ad078-109">**Union**.</span></span> <span data-ttu-id="ad078-110">通过使用联合机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为多个指定类型之一的单个值。</span><span class="sxs-lookup"><span data-stu-id="ad078-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
 <span data-ttu-id="ad078-111">本部分将详细介绍这些简单类型派生，包括如何通过在“属性”窗口中设置相应节点属性定义这些派生以及如何构造相应 XSD。</span><span class="sxs-lookup"><span data-stu-id="ad078-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad078-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="ad078-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ad078-113">使用限制机制的简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ad078-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="ad078-114">使用列表机制的简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ad078-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="ad078-115">使用联合的机制的简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ad078-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)