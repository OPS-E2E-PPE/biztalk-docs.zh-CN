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
ms.openlocfilehash: c0297c205eac27a5c1cbde11ea22cbf86c078b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393003"
---
# <a name="simple-type-derivation"></a><span data-ttu-id="20733-102">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="20733-102">Simple Type Derivation</span></span>
<span data-ttu-id="20733-103">XML 架构定义 (XSD) 语言提供了多种机制，用于定义基于的现有简单类型派生，如下所示的简单类型的变体：</span><span class="sxs-lookup"><span data-stu-id="20733-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
- <span data-ttu-id="20733-104">**限制**。</span><span class="sxs-lookup"><span data-stu-id="20733-104">**Restriction**.</span></span> <span data-ttu-id="20733-105">通过使用限制机制进行简单类型派生涉及到针对该类型的可能值的限制简介。</span><span class="sxs-lookup"><span data-stu-id="20733-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="20733-106">示例包括，数值类型的最小和/或最大值或字符串类型的最小值和最大长度。</span><span class="sxs-lookup"><span data-stu-id="20733-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
- <span data-ttu-id="20733-107">**列表**。</span><span class="sxs-lookup"><span data-stu-id="20733-107">**List**.</span></span> <span data-ttu-id="20733-108">通过使用列表机制进行简单类型派生允许单个属性或元素值定义为包含实例消息中的特定类型的空格分隔的值的列表。</span><span class="sxs-lookup"><span data-stu-id="20733-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
- <span data-ttu-id="20733-109">**联合**。</span><span class="sxs-lookup"><span data-stu-id="20733-109">**Union**.</span></span> <span data-ttu-id="20733-110">通过使用联合机制进行简单类型派生将允许定义为单个值的多个指定类型之一的实例消息中的单个属性或元素值。</span><span class="sxs-lookup"><span data-stu-id="20733-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
  <span data-ttu-id="20733-111">本部分介绍更多详细信息，包括如何通过在属性窗口中设置相应的节点属性定义这些派生以及如何构造相应 XSD 这些简单类型派生。</span><span class="sxs-lookup"><span data-stu-id="20733-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20733-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="20733-112">In This Section</span></span>  
  
-   [<span data-ttu-id="20733-113">使用限制机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="20733-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="20733-114">使用列表机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="20733-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="20733-115">使用联合机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="20733-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)