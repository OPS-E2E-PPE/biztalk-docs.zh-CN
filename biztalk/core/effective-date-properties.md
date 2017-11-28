---
title: "生效日期属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="effective-date-properties"></a><span data-ttu-id="d46fe-102">生效日期属性</span><span class="sxs-lookup"><span data-stu-id="d46fe-102">Effective Date Properties</span></span>
<span data-ttu-id="d46fe-103">PeopleSoft Enterprise 通过使用名为“有效日期”（简写为 EFFDT）的特殊属性，提供了为项目制定计划和跟踪已计划项目的功能。</span><span class="sxs-lookup"><span data-stu-id="d46fe-103">PeopleSoft Enterprise provides the ability to schedule and keep track of planned items by using a special property called Effective Date (abbreviated EFFDT).</span></span> <span data-ttu-id="d46fe-104">此类项目要么正在实施中要么只是已制定了计划，具体取决于其日期是在 PeopleSoft 当前日期之前还是之后。</span><span class="sxs-lookup"><span data-stu-id="d46fe-104">Such items are either in effect or merely planned, depending on whether their date is before or after the PeopleSoft current date.</span></span>  
  
 <span data-ttu-id="d46fe-105">如果组件接口的属性包含此类有效日期项（即，名为 EFFDT 的字段），则呼叫方可以使用适配器来检索完整的值组，或只检索尚未生效的值（仍可更改的值）。</span><span class="sxs-lookup"><span data-stu-id="d46fe-105">If the properties of a component interface contain such effective-dated items (that is, a field with a name of EFFDT), the adapter makes it possible for callers to retrieve the complete set of values or only those values not yet effective—those that can still be changed.</span></span>  
  
## <a name="gethistoryitems-parameter"></a><span data-ttu-id="d46fe-106">getHistoryItems 参数</span><span class="sxs-lookup"><span data-stu-id="d46fe-106">getHistoryItems Parameter</span></span>  
 <span data-ttu-id="d46fe-107">对于其属性包含有效日期的组件接口，适配器会为 Get 操作提供一个名为 `getHistoryItems` 的附加参数。</span><span class="sxs-lookup"><span data-stu-id="d46fe-107">For component interfaces with properties that include an effective date, the adapter provides an additional parameter, called `getHistoryItems`, to the Get operations.</span></span> <span data-ttu-id="d46fe-108">此参数为布尔型，如果将其设置为 True，则会返回所有有效日期项。</span><span class="sxs-lookup"><span data-stu-id="d46fe-108">This parameter is of type Boolean, and if it is set to True, all effective-dated items are returned.</span></span> <span data-ttu-id="d46fe-109">其中包括所有过去、当前和将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="d46fe-109">These include all past, current, and future effective-dated items.</span></span>  
  
 <span data-ttu-id="d46fe-110">如果将 `getHistoryItems` 参数设置为 False，则只会返回当前和将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="d46fe-110">If the `getHistoryItems` parameter is set to False, only the current and future effective-dated items are returned.</span></span> <span data-ttu-id="d46fe-111">如果您需要添加或更改这些项目，请选择 False（因为过去的项目无法更改）。</span><span class="sxs-lookup"><span data-stu-id="d46fe-111">Choose False if your intention is to add or change these items (because past items cannot be changed).</span></span>  
  
 <span data-ttu-id="d46fe-112">也可以出现多个有效日期项具有相同有效日期的情况。</span><span class="sxs-lookup"><span data-stu-id="d46fe-112">It is also possible to have multiple effective-dated items having the same effective date.</span></span> <span data-ttu-id="d46fe-113">在这种情况下，还必须提供一个附加属性：“有效序列”(EFFSEQ)。</span><span class="sxs-lookup"><span data-stu-id="d46fe-113">In this situation, an additional property, Effective Sequence (EFFSEQ), must also be provided.</span></span> <span data-ttu-id="d46fe-114">EFFSEQ 的值必须唯一，以便区分具有相同有效日期的项目。</span><span class="sxs-lookup"><span data-stu-id="d46fe-114">The values of the EFFSEQ must be unique to differentiate items with the same effective date.</span></span> <span data-ttu-id="d46fe-115">请参阅 PeopleSoft 文档以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="d46fe-115">See the PeopleSoft documentation for more information.</span></span>  
  
## <a name="modifying-past-effective-dated-items"></a><span data-ttu-id="d46fe-116">修改过生效日期的项</span><span class="sxs-lookup"><span data-stu-id="d46fe-116">Modifying Past Effective-Dated Items</span></span>  
 <span data-ttu-id="d46fe-117">`correctionMode`中同时参数[UpdateEx](../core/updateex-method.md)和[DeleteOnly](../core/deleteonly-method.md)方法控制是否可以修改过去有效的发布日期为项。</span><span class="sxs-lookup"><span data-stu-id="d46fe-117">The `correctionMode` argument in both the [UpdateEx](../core/updateex-method.md) and [DeleteOnly](../core/deleteonly-method.md) methods control whether past effective dated items can be modified.</span></span> <span data-ttu-id="d46fe-118">如果将其设置为 True，则可以修改所有项目。</span><span class="sxs-lookup"><span data-stu-id="d46fe-118">If it is set to true, all items can be modified.</span></span> <span data-ttu-id="d46fe-119">否则，修改过去的有效日期项会生成异常。</span><span class="sxs-lookup"><span data-stu-id="d46fe-119">Otherwise, modifying past effective dated item generates an exception.</span></span>  
  
 <span data-ttu-id="d46fe-120">对具有有效日期项的组件接口调用已弃用的 `Update` 方法时，您务必要小心不要包含任何早于 PeopleSoft 当前有效日期的有效日期值，否则，调用会失败并生成异常。</span><span class="sxs-lookup"><span data-stu-id="d46fe-120">When calling the deprecated `Update` method on a component interface that has effective-dated items, you must take care not to include any effective dates of a value earlier than the PeopleSoft current effective date, or the call fails with an exception.</span></span> <span data-ttu-id="d46fe-121">但是，可以包含当前的有效日期项，因为在设置属性时会绕过该项目。</span><span class="sxs-lookup"><span data-stu-id="d46fe-121">However, the current effective-dated item can be included as it is bypassed when setting properties.</span></span> <span data-ttu-id="d46fe-122">如果存在“有效序列”，则在设置属性时会跳过服务器中带有匹配的“有效序列”的所有当前有效日期项。</span><span class="sxs-lookup"><span data-stu-id="d46fe-122">If Effective Sequence exists, then all current effective-dated items with matching Effective Sequences in the server are skipped when setting properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46fe-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d46fe-123">See Also</span></span>  
 [<span data-ttu-id="d46fe-124">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="d46fe-124">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)