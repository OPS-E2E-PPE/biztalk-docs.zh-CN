---
title: 生效日期属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42373f55391f8bf3401d18e0a964005def222a8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389103"
---
# <a name="effective-date-properties"></a><span data-ttu-id="2ae35-102">生效日期属性</span><span class="sxs-lookup"><span data-stu-id="2ae35-102">Effective Date Properties</span></span>
<span data-ttu-id="2ae35-103">PeopleSoft Enterprise 提供的功能来计划和跟踪使用一个名为生效日期 (缩写 EFFDT) 的特殊属性的已计划的项目。</span><span class="sxs-lookup"><span data-stu-id="2ae35-103">PeopleSoft Enterprise provides the ability to schedule and keep track of planned items by using a special property called Effective Date (abbreviated EFFDT).</span></span> <span data-ttu-id="2ae35-104">此类项实施中要么只被计划，具体取决于其日期是之前或之后在 PeopleSoft 当前日期。</span><span class="sxs-lookup"><span data-stu-id="2ae35-104">Such items are either in effect or merely planned, depending on whether their date is before or after the PeopleSoft current date.</span></span>  
  
 <span data-ttu-id="2ae35-105">如果组件接口的属性包含此类有效日期项 （即，一个名为 EFFDT 的字段），该适配器，可以让调用方不检索值或仅使用这些值的完整集合尚未生效，那些仍可进行更改.</span><span class="sxs-lookup"><span data-stu-id="2ae35-105">If the properties of a component interface contain such effective-dated items (that is, a field with a name of EFFDT), the adapter makes it possible for callers to retrieve the complete set of values or only those values not yet effective—those that can still be changed.</span></span>  
  
## <a name="gethistoryitems-parameter"></a><span data-ttu-id="2ae35-106">getHistoryItems 参数</span><span class="sxs-lookup"><span data-stu-id="2ae35-106">getHistoryItems Parameter</span></span>  
 <span data-ttu-id="2ae35-107">对于包含有效日期的属性的组件接口，适配器提供了一个附加参数，调用`getHistoryItems`，为 Get 操作。</span><span class="sxs-lookup"><span data-stu-id="2ae35-107">For component interfaces with properties that include an effective date, the adapter provides an additional parameter, called `getHistoryItems`, to the Get operations.</span></span> <span data-ttu-id="2ae35-108">此参数是布尔型，如果设置为 True，则返回所有有效日期项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-108">This parameter is of type Boolean, and if it is set to True, all effective-dated items are returned.</span></span> <span data-ttu-id="2ae35-109">其中包括所有过去、 当前和将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-109">These include all past, current, and future effective-dated items.</span></span>  
  
 <span data-ttu-id="2ae35-110">如果`getHistoryItems`参数设置为 False，返回仅当前和将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-110">If the `getHistoryItems` parameter is set to False, only the current and future effective-dated items are returned.</span></span> <span data-ttu-id="2ae35-111">如果想要添加或更改这些项 （因为过去的项目不能更改），请选择 False。</span><span class="sxs-lookup"><span data-stu-id="2ae35-111">Choose False if your intention is to add or change these items (because past items cannot be changed).</span></span>  
  
 <span data-ttu-id="2ae35-112">还有可能有多个有效日期项具有相同有效日期。</span><span class="sxs-lookup"><span data-stu-id="2ae35-112">It is also possible to have multiple effective-dated items having the same effective date.</span></span> <span data-ttu-id="2ae35-113">在这种情况下，还必须提供附加属性，有效序列 (EFFSEQ)。</span><span class="sxs-lookup"><span data-stu-id="2ae35-113">In this situation, an additional property, Effective Sequence (EFFSEQ), must also be provided.</span></span> <span data-ttu-id="2ae35-114">EFFSEQ 的值必须唯一，以便区分具有相同有效日期项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-114">The values of the EFFSEQ must be unique to differentiate items with the same effective date.</span></span> <span data-ttu-id="2ae35-115">请参阅 PeopleSoft 文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ae35-115">See the PeopleSoft documentation for more information.</span></span>  
  
## <a name="modifying-past-effective-dated-items"></a><span data-ttu-id="2ae35-116">修改过去的有效日期项</span><span class="sxs-lookup"><span data-stu-id="2ae35-116">Modifying Past Effective-Dated Items</span></span>  
 <span data-ttu-id="2ae35-117">`correctionMode`参数在这种[UpdateEx](../core/updateex-method.md)并[DeleteOnly](../core/deleteonly-method.md)方法控制是否可以修改过去的有效日期的项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-117">The `correctionMode` argument in both the [UpdateEx](../core/updateex-method.md) and [DeleteOnly](../core/deleteonly-method.md) methods control whether past effective dated items can be modified.</span></span> <span data-ttu-id="2ae35-118">如果设置为 true，所有可以修改项。</span><span class="sxs-lookup"><span data-stu-id="2ae35-118">If it is set to true, all items can be modified.</span></span> <span data-ttu-id="2ae35-119">否则，修改的过去的有效日期的项将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2ae35-119">Otherwise, modifying past effective dated item generates an exception.</span></span>  
  
 <span data-ttu-id="2ae35-120">当调用不推荐使用`Update`具有有效日期项的组件接口的方法，您必须采取措施无法包含值的任何有效日期早于 PeopleSoft 当前有效日期或调用失败，出现异常。</span><span class="sxs-lookup"><span data-stu-id="2ae35-120">When calling the deprecated `Update` method on a component interface that has effective-dated items, you must take care not to include any effective dates of a value earlier than the PeopleSoft current effective date, or the call fails with an exception.</span></span> <span data-ttu-id="2ae35-121">但是，当前有效日期项可以包含如绕过设置属性时。</span><span class="sxs-lookup"><span data-stu-id="2ae35-121">However, the current effective-dated item can be included as it is bypassed when setting properties.</span></span> <span data-ttu-id="2ae35-122">如果存在有效的序列，然后设置属性时具有的所有当前有效日期项匹配的服务器中的有效序列都将跳过。</span><span class="sxs-lookup"><span data-stu-id="2ae35-122">If Effective Sequence exists, then all current effective-dated items with matching Effective Sequences in the server are skipped when setting properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae35-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae35-123">See Also</span></span>  
 [<span data-ttu-id="2ae35-124">附录 a:组件接口方法</span><span class="sxs-lookup"><span data-stu-id="2ae35-124">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)