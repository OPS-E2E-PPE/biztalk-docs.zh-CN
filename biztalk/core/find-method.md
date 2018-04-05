---
title: Find 方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="find-method"></a><span data-ttu-id="7d838-102">Find 方法</span><span class="sxs-lookup"><span data-stu-id="7d838-102">Find Method</span></span>
<span data-ttu-id="7d838-103">用于返回满足所提供部分搜索项的项列表。</span><span class="sxs-lookup"><span data-stu-id="7d838-103">Used to return a list of keys that satisfy the supplied partial search keys.</span></span> <span data-ttu-id="7d838-104">请注意，对于只有一个实例组件接口（即无项），不会生成 `Find()` 函数。</span><span class="sxs-lookup"><span data-stu-id="7d838-104">Note that for a component interface that has only one instance, that is, there is no key, the `Find()` function is not generated.</span></span> <span data-ttu-id="7d838-105">另请参阅[Get 方法](../core/get-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7d838-105">See also [Get Method](../core/get-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d838-106">语法</span><span class="sxs-lookup"><span data-stu-id="7d838-106">Syntax</span></span>  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d838-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="7d838-107">Parameters</span></span>  
  
|<span data-ttu-id="7d838-108">参数</span><span class="sxs-lookup"><span data-stu-id="7d838-108">Parameter</span></span>|<span data-ttu-id="7d838-109">Description</span><span class="sxs-lookup"><span data-stu-id="7d838-109">Description</span></span>|  
|---------------|-----------------|  
|`partialKey`|<span data-ttu-id="7d838-110">各个项可选的结构。</span><span class="sxs-lookup"><span data-stu-id="7d838-110">A structure where the individual keys are optional.</span></span>|  
|`keyList`|<span data-ttu-id="7d838-111">与 `partialKey` 匹配的项列表。</span><span class="sxs-lookup"><span data-stu-id="7d838-111">A list of keys that matches the `partialKey`.</span></span> <span data-ttu-id="7d838-112">它是一个输出参数。</span><span class="sxs-lookup"><span data-stu-id="7d838-112">It is an output parameter.</span></span><br /><br /> <span data-ttu-id="7d838-113">这些项对应于为特定组件接口定义的“查找”项集。</span><span class="sxs-lookup"><span data-stu-id="7d838-113">The keys correspond to the set of Find Keys as defined for the particular component interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d838-114">注释</span><span class="sxs-lookup"><span data-stu-id="7d838-114">Remarks</span></span>  
 <span data-ttu-id="7d838-115">指定部分项时，可以使用从 PeopleSoft 内部 `Find()` 函数中可用的相同通配符搜索。</span><span class="sxs-lookup"><span data-stu-id="7d838-115">When you specify the partial keys, it is possible to use the same wildcard search available from the PeopleSoft internal `Find()` function.</span></span> <span data-ttu-id="7d838-116">例如，"11" 的部分 ACCOUNT 项将返回以 "11" 开始的所有 ACCOUNT 项，而 "%40" 将返回项中任何位置包含 "40" 的所有 ACCOUNT 项。</span><span class="sxs-lookup"><span data-stu-id="7d838-116">For example, the partial ACCOUNT key of "11" returns all ACCOUNT keys that start with "11", whereas "%40" returns all ACCOUNT keys that contain "40" anywhere within the key.</span></span> <span data-ttu-id="7d838-117">部分项 "_4_4" 将返回第 2 个和第 4 个位置为字符 4 的所有 ACCOUNT 项。</span><span class="sxs-lookup"><span data-stu-id="7d838-117">A partial key "_4_4" returns all ACCOUNT keys with the character "4" in the 2nd and 4th positions.</span></span>  
  
 <span data-ttu-id="7d838-118">注意： 与 PeopleSoft 服务器的当前实现，如果大于 300 个项匹配搜索条件，则调用失败。</span><span class="sxs-lookup"><span data-stu-id="7d838-118">Note: With the current implementation of the PeopleSoft Server, if more than 300 items match the search criteria, the call fails.</span></span> <span data-ttu-id="7d838-119">这是 PeopleSoft 服务器的限制。</span><span class="sxs-lookup"><span data-stu-id="7d838-119">This is a restriction of the PeopleSoft server.</span></span> <span data-ttu-id="7d838-120">如果组件接口中的 PeopleSoft `Find()` 函数已启用，并且 Get 项可用，则提供用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器 `Find` 方法。</span><span class="sxs-lookup"><span data-stu-id="7d838-120">The Microsoft BizTalk Adapter for PeopleSoft Enterprise `Find()` method is provided if the PeopleSoft `Find` function in the component interface is enabled and Get keys are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d838-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d838-121">See Also</span></span>  
 [<span data-ttu-id="7d838-122">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="7d838-122">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)